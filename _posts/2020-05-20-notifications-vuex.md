---
layout: post
author: Jordan Marshall
title: The Right Way to Show Notifications w/ Vuex
tags: tech, advice, vue
---

Short Summary:

1. Keep a list of notifications (just the content) in Vuex.
2. Display notifications via a separate component that watches for notifications.
3. Watch [this great video](https://www.youtube.com/watch?v=blGp6vslw7s) for a full working example.

# The Problem

How do you show error notifications from Vuex?  As a state management library it shouldn’t have any role in the view of the application, that is, showing state to users.  However, anyone who’s built a big enough application with Vuex also knows that you need some way to get notifications from Vuex to the user.  

I recently found myself in this situation while working on a large application at work.  We have a significant number of API calls being made from the Vuex store across several [modules](https://vuex.vuejs.org/guide/modules.html).  Many of these calls require success or failure notifications to be displayed to the user.  

At first my strategy was to return the result (a promise) from actions to the component making the call, and then handle the notifications there.  This was a little tedious, but effective, and I reasoned that the components should be doing most of that work anyway. 

{% highlight javascript %}

this.$store.dispatch('createNewItem', itemName)
.then((resp) => {

    let newItemID = resp.data.Integer

    this.$store.commit('ADD_ITEM', {
        itemName: ItemName,
        itemID: newItemID,
    });

    this.$router.push({ name: "userItem", params: { itemID: newItemID } })
    this.makeSuccessToast(`Item ${itemName} was created`)
}).catch((resp) => {
    this.makeFailureToast('There was an error creating the item.')
})

{% endhighlight %}

<em>Imagine doing this for each component!</em>

This worked until I ran into a problem I should have seen coming.  Another developer on my team asked for some uniform error notifications for certain authentication errors we were seeing frequently.  These errors could occur on any API call, so my “let the component deal with it” strategy wouldn't work.  

Part of the problem was easy.  We already used a uniform [axios interceptor](https://github.com/axios/axios#interceptors) that was attached to all API requests and responses, so it was easy to actually parse the response codes in one place.  The hard part was figuring out just how to send out a notification.  These interceptors didn’t return their result to the component, and even if they did, it would be crazy to try and handle all the possible results codes in every api call.

The only option seemed to be putting some sort of notification logic into the Vuex API module itself.  Even if that were possible (it probably is - don’t do it), it definitely goes against the intended usage of the library.  Vuex should only be used to manage state, not display.

# The Solution

Our solution was to break down notifications into two pieces - state and display - and handle those two pieces separately.  Notification “state”, their occurrence and content, is handled by Vuex.  The actual display of the notifications is then handled by a separate Vue component.

## Notification State

To record notifications I created a separate Vuex module.  It kept an array of notifications and had just a few mutations to set and remove them.  Notifications in this case were just objects that could contain anything, the only purpose of the mutations was to add metadata then add them to the state.

{% highlight javascript %}

export default {
 state: {
   notifications: []
 },
 mutations: {
   ADD_NOTIFICATION(state, notification){
     state.notifications.push({
       ...notification,
       id: Date.now().toString()
     })
   },
   REMOVE_NOTIFICATION(state, notificationID){
     state.notifications = state.notifications.filter((obj) => {
       return obj.id != notificationID
     })
   }
 },
 actions: {
   notifyError({commit}, notificationText){
     commit('ADD_NOTIFICATION', {
       text: notificationText,
       type: 'error',
     });
   },
   // Not shown: notifySuccess()
 },
 ...
}

{% endhighlight %}

## Notification Display

The display of notifications was handled by a separate Vue component.  There was only one instance of this component and it lived in the base App view, next to the router-view component.  It watched the array of notifications and displayed them (via toast) anytime a new one was created.  It also removed them from the array as soon as they were created, as the toast library had a builtin expiration timer.

{% highlight javascript %}

export default {
 mixins: [Toasts],
 computed: {
   ...mapGetters(['activeNotifications']),
 },
 methods: {
   showNotification(notification){
     if(notification.type == 'success') this.makeSuccessToastSimple(notification.text)
     else this.makeFailureToastSimple(notification.text)
 
     this.REMOVE_NOTIFICATION(notification.id)
   },
   ...mapMutations(['REMOVE_NOTIFICATION']),
 },
 watch: {
   activeNotifications(newValue){
     newValue.forEach((obj) => {
       this.showNotification(obj);
     })
   }
 }
}

{% endhighlight %}

Other solutions I looked at solved this slightly differently.  Instead of using toasts they created a separate notification component and looped through the contents of the array.  Each notification component set a timer and deleted itself both from the view and state after it expired.  You can see the whole demonstration in [this great video](https://www.youtube.com/watch?v=blGp6vslw7s).

# To Summarize

1.  Create a “notifications” array in your Vuex store to record messages you want to show to the user.  
2.  Add to this array from anywhere in the code, include the store itself or other components.
3.  Create a separate component to display notifications.  This component should read from the notifications array in the store and show them to the user, removing them when completed.

# Other Tips

1. Have exactly one place in the code where you display notifications.  In my current project this was a mixin, but it could also be another component.  This makes it easy to change things like the colors, or how long they should be displayed for.  You do not want 100 different components each creating their own version of a notification.    
2. Use interceptors (or some version thereof) with your API library.  This lets you define a response for common errors in one place, something that is critical for a large app.
 
It’s funny how impractical this approach seemed at first, but now I realize how nicely it illustrates the divide between state and view handling.  As someone who is still trying to master Vuex and reactivity this was definitely not the intuitive solution.  

In the past I would have been tempted to cheat, and find some way to force a call to the notification library into the state management (telling myself “just this one time”).  Luckily Vuex makes that hard by design, and I ended up with a better architecture for it.

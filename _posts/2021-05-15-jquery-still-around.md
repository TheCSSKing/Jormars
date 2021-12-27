---
layout: post
author: Jordan Marshall
title: Reports of jQuery's Death Have Been Greatly Exaggerated
tags: javascript design
---

I read [Hacker News](https://news.ycombinator.com/) regularly, and one of my favorite recent posts was an [announcement for the latest version of jQuery](https://news.ycombinator.com/item?id=26318872).  What made it so interesting was the sheer number of commenters who came forward to voice their strong support for the venerable language.  I’m not sure I’ve seen the word “love” so often in a Hacker News discussion for any other library or piece of technology.    

I walked into the discussion expecting to find people waxing nostalgic for simpler times when a single Javascript library was all you needed to run a dynamic web application.  Sure, they are still releasing new versions, but nobody is actually using them, right?

Sure enough, the top comment mirrored my expectations: “Do people still use jQuery?” it started, followed by a brief overview of all the new additions to Javascript as well as frameworks that have made jQuery “obsolete”.  I read on, expecting to find a few stalwart apologists bracing themselves against a tide of support for newer frameworks.  I was wrong.

What I found instead was an absolute flood of responses from people who still actively use jQuery on new projects, old projects, personal projects, and even in their washing machine (okay not really, but that would be great to try).  Here is a sample of some of the numerous replies:

* “Still use it. Still love it.” 
* “It is literally the first thing I add to every personal project I build” 
* “All the time.”
* “Every day I do.”  

This goes on for most of the thread.  In fact, one astute individual even [cited a study](https://almanac.httparchive.org/en/2019/javascript#open-source-libraries-and-frameworks) showing that jQuery was in use in roughly 85% of all webpages.  Part of this is because it’s bundled in a lot of major frameworks (Bootstrap, Wordpress), but it is still a stunning figure.

In retrospect, this should not have been that surprising.  Even though my team has moved on, to the “latest and greatest”, it doesn’t mean everyone else has.  In fact, we still run jQuery on our production website!  

# A Lesson in Design

One of the reasons I was so surprised was because many of the key features from jQuery have been merged into the Javascript language itself.  Most notable being the more advanced element selectors in the form of document.querySelector and document.querySelectorAll.  Why then would you use jQuery if you could get the same functionality with the base language?  It turns out there are a number of good reasons.

One of the primary ones I saw cited throughout the thread was expressiveness.  The jQuery syntax of using $(‘.class-name’) is much more readable and easy to parse than the equivalent document.querySelector(‘.class-name’).  

Along the same lines, the jQuery syntax is also much shorter and easier to work with.  My experience when forcing myself to learn the new Javascript selectors was that they were long and not intuitive, I much preferred working with jQuery (although not enough to add a new library to the project).  Many people echoed this same thought, also noting that the library has gotten small enough that it’s easy to justify using just for the selector interface.

Many people (including myself) also miss the composability of jQuery.  Being able to easily iterate over results from a selector, or chain operations together, was really nice.  You can do similar things in vanilla Javascript, but it requires some customization.  With jQuery it just works.

There are many reasons that Javascript is the way it is, and the takeaway from this shouldn’t be that one approach is preferable or “better” than the other.  Rather, we should look at what this example can teach us about good design.  

* Elegance and simplicity are important, even when designing something as mechanical and impersonal as a programming language.
* Design is more than checking off a list of features.  To build something that users really love you need to find efficient ways for pieces to work together.    
* Good design takes time.  jQuery has been around for more than a decade, and it didn’t start as a beloved library.  The long cycle of improvements over time is a slow moving freight train that eventually yields great results.

These guidelines are a bit less pragmatic than I usually prefer, but I think they can be applied in a general sense.  When designing a user interface, even if you’ve built all the features, it is still worthwhile to ask yourself if the design is really as efficient and elegant as it could be.  Can you find ways to make it easier and more intuitive to use? Are there features not on “the list” that could streamline things more?  Have you reached out to users for feedback?  Most importantly, don’t be discouraged if your first draft doesn’t blow people away, it takes time to build something great.      

# Choosing the Right Tools

Another important lesson that can be gleaned from this discussion is about the choice of tools for a project.  It is always worth considering all of the options, comparing the tradeoffs, and making a calculated decision.  A library or tool that is older shouldn’t automatically be excluded, especially if it is well established.  

This calculation is complex and should consider many factors, including your own familiarity with tools, availability of support, and features needed for the project.  Established tools have their drawbacks, such as a shorter support horizon or lack of support for newer features.  Newer libraries (think React/Vue/Angular) have other drawbacks, like less completeness or a more rapidly changing feature set.   

It is important to consider both the technical, psychological, and social aspects of tooling choice.  Maybe you are more comfortable with one language, or maybe you just really want to learn the newer framework.  Those are both legitimate reasons to use a tool or library, and should be weighed against the overall needs of the project.  

One of the large projects I’m working on now at work is built with the full Vue ecosystem - Vue Router, Vuex, Vue CLI, and Bootstrap Vue.  Could we have built it in jQuery?  Maybe.  It’s a longer discussion, but technically I’m sure it would have been possible (although not ideal).  Psychologically though it would have been a lot harder.  Myself and the other developers have enjoyed learning new tools and being part of the community surrounding those.  By the time we got on board (Vue 2), it was stable enough that it made sense for a larger project.

All this goes to say that things like developer preference, wanting to keep up with new trends, and technical needs should all be considered in the decision.  More established frameworks like jQuery should not be dismissed out of hand, nor should they be the automatic choice if they are “enough” to get the job done.   

# Remind Me In 10 Years

I’m writing this in 2021, how will the landscape have changed in another 10 years?  Will jQuery still see much use?  Can it survive for another decade?  Or is it possible that in 2031 I will be waxing nostalgic for the “simpler” times when all you needed for reactivity was a single library and it’s command line tool?

The tools we use in the next decade might be a surprise, but there is one thing we can count on to stay the same: Hacker News.  It will still have fascinating discussions on obscure topics unrelated to technology, tech legends and CEOs will still post in the comments, and of course, it will still be orange. 

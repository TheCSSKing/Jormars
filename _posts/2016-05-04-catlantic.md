---
layout: post
author: Jordan Marshall
title: The Catlantic, or How Not to Build an App
tags: bootstraping funny
---
<em>This article is about "The Catlantic", a website I built in spring 2014.  You wont find it in my project portfolio, for reasons that should become clear.</em>

# The Story

A few months ago was looking for a new project and decided to implement an idea I had for a "100% user submitted news website".  The idea was that users would write news stories about boring events from their own life. People could then vote on their favorite stories and the front page would have interesting/funny news type stories.  It was meant to be a fun project with a creative side, instead of a business.  I called it "The Catlantic" to juxtapose the mundane elements of daily life (cats) with a more erudite publication - The Atlantic.

From a technical standpoint there is nothing new about the idea.  It was basically a crowd sourced blog that allows users to vote on their favorites.  I looked briefly for some way to implement this "out of the box", but quickly decided to build it from scratch.  My plan was to build it, work as user #1 to build up some content, then use the existing content to gain attention and attract other users.  I also considered hiring freelancers to write content early on.

I spent several weeks building it from scratch using python and the Ferris Framework.  In the end I succeeded in building something that had most of the core functionality I was looking for: user accounts, user articles, voting, and more.  Unfortunately, despite using a template, it looked pretty mediocre.  I also quickly realized that there was a lot of non-core functionality that needed to be implemented.  Oh, and testing.  And at this point I had no users.  Faced with the prospect of working several more weeks for nobody, I decided to "take a break" for awhile.

<!-- [caption id="attachment_73" align="alignnone" width="672"]<a href="http://www.jormars.com/wp-content/uploads/2014/09/CatlanticScreen.png"><img class="wp-image-73 size-large" src="http://www.jormars.com/wp-content/uploads/2014/09/CatlanticScreen-1024x655.png" alt="CatlanticScreen" width="672" height="429" /></a> A screenshot of The Catlantic.[/caption] -->

# What Went Wrong

There was no catastrophic failure here.  In fact, all of the problems here have nothing to do with software design or development skill.  They are all rooted in how I approached the project.

The problem was that I was working in a vacuum.  I had not talked to anyone or done any sort of user research.  That meant, roughly, that I was going to build the whole thing first, then see if anyone wanted to use it.  This is such a bad idea.  It very hard to keep going when you are not even sure you like the product.

The "build it first" approach could have worked if I had found a way to quickly build a prototype (or even planned on building a prototype).  Having spent a little more time looking around I realize now there are several different platforms/libraries that would have helped me do this quickly.  I should have spent the whole first week doing research, instead of a few hours.

The final problem was that I did not give myself a realistic time frame. I severely underestimated how long it would take to build the thing, and as a result was very frustrated when it took longer than expected.  I think that if I had been more realistic with my estimate from the beginning (months instead of weeks) I might have spent more time trying to find existing technology, or even finding users.

# Lessons Learned

These are the big takeaways from the project.

1.  You should never work in a vacuum, at least not for long.  You need interest from other people in the form of funding, commitments, or signups before you start building.
2.  Customer validation and/or user acquisition should come before building the project itself.  There are many ways go gain traction on a project without having a finished product.  The worst case scenario is that you have to build the prototype first.
3.  Plan on building a prototype (your MVP).  It should not be the final version.
4.  Do your research.  Find a way to use existing technology to build the prototype.
5.  Be realistic about time estimates.  It is worth it to spend an hour or two early on going over the details to get it right.  Whatever your estimate is at the outset, double it.  

# An Addendum

I still like the idea a lot.  In the last few months I have found several options for building something like this "out of the box", and I hope one day to return to it.

For a closing remark, here is one of the articles I wrote for The Catlantic:

> ## Potluck Requirements Send Household Into a Panic
> At approximately 8:03 AM local girlfriend Annie sent the household into a panic following the revelation that she did not have anything to bring to her potluck at work. She informed her boyfriend, Jordan, who was stretching in front of the TV, that she needed to bring a "breakfast item" in for a potluck, and could not think of anything. 
>
>Jordan offered numerous unhelpful suggestions, including "pasta", "a few of my bagels", and "cereal". He then got up and browsed through shelves in the kitchen, but sources say he was only looking for a piece of candy, and not trying to resolve the crisis.
>
>The crisis lasted for exactly three minutes. At 8:06 AM Annie admitted defeat and resolved to stop by the grocery store on her way to work.

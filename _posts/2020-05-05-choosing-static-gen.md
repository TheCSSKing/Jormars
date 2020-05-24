---
layout: post
author: Jordan Marshall
title: Choosing a Static Site Generator
tags: projects, meta
---

When it came time to rebuild my personal site I knew I wanted to run it on a static site generator.  There are innumerable benefits to this approach, including low maintenance overhead, lots of room for customization, less security concerns, and mostly free hosting.  A lot more can be said on the benefits, but ultimately it seemed like the best approach for a website that I wanted to last for [at least ten years]({% post_url 2020-05-01-building-to-last %}).  

The only thing I had to do was pick out which one I wanted to use.  This proved more challenging than I thought.

# First Attempt: Hugo

One of the first things I did was go over to [staticgen](https://www.staticgen.com/) to see what some of the most popular generators were.  I had used Jekyll and Hexo in the past, but I wanted to see if there was something more modern that would take me to 2030.  [Enter Hugo](https://gohugo.io/).  Besides the two React based libraries (I’m more familiar w/ the Vue ecosystem), Hugo seemed to be the clear winner in terms of popularity.  I decided to give it a try.

The first thing I did was try the quickstart, after all, who wants to do the slow start?  I got the library installed fairly quickly, downloaded the sample template, and had a local instance running in short order.  

This was very promising, and from my experience w/ other generators, I assumed I was close to being productive in the environment.  I grabbed a minimalist template I could use as a base, and went to work re-building my site.  Or tried to at least.

What followed was several hours of running around in circles, trying to figure out what the heck was going on.  I started by trying to get Hugo to compile my own custom Sass file, which the docs had clear instructions for.  This took nearly an hour, as I had to create a custom ‘assets’ directory in two places, one for the theme, and one for my local.  What I didn’t realize then, and that made this more complicated, was that editing the theme itself probably wasn’t a good idea.  

After an hour of frustrating debugging, I decided maybe it was time to take a step back and read through the docs more carefully (the “slow start”).  First I tried the direct way, reading them sequentially.  This approach quickly got shelved, as there was just too much information.  You shouldn’t need to read all the docs to get to basic proficiency, especially for a simple use case like mine.

Next I looked for a medium weight tutorial, something between “quick start” and “read all of the documentation”.  This was surprisingly hard to find.  Most of the tutorials (and the only one on the main site) were the equivalent of downloading a theme and getting it running.  The one or two more detailed tutorials I found were more strongly weighted towards “read all of the documentation”, which was not what I wanted.

In the process of hunting for tutorials, I stumbled across [this comment](https://discourse.gohugo.io/t/comprehensive-hugo-tutorial-for-beginners/12586) from a contributor on the discourse board: 

> “Development in Hugo happens fairly rapidly … I think that is the main reason there isn’t a book or anything. It would be outdated in a few weeks.” 

Wow. That certainly opened my eyes. Remember, I’m trying to build something that will last for years.  I don’t want to use a library that will require me to make updates every couple of months, or even every year.

# A Bumpy Road

After reading that, I did more research and found that I was not alone in my frustration.  There were a number of people who had issues getting Hugo setup, and many who advised steering clear entirely.  Many feature comparisons noted that while it was extremely fast, ease of use was not great, especially if you’re not familiar with golang (which I am not).  Reading more opinions, and then trying to parse more of the docs, made me decide to throw in the towel.  

What went wrong?  First, my use case was not the most common one.  I wanted to build my own template, mostly from scratch, instead of just plugging in an existing theme.  If I had not wanted to do much customization the task would have been much easier.  

The other big factor was documentation. There could be a better intermediate tutorial for folks who want to do more than run a template (the [Jekyll tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) is great).  Maybe it exists, but I didn’t find it, and it's not in the official docs.  Starting down the wrong path was incredibly frustrating, and I can only think that if I had been pointed in the right direction earlier, maybe I would still be using it now. 

# Choosing Jekyll

In the end I went with Jekyll.  It has been around since 2008, has wide support, and most importantly, isn’t changing a lot.  When I dove in again I recognized most of the features from the last time I used it, years ago.  Even the documentation seemed mostly unchanged, with an easy to find mid-level tutorial that walked you through many of the core features.  

Even though it is not the most fully featured or most popular static site generator (this is splitting hairs - it is very popular), Jekyll fit my needs perfectly.  In ten years maybe my needs will change, but for now I am hopeful this will last.

A good lesson to remember here is that stars, likes, and mentions are not everything.  Especially in the world of static site generators, when there are so many good options, reading comparisons and reviews is a great idea.  As always, a little bit of research beforehand can save hours of development time.  

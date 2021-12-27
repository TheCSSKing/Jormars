---
layout: post
author: Jordan Marshall
title: Lessons Learned from "The Managers Path"
tags: management advice
---

I recently finished “The Manager’s Path” by Camille Fournier.  [I wrote a review]({% post_url 2021-03-28-the-managers-path %}) in my previous post, but here I would like to go over some of my favorite material in more detail.  In particular, I’m going to look at the management advice that surprised me or stood out in other ways.  

# Delegate, But Don’t Abdicate

Delegation can be a tricky business.  If you’re already very familiar with the task and have worked on it previously, it can be hard not to micromanage the team member you’ve passed it on too.  On the opposite end of the spectrum, it can be easy to hand off a task to someone and let them work unsupervised, whether in an effort to avoid micromanagement, or just because you think they can handle it.

Both approaches can lead to problems.  Micromanagement saps motivation, while letting someone work independently (abdicating) can mean they follow the wrong path, or make decisions you don’t agree with.  

The best approach is somewhere between the two: carefully setting goals, checking in often, but also not trying to control every detail.  Let your team member make decisions, but make sure you have guard rails in place to avoid traveling off the desired path.

# Autonomy is Motivation 

I’ve always known micromanagement is “bad”, but had a hard time explaining exactly why.  When I read the section on delegation, it clicked.  Autonomy and the ability to actually make decisions, no matter how small, are an important motivator.  Take that autonomy away by micromanaging, and you end up with team members who are not going to work as hard or think creatively.

This moral was easy to realize as I looked back at the many projects I’ve worked on over my career, both large and small.  The projects I worked hardest on, was most proud of, and went the extra mile for, were all ones where I had autonomy and freedom.  When I felt ownership it motivated me to work harder, and the results were better.

This is an especially important lesson for new managers and leads.  You are typically closer to the code and have strong opinions on how things should be done.  Additionally, team members who aren’t as familiar with the subject matter might need coaching, which can easily slide into micromanagement.  You should try and give even the most junior team members some degree of autonomy, it will help them learn and stay motivated.

# Don’t Be Lazy

Instead of automatically asking a report when you have a question, see if you can find the answer from systems yourself before reaching out.  Go to the database, code, or documentation.  Unless you're a VP with a dozen reports, you should have enough time to run a simple query or quickly check a file in the repository.

As a manager in the age of Slack it is easy to ping a team member when you have a simple question.  It’s easy to justify because you’re “very busy” and because there are harder questions you do need to delegate, so it’s not a giant leap to ask every question instead of being selective.  I found myself doing exactly this when I had even the smallest question, and I didn’t even realize I was doing it until I read the section in the book.

Not only do these simple questions interrupt the people you ask, but it takes you just a little bit farther from the systems you manage.  It’s a bad sign if you’re no longer comfortable scanning the code base or reading the docs.  The more of a habit it becomes, the farther away you can get. 

# Stay Technical

This was the most surprising advice from the book because I had heard the exact opposite from a number of sources.  I thought that once you were managing people you were doing the team a disservice by trying to do any engineering work at all.  I realize now this wasn’t “wrong” advice, just less nuanced.

The real answer to “should managers code” is not binary, and depends on a number of factors, including what your role is, how many reports you have, and what systems you are working on.  There are many leadership roles where you have to remain technical, both to remain credible to your team and to make key decisions.  You will have a much harder time making decisions about the project or discussing challenges if you don’t understand the code and tools your team is using.

The big mistake, especially for new managers, is to spend too much time doing engineering work, thereby neglecting management duties.  There are plenty of ways to stay current without blocking team members or spending too much time.  In “The Managers Path”, Camille Fournier recommends a number of strategies, like fixing smaller issues when you can, and having team members mentor you in certain areas of the code.

The reality is that almost no job in a software company will come with detailed instructions about how much technical work you should be doing.  You will need to decide this yourself based on how familiar you already are with the projects and how much time other duties take.  The important thing is to stay technical to some degree as long as possible, without letting it get in the way of other duties.

# Be Able to Build and Deploy

This isn’t from the book, but I extrapolated from “staying technical” advice and my own experience.  Until you get to the point where you are managing multiple teams, you want to be familiar with the projects you are running.  One of the best ways to do this is to make sure you can run, build, and deploy the project.  This doesn’t mean you are the person responsible for deployments, just that you are capable of doing it.

The key benefit is that it helps you understand the tools and processes your team is using.  This is especially important if build and/or deployment has been a pain point.  Being familiar with the system enables you to help guide the team to a better approach.  Other benefits include being able to do the deployment if needed, and being able to easily check the progress of PRs.

This may seem like obvious advice, but I’ve worked with technical managers who couldn’t run the project they were in charge of.  Obviously this doesn’t apply to every manager, especially those with multiple teams or multiple projects.  However, if you are running a small team and regularly making architectural decisions, you should make sure you can at least run, build, and deploy.  

# A Strategy For Saying No

I wanted to share this because I thought it was a cute little trick.  In the section “Strategies for Saying No” we learned the “Yes, And” technique.  It is a rhetorical technique whereby you first answer “yes” to a question, but then go on to list the caveats that qualify your “yes” answer.  For example, “Yes, we can deliver the SEO changes in the next release, and all we will need to do is shift the data dashboard changes to next month.”  

The benefit is that it forces you to (1) give your response a positive tone and (2) explain in more detail why the objective is hard to reach.  In practice I doubt this is that useful, as most competent managers should listen to your explanation even if you start with “Hell no!”.  I think it is more valuable as a framework for any answer (or estimate), a reminder to be positive and clearly explain reasoning. 

# Bonus Round

A few more quick tips that I found helpful. 

* **Performance reviews**.  Keep critiques focused on a few key areas.  Avoid surprises - if there are major issues the person should already be aware.  If you have no areas of improvement, maybe it's time for a promotion.
* **Fallacy of the open door policy**.  Most reports won’t feel comfortable showing up to a senior managers office without an invite, especially if they want to raise an issue.  Hold skip level one on ones instead.
* **Release frequency is an indicator of team health**. Even development teams working on research or early stage projects should be able to show some kind of deliverable at a regular interval.     
* **Hold regular one on ones**.  Even if you are in frequent contact with somebody, it is still useful to have set aside time in which they can ask questions, raise concerns, or just vent. 

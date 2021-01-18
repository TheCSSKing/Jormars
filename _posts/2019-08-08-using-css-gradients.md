---
title: How to Use CSS Gradients
layout: post
author: Jordan Marshall
tags: gradients css
excerpt_separator: <!--more-->
---

A short overview of how to use CSS gradients on your website.  Gradients are a great option for neat background patterns without the overhead or size of images.

<!--more-->

## TLDR Summary

Copy the CSS, add it to the `background` or `background-image` tag of the element you want to have the gradient.

## Short Version

* Find a gradient you like, either on [Gradient Magic](https://www.gradientmagic.com/) or one of the [many](https://uigradients.com/) [other](https://webgradients.com/) [galleries](https://leaverou.github.io/css3patterns/) out there.
* Copy the CSS.
* Add the copied CSS to the `background` or `background-image` tag.  You can do this in the browser (for a quick preview) or in your CSS editor.
* Viola!  That's all you need to do.  A world of color is at your fingertips.

## Slightly Longer Version

Gradients are really easy to use, so the longer version is very similar to the short version - only with more detail.

* You’ve found a gradient you want to use?  Great! Copy the CSS.
* You can add the gradient to the `background` or `background-image` property, as shown below:
``` CSS
background-image: linear-gradient(90deg, rgb(235, 216, 9),rgb(202, 60, 134));
```
* The background property is a CSS shorthand property - which means it can be used to set multiple CSS properties at once.  For gradients it sets background-image, since the browser renders gradients as an image.
* Did you know you can easily modify the gradient?  By using the developer tools in your browser you can edit gradients on the fly.  Right click on the element and select "inspect" - it should open web developer tools.  
* For simple gradients it is easy to use dev tools to modify colors and tweak the angle to get what you like.

## Reference

Other helpful articles:

* [MDN Docs on Using CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Using_CSS_gradients)
* [MDN Docs on Linear Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* [Good CSS Tricks Overview of CSS Gradients](https://css-tricks.com/css3-gradients/)

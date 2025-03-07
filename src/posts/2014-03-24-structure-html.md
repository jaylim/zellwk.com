---
title: How to structure HTML for an actual website (Part 2)
layout: post
slug: html-structure-2
tags:
  - html
newsletter: better-fed
---

This is a continuation of the series on learning to write HTML for an actual website for the first time. We have looked at how to write html structure for the big picture with wrappers in the previous section, and we will be diving into the smaller details in this section.

<!--more-->

[The first part can be found here][1]

## The Micro Details

Micro Details refer to the smaller pieces on the web and how they are placed. One example of such a smaller piece is the navigation while another is an article.

As you may have imagined, navigations and articles are wildly different, and they require very different markups. You'll also realize that this applies to every other group of elements as well!

The question is: **How should you write markup for whatever you're trying to create?**

## The Answer

There are really no hard and fast rules to this question. You can use HTML to markup things in anyway you like, as long as they seem reasonable.

However, precisely because you can write anything you want in HTML, there has been an ongoing battle of [semantics][2](The meaning of things used in HTML).

Lets take the navigation as an example and walk through the steps

![picture of a navigation area][image-1]

The first step to finding out what kind of markup and how many levels are required. You should be familiar with this because this is exactly what you have done the last week.

![Navigation breakdown][image-2]

It's quite easy to see that a minimum of two levels are required for this to happen.

The simplest way that you could write HTML for this nav is:

    <div class="nav">
      <div>Blog</div>
      <div>Work</div>
      <div>About</div>
      <div>Contact</div>
    </div>

You then noticed that each item is supposed to be a link. In this case, you can either replace each `<div>` with an `<a>` tag, or simply nest the `<a>` tag within the `<div>`.

Here are the two ways in code form.

    <!-- option 1 -->
    <div class="nav">
      <a href="#">Blog</a>
      <a href="#">Work</a>
      <a href="#">About</a>
      <a href="#">Contact</a>
    </div>

    <!-- option 2 -->
    <div class="nav">
      <div><a href="#">Blog</a></div>
      <div><a href="#">Work</a></div>
      <div><a href="#">About</a></div>
      <div><a href="#">Contact</a></div>
    </div>

Both ways work, and there is no right or wrong answer.

If you go with semantics, option 2 is preferred because `<a>` tags are usually meant for inline elements, and `<div>` are for layouts.

If you dive deeper into semantics, `<div>` are not preferred because `<div>` doesn't have a meaning to itself. You need to find something that explains this navigation even more.

Look at it from another way, a navigation is actually just a list of links. So if you care about semantics, a list works much better.

    <ul class="nav">
      <li><a href="#">Blog</a></li>
      <li><a href="#">Work</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>

Now the HTML markup has some sort of meaning when you look at it, and its easy to discern this part from others.

To make it even better, HTML 5 has provided a `<nav>` element for navigations. The markup can be improved to

    <nav>
      <ul>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Work</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>

When you read the HTML now, it is incredibly clear what this portion is saying, compared to what you have above. It is clearly say thing that this is a navigation area. Within the navigation area, there is a list of 4 items, and each item consist of a link to some other area.

## Does Semantic Matter?

Yes and no.

If you are comfortable writing your own HTML. I would suggest to be as semantic as possible, because it helps alot when you're trying to debug your own code.

However, if you're just starting out, don't worry too much about semantics. Almost everything can be replaced with a `<div>`, and HTML was like that in the past.

A `<nav>` works and functions exactly the same as a `<div>`. If you're confused about HTML, there's no point trying to dig a deep hole into semantics yet. Work on understanding layouts and making them appear the way you want it with CSS first.

When you feel that you're comfortable learning more, view other people's source codes and try renaming some of your HTML stuff into more semantic blocks.

[1]: /blog/html-structure/ 'HTML Structure for an actual website'
[2]: http://html5doctor.com/lets-talk-about-semantics/
[image-1]: /images/2014/03/11.png 'picture of a navigation area'
[image-2]: /images/2014/03/21.png 'Navigation breakdown'

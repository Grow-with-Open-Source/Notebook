---
title: Introduction to Deep Learning
date: 2025-03-06 20:04:00 +0530
categories: [Machine Learning, Deep Learning]
tags: [introduction, artificial-intelligence, machine-learning, deep-learning, python, pytorch]
author: shamith_watchdogs
media_subpath: "/assets/img/intro-to-deep-learning"
image:
  path: "deep-learning.[png | jpg | jpeg]"
  alt: "Deep Learning"
---

Deep learning is currently one of the most booming technologies, playing a major role in the _"OpenAI's ChatGPT era"_. Although it is built upon the transformer architecture—proposed by Google developers in 2017—the roots of this architecture go back to the very fundamentals that have shaped deep learning into what it is today. In this blog, we're going to explore a few key concepts behind this revolutionary technology...

## Motivation

The main motivation of this blog is help both developers and people in general who are looking to learn a few things about Machine Learning and specifically Deep Learning. I want to demystify some of the common misconceptions that people take for granted without filtering out the facts from the overly hyped ___"AI"___ product within the current marketplace. Talking specifically about developers, this blogs helps them kick-start their journey into field deep learning and helps them understand a thing or two when they hear more advancements or attend an event.

When I was planning to write a blog on deep learning, I have no prior exposure to this domain. I do have some idea where to begin, but I got lost in numerous resources but most of them are not so clear on the prerequisites to understand their material. During that time, I got into one of scholarship for a GenAI course on Udacity platform offered by Bertelsmann. Taking this course helped me understand the core fundamental of deep learning within the first module. I spent quite some time understanding the core components of a simple deep learning model called "Multilayer Perceptron". I really thank Bertelsmann for sponsoring the GenAI Nano Degree program on Udacity platform, this course motivated me to share my learning thus supporting my initial cause to work on this blog. 

{% include embed/twitter.html id="1894221279336480880" %}

Don't worry, this course is not the only resource from which I transpile the knowledge to you. I have my done my research and iterated over many parts of blog just to get thing right and more beginner-friendly.

## In this blog

In this section, we'll talk about the things you can expect from this blog and prerequisites and stuff... And before we proceed, I want to let you know that Deep Learning is vast domain and there are lots 'n lots of concepts within deep learning and can't be covered within this blog. Even though the scope of this blog ends with <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>, I want to you understand the very fundamentals that made Deep Learning what it is today.

### Overview

With that being said, let take a look at things which we're going to cover in the blog.

- We'll start from the very beginning and fundamental question ___"What is Deep Learning ?"___
- Then, we'll take a peek into the overall architecture of a very simple & very basic deep learning model called "Multilayer Perceptron" _(also known as <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>)_
- After that, we'll pick the **core algorithm** from which <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> and many other deep learning architecture is built upon
  - Within this topic, we start from absolute beginning and see who _"this algorithm"_ was originated
  - Then we'll look how it evolved to the ones we use today across various deep model architecture.
  - We end this topic by looking at its limitation which was one of the reason that caused first AI winter.
- Then we take a closer look at <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> and why its overcame the limitation of this core _"algorithm"_ we talked above.
- Understanding how <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> are built doesn't get you far if you're not sure what how your model evaluates given data and that's what we're gonna learn here.
- Now it's time to see how your deep learning model calculates its mistake to learn from them.
- Then we talk a few things about functions that help your deep learning model rectify its mistakes.
- If you made it this far within the blog, then you understand the core components that make a deep learning model. But it's not complete if you don't know how it learns from data.
- Now that we understand how deep learning models work at conceptual level, let's wrap up everything by building an <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> using `pytorch` module.

I know it's a lot to take it, but don't you worry about a thing. I'm going to guide you step-by-step not only understand on a conceptual level but also building a model for yourself. I don't expect you to learn the whole thing within a single session and I don't want you to do that. Just take your time, come back when you feel like resuming your journey into deep learning with me.

> Please don't be dismayed by such large number of concepts, all the concepts discussed within this blog are very **beginner-friendly**. I have made sure to keep concept in such a way **even a toddler could understand** _(within some prior knowledge of basic math and python as mentioned within [Prerequisites](#prerequisites "goto Prerequisites section"))_. Please take your time and build your foundation on clear understanding of these concepts.
{: .prompt-info}
---
title: Introduction to Deep Learning
date: 2025-03-06 20:04:00 +0530
categories: [Machine Learning, Deep Learning]
tags: [introduction, artificial-intelligence, machine-learning, deep-learning, python, pytorch]
author: shamith_watchdogs
media_subpath: "/assets/img/intro-to-deep-learning"
image:
  path: "deep-learning.webp"
  alt: "Deep Learning"
---

Deep learning is currently one of the most booming technologies, playing a major role in the _"OpenAI's ChatGPT era"_. Although it is built upon the transformer architecture—proposed by Google developers in 2017—the roots of this architecture go back to the very fundamentals that have shaped deep learning into what it is today. In this blog, we're going to explore a few key concepts behind this revolutionary technology...

## Motivation

The main motivation of this blog is help both developers and people in general who are looking to learn a few things about Machine Learning and specifically about Deep Learning. I want to demystify some of the common misconceptions that people take for granted without filtering out the facts from the overly hyped ___"AI"___ marketplace. Talking specifically about developers, this blogs helps them kick-start their journey into field of Deep Learning and helps them understand a thing or two when they hear about more advancements made within this domain or when you attend a relevant event/keynote.

When I was planning to write a blog on deep learning, I have no prior exposure to this domain. I have an idea of where to begin, but I got overwhelmed by the numerous resources, many of which are unclear about the prerequisites needed to understand their material. And during that time, I got into one of scholarship for a GenAI course on Udacity platform offered by Bertelsmann. Taking this course helped me understand the core fundamental of deep learning within the first module. I spent quite some time understanding the core components of a simple deep learning model called "Multi-Layer Perceptron". I really thank Bertelsmann for sponsoring the GenAI Nano Degree program on Udacity platform, this course motivated me to share my learning thus supporting my initial cause for writing this blog. 

{% include embed/twitter.html id="1894221279336480880" %}

Don't worry, that course 👆 is not the only resource from which I explain the concept to you. Please be assured as I have my done my research and iterated over many materials to get things just the right amount for you to learn enough about deep learning. I spent countless hours in refining my learning and evaluating various reference material to make this blog as accurate and beginner-friendly as possible. I would really appreciate it if you show your support on my social network like <a href="https://www.linkedin.com/in/shamith-nakka/" title="goto my linkedin profile" target="_blank">LinkedIn</a> and <a href="https://x.com/shamith_nakka" title="goto my twitter/x profile" target="_blank">Twitter/X</a>, motivating me to bring more quality content to you.

## In this blog

In this section, we'll talk about the things you can expect from this blog and prerequisites and stuff... And before we proceed, I want to let you know that Deep Learning is vast domain and there are lots 'n lots of concepts within deep learning and can't be covered within this blog. Even though the scope of this blog ends with <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>, I want to you understand the very fundamentals that made Deep Learning what it is today.

The agenda of this blog goes as follows: 
- First we're going to start with conceptual topics with some mathematics.
- We'll end this blog with by building a simple <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> model by creating a custom dataset. 

As much I want to implement each algorithm for each component within the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> architecture using python & its libraries, I decided to keep things simple and keep the explanation of various topics on a conceptual level while maintain a good level of abstraction and separate the implementation while using modern practices to build/design the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> architecture using PyTorch library when we reach the end of this blog.

### Overview

With that being said, let take a closer look at the things which we're going to cover in the blog.

- We'll start from the very beginning and the fundamental question ___"What is Deep Learning ?"___
- Then, we'll take a peek into the overall architecture of a very simple & very basic deep learning model called "Multilayer Perceptron" _(also known as <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>)_
- After that, we'll pick the **core algorithm** from which <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> and many other deep learning architecture is built upon
  - Within this topic, we start from absolute beginning and see how _"this algorithm"_ was originated.
  - Then we'll look how it evolved into the ones we use today, across various deep model architecture.
  - We end this sub-topic by looking at its limitations, which was one of the reason that caused first AI winter.
- Then we take a closer look at <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> and how its overcame the limitation of this core _"algorithm"_ we just talked about.
- Now we know how <abbr title="Multi-Layer Perceptron"><b>MLPs</b></abbr> are built, but it doesn't get us far if we don't understand how it evaluates its mistake to learn from them.
- Now that we know how our <abbr title="Multi-Layer Perceptron"><b>MLPs</b></abbr> measure its mistakes, let's understand how model learns from its mistakes.
- If you made it this far within the blog, then you understand the core components that make a deep learning model. But it's not complete if you understand the whole learning process.
- Now that we understand how deep learning models work at conceptual level, let's wrap up everything by building an <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> using `pytorch` module.

I know it's a lot to take it, but don't you worry about a thing. I'm going to guide you step-by-step not only understand on a conceptual level but also building a model for yourself. I don't expect you to learn the whole thing within a single session and I don't want you to do that. Just take your time, come back when you feel like resuming your journey into deep learning with me.

> Please don't be dismayed by such large number of concepts, all the concepts discussed within this blog are very **beginner-friendly**. I have made sure to keep concept in such a way that **even a toddler could understand** _(with some prior knowledge of basic math and python as mentioned within [Prerequisites](#prerequisites "goto Prerequisites section"))_. Please take your time and build your foundation on clear understanding of these concepts.
{: .prompt-info}

### Prerequisites

Even thought this blog will be a totally beginner-friendly with some great in-dept insights with pretty good explanation of why things are done in a certain way and the things that made them as a go-to option for a few specific tasks. You need to have some basic foundation of following things for you to make sense out of this blog. Even though, most of these concepts are re-explained ___(depending upon context)___, Please make sure you have good/solid understanding of the following prerequisites...

> Remember!!!... Not all the following topics within prerequisites are broken down and re-explained, Only the ones that are more complex or the ones which required a pre-context to understand current usage are re-explained.
>
> You're expected with **at-least bare minimum basics** of the mentioned topics. If you find some concepts difficult to understand make sure you have some base foundation of that concept before you commenting your question at the complete end of this blog.
{: .prompt-danger}

#### Mathematics

I hate to break it to you that deep learning is not about calling various functions from libraries and training it tons 'n tons of data. Well it's not totally wrong, but what you don't realize is that deep learning was mathematics all along. Everything is deep learning is built upon tons of researches and inspirations that are better represented & implemented using mathematics. 

> Note that the actual meaning of the vaguely used term ___"Model"___ is basically a combination of various mathematical functions and concepts that goes hand-in-hand in different phases, including the phase where the end result is used as a final product. **Remember, It was Math---all along**.
{: .prompt-tip}

With that being said, tell take a look at the important mathematical concepts that are required for Deep learning:

- Basic Math _( pre-school / high-school )_
- Linear Algebra
  - Vectors
  - Matrix
  - Linear Transformations
  - Matrix Multiplication
- Discrete Mathematics
  - Boolean Algebra
  - Boolean Functions
  - Truth tables
- Coordinate Geometry
  - Linear Equation
  - Hyperplanes
  - Distance and Angle
- Calculus
  - Differential Equations
  - Chain Rule
  - Taylor Series
- Probability and Statistics
  - Probability Distribution

I know that's a lot of math right there, but don't get scared. This blog is designed in such a way that, you as the reader, is ONLY expected with bare minimum of the mentioned topics. And most of the time, I break down some of the fundamental concept for you to understand the _what, why, how_ behind these mathematical implementations that are curial for understand and implementing deep learning concepts.

#### Python

Since we're going to build a Deep Learning model at the end of this blog, you need to have **AT LEAST** foundational level of hands-on knowledge on Python Programming language. Don't worry if you're not familiar with most of the advance stuff within Python, Just make sure you some good hands-on knowledge on the following concepts:

- Python Basics
  - Data Types
  - Operators
  - Conditional Statements
  - Iterative Statements
- Python Native Data Structures
  - List
  - Tuple
  - Set
  - Dictionary
- Comprehensions
- Functions
- OOPS Concepts
  - Class
  - Object
  - Methods
  - Inheritance
- Packages & Modules

Well that's most of the basic foundational concept you need to know for the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> which we're going to build at the end of this blog. Normally, I could add other important libraries for data handling like `numpy`, `pandas` and stuff. But since we're using `pytorch` module for our <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>, we're going to use all the tools and features that comes natively with `pytorch` library. So that we stay right on topic instead of understanding how to use all the other 3rd-party libraries. 

Also, don't worry about `pytorch` library. We'll have a brief introduction to this library when we're building the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr>. Just make sure you're having a good/solid understanding and hands-on knowledge as mentioned above, before you proceed to the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> in the end.

#### Handling Environment

In this blog, we're not going over the steps to set up the required environment to build the final project. So, you need to do your own research to replicate the result or to run the code within your local machine. Here are list of things that are required to set up the required environment,

- Setting up virtual environments _(python-specific)_
  - Conda Environment ___(Recommended)___
  - Virtual Environment _(venv)_
  - Pip env
- Using Python Package Manager _(pip)_
- Containerization _(optional)_

These are most of the things required while working with any Python projects in general. But as of this blog and <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> which we're going to implement, it's more than enough to use `miniconda` for creating a virtual environment with `python 3.10` and `pytorch` as core dependencies. But if you're some whose more comfortable using `jupyter-notebook`, then I suggest you to go with `anaconda` for creating virtual environment _(as most of you, might have already installed it within your system)_.

Coming to containerization, it's not exactly a required necessity but kind of good practice. It might not make much sense for small python project _(like the <abbr title="Multi-Layer Perceptron"><b>MLP</b></abbr> within this blog)_ and creating a virtual environment could suffice for the current requirement, but it can help you familiarize with a few concepts when you're working on a comparatively bigger projects. 

If you're familiar with containerization, go ahead set up your environment accordingly. But if you're someone who's not familiar with these concepts but still want to implement them, then I suggest you to give Dev Container a try. And if you don't want to make it more complex or not interested in containerizing your project, then that to is fine because _"Simplicity is the ultimate sophistication"_.

#### Basics of Machine Learning (Optional, but Good to have)

This one is totally optional, you don't need much machine learning knowledge to understand this blog. But it's most certainly a Good-to-Have when it comes to understand how similar it is from many other ML algorithm out there. 

If you're familiar with ML concept, then Great !!!... Most of the things will make sense to you with much simpler explanation. And if you don't, it's still fine as I designed this blog assuming that you HAVE heard about Deep Learning but never learn knew what it really is...

And for people who're familiar with ML concepts, we're going to cover only the supervised learning part of deep learning concepts and while going through this blog, you'll understand how some concepts are very similar to the ones of linear regression. That might have been a spoiler for people who're not familiar with linear regression, so let's proceed to the actual content without any more spoilers.
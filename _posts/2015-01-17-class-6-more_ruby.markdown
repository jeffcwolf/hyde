---
layout: post
title:  "Class 6: Jan. 16, 2015 [Ruby]"
date:   2015-01-17 20:33:16
categories: starter league
---

In yesterday's class, we continued our exploration of Ruby and general programming constructs. We first worked through an example on the screen that showed the simplicity of using Ruby's String Interpolation operator - it really helps to avoid all the mistakes associated with conversion methods. And it just feels more natural to write code using it.

We reviewed 'if' statements and their varieties, including 'elsif' and writing nesting conditionals. We are, apparently, going to be writing a lot of 'if' statements, as we use Rails, so Raghu wanted us to be clear about how they work.

But the major new concept of class was another list structure (kind of like an array) called a <a title="Introduction to Hashes in Ruby" href="http://rubymonk.com/learning/books/1/chapters/10-hashes-in-ruby/lessons/46-introduction-to-ruby-hashes" target="_blank"><em>hash</em></a>. We use hashes in Ruby when we want to create a list of values that is linked meaningfully with a set of related values that describe or define those original values. In other words, a set of <em>keys </em>and their paired values. For example, the following key and its paired value would work well in a hash:

{ Instructor (key) =&gt; Raghu Betina (value) }

The curly brackets and the hash rocket (=&gt;, read as 'goes to') show that we are dealing with a hash here. In an important sense - which we will learn about later - everything in Rails (and a lot of web development) can be reduced to a hash, or a list with meaningful, descriptive labels attached.

The final section of class was about APIs, or Application Programming Interfaces (commonly written in <a title="Introduction to JSON" href="http://blog.scottlowe.org/2013/11/08/a-non-programmers-introduction-to-json/" target="_blank">JSON</a> nowadays). These are critical to developing web apps that use dynamic, live data on the web. I knew about them conceptually but have never used one, so I'm excited to get my hands dirty soon.

To illustrate how powerful having a well-structured API can be, Raghu told us about his own discovery of them and how he could write a program using the Facebook API to import and parse his newsfeed, producing a list of all the videos that his friends' posted. In only a dozen lines of code or so, he was able to write a ruby program that downloaded his newsfeed (written in JSON), parsed it, filtered out only the videos, and saved this - as an HTML file! - all written in ruby. He was showing us how one can actually write a Ruby program that writes HTML for us (based on a dynamic data source)!

This was all by way of introduction to Rails, which does this on a much larger and more sophisticated scale. We don't have class on Monday (MLK Jr. Holiday) but we will still begin Rails next week (either Wed. or Fri). I'm pumped.

---
layout: post
title:  "Class 8: Jan. 23, 2015 [Rails]"
date:   2015-01-23 23:08:12
categories: starter league
---

[I will be migrating this blog from its Wordpress and PHP internals to something Ruby-based, whether this be the <a title="Jekyll" href="http://jekyllrb.com" target="_blank">Jekyll</a> platform or a full-fledged Rails website, with blog included. Trying to create such a thing will be a wonderful learning experience, I expect.]

Today was a big day: our introduction to Rails!

We learned about the Model-View-Controller (MVC) architecture that is behind Rails (and other frameworks). And we saw how the embedded Ruby template file (.html.erb) allows us to embed Ruby within an HTML file. This was the first hint of Rails' power.

Raghu then described RCAV (<strong>R</strong>outes <strong>C</strong>ontroller<strong> A</strong>ction<strong> V</strong>iew), and how it is <i>the </i>fundamental workflow in every single Rails application that we will create. We will follow RCAV so often that it will be embedded into our minds.

It was clear, as well, that a lot of Rails' error messages are actually quite helpful and that the errors we should be concerned with are, counterintuitively, the ones where we can't rely on Rails' error messages. These are the hardest to debug.

We ended by discussing the critical concept of using Rails to capture dynamic input and then creating dynamic URLS on the fly from that input. The <strong>params </strong>variable that Rails uses to store input (in the form of a hash) will be something we use very often. And it is the power of that params variable that allows us to capture dynamic content and display it via dynamic URLS—a kind of dynamic version of Ruby's 'gets' method.

And with this critical concept we got another glimpse of Rails' power. We are on the cusp of being able to create our own (initially quite basic) web apps, using Rails. I predict that by the end of next week we will start to have a lot of the basic tools down that will allow us to build basic versions of more complicated web applications. Exciting stuff.

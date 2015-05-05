---
layout: post
title:  "Class 21: Feb. 25, 2015 [Scaffolding]"
date:   2015-02-25 23:17:20
categories: starter league
---

Today we did a lot of hands-on practice, which I found very helpful. The goal was to see how the Rails 'scaffold' command works - what it does from the ground up - because we will be relying on it going forward (according to the official Rails Guides, a "<a title="Ruby Command Line" href="http://guides.rubyonrails.org/command_line.html" target="_blank">scaffold</a> in Rails is a full set of model, database migration for that model, controller to manipulate it, views to view and manipulate the data, and a test suite for each of the above.") But before we do, we need to understand exactly what the scaffold command does for us. It's a good rule of thumb: don't use a generator unless you understand the lines of code that it writes on your behalf.

In the course of our practice, we learned a couple of new concepts or ways of doing things. First, we were introduced to some more advanced 'link_to' tag shortcuts. Second, we got a better feel for when to use mass assignment with the 'create' method, and when to simply use the combination of 'new' and 'save'. Similar considerations apply to using 'assign_attributes' vs. 'update_attributes'. We also became more comfortable with handling some of the security features of Rails, and in particular, using a parameters whitelist when creating and updating forms.

While we did not learn many new concepts today, we got a lot of great practice building an app from scratch, implementing a lot of the more advanced methods we've been learning about. This, along with more practice, really helps us build this knowledge into our muscle memories.

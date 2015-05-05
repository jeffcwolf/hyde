---
layout: post
title:  "Class 25: Mar. 6, 2015 [Callbacks, Partials, Self-referential Many-to-Manys]"
date:   2015-03-06 23:56:39
categories: starter league
---

Today we focused on completing our Instagram clone (Photogram). In a way, we also laid the groundwork for being introduced to <a title="JavaScript" href="http://en.wikipedia.org/wiki/JavaScript" target="_blank">Javascript</a> and <a title="AJAX" href="http://en.wikipedia.org/wiki/Ajax_(programming)" target="_blank">AJAX</a>, which we will see next class.

We also came up with a list of Rails-related concepts that it would be nice to cover in the final week or two of class, in order to help us build our apps. These included:

<ul>
  <li>Chron jobs</li>
  <li>How to use the Asset pipeline</li>
  <li>How to implements payments (using Stripe or Braintree)</li>
</ul>

Next, we took a closer look at <a title="Callbacks" href="http://guides.rubyonrails.org/active_record_callbacks.html" target="_blank">ActiveRecord callbacks</a>, which we had not discussed before. Callbacks are, according to the Rails Guides, "methods that get called at certain moments of an object's life cycle. With callbacks it is possible to write code that will run whenever an Active Record object is created, saved, updated, deleted, validated, or loaded from the database." They seem like a particularly good way to prevent orphan records that disrupt our apps; that is, at least the use case we considered in class. For example, suppose we have a photo that has a number of comments associated with it. If we delete the photo, then it makes sense to delete the comments that depend upon it. But this doesn't happen automatically, unless we include a callback in our model. So callbacks seem to be pretty important methods in Rails. Of course, because they can, for instance, automatically delete records, we need to be careful when using them. And we can, according to Raghu, write our own callbacks to customise them further.

Now, a key concept we need to be comfortable with in preparing to learn Javascript is the notion of partials. We have seen them before, and how they enable us to write much more modular, DRYer code. Today we took a closer look at how to use partials, and in particular, how we can actually pass arguments to the partials (for instance, when we call the 'render' method, we can pass through a hash of variable names that the partial needs to function). This helps us make our views extremely modular. We can even have partials within partials! We haven't been introduced to AJAX yet (AJAX is short for 'asynchronous JavaScript and XML' and it refers to "a group of interrelated Web development techniques used on the client-side to create asynchronous Web applications"), but Raghu emphasises that mastering this use of partials (passing them arguments that contain variables) is essential to AJAX.

The final concept we reviewed today, which is essential to our creation of Photogram, is the use of a self-referential many-to-many association method. For instance, in Photogram we only have one User table, but users can serve two functions, as followers (of other users' posts) and as (what we called) 'leaders', i.e. those whose posts are followed by other users. Yet we only have one User table so we need that table to be associated with itself! This sounds complicated, and it is certainly more tricky than other associations we have seen until now. At least in terms of visualising and talking about the relationship. At the same time, it's really just another many-to-many association (albeit one where the two tables are in fact the same), which we're already familiar with. We saw how we can customise our usual many-to-many association method, using :through and :source to work in the way we want. It is just another 'has-many' :through method, customised to reflect different unconventional naming. So long as we can manage the naming (using descriptive, accurate names), this kind of association is no more difficult in theory than ones we have already seen, and we can make it work with a little customisation.

That's it for Week 9. We begin the final two weeks of class on Monday, starting with Javascript and AJAX. In the meantime, I have begun more intensive work on my own app, Solidify.

---
layout: post
title:  "Class 20: Feb. 23, 2015 [Seed Data, Form Security, &amp; Helper Methods]"
date:   2015-02-24 00:05:50
categories: starter league
---

Today was mostly about learning how to implement a lot of the Rails functionality (and security) we have already seen but using more concise, advanced (DRYer) methods. That will, in fact, be the theme for this week: getting us up to speed on a lot of the best practices in the Rails community for a lot of the functionality we already know how to build - perhaps with better security built-in.

But first we spent a little time exploring a gem (<a title="Faker Gem" href="https://github.com/stympy/faker" target="_blank">stympy/faker</a>) that will be very handy in generating dummy seed data for our apps. It will help us create some fake users and data to populate our apps, while we build out their UI.

Next, we learned a bit more about securing our apps using the devise gem and some of Rails' built-in security features. We discussed the concept of 'before actions' in Rails. These are actions, often placed in the relevant controller, that are used both for security and to DRY up code that we repeat in our actions. We can use before_actions in our controllers - in fact we want to do so - in order to verify the authentication of our users so that they cannot accidentally, or maliciously, hack our apps. This is much more secure than trying to implement security in our view templates, simply by hiding parts of forms.

Next, we reviewed some useful Helper methods that we will want to begin using, so that we can write more concise code. These include ways of employing 'mass assignment' (say, using the '.create' and '.update_attributes' methods), as well as the 'resources' method that will write a suite of RESTful routes for us.

One of the most complicated but also most powerful helper methods that we learned is the 'form_for' method. It is a special purpose (and very smart) form helper method, whose job is specifically to create forms that allow us to update and add rows to our tables (which, admittedly, is what we want to do most of the time with a form). The 'form_for' method creates a hash that we can then pass onto some of our mass assignment methods, making this process a lot more efficient and concise. There are some security issues related to this, however - namely, the issue of using 'Strong Parameters' but we can make some adjustments to whitelist the parameters we need, allowing the 'form_for' method to help us with mass assignment.

The final new concept we touched on today was the notion of 'Partials' - a really great feature in Rails that allows us to DRY up a lot of the code we might ordinarily place in our View templates. For instance, we can write a form partial and then call that block of code in multiple view templates. It really helps us to write modular, self-contained, re-useable code that is much easier, in the long run, to update, maintain, and debug.

Lastly, Raghu - as a teaser of sorts - showed us how easy it is to reformat our eRuby code as json (to build an API), right in Rails itself.

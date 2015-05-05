---
layout: post
title:  "Class 24: Mar. 4, 2015 [Instagram Clone, Customising Association Methods]"
date:   2015-03-04 23:17:53
categories: starter league
---

Today we began building a functional Instagram clone from scratch. The goal here is to consolidate a lot of what we have learned since the beginning of class, as well as to see a particular kind of association (a tricky one) that we have not worked with yet, namely a self-referential many-to-many.

Raghu told us that, at this point, we have covered the core of Rails. Until the end of class in three weeks, we are going to see (in addition to non-Rails concepts like JavaScript) some of the gems that 90% of Rails developers rely on 90% of the time. This will make our lives easier and give us more insight into the code that other Rails developers write daily.

We talked about one of these gems today, the one we touched on briefly last class: <a title="ActiveAdmin gem" href="http://activeadmin.info" target="_blank">ActiveAdmin</a>. ActiveAdmin uses the devise gem  under the hood to build an admin sub-layer to our app. It creates an Admin user table for us and a powerful Admin dashboard with sophisticated filters (based on the <a title="Ransack gem" href="https://github.com/activerecord-hackery/ransack" target="_blank">Ransack gem</a>). We can register our models (resources) with ActiveAdmin, and it monitors them for us, as well as creating something like a separate scaffolding system that we can use to CRUD our resource(s). Basically, the Admin framework that it creates is one way of giving us (the Admin) an eagle-eye overview of our web app, especially parts of it that we want to hide from our users.

Another gem we saw in action today was the file uploading gem <a title="Carrierwave Gem" href="https://github.com/carrierwaveuploader/carrierwave" target="_blank">carrierwave</a>. Carrierwave helps us manage file uploading for our Rails apps and will come in handy for our Instagram clone (Photogram).

While setting up our Photogram app, we focused on writing association helper methods that customised. Essentially, in this app we want to use non-conventional method names (and sometimes non-conventional foreign key names) and so we can't simply use the association method shortcuts that we've learned. We need to customise our association methods to reflect these non-conventional names and this was reminiscent of what we learned a few weeks ago, when we had to write these methods out in full, the long way.

Finally, we began building up the front-end UI for Photogram, reminding ourselves of Bootstrap and various relevant classes that we came across near the beginning of this class.

Next class, we are going to continue building Photogram, with a focus on the advanced associations we did not have time to see today (e.g. the self-referential many-to-many). We will also review some advanced Ruby concepts that will prepare us for the introduction of JavaScript, which we will hopefully begin on Monday at the latest.

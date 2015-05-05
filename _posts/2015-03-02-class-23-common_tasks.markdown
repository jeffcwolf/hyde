---
layout: post
title:  "Class 23: Mar. 2, 2015 [Common Tasks Workflow, Cont.]"
date:   2015-03-02 21:13:33
categories: starter league
---

Today we continued to consolidate our knowledge of common tasks that we will most likely need for nearly every Rails app we create. Raghu also gave us a preview of the final three weeks ahead: Starting Wednesday we will see the most complicated associations we are likely to encounter (self-referential many-to-manys), when we build our Instagram clone from the ground up. On Friday we will begin our exploration of JavaScript and JQuery, which will last at least a week. Finally, we will fill in some gaps and add some UI polishing tricks to our skillset, including how to implement SMS, email, and APIs using Rails.

But to return to today: we reviewed the differences between the form_tag and form_for. Raghu emphasised that we should not be afraid to revert to more explicit methods - the more basic methods - if at first we stumble over how to implement more advanced ones, like form_for. While best practices and professional rail developers prefer the latter, we can always use the former first, in order to gain clarity. Then, upon review, we can always refactor to produce DRYer code.

We reviewed various manifestations of the link_to tag, and how to use the debug helper method for insight into some of the errors we may encounter. We saw a new version of the redirect_to tag (referencing :back), as well as when we might want to call the .uniq method on an array.

We spent a considerable - and helpful - amount of time on security-related issues. We reviewed, once again, the use of before_actions ('filters' in the old parlance) to enhance the security of our forms and our actions more generally, especially with respect to user authentication. Raghu also showed us how the .try method can help to prevent situations where an associated object is 'nil' (permissibly) and thus breaks an entire display page, when we still want to allow it to be 'nil' without doing so.

A new concept that we learned today was how to implement <em>pagination</em>. Raghu first demonstrated the proof-of-concept, or how to do this from scratch, using a combination of the .offset and .limit query methods. Then he introduced us to an easier way to implement this ourselves, using the <a title="Kaminari Gem" href="https://github.com/amatsuda/kaminari" target="_blank">kaminari gem</a>. Kaminari does pagination quite nicely, is fairly configurable, and is straight-forward to use.

In his introduction to this gem, Raghu provided us with some good rules of thumb about how to decide when - and which - gems to implement in an application. How should we choose a gem? His thinking is structured by the following questions:

<ul>
  <li>Is the gem on GitHub, as opposed to somewhere else? (Good, if yes)</li>
  <li>How many Stars and Forks does it have (especially Forks) on GitHub? This is a measure of its popularity and user base.</li>
  <li>How good is the Readme file? How much detail does it offer?</li>
  <li>How recent are the Commits? They should, at a minimum, keep up with the latest major release of Rails.</li>
</ul>

And the ultimate test: Is there a <a title="RailsCasts" href="http://railscasts.com" target="_blank">RailsCast</a> for it? Incidentally, Raghu said that one way of thinking about the goal of our web development course more generally is: when we're done, do we have the vocabulary and know-how to understand RailsCasts? In the future, can we use them to build up our own knowledge and expertise in Rails (e.g. could we follow the one on <a title="Pagination with Kaminari" href="http://railscasts.com/episodes/254-pagination-with-kaminari" target="_blank">Kaminari</a>)? They are an incredible resource (though, sadly, they are growing stale) and that's how Raghu really built up his own knowledge, once he got the basic foundations. He wants us to be able to follow in his footsteps here.

Another concept that Raghu introduced us to today was the notion of default scope. We can actually set a default ordering of our list data on a model by model basis. That is, by adding the following line of code to our model logic (suitably adjusted for the column which we want to sort by), we can have default ordering of all the data we wish to display on our index pages:

default_scope { order("name ASC") }

Finally, we talked a bit about what to do once we have our web app fully functional and more or less the way we want it to work. What then? Ultimately, we want to get rid of a lot of the scaffolding we may have generated to get us up and running; there is likely a lot of 'dead code' that we no longer need to show to our users or even have available, so we need to go through and eliminated that. The simplest way to do this is to eliminate the routes we don't need, and we can do this by white (or black) listing our resources command to only include/exclude what we want to be available.

Of course, this is not always desirable; perhaps we want an Admin (or multiple admins) to have access to these routes, in which case we could write some before_actions to make them accessible only to a few users. Or, even more comprehensively, we could even write an entirely separate sub-application specifically for admins (an 'administrative framework'). We will likely review this in more detail next time, but Raghu suggested that we explore the very powerful <a title="Active Admin Gem" href="http://activeadmin.info" target="_blank">Active Admin gem</a> to get a sense of how this can be implemented.

So we covered a lot of ground today, and I have a fairly clear roadmap for building up my own application, Solidify, which I will not spend most of my time outside of class doing. More on that soon.

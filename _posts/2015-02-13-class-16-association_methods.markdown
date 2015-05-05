---
layout: post
title:  "Class 16: Feb. 13, 2015 [Reviewing Relationships &amp; Association Methods]"
date:   2015-02-13 23:20:16
categories: starter league
---

Today we continued to focus on how to set up the initial data structure of our applications. We practiced identifying  proper database relationships, accurate naming of join tables, and where to place foreign keys to make it all work. Raghu emphasised that the join table (or Model) should really represent the relationship between a single instance from one table (that it joins) to a single instance from another table (which it joins). For instance, when thinking about the relationship between, say, Movies and Actors, the join table might be 'Roles' because we are trying to represent the relationship between a single movie and a single actor. Of course, each of these is in a one-many relationship to the Roles table: one movie has many roles, and an actor belongs to many roles (though only a single role in a single movie).

It's critical, going forward, to understand how to traverse tables via association methods and route naming methods. In doing so, we need to be very familiar with both the 'link_to' method and how to use route naming methods (e.g. 'movies_url') because these are going to be a part of many of the apps we see.

We also abandoned some of our training wheels today, when Raghu showed us some key shortcuts to writing association methods. Rather than coding these all by hand (which we have been doing, in order to learn how they work), we can now use (1) belongs_to and (2) has_many methods. These write our Association methods for us, even if they are quite complicated many-many methods. Here is the syntax for the different kinds of relationships, when using these methods:

(1) <strong>belongs_to</strong> :method_name :class_name =&gt; "Table_name" [from where we want to draw our results], :foreign_key =&gt; "Name". Now, if we adhere to conventional naming and RESTful routing, we often can leave off the last two parameters and just include the method name that we want to write, so it actually looks more like this: belongs_to :method_name

(2) <strong>has_many</strong> :method_name :class_name =&gt; "Table_name", :foreign_key =&gt; "Name". Again though, we can often shorten this to simply: has_many :method_name, so long as the parameters are conventionally written.

The many-many lookup is a bit more complex, and Raghu showed us how to write it by hand. However, we will normally see it written using the has_many method but with a different syntax to indicate some of its added functionality:

(3) <strong>has_many</strong> :method_name :through =&gt; table_name :source =&gt; table_name. Again, though, we can often shorten this to simply has_many :method_name :through =&gt; table_name

Raghu emphasised how important it is to design our database architecture up front; that is the KEY task in the creation of our app. And we need to think carefully about the choice of the name for each of our tables (especially our join tables). Ideally, our names should reflect what they represent in a concrete way. In any case, actually writing the Ruby in Rails, on account of all the shortcut methods we are learning, we'll be comparatively straightforward, once we have our Domain Model in place. We are now going to spend more time (after reviewing user authentication) building our own apps.

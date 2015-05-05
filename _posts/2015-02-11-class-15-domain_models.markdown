---
layout: post
title:  "Class 15: Feb. 11, 2015 [Domain Models &amp; Many-to-Many Relationships]"
date:   2015-02-11 23:47:23
categories: starter league
---

We continued our exploration of database structure today. Raghu emphasised that the hardest part of building an application is getting the Domain Model right - that is, getting the proper database architecture to work. And, in fact, our data structure is essentially the heart of an application.

Recalling what we learned last class: there are basically two relationships that encompass how our database tables might relate to each other - the one-to-many relationship and the many-to-many. We will get better at identifying these relationships and knowing how to set them up in our Domain Models. Ultimately, we need to be able to use foreign keys to traverse the data across our tables.

We spent some time solidifying our understanding of association (helper) methods and how creating these in our Models can greatly simplify our code throughout our application. This touched upon why the OOP paradigm (<a title="OOP" href="http://en.wikipedia.org/wiki/Object-oriented_programming" target="_blank">Object-Oriented-Programming</a>) can be so powerful: we create our own Class and our own super-charged methods within those classes so that we can use them later on throughout our application to simplify our code. We invest time up-front creating these methods so that they can do a lot of our tedious work (e.g. writing long lines of HTML) for us. This is how we make our code simpler and more powerful at the same time.

Once we've created our association helper methods, we need a better way to display data in our forms in order to reflect the associations between our tables. This is often done with dropdown boxes (or the slightly more advanced type-ahead box). In order to code these, we learned some neat time-saving helper methods, including 'select_tag' and 'options_from_collection_for_select'. They will facilitate our form creation from here onwards.

Finally, we took our first look at the Many-to-Many relationship, which is slightly more complicated than the One-to-Many relation we have grown accustomed to. For the latter, we now know that once we identify these, we need to do the following:

<ul>
  <li>Make sure to put the foreign key in the right table</li>
  <li>Implement relevant association methods in our Models</li>
  <li>Fix our forms by creating dropdown (or type-ahead) boxes</li>
</ul>

But how do we deal with Many-to-Many relationships? First, let us be clear about what these are: imagine two tables, one is a list of actors and the other a list of movies. They are in a Many-to-Many relationship because each movie has many actors AND each actor belongs to many movies. So, if we want to capture this relationship, we cannot simply put a foreign key in both tables and link them together because a column can only one value (e.g. in an actor table a movie_id column only contains one id, even though an actor may belong to multiple movies). So we have a Many-to-Many relationship here.

The solution is something called a Join Table. This is an entirely new table, an intermediate one, that allows us to reduce the Many-to-Many relationship to two connected One-to-Many relationships. In this case, we might have a 'Roles' table that list all the roles in a movie. Thus each movie contains multiple roles, and we have a one-to-many relationship in that respect. But, on the other side, an actor likely belongs to many roles, so that there is a One-to-Many relationship from Actors to Roles, as well. The Join Table then contains foreign keys for both linked tables, as well as any other relevant real-world attributes related to that data, e.g. the character_name for that role.

Ultimately, our database architecture is, or should be, totally independent of the client we build on top of it (e.g. a web app, a mobile app, etc). Thus it is helpful to think of these database questions more generally and not just in terms of what we know about Rails, though Rails will give us (as we will see) some extra methods to deal with them.

We are therefore now in a position to begin thinking more critically about our own web applications. We can begin our Domain Modelling and ask fruitful questions about the architecture of what we want to build. For each table, or set of tables, we need to know:

<ol>
  <li>What are the One-to-Many relationships?</li>
  <li>What are the Many-to-Many relationships?</li>
  <li>Where should we place our foreign keys?</li>
  <li>And what will our Join tables look like?</li>
</ol>

This is plenty to get us thinking about how we want to design our own apps.

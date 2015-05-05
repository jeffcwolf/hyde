---
layout: post
title:  "Class 14: Feb. 9, 2015 [Database Associations]"
date:   2015-02-09 23:22:20
categories: starter league
---

Today we moved beyond our introductory knowledge of database associations and began to see how to incorporate them into our Rails apps. But, first, we reviewed some of the concepts from last class. We talked about data validation and how we can use the error messages collection to complement that. Raghu told us that until you ask an object in Rails for validity (until you check for validity), you won't have anything in your errors array. We can only save a new record into our database (or update an existing one) use .save if there are no errors in our errors collection. That's the power of testing for validity first.

Next, we more formally explored the notion of relating tables to each other in our Rails apps. How, in other words, do we start relating models/tables to each other? Our ability to do so is where the real power of our apps comes into play. Indeed, this is how a lot of web applications work. They would be far less useful if we just had a set of disconnected databases.

Raghu told us that we have, essentially, only two kinds of relationships between database tables: (1) the one-to-many relationship and (2) the many-to-many relationship. If we consider (1): imagine a table of movies and a table of directors. The one-to-many relationship would reflect that fact that each director may have directed many movies, while each movie (let's posit) will only have one director. It is therefore a one (director) to many (movies) relationship. If we consider (2): imagine if we had another table of actors. Then we can imagine that multiple movies also have many of the same actors and that multiple actors are in multiple movies. This is the many-to-many relationship.

Now, given this added complexity, it's important that we take a little time to plan our web applications before creating our tables. We need to think about not only which tables we will need, but how they relate to each other. This process of mapping out the database tables we need, and their relationships, is called <a title="Domain Modeling" href="http://en.wikipedia.org/wiki/Domain_model" target="_blank">Domain Modeling</a> and it is the heart of every web application. Ragu recommends we begin doing this, perhaps using Excel, so that we can have a more sophisticated understanding of the data structure of our app.

A key component of this Domain Modeling is understanding where we place our foreign keys in each table (of course, each table has its own primary key, which Rails manages for us behind the scenes). The foreign key is a table row that contains another, related table's primary key.

With all this in mind, as we move forward, Raghu has suggested a new workflow for us:

Work on our Domain Model by sketching our tables and their relationships in Excel, including the placement of foreign keys

<ol>
  <li>Then use our starter generators to build or generate the resources we will need for our app (thus creating an empty but ready app)</li>
  <li>Next, we open up the app and immediately edit the Models files by writing validation rules <strong>before</strong> we do anything else in the app, or even importing seed data. This is to ensure and enforce the integrity of our data.</li>
  <li>We might then import our (seed) data, if we have some.</li>
  <li>Finally, we are ready to get to work, by relentlessly customising what we begin with. We modify/customise the generated markup to suit our needs.</li>
</ol>

This is the general workflow we should have in mind, when we sit down to build a new app, from her on out (probably to be modified later).

With some more practice, I will feel ready to build and construct the core components of my own Rails application.

[Addition]

I should mention that we also reviewed two of the basic queries in Rails - 'find_by' and 'where'. The first is a simple lookup that returns a single record from the Table; the latter returns a list of values from the Table in question. That's an important distinction. Finally, we also reviewed how to create our own class methods and, with the help of the 'self' method, created methods that allowed us to do do these lookups on the fly. I was initially confused about the use of 'self' - was it not redundant? And when do we really want to use it? Why is it necessary in these instances? A useful discussion of this can be found <a title="Self in Ruby" href="http://www.jimmycuadra.com/posts/self-in-ruby" target="_blank">here</a>.

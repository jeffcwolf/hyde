---
layout: post
title:  "Class 17: Feb. 16, 2015 [App Building Checklist]"
date:   2015-02-16 23:37:32
categories: starter league
---

Class 17 was very much about process and workflow. When we're asked to develop an app from scratch, how do we go about doing it? In a way, this was a very nice roundup of a lot of what we’ve learned about Rails so far. Raghu walked us through what he called an App Building Checklist - a process similar to the one he goes through when he sits down and codes an app from scratch.

What I want to do below is provide a high-level overview of this process, without going into too much detail (I will create, at a later date, a more detailed version of this checklist). I skip over many detailed and specific steps here; the point is just to gloss the big picture.

The App Building Process can usefully be divided into the following stages (these are my terms but capture the essence of Raghu’s discussion):

<ul>
  <li>Preparation</li>
  <li>Generation</li>
  <li>Customisation</li>
</ul>

<strong>I. PREPARATION</strong>

This is, conceptually-speaking, the hard part of building an app. It involves the following, presuming you already have an app idea:

(1) Create some rough sketches of a few screens from the app you want to create

(2) Develop ‘user stories’ based on the sketches: what are the abilities you want this app to provide for your users?

(3) Determine the Domain Model for the app: what tables and columns will you need (including the proper placement of foreign keys) for the core functionality of the app? Don’t get too ambitious here; focus on the handful of core actions that you want your app to perform.

All the above is prep work for building the app but extremely necessary. And, in fact, a little more effort at this stage will go a long way toward preventing cumbersome headaches in the future.

<strong>II. GENERATION</strong>

(4) Once we have our Domain Model in hand (including columns, data types, and foreign key placements), we can begin to generate the resources we will need, using generators that Rails provides us
  —&gt;It’s a good idea to make tiny, granular commits of your project to GitHub at this stage, so that you can revert commits at any time, without having to throw away your entire app
  —&gt;This is also an appropriate time to add some appealing style (Bootstrap, for instance) to your app to make it more enjoyable to work with
  —&gt;Since most apps will require Authentication, when you’re generating your Users (or similar) table, this is the time to use the devise gem, if that’s what you want to use to handle it. So, when generating the Users resource, use devise instead of the usual starter generators

(5) Once we have generated our resources, the very first thing we want to do, before even starting up our server or opening up a browser, is to add our Model logic - at a minimum, data validations and association methods.
  —&gt;Validate our data based on, at a minimum, presence and uniqueness (where relevant). Of course, there are lots of other validation methods. It can be helpful to go through each of our tables and ask ourselves two questions: (i) Does a specific row in that table have to be there; can we allow a user to access it but leave it blank? (ii) Are we going to allow multiple rows with the same value in that table?
  —&gt;With respect to associations, go through first and complete all the simple one-to-many associations. Don’t even hesitate to do these right away. They follow directly from the structure of our database schema and the placement of foreign keys (yet another reason to be confident that we’ve got a good Domain Model upfront).
  —&gt;Next, ask ourselves if we need to include a many-to-many associations. We won’t want to add all possible ones - just the handful (if any) that are critical to the core functionality of our app. We need not stress too much about this now; we can always come back and add further ones later.

(6) Before trying to build our user interface (UI), we really want to create some solid seed data. This makes it a lot more enjoyable (and effective) to build out the functionality of our app. We can generate seed data in a variety of ways, including:
  —&gt;Writing ruby directly in our seeds.rb file
  —&gt;Manually add some seed data to our app using our forms; this is tedious but it works. Once we’ve done this, we could use the seed_dump gem to turn this data into ruby and store it in our seeds.rb file (thus alleviating the need to write the ruby ourselves)
  —&gt;Import and parse a CSV (or similar file) and then write some ruby (also in seeds.rb) to save it into our database

(7) By now we have a lot of our scaffolding in place and even our basic UI. But our generators are not smart and the forms they’ve created for us are clumsy and not very user-friendly. We need to go through and replace, for instance, all the text input boxes for foreign keys with dropdown boxes instead (we don’t want our users to have to type this in!). We can use our form helper methods to accomplish a lot of this. The same goes for other places in our view templates where we are still displaying raw foreign keys. We don’t want this but rather the associated data, e.g. instead of showing a Venue ID, we want to display the associated Venue Name. Using our association helper methods, we can fix our view templates to render the associated data.

<strong>III. CUSTOMISATION</strong>

Once we’ve accomplished everything above, we’ve got a lot of our boilerplate in place. We have the scaffolding for the app we want to build, but it has not been customised to display, or generate, its core functionality. It’s still a generic Rails app. So the next step is to customise what we have so that the app will do what we want it to do. We want it to reflect our core User Stories.

(8) The first step to doing this can be (though it need not be, of course) is to go into the relevant Show and Index pages and literally write out, in English, what we want to accomplish on that part of the page, e.g. “Display a list of this user’s favourite dishes at a particular restaurant”. It can be helpful to write out these prompts explicitly, before going into the Ruby.

Then the real work begins.

Now, there are a lot more steps here that I am leaving out - almost everything to do with authentication, for instance, or more detail about adding association methods or further customisation. But everything above is a pretty good high-level schematic for how to create the basics of a Rails app. And that was the essence of Class 17.

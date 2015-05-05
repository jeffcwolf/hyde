---
layout: post
title:  "Class 12: Feb. 4, 2015 [Helper Methods &amp; RESTful Routing]"
date:   2015-02-04 19:23:53
categories: starter league
---

Note: We did not have class on Monday, February 2, due to the massive snowstorm that hit Chicago (19 inches!). We will make up for lost time closer to the end of the course].

Today was a lot of great new material. We're really moving toward being able to create Rails apps that are more conventional, more akin to what professional Rails developers produce. We are getting rid of our training wheels.

That was the thrust of much of today's class: learning how to write code according to best practices. The code will be more succinct and more powerful than what we have been learning so far—and more complicated—which is why we have been hammering on the fundamentals first.

We spent a lot of time today understanding routes. We have to be knowledgeable about what matches with what and what <strong>must</strong> match for things to work in Rails. The job of every action, in fact, is to send an HTTP response back to the user. This is usually in the form of HTML but it doesn't have to be. Thus, we do not always want to render our methods as HTML pages, however dynamic (i.e, we don't always need a matching View template). Sometimes we want to simply redirect our users to another page (perhaps the original), sometimes accompanied with an alert or notice. Thus, the first new method we learned today was the 'redirect_to' method, which allows us to do these very things.

Next, we wanted to learn some ways to clean up our code, to write apps that are more in line with best practices, what professional Rails developers generally, and by convention, do. And that means learning some helper methods.

(1) Helper Methods

Helper methods are Ruby methods (in Rails) we can use, especially in our view templates, to write HTML code for us. Raghu said we are going to focus on four of them for now, though there are many more. These include:
<ul>
  <li>The <strong>link_to</strong> method</li>
  <li>The <strong>image_tag</strong> method</li>
  <li>The <strong>form_tag</strong> method</li>
  <li>The <strong>:as</strong> name route method</li>
</ul>

I am not going to describe the details of these methods here. But suffice it to say that they help us write more secure, less brittle code in our Rails apps. We will therefore have to do a bit of unlearning and incorporate these new methods in our apps going forward.

The second major concept we learned today was:

2) RESTful Routing (Architecture)

From now on, there is a conventional way we should write our routes in Rails. These conventions have been developed from an interpretation of how HTTP should work, and in particular, arise from an understanding of a type of software architecture known as REST (<strong>Re</strong>presentational <strong>S</strong>tate <strong>T</strong>ransfer). What is REST?

Without going in to much detail here, REST is generally described as "a software architecture style consisting of guidelines and best practices for creating scalable web services." [<a title="REST" href="http://en.wikipedia.org/wiki/Representational_state_transfer" target="_blank">Wikipedia</a>] That is a bit vague but essentially "RESTful systems typically, but not always, communicate over the Hypertext Transfer Protocol with the same HTTP verbs (GET, POST, PUT, DELETE, etc.) used by web browsers to retrieve web pages and send data to remote servers." [<a title="REST" href="http://en.wikipedia.org/wiki/Representational_state_transfer" target="_blank">Wikipedia</a>] Therefore, if a web app adheres to the guidelines and constraints of REST architecture, it is considered a RESTful web application, which is what we are building. For our purposes, this means that we need to design our routes in such a way that we map certain HTTP actions (or VERBS) to certain routes. Instead of using 'get' Verbs for all our routes, we restrict these to cases where our users are simply <em>reading </em>from our applications. When a user wants to create something new (i.e. add a record to our database), we map this URL route to the relevant HTTP verb, in this case 'post' (though 'put' would work as well). The same logic applies to update actions, which will now be mapped to the 'patch' verb. And so on.

This is just a short summary of RESTful routing but for our purposes, it means we will now think of routes differently (for a nice introduction to HTTP and REST, I have found the following discussion helpful: <a title="Beginner's Guide to HTTP and REST" href="http://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340" target="_blank">Beginner's Guide to HTTP and REST</a>). Instead of simple 'get' methods attached to dynamic URLS, we will now think of routes as being composed of <em>both</em> an HTTP Verb and URL (or the noun). Routes are therefore really composed of both the URL and the HTTP verb, which indicates the intention of the user. With this knowledge, and with the use of helper methods, from now on we will not hard-code URLS into our apps, except in our routes.rb file.

We will continue to practice writing our routes by hand, now incorporating RESTful routing conventions and critical helper methods, but we will also start using generators going forward, as most professional developers do. But it has been essential that we first learned how all this works from scratch, so that when we want to customize our generators and our apps in the future, we know how to do it. Not to mention that our grasp of the fundamentals has been greatly enhanced by learning things the 'tedious way' rather than relying on shortcuts from the beginning. I definitely approve of this pedagogical approach.

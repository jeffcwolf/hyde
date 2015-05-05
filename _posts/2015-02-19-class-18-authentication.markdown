---
layout: post
title:  "Class 18: Feb. 18, 2015 [Authentication]"
date:   2015-02-19 00:20:39
categories: starter league
---

Today we learned how to implement authentication (sign in/sign out) in our Rails apps using the <a title="Devise Gem" href="https://github.com/plataformatec/devise" target="_blank">devise gem</a>. The devise gem is an incredible sign in/sign out system that is feature-rich and very well-tested, used by thousands of other apps.

But before we learned how to implement authentication with devise, Raghu gave us an overview of how sign in/sign out generally works.

<em>Cookies</em>

Thus far we have treated server requests (GET, POST, UPDATE, DELETE) as all being equal in terms of their origin, making no distinction between them as far as the server is concerned. But this is not generally what we want; usually we want to distinguish them based on the user who makes the request. But in order to do this, we need some extra information that will distinguish between user requests, information that must come from the user (or, more accurately, the user’s browser). These identifying data, stored on a user’s browser instead of within a database, are known as <a title="HTTP Cookie" href="http://en.wikipedia.org/wiki/HTTP_cookie" target="_blank">cookies</a> (4kb of storage space in a browser that developers get to use).

Now, like many things, Rails dramatically simplifies the process of managing cookies. Essentially, we get a hash called 'cookies' (similar to the ‘params’ hash) that is predefined and allows us to add cookies to our users' browsers. If we put a cookies key-value pair (hash) on someone's browser, and if that hash subsequently comes back to the server, we can tailor our app to that specific user. This is how we can use cookies to implement user authentication in Rails.

<em>Using Devise</em>

I am not going to go into the details - step by step - of implementing devise. But in general terms, once we add the gem to our application, we can use it, first, to generate our Users table, and second, to implement a full suite of authentication actions and views. Once we have the power of devise in our app, the key thing we have to do ourselves is to customise our application based on who is signed in. And the golden gatekeeper tool that we will use to help us to do this work is a method called <em>current_user</em>. This is a helper method that devise defines for us that we can call from anywhere in our views and controller actions.

In addition to this helper method, what we will normally do is to write some conditional logic in our view templates to change what any particular user can or cannot see.

Another trick - for simplicity and security’s sake - is to make the landing page for our app also the sign up/sign in page, so that a user cannot even use the application if s/he is not signed in. Basically, we lock down the application until sign in. This is a pretty common way nowadays of doing things in web apps (see Instagram and Facebook, for instance) and it ensures that the rest of the application does not always need to be checking to see whether the user is present or not—the user will always be signed in.

We can lock down the application to non-users in this way, using devise, by calling the ‘before_action :authenticate_user!’ method in our ApplicationController.

Once we have devise set up in this way, we can go through and customise the standard view templates that devise creates for us automatically. There is some additional complexity around adding more columns to our Users table, beyond the default ones, but we can whitelist these extra  parameters in our ApplicationController as well.

Devise is clearly a very powerful gem, and we’ve only scratched the surface. But we now know enough to implement basic (but powerful!) authentication in our own Rails apps. In later lectures, we will dig into some of the more advanced security features that come with devise.

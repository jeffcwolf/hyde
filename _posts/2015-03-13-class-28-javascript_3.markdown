---
layout: post
title:  "Class 28: Mar. 13, 2015 [AJAX, jQuery UI]"
date:   2015-03-13 22:33:41
categories: starter league
---

Today we continued learning AJAX, 'ajaxifying' our primary CRUD actions in Rails. We saw, once again, how the Google Chrome browser has some amazing developer tools - for HTML, CSS and JavaScript - and we used them to debug our jQuery code and AJAX actions. To ajaxify the 'create', 'update', and 'edit' actions, the code gets a bit complicated, but they each have their own patterns, which we can learn. And there is a basic workflow for ensuring that we can write the correct jQuery code in our view templates:

<ul>
  <li>Identify what HTML element(s) we want to 'grab' using jQuery</li>
  <li>We can do this by using Google's 'Inspect Element' method in the browser</li>
  <li>If no specific ID or tag exists to allow us to select the element in question, we can add our own. It is, after all, our code. So we would then add the appropriate ID to the element, if none exists.</li>
  <li>Finally, we would write the jQuery code. Once we have the correct 'grab' statement, we find a workable method from the jQuery documentation (methods listed under Manipulation, Effects, and Traversal are quite common). There will often be more than one method that can do the job for us. Now, sometimes the code requires multiple lines and the use of variables for clarity, but once we understand the basics, this is not too onerous.</li>
</ul>

That is basically it for our exploration of AJAX. Raghu told us how we could, in the future, use AJAX to create single page apps (SPAs), basically turning a normal web application into a mobile one. But it does take a lot of work to keep the app properly ajaxified. He also showed us some of the shortcut variations on the 'render' method in Rails that will make writing our AJAX code more concise.

In the final part of class, which we will continue on Monday (our last week), we saw how we could use jQuery to add even more functionality to our apps. There is a whole world of power behind jQuery; there are tons of libraries built on top of it (including Bootstrap's JavaScript library).

One way of seeing this is by looking at the jQueryUI library, which we began to explore (although this no longer comes packaged into Rails, we can still use the jquery-ui-rails gem).

We saw how to drag and drop elements in a mock-up of a chess game, using jQuery UI. In doing so, Raghu highlighted the need to know the (document).ready handler to wrap our JavaScript code so that it runs only once our document is ready (ordinarily it runs sequentially and asynchronously but we often need it to run only after we've run the underlying HTML code so that we can use jQuery to grab a rendered object). In general, we'll always want to wrap our JS in the (document).ready handler (this can be done, for example, in the application.js file in Rails).

We'll continue our review of jQuery on Monday, our final week.

I was left wondering - and this is likely the historian in me - why JavaScript has become the language of the web. After all, Ruby seems so much more intuitive and clean, and it is a full-fledged object-oriented language. JavaScript is not quite like that, and yet it has become ubiquitous. The short answer is that JavaScript won the browser wars and Ruby only took off in the early 2000s with the creation of Rails, and the Web was already everywhere. So we must learn JavaScript if we're going to write applications for the web. Still, I'd be curious to learn more about just why JS came out on top.

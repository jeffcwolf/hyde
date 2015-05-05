---
layout: post
title:  "Class 27: Mar. 11, 2015 [JQuery &amp; AJAX in Rails]"
date:   2015-03-11 22:32:12
categories: starter league
---

Today we continued our exploration of JavaScript by moving forward with jQuery and AJAX, especially as they are implemented (or can be used) in a Rails app.

Recall that with JavaScript we still want to be able to send a call back to our database, updating or adding to its data. And AJAX is what will allow us to do this. It works in the background, sending ('whispering') an asynchronous request to our database.

But, before becoming familiar with AJAX, we spent a little more time working with jQuery, which is included with Rails by default. We examined the jQuery function ('$') and learned to read the jQuery API documentation to find the methods we want. A key point about using jQuery effectively is ensuring that we grasp the fundamentals of CSS selectors because the jQuery function essentially grabs elements from the DOM in the same way that CSS uses its selectors.

Once we practiced a bit with jQuery, we took a closer look at AJAX, which is what we really care about in our Rails apps because it helps us create smooth, in-place changes in our browser, without needing to refresh the page (though a silent request is made by AJAX to the back-end). AJAX is able to update both the DOM and the database, keeping them in sync - all without an explicit 'synchronous' route request.

Rails makes implementing AJAX fairly easy; it does not require too much extra work or demand that we learn a great number of new concepts that we haven't seen before. It feels pretty seamless, given what we already know. Basically, we follow the following steps:

Find the link or form that we want to transform into AJAX (Raghu calls this 'to ajaxify something') and add the :remote =&gt; true Rails helper method to it. This ensures that the request gets whispered to our database, 'ajaxifying' our back-end.

Next, we need to update the DOM in the browser. We do this through some modifications to our controllers and views. For instance, if we wish to ajaxify the Destroy action, we need first to tell Rails to support, or expect, the format to be JavaScript (rather than the usual HTML or JSON). Thus, we add 'format.js' to the respond_to code in the relevant action. Our server will now be able to support JavaScript requests.

Next, similar to our usual RCAV workflow, we have to add a template that matches the action. The difference here is that we add a .js.erb view template file - that is, a javascript.erb file that recognises both JS and Ruby.

Finally, in that file, we can write JavaScript in the form of jQuery, so that our views are in sync with our back-end. This is where we tell the browser how we want it to act, what kind of effects we want to implement using JS. And we use jQuery to do this. We can include Ruby in this file (as we would expect, being an .erb) in order to write dynamic javascript responses.

That's the basic workflow. Now, there are some variations to what we learned initially for our Golden 7 CRUD actions. We now need to implement these actions asynchronously and that requires a few more steps, learning a few helper methods, etc. We will focus on that next time.

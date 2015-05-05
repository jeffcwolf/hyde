---
layout: post
title:  "Class 22: Feb. 27, 2015 [Styling &amp; Workflow]"
date:   2015-02-27 23:31:53
categories: starter league
---

Today we focused on two things: (1) How to incorporate more professional styling into our scaffold-generated apps and (2) Continuing to work on process and workflow to get a functioning app up and running.

<i>Styling - Templates &amp; Sass</i>

Now that we have jettisoned our training wheels and no longer use the 'starter' generators (moving over to Rails' scaffold generator), how do we incorporate professional styling into our apps as we build them? We don't need to worry about top-notch, professional front-end design at the beginning; but it would be nice to have aesthetically-pleasing styling automatically incorporated into the boilerplate of any app we create. This just makes back-end creation more fun.

Well, we can actually create templates that the Rails scaffold generator will incorporate as it does its thing—templates for our view templates, if you like. Raghu has, over time, created a list of these that he uses as a foundation for all his apps, and he suggested that over time we can create our own.

In any case, the first step to incorporating styling will be to use some well-tested, first-party gems, including <a title="Font-Awesome-Sass" href="https://github.com/FortAwesome/font-awesome-sass" target="_blank">font-awesome-sass</a> and <a title="Bootstrap-Sass" href="https://github.com/twbs/bootstrap-sass" target="_blank">bootstrap-sass</a>. This will load all the capabilities of Font Awesome and Bootstrap directly into our app (without the need for a CDN, for instance). This is one of the first times, incidentally, that we have seen Sass (and its competitor Less). They are worlds unto themselves, but for us the important thing to know is that they are essentially pre-processor extensions to CSS (or in the words of Sass's marketing team: "Sass is the most mature, stable, and powerful professional grade CSS extension language in the world."). Although Bootstrap has adopted Less (instead of Sass, which Rails uses), there is an official Sass port of Bootstrap in the form of the 'bootstrap-sass' gem, which is why we use it.

Raghu showed us how to incorporate the power of both Bootstrap and Sass into our apps in the application stylesheet(s)—including a great amount of customisation of dozens and dozens of Sass variables—so that we have a great deal of styling power at our fingertips, from the beginning. It's clear that spending a little more time upfront can yield big dividends later.

<em>Workflow</em>

The rest of the class was devoted to building our app - Best of Everything - from scratch, using our new, more advanced workflow. After incorporating styling, we added the devise gem so that we can use its power for sign-in/sign-out. Then we used our recent knowledge of Rails scaffolding to generate the full MVC suite quickly and efficiently. We learned the 'references' command line parameter, which will make it easier to input our foreign keys in our scaffold commands. By using the simple_form gem, as well, we save some time later on building our forms. Once we generated our scaffolds, we included our associations and validations - the model logic. This then allowed us to create a more sophisticated seeds file, which gives us some flexibility later on, if we want to start over or share our app development with another developer. In fact, we used the .build method in our seeds file, which we hadn't used before.

After all this, we finished completing our UI and smoothed over some of our view templates and eliminated foreign keys. We made sure our devise authentication was properly configured as well, including hiding user ids and just making sign-in/sign-out work seamlessly. And that is pretty much about it for the boilerplate code.

Finally, we took a stab at implementing the functionality that we deemed essential to our app; the actions and abilities that make the app different from others and that fulfill our User stories.

Therefore, we now have a checklist for how to build an aesthetically-pleasing, back-end functional, professionally-written web application. Time to make progress on my own app, Solidify: after all, we only have 3 weeks left in our course!

Next week, we tackle JavaScript.

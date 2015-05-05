---
layout: post
title:  "Class 29: Mar. 16, 2015 [Nokogiri, Rake Tasks, Cron, SMS &amp; Mailers]"
date:   2015-03-16 22:24:59
categories: starter league
---

Today we focused on a variety of topics that we still wanted to learn, including how to scrape HTML periodically using a custom rake task and a cron job.

Scraping an HTML page is essential if the information we want is not provided in an API, though this is increasingly common. <a title="Nokogiri" href="http://www.nokogiri.org" target="_blank">Nokogiri</a> is a very powerful and easy to use gem that facilitates HTML/XML parsing. In conjunction with the<a title="Mechanize gem" href="http://docs.seattlerb.org/mechanize/" target="_blank"> mechanize</a> gem (which helps automate website interaction), we can use nokogiri to scrape almost anything we want.

In today's class, we built an app that monitors a webpage periodically and  then sends the user an SMS if something on the page of interest changes. In our case, we decided to monitor a musician's page (a mock-up of one at least) so that we would be updated if a new concert were added. When learning to use nokogiri, it's imperative that one knows one's CSS selectors (especially the pseudo-selectors), very much like our use of jQuery.

Once we mastered the basic scraping technique, which we can do in a simple Ruby file, we learned how to use <a title="Twilio" href="https://www.twilio.com" target="_blank">Twilio</a> to send text messages. We used their '<a title="Twilio-Ruby" href="https://github.com/twilio/twilio-ruby" target="_blank">twilio-ruby</a>' gem which wraps the functionality of their API into Ruby.

Once we saw how to do this we put our knowledge together - and the steps we wanted to perform in our app - into a custom <a title="Rake Tutorial" href="http://jasonseifer.com/2010/04/06/rake-tutorial" target="_blank">rake task</a> which Rails knows how to generate for us. Sometimes we might want to use the .find_each method to manage the number of records we look up for our rake task (we don't need to look up millions of rows every time it runs, for instance). In any case, we store custom rake tasks in the lib/tasks folder and we can organise them into their own <a title="Organizing using Namespaces" href="http://blog.makandra.com/2014/12/organizing-large-rails-projects-with-namespaces/" target="_blank">namespaces</a> for convenience. Ultimately, it makes sense to use a custom rake task when you have some arbitrary Ruby code that you wish to run yourself outside the normal RCAV. In practice, a lot of maintenance tasks (pruning one's database, periodic API querying or HTML scraping) work well as custom rake tasks.

The final piece of the puzzle for our app was to learn how to automate or schedule tasks that run in the background. 99% of the time, according to Raghu, we will want Heroku to handle this for us (using Heroku scheduler). And this is easy to implement though it does cost something, given the extra server usage it requires. Of course, we can also run <a title="Cron jobs" href="http://www.unixgeeks.org/security/newbie/unix/cron-1.html" target="_blank">cron jobs</a> locally (e.g. using the '<a title="Whenever Gem" href="https://github.com/javan/whenever" target="_blank">whenever</a>' gem) but this may be more hassle than it is worth.

At the end of class, as a complement to knowing how to send SMS messages, we learned how to use Rails' <a title="Action Mailer Basics" href="http://guides.rubyonrails.org/action_mailer_basics.html" target="_blank">built-in Mailers</a> class to set up and send emails. One still needs a third-party to send the emails themselves (<a title="Mailgun" href="http://www.mailgun.com" target="_blank">Mailgun</a> and <a title="Sendgrid" href="https://sendgrid.com" target="_blank">Sendgrid</a> are options) but the basic functionality is already in Rails, and we had a quick tour of it.

It's remarkable that their are only two classes left!

---
layout: post
title:  "Class 30: Mar. 18, 2015 [Nokogiri + Mechanize, OmniAuth]"
date:   2015-03-18 22:36:42
categories: starter league
---

Today was another class of helpful odds and ends. It's really empowering to see how some basic tools and simple scripts can still provide a lot of power. We continued our exploration of Nokogiri and Mechanize, using these gems to scrape a series of webpages for specific data, then saving that data in our Rails app. The potential uses of this are very large indeed.

Our basic process was to first write a simple Ruby script to capture some of the data we want from a single URL. Using Mechanize (which is built on top of Nokogiri), we were able to isolate and print a variety of different kinds of data from a webpage on the NPR podcast website. Once we figured out how to do this, we created a custom rake task to hold our Ruby script. We enhanced it by saving the data we scraped into a Rails generated database. Conceptually there was nothing new here, but it was helpful to see how to do it in action, and it certainly gave me a lot of ideas.

We also talked about how to use the popular <a title="OmniAuth" href="https://github.com/intridea/omniauth" target="_blank">OmniAuth gem</a> to setup 'multi-provider' authentication (e.g. using Facebook or Twitter) for our web applications.

I can't believe there is only one class left. Everyone is busily working away on their web apps as we speak.

---
layout: post
title:      "'AJAX of all Trades': My Javascript Portfolio Project"
date:       2018-04-20 00:06:56 +0000
permalink:  ajax_of_all_trades_my_javascript_portfolio_project
---


This project was an interesting mix of fun and frustrating. I thought it was a great way to practice all the functionality that Javascript can offer by building on top of our previous project. When working on the Rails project, there were a lot of things I wanted to build or do but felt too limited by Ruby and the resources I had at the time. However, with what I have learned so far with Javascript, I was able to make many of those ideas a reality. Having the ability to post comments on the recipes and have them show up on the page without a page reload was a really cool thing to see in practice.

The thing I'm most proud of about my project is the search capabilities I built into the recipe/index page. With the use of jquery, users can search for recipes based on title and/or certain categories, and can even sort the order of the recipes based on certain parameters. I decided to accomplish this by creating a Search controller that handled a json presentation, with functionality built in to decide which recipes were shown on that json page based upon the search parameters that are entered.

I will say however, the one aspect that was frustrating about this project was the amalgamation of Javascript with Ruby. More than once I had to remind myself that my Javascript functions had completely different logic from my Ruby code, and therefore couldn't as easily access certain attributes or functions. At times it felt like I was having to re-invent the wheel just to get some of the Javascript to do what I had already created in Ruby. That being said, it was still a great learning experience in dealing with both, and I enjoyed getting to update a previous project with what I have learned so far!

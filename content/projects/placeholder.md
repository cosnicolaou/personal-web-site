---
title: "You're looking at it!"
date: 2018-08-16T12:47:54-07:00
draft: false
---

So obviously the first project that I'm going to describe is building this
site and [cloudeng.io](https://cloudeng.io). I started down the path of using
wix in the spring of this year but got frustrated with the editing and preview
process and lost interest (I should go back and cancel my subscription shortly!)
before I could finish the site! If I found wix frustrating then I didn't hold
out too much hope for wordpress or any other similar solution. As a developer
I naturally gravitated toward more 'programmer' oriented solutions. I was
coincidentally introduced to netlify and decided to give that service a try
instead, but then I needed to find a site builder app...

I tried using netlify's CMS but the default site was overkill for my needs so
I decided to use [hugo](https://gohugo.io) directly. I chose hugo primarily
because it's implemented in go, which is my preferred programming language, and
consequently I already understood the templating language it used and could
pretty much intuit how it works and more importantly its quirks.

Even though I didn't pay too much attention to the documentation I was able
to get a one page site up and running very quickly and being able to preview
locally (just run hugo serve against your content tree) made debugging easy.
By far the most time was spent choosing a theme and a little less on
customising it. Most of the customisation time was really just learning how
hugo organised its content and re-learning html/css etc.

Then I had to actually write content for the sites, which also took a while.

There were a number of things that caught me out along the way that
may save someone else some time:

- any typo in the content front-matter (e.g. leaving off the lead ---) will
generate confusing web pages. However, the hugo log messages generally give
a good description of the error, so remember to read what hugo's telling you!
- netlify needs themes to be added as git modules
- it's easy to forget to git add files so remember to make sure that all of your
content makes it to github


Overall, the process is pretty straightforward and after a couple days worth
of work I have two sites running that are easy to update and served via
a CDN!


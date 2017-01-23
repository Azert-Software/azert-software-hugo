+++
author = "Mark Smith"
date = "2017-01-23T13:49:26+00:00"
sourceUrl = "www.nimicrolights.co.uk"
tags = ["project", "website"]
title = "NiMicrolights Website"

+++
![](/uploads/2017/01/23/Homepage.PNG)

[www.nimicrolights.co.uk](www.nimicrolights.co.uk)

I have recently begun training towards achieving my NPPL microlight licence, flying has always been a real love of mine and between flying r/c planes and the odd trial lesson the desire to get a licence only grew! Well, I decided to go for it and the most affordable route for me was Microlights, plus, they give a really raw flying experience, it's great!

Anyway, the school I am attending had a very old, 17 years I think, website, that was just really bothering me, so I decided to spend a week and build them something much better.

## Technology Used

For this I build the site using a static site generator [Hugo](wwww.gohugo.io). This allows you to build a theme, templates etc and rather than host a server & database, the generator builds your site once and outputs all html, css & js. This can then be hosted for free on [Github Pages](https://pages.github.com/). As there is no server side processing to render pages, the site ends up being extremely fast and lightweight.

The site itself uses [Bootstrap](http://getbootstrap.com/) for it's excellent responsive grid and to make future theming really easy, in fact, it's so easy to theme, you can just open the CMSand paste a new link to a bootstrap theme to use, hey presto, new skin!

Aside from that, a little of Javascript was used to power the live weather widget and that was it!

The CMS that the school will use to edit content is [Forestry.io](https://forestry.io). This is designed specifically for static sites built using Hugo & GitHub pages. <span style="letter-spacing: 0.01em;">It also supports Jekyll and bit bucket. Now the school can login and make site edits, upload images etc whenever they wish, without having to get their old hosting provider to do it for them and charge for it to boot. (Azert is also built on the same stack).</span>

## The Site

### Homepage

The home page is shown at the top of this page, that is the main carousel and banner for the site. The user can easily change the images displayed here.

#### Panels

![](/uploads/2017/01/23/Home-panels.PNG)

On the homescreen these panels show key information a new or returning student may need with lesson booking front and centre. The live weather widget can be seen on the right, this pulls live weather from the nearest METAR weather station to the airport, very useful for students wanting to check on conditions before heading up. If conditions are not favourable it will display an alert advising them to contact the instructor.

#### Testimonials

![](/uploads/2017/01/23/Testimonials.PNG)

Another thing I thought missing from the original site was student feedback. Here the site user can add new testimonials from students using the sites CMS, just like they would any other content. This also helps prospective students to gain a bit of trust that the tuition they are getting is top notch.

## News

![](/uploads/2017/01/23/News.PNG)

The old site was a pure static html site, no CMS was involved and therefor it was very hard to get content changed, one thing the school wanted was to be able to post when a student goes solo for the first time, or passes their exams. The news section allows them to do this, they can set a featured image as well as add whatever images, videos etc to the content page itself. It also allows users to share content, subscribe with an RSS reader as well as leave comments.

## Gallery

![](/uploads/2017/01/23/Gallery-1.PNG)

Another new feature is the gallery, again, for a flying school, not having somewhere they could showcase pictures of the aircraft and student was sorely missed on the old site. This is fully responsive and works brilliantly on phones as well as the desktop.

## Mobiles

![](/uploads/2017/01/23/Mobile.PNG)

Of course, using bootstrap means the site works perfectly on mobiles, but see for yourself, visit [NiMicrolights](www.nimicrolights.co.uk).

## Old Site

![](/uploads/2017/01/23/Old-site.PNG)

The old site was very much 'of its time' and just not fit for purpose, I'm sure you will agree the new site is a breath of fresh air and will hopefully encourage more students towards NiMicrolights.

## My Work

As well as the website I also helped setup the hosting provider to ensure A records and CNames were properly setup. i Also provided support to train the school up on the website.

If you like what you see and would like me to work on a site, just get in contact using the contact buttons on the left hand bar.
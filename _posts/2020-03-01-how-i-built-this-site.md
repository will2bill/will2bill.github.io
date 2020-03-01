---
layout: post
title: How I Built this Site
author: William Moore
excerpt_separator: <!--more-->
categories: [development]
---

Creating this website was something I have been meaning to do for....well, a very long time. Probably since I built it
for while hunting for jobs three and a half years ago. It's the sort of thing that I knew I needed to do, but which
would take enough time that I never really found the time.

<!--more-->

Until I found myself hunt for jobs again! 

##### What I wanted to achieve
For...oh, 4 years now, I have been paying about $10 a month for something that gets shockingly little use. I was
probably the only visitor in all that time, and even if I wasn't, I knew there were better ways to host my site that
wouldn't cost me as much. 

So cutting costs was a big part of this.

The other part was...well, look at it:

![Screenshot of my old site]({{ my_page.url | relative_url }}/assets/images/old-site-screenshot.png "Screenshot of a very orange website")

I have a certain fondness for it, but there's no denying that that design was not good. Too orange, too busy, _too much_.
Fun fact most of the images for the different sections were animated. It was all a bit intense.

So I wanted something free/cheaper, and something simpler, cleaner. With a bonus of potentially something more useful
(aka this blog).

So I settled on GitHub Pages

##### GitHub Pages
GitHub pages was stumbled on more or less accidentally. I had heard of pages but not given it too much thought.
I was initially thinking of creating a site on s3 in AWS. Mostly because I have come to know AWS pretty well, I
understand how it works, and it would allow me to do infrastructure as code. 

S3 probably would have been free (not a lot of access going through it), but I liked the simplicity of GitHub Pages, 
especially once I found a useful repo to base mine on. I'll probably still play around in AWS for bigger, non static 
projects when I get going on those, but for now GitHub suited me well.

I found and forked this project: [bootstrap-4-github-pages](https://github.com/nicolas-van/bootstrap-4-github-pages)
which allowed me to get something up an running pretty well instantly. From there it was a lot of design and fiddling
to get the right look ([pulse](https://bootswatch.com/pulse/)) and layout. And also work out actually how it all fit
together.

##### Trials and Tribulations
Most of this process was pretty smooth, a little bit of configuration here and there, but turns out a process designed 
to be easy is, well, easy. There were a few blips though:

<b>Getting it in Docker</b>: I had vaguely assumed that I would be able to look at my GitHub Pages on a branch through GitHub 
magic, but turns out nah. So I needed to get this site working via docker if I wanted the development process
to be anything other than glacial. Again my solution was mostly just looking around until I found someone who had done
the work for me. [docker-github-pages](https://github.com/Starefossen/docker-github-pages) provided the answer, 
they had effectively done all the work, just needed to fiddle with the configuration on the site, and bang, working.
Having it in Docker really has proved invaluable for testing it all out. Never looking back.

<b>I have no idea how to design things</b>: Yeah this problem was a big one. The project could have been done a lot 
quicker if I had a better idea of how I wanted the site to look and, more importantly, what information I wanted on it.
That sort of design has never really been my strong suit, and all I really had to go on was that I didn't like the 
existing set up. I ended up borrowing heavily from the personal site of one of my friends [Adam O'Grady](https://adamogrady.id.au/).
Adam's a genius, and I loved the simplicity of his site. 

I took that blueprint and got...idk, somewhere close to it? It's still a bit louder, and more colourful (I would be sad
if I didn't have a lot of colour), but it's so very much cleaner than it used to be. It's only really got three pages,
Home, Blog, and 'Creative' (which is basically just a list of where to find me on the internet). Much nicer. 

It might be exposing more of me than I'd necessarily want potential employers to see? But it's also a portfolio for 
the rest of the world and I figure I need a centralised home for my links.

There's room for more pages in the future, like a social media page listing out the (many, many) social sites I'm on,
but I think it's plenty for now. Plus, it's better to work in stages.

<b>Oh god, oh god, I've broken everything</b>: The only major problem I encountered was naturally due to networking, 
my one weakness. I knew I wanted to point the existing [will2bill.com](will2bill.com) domain at my github pages, but I 
was unsure what would happen to my existing site, since there were parts of that I wanted to keep if I could. While
clicking around on GoDaddy (my current provider) I clicked on a button that would allow me to change the base domain
of my existing site to one of the others I owned. I clicked on one, thinking there would be more checks on the way,
but then decided that making that change now would be too much work.

GoDaddy decided otherwise. I clicked cancel but I guess something had already been set because suddenly [will2bill.com](will2bill.com)
was down. I eventually found it running on my other domain, though since a lot of the paths on that site were hardcoded,
it was virtually unusable. And in fact the specific thing I was wanting to save was unreachable.

Yay.

A bit more stress than I needed. I went into the dns settings and made the changes that would point [will2bill.com](will2bill.com)
to GitHub, figuring at least I could fix that part, and then deal with the broken old site later. Unfortunately what I
didn't appreciate was that this process could take a while. And that adding the CNAME file on github would in fact
immediately redirect the Github page to [will2bill.com](will2bill.com). So not only was my webpage not looking anywhere
useful, but I could no longer see the GitHub site.

I maaay have gotten a little panicked, and I spent ages pouring over sites trying to get any indication if I had set 
everything up correctly. I was fine to wait 24 Hours, people would be unlikely to visit my site on the weekend, but 
I didn't actually know that I had configured the dns correctly. And without that information how could I be sure the
website would work tomorrow.

The good ending is that it just started working after about 3 hours. Probably should have been calmer, but what can you
do. I also managed to get (most) of the old site back by manually updating the references to [will2bill.com](will2bill.com).

##### What's Next?
I'm essentially done, once I merge this branch creating the Blog. I'm hoping to keep tinkering though. I want to keep 
this website more alive than the last one. Partially that will be through updating the blog, but there's certainly room
to fiddle with the site itself and maybe add pages as and when I see fit. 

I've also got some projects I would like to start working on:
 - A web based photoframe: Something I can use to place a little photoframe on my desktop at work that features my family
 and friends (and cats), cycling randomly through images. I've looked around and not found much and I think this could 
 be really useful. Especially as a website that can be re-sized more freely than a desktop application. 
 - A clicker game. This is something I've had an idea for for ages and just never made the time to actually implement.
 Part of the reason is that I am not super good at web design or programming,  but I'd like to learn and I'd love to
 make this idea a reality.
 - More writing! Okay I sort of covered this in the intro blog post, but I want to write more and post here fairly 
 frequently. I don't have a specific thing I'm working on as yet, but I do want to make a habit of it.
 
 This was longer than I planned :p That's kind of my style. As a reward for sticking it out, here's a picture of my cats:
 
 ![Bondy and Kita]({{ my_page.url | relative_url }}/assets/images/bondy-and-kita.jpg "two black and white cats")

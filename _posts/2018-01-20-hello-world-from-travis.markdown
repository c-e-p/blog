---
layout: post
title:  "Hello World, From Travis"
date:   2018-01-20 13:11:26 -0500
categories: continuous-integration
---

Hello world, from Travis.

^ Whew, that feels better. I spent so long with this pseudo-"blog" in its infancy that I had to upgrade a bunch of gems just to get Travis CI working. It's funny to pick up old projects again and realize you've been procrastinating on a relatively simple task for, uh, 1.5 years. Hey, I was busyyyy.

Anyway, continuous integration is an exciting thing, but I don't know that this counts since I'm not running any tests or anything; I am simply too lazy to remember to log into my server and scp things over manually. Lazy developers are the best kind, right?

Speaking of continuous integration, I've spoken to multiple developers lately who are marketing themselves as "full stack", but whose server experience is primarily Heroku or another cloud-based deployment thingy. Guys! I know you're always supposed to sell yourself as hard as possible to a potential employer, but Heroku is not and never will be "full stack". How is that even (apparently) up for debate?!

In the interest of full transparancy, I should admit that I'm extraordinarily weak on the server side. Kate, my fiancee, is a whiz with pretty much everything server related. I have googled "chown a directory" or "make a shell script executable" more times than I care to admit. ('But Elena, those are both incredible simple commands!' I KNOW.)

We use Linode to host all our stuff. There's a lot of really good documentation out there related to setting up a LAMP stack, a static blog like this site, hooking up your server with CI, and so on; I recommend, traitorously, Digital Ocean's documentation for things like [Deploying a Flask app](https://digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps). Before moving my stuff to Linode, I spent a good 7 years on Digitalhost, inexplicably convinced that it was tooooo haaaaard to host my own stuff. Not true, it turns out. 

I have no conclusion here. Travis good; Heroku bad (if you want to claim you can administer a server)(it's fine for other stuff)(I am not the arbiter of who is full stack! But still!).
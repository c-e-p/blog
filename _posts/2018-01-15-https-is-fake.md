---
layout: post
title:  "HTTPS is Fake, and Other Tales"
date:   2018-01-15 12:00:00 -0500
categories: infosec
---

HTTPS: it's fake.

Oh, the technology is real enough. Modern encryption is a beautiful thing, and things like HTTPS Everywhere and Let's Encrypt have made HTTPS that rare crypto unicorn, a privacy measure that is actually pretty easy to implement and user friendly on both the admin and client side. Everyone's happy! Except, whoops, browser cert standards haven't really evolved; "is my data encrypted" is still tightly coupled with "do I know who I'm sending my data to". And that, as they say in the biz, is a problem.

I'm not the first person to point this out. It's a [well known issue](https://nakedsecurity.sophos.com/2017/03/30/lets-encrypt-issues-certs-to-paypal-phishing-sites-how-to-protect-yourself/). Even my beautiful fiance&eacute;'s website uses Let's Encrypt. But, while it might not be a unique observation, I think it bears repeating by anyone who's willing to say it, to anyone who will listen: we've backed ourselves into a dangerous corner, and vulnerable consumers are likely to pay the price.

Tightly coupling encryption and identity verification makes sense when 1. encryption is relatively rare, and 2. identity verification is thorough and accurate. But 1. is being actively changed, and as a direct consequence of that change, 2. totally breaks down. Web standards being enforced by a weird combination of the honors system and a lot of governing boards is already kind of bonkers, when you think about how much actually happens on the internet in our painfully modern world. Beyond that, things get weirder. As far as I can tell, the modern process for getting a TRUSTED CERT, which your brower will give the total green-lock thumbs-up to, goes:

* Sign up and pay a tiny amount of money
* A computer goes, "sure, paypal.com.badsite.biz, this seems legit"
* Phish! Phish! Phish!

This is not a sustainable system.

What drives me crazy about it is that the "enforcement", which in practice looks more like lying to consumers, is entirely within the control of browser makers. Chrome is rapidly careening towards Windows-style market domination, so let's pretend they're the only browser out there for the purpose of this example. If I issue a cert to myself and set it up on my server - properly, so that traffic is encrypted, which for a private file server is *all I care about* - Chrome will scream at me every time I visit that legitimately encrypted site. It will scream at me louder than the time I visited a local diner's website and clicked on a clearly hacked Wordpress link just to see what would happen (MY COMPUTER IS INFECTED AND ONLY A $200 CALL WITH TOTALLY LEGITIMATE MICROSOFT SUPPORT WILL SAVE ME OH NO). But imagine now that I've got a cert from a trusted authority, which I can now do for pennies on the dollars I'll be scamming. Chrome will give my victims fingerguns of approval as I gently guide them to give me, gmail.com.pwned.net, their credentials.

But Chrome knows the difference between self-issued certs, or certs issued by an authority that does not do any kind of identity verification or scam check, and legitimate certs that cost actual money and are definitely not being installed by a scammer. Chrome could, say, create an intermediary warning screen saying "your traffic is encrypted, but this cert is registered by Badco Anonymous, do you want to continue"? And then save that preference, so that the next time I visit my file-sharing app, I don't get screamed at that I'm trying to steal my own login credentials.

I assume the reason this hasn't happened is because a lot of smaller companies don't want their clients seeing even a nice warning, but they also maybe can't pay for certs that cost several grand. That's legit and I get it. I'm sure there are also market incentives that I know nothing about. So maybe people should be pushing for decoupling "encryption is present" from "I am who I say I am", or maybe we should all just realize the internet in general and modern browsers specifically were a mistake, and go home to our dogs and loved ones: who knows. But as cheap-cert-powered phishing activity continues to rise, I strongly suspect we'll see still more centralization of the internet, under the Amazon/Goog/Facebook umbrella of monopolies. To borrow a quote from The Incredibles, if everyone is trusted, then no one is.

There's still time to stop this. Maybe. Probably not, but maybe! We have the tools and the power to differentiate between encrypted traffic, which is objective and easy to detect, and trusted sources, which is a fuzzy concept that can be difficult to enforce and also has *absolutely nothing to do with the privacy of your damn web traffic*. 
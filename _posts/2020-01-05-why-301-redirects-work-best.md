---
layout: post
title: Why 301 Redirects Work Best
description: Server-side redirects, JavaScript redirects, meta refreshes, and canonical link elements are all about trust.
date: 2020-01-05
---

Server-side redirects, JavaScript redirects, meta refreshes, and canonical link elements are all about trust. Google and Bing are seeking to understand content, and they need to know that content's location to index and rank it.

The simplest case is a single piece of content that has only ever existed on one web page, a singular URL that is easy to rely on as it has no other variations or duplicate instances. In this case, indexing and ranking only needs to evaluate that singular URL.

However, content tends to move, and it moves a lot. We redesign websites, change information architecture, refine categorization, and migrate to new domains (sometimes all at the same time). When any or all of those cases occur, URLs change, we can let all the old links break, or determine how to forward users (and search engines) to the new location of each individual piece of content.

## Redirects Work Like the Postal Service

One of my colleagues used to say redirects work like the post office. Your mailing address changes when you buy a new home or move into a new apartment, so you need to update all the references to your old address and switch them to the new address. That can entail sending a "We've Moved" email or postcard, texting or calling some relatives, and definitely updating a lot of online account information for your bank, employer, and other important places.

The most trustworthy way to indicate you moved is to tell all of those people of your new address, so they can update their address book or contacts list with your new mailing address. On the Internet, that's the equivalent of getting all the websites that link to you to update their historical links (and of course changing all the links and references you have on your own websites). This change requires no redirect since all the references have been updated, and this is the clearest, most authoritative signal to users and search engines that they can be confident about new address.

Sometimes an important contact slips through the tracks, and still sends you an important letter to your old home and mailing address. To address this case, you need to change your address with the Postal Service, and this is the equivalent of setting up a redirect for a website. It's not as good as getting the mail directly, and sometimes letters get lost or delayed in the mail, but it usually works and you eventually get the mail at your new address. Redirects are especially important for websites since we don't have an equivalent of the postal service identifying undeliverable mail or returning it to the sender.

## Choose the Most Authoritative Redirect

Redirects come in a [variety of shapes and sizes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections) including server-side redirects (301s, 302s, etc.),client-size redirects (JavaScript redirects, meta refreshes, etc.), and you could even consider a canonical link element a sudo-type of redirect.

In the SEO community, we have been somewhat obsessed with 301 redirects. The HTTP status code 301 means "Moved Permanently" and is nearly always the preferred option to indicate a URL and its content has in fact been permanently moved from one place to another. The historical theory was that 301 redirects pass the most authority (link juice, PageRank, or the new equivalent), which helps the new page rank better.

## Redirects Help with Canonicalization

In my experience working at agencies and consulting with clients back in the early 2010s, converting redirects from 302s into 301s, or replacing meta refreshes and JavaScript redirects with server-side 301 redirects almost always tended to correlate with increased rankings and more traffic. SEO was in many ways much easier back then when "fixing" redirects could be an entire strategy and have a significant ROI. What I didn't understand at the time is that the redirect type didn't really matter. Instead, it was how search engines evaluate canonicals.

Matt Cutts [discussed this with Eric Enge back in 2007](https://blogs.perficientdigital.com/2007/10/08/eric-enge-interviews-googles-matt-cutts/), but we never really got to the root of the issue at the time. More recently, Barry Schwartz created a [helpful compilation of tweets from John Mueller](https://www.seroundtable.com/google-meta-refresh-redirects-work-25335.html) that indicate a meta refresh should work just fine, then started to get into canonicalization, but it still didn't click for me.

Then yesterday I was forced to fully wrap my mind around meta refreshes. I just re-launched this site with GitHub Pages, which uses a static site generator called Jekyll to publish content. With this site configuration, I have no control over server-side redirects and my best option seemed to be a Jekyll plugin that uses 0-second meta refreshes to signal content has moved.

I was still skeptical about meta refreshes due all my past experience, so I reached out to John Mueller, and was fortunate enough to get a clarifying response:

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en" data-theme="light"><p lang="en" dir="ltr">If a URL ends up as the canonical, it&#39;s treated as the canonical, so that would probably work out. That said, the harder you make it for us to figure out, the less likely we&#39;ll do what you&#39;d prefer us to do :-)</p>&mdash; 🍌 John 🍌 (@JohnMu) <a href="https://twitter.com/JohnMu/status/1213743326295445504?ref_src=twsrc%5Etfw">January 5, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

That simple message really says it all. It doesn't matter if you use a 301, 302, JavaScript redirect, meta refresh, etc. Google is just trying to figure out which URL is the canonical.

My theory is that Google will have a harder time figuring out the canonical via a meta refresh as opposed to a 301 redirect, so my site may still have some older pages indexed for a little while. I'll keep an eye on it via Google Search Console and make sure all the content gets transitioned over. I still would prefer to setup 301 redirects, but now I have a new experiment to watch for meta refreshes, and I think I also understand just a little bit more about how search engines truly work.
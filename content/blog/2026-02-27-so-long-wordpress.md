---
title: "So long, WordPress!"
date: 2026-02-27
categories: 
  - "technology"
tags: 
  - "wordpress"
  - "11ty"
  - "webDev"
  - "aws"
  - "microsoft"
  - "githubPages"
description: "I’ve moved my last site off WordPress, and also off AWS! I'm using 11ty, which is great! Also using Pagefind for search, and authoring blog posts using Obsidian."
---

tl;dr: I’ve moved my last site off WordPress, and also off AWS! Yay! I'm using [11ty](https://www.11ty.dev/)! 11ty is great! Yay! Also using [Pagefind](https://pagefind.app/) for search, and authoring blog posts using [Obsidian](https://obsidian.md/).

## Ancient History

I've had a version of this web site since 1994, at which point, it was just some hand-written html pages hanging off `blues.epas.utoronto.ca\~jankowsk`. That site ran on an SGI Indigo, so IRIX was the first \*nix I got to know. For a while, the main page was called “Chester's emusic page,” and I thought about purchasing the domain `emusic.com`, which was available at the time–that would have been smart! Interestingly, a friend of mine from undergrad days later went on to be the CEO of `emusic.com` (“Hi, Chris!”). 

After I finished my doctorate in 1997, we moved to nyc and I had to find a new service provider. Those were the days of little mom & pop ISPs, and I went with one called OnePine. Around 2002, I had a Linux server at home and started self-hosting. It was still a static site. In the fall of 2004, I started this blog, running on–of all things!–slashcode, the server for [slashdot](https://slashdot.org/). (Which, by the way, kudos to them for having a web site that still looks the same thirty years later!) 

The announcement for running slash became this site’s [first blog post](/blog/welcome-to-the-new-site/). Things chugged along for quite some time, but slash was kind of a pain to admin. So, like pretty much everyone, at the end of 2006, I migrated the site to WordPress, as announced here: [What's up with the blog, anyway?](/blog/whats-up-with-the-blog-anyway/). At that point, there was no auto-importer, so I had to dump all the slashcode posts from mysql and create new posts in WordPress. Fun!

## The AWS era

At some point in the teens, everything had to run on AWS, so I migrated everything over there. By this point, I had a few sites, including cyberkrunk, my home site, Nora’s home site, and, later, culturednyc. AWS was a good skill to have for work, and I got certified in it. All fine. The ec2 instances would freeze fairly often, so everything took a fair bit of hand-holding. When everything just *had* to run on Docker, I ran everything on Docker. Again, fine, but not really worth the hassle for this use-case. After a while, I went back to just using LAMP stacks.

## SSGs, or “Falling in love with the web again”







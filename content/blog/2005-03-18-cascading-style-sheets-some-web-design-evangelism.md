---
title: "Cascading Style Sheets: some web design evangelism"
date: 2005-03-18
categories:
  - technology
tags:
  - web
---

From the "It's-worth-the-drive-to-Acton" department:

It's been a long while since I've had religion about web design. But the project I'm undergoing to revamp the [cyberkrunk](http://www.cyberkrunk.com) main web site has made me see the light. For several years, my main web site had languished in a cypherpunk-esque anti design. The idea was simple: no graphics, just ASCII and a table-based layout. On the plus side, it was blazingly fast to load.

But it was perhaps just a little too minimalist. The design wasn't just an expression of an aesthetic credo, it was also a reaction against horrible late-90's web design. Remember all those pages crowded with dancing babies and animated GIFs? (This kind of design was parodied brilliantly by The Simpsons in the episode "The Computer Wore Menace Shoes.") To be honest, though, I may have stuck with the simple design for so long because I didn't want to sort through all the competing technologies for creating more advanced HTML. JSP, ASP, PHP, CSS... WTF?

I finally bit the bullet and spent a couple of hours learning about Cascading Style Sheets, and I became a convert. The concept behind CSS is brilliantly simple, and incredibly powerful: the complete separation of formatting and content. Essentially, you strip out all formatting from your HTML files, and instead _classify_ your content into, for example, headings, paragraphs, block quotes, etc. You then create the formatting for all of these different classes of content within a single style sheet. This is amazing because not only does it allow you to create a uniform style, but it also allows you to completely revamp that style for all of your pages with a simple edit of the style sheet. _Zap!_

I used to think that CSS had to do mostly with things like font selection, but it's much more robust than that. One of the big challenges in traditional HTML was creating interesting page layouts. This lead people to use either frames (bleech!) or tables (double bleech!). CSS, however, offers a full set of tools to divide the screen into sections to create columns or whatever the heart desires, and with full control over colors and backgrounds.

The best part of all this is how easy and intuitive it is to learn. Spend an hour or two at one of the many tutorial web sites and you will change the way you do web design forever. If you're not convinced yet, then a trip to the [CSS Zen Garden](http://www.csszengarden.com/) will do the trick. Definitely start there.

Next stop, PHP.

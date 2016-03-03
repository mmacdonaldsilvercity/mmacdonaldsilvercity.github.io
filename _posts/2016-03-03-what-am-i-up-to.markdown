---
published: true
title: What am I up to?
layout: post
---
I've been spending some time on a project that I had originally started over a year ago;  a table-top role-playing game character monitor.

The idea is that table-top gaming is... well, table-top gaming.  It isn't a video game, not a computer game, it has nothing to do with electronics.  That is very cool -- getting people to interact face to face in a social setting.  And I don't intend to muck with that aspect of the experience.

However, there is a lot of record keeping and paperwork.  I watched my son cart handfuls of character sheets around and realized that hey, computers do good record keeping.  I could do that... And as soon as I started, I realized that would be REALLY neat would be to print out the character data in the exact format of published character sheets.

I started the project, originally trying to build a duplicate of the character sheets at hand using HTML.  Spent a couple weeks trying to rebuild the forms into HTML, and finally got frustrated.  I moved over to using the published PDF forms, and had just gotten started on using some libraries to interact with PDF forms when I took a break from the project..  

Starting back up lately, I ran into difficulties with the PDF viewers available on linux, and then some more issues with the widgets built into the forms.  About the same time I was hacking away at those, I was asked if I could incorporate a character generation routine.  I thought that would be easy -- why, there must be dozens already out there, right? ... Wrong.  

Dungeons and Dragons anyway has taken a for-profit stance on use of their proprietary gaming system.  I can't fault them for that at all, but it did start me thinking about all the trouble I was going to on a programmatic PDF form interaction.  I went back to an HTML based print form, without any attempt to mimic the original character sheets, except in the data content. 

Much easier, and I am close to the point of putting the result up on a website.

Python/Django, by the way, and using Bluefish as the editor.  Much evolution to go on there, de-hackifying code, correcting some not-best-practices shortcuts, documenting, and upgrading to Python 3.  ... All in a day's work, right?
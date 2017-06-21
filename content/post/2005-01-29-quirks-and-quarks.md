---
title: Quirks and Quarks
author: Matthew Routley
date: '2005-01-29'
slug: quirks-and-quarks
categories:
  - code
tags: []
---

<a href="http://www.cbc.ca/quirks/">Quirks &amp; Quarks</a> is the <a href="http://www.cbc.ca">CBC</a>'s excellent science program. I usually download the mp3 archives of the show on the weekends and listen while I walk Ceiligh.

Of course, loading up the <a href="http://www.cbc.ca/quirks/">Quirks &amp; Quarks</a> webpage, finding the archives, downloading the mp3s, and adding them to <a href="http://www.apple.com/itunes/">iTunes</a> takes at least a few minutes. Computers are much better and handling such tedium.

Inspired by the success (for me) of the <a href="http://matt.routleynet.org/post/50696956/astronomy-pictures-on-the-desktop">apod script</a>, <a href="http://s3.amazonaws.com/mroutley_public/quirks.pl">quirks.pl</a> is a <a href="http://www.perl.com">perl</a> script that downloads the current <a href="http://www.cbc.ca/quirks/">Quirks &amp; Quarks</a> episode to the Desktop. <a href="http://s3.amazonaws.com/mroutley_public/runQuirks.scpt">runQuirks.scpt</a> is an <a href="http://www.apple.com/applescript">applescript</a> that further simplifies the process by adding the downloads to <a href="http://www.apple.com/itunes/">iTunes</a> and trashing the redundant downloads. I&#8217;ve set <a href="http://www.apple.com/ical/">iCal</a> to invoke <a href="http://s3.amazonaws.com/mroutley_public/runQuirks.scpt">runQuirks.scpt</a> in the middle of the night, so now <a href="http://www.cbc.ca/quirks/">Quirks &amp; Quarks</a> is on my <a href="http://www.apple.com/ipod/">iPod</a> and ready to go Sunday morning.

Note that <a href="http://s3.amazonaws.com/mroutley_public/runQuirks.scpt">runQuirks.scpt</a> expects <a href="http://s3.amazonaws.com/mroutley_public/quirks.pl">quirks.pl</a> to be in &#8220;~/Library/Scripts/quirks/&#8221;.
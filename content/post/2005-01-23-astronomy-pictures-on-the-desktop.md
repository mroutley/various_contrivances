---
title: Astronomy pictures on the Desktop
author: Matthew Routley
date: '2005-01-23'
slug: astronomy-pictures-on-the-desktop
categories:
  - code
tags: []
---

<p>The &#8220;<a href="http://antwrp.gsfc.nasa.gov/apod/astropix.html">Astronomy Picture of the Day</a>&#8221; is a source of fantastic images. To take advantage of this resource, I went looking for a way to automatically set the current image as my Desktop background. A quick <a href="http://www.google.ca">Google</a> search turned up a <a href="http://www.perl.com">perl</a> script at <a href="http://www.haroldbakker.com/"><a href="http://www.haroldbakker.com">www.haroldbakker.com</a></a>. Although this was a great start, I wasn&#8217;t completely happy with the implementation of this script and decided to write my own.</p>

<p>The <a href="/files/apod.pl">apod.pl script</a> is written in <a href="http://www.perl.com">perl</a> and both sets the Desktop background and copies a description of the image to the Desktop as an html file. You can add the script to your <a href="http://www.apple.com/applescript/scriptmenu/">Script menu</a> and run it as appropriate. Even better, download the <a href="/files/runApod.scpt">runApod.scpt</a> <a href="http://www.apple.com/applescript">applescript</a> and have <a href="http://www.apple.com/ical/">iCal</a> set the Desktop at a convenient time. I&#8217;ve set up my computer to run the perl script early each morning so that I have a new Desktop background each day. Note that <a href="/files/runApod.scpt">runApod.scpt</a> expects <a href="http://www.routleynet.org/matt/docs/apod.pl">apod.pl</a> to be in &#8220;~/Library/Scripts/apod/&#8221;.</p>
---
title: iTunes remote control
author: Matthew Routley
date: '2005-10-28'
slug: itunes-remote-control
categories:
  - code
tags: []
---

<p>The current setup at home is that I&#8217;ve added all of our music (several thousand songs) to our <a href="http://www.apple.com/macmini/">Mac Mini</a> and then send it through <a href="http://www.apple.com/airportexpress/airtunes.html">AirTunes</a> to the home stereo. The complication is that the stereo and computer are at opposite ends of the house. Ideally, I can use my <a href="http://www.apple.com/ibook">iBook</a> to control the Mac Mini without needing to walk down the hall, but how?</p>

<p>One solution is to use <a href="http://www.realvnc.com/">VNC</a>, which allows complete control of the Mac Mini. Essentially, the iBook becomes a remote keyboard, mouse, and display. However, I generally only want to either toggle iTunes between play and pause or skip to the next track. Loading up a VNC client and interacting with iTunes directly seems excessive in this case.</p>

<p>An alternate approach I have taken relies on a <a href="http://www.macdevcenter.com/pub/a/mac/collections/unix.html">Terminal session</a> and <a href="http://developer.apple.com/documentation/Darwin/Reference/ManPages/man1/osascript.1.html">osascript</a>. The first step is to log into the Mac Mini:</p>

<pre><code>$ ssh Nexus.local. -p 22
</code></pre>

<p>Then I can toggle between play and pause with:</p>

<pre><code>$ osascript -e 'tell application "itunes" to playpause'
</code></pre>

<p>or skip the current track with:</p>

<pre><code>$ osascript -e 'tell application "itunes" to nexttrack'
</code></pre>

<p>I keep the Terminal session active and have added the osascript commands to <a href="http://www.petermaurer.de/nasi.php?section=textpander">Textpander</a> so that I can quickly control iTunes remotely.</p>
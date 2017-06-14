---
title: plantae foundations
author: Matthew Routley
date: '2006-01-15'
slug: plantae-foundations
categories:
  - evolution
tags: []
---

<p>I’ve made a variety of important changes to plantae’s foundations. For the curious they are:</p>

<ul><li>Converted the webserver from apache to <a href="http://lighttpd.net/">LightTPD</a>. LightTPD is fast and easy to configure. Plus it has built-in support for FastCGI which makes plantae run much faster.</li>
<li>Set up a <a href="http://subversion.tigris.org/">Subversion</a> repository. This manages the code for plantae and allows me to track and reverse changes. This will also be very useful if someone else helps with the coding.</li>
<li>Figured out <a href="http://manuals.rubyonrails.com/read/book/17">Switchtower</a> to handle plantae’s deployment.</li>
<li>Hooked up a code repository at <a href="http://code.plantae.info">code.plantae.info</a> using <a href="http://collaboa.org/">Collaboa</a>. This is how I intend to track feature requests and bugs. Hopefully our users will also use this feature to pass on suggestions.</li>
</ul><p>Now the plan is to start adding plant characters.</p>
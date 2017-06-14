---
title: Remote data analysis
author: Matthew Routley
date: '2006-03-15'
slug: remote-data-analysis
categories:
  - code
tags: []
---

<p>My six-year old laptop is incredibly slow, particularly when analysing data. Unfortunately, analysing data is my job, so this represents a problem. We have a new and fast desktop at home, but I can’t monopolise its use and it would negate the benefits of mobility.</p>

<p>Fortunately, with the help of <a href="http://www.gnu.org/software/emacs/emacs.html">Emacs</a> and <a href="http://ess.r-project.org/">ESS</a> there is a solution. I write my <a href="http://www.r-project.org/">R</a> code on the laptop and evaluate the code on the desktop, which sends the responses and plots back to the laptop. I can do this anywhere I have network access for the laptop and the results are quite quick.</p>

<p>There are a few tricks to the setup, especially if you want the plots sent back to the laptop’s screen, so I’ll document the necessary steps here.</p>

<p>First, you need to enable X11 forwarding on both the desktop and laptop computers (see the <a href="http://developer.apple.com/qa/qa2004/qa1383.html">Apple Technote</a>). Then start up <a href="http://www.apple.com/macosx/features/x11/">X11</a> on the laptop.</p>

<p>Now, on the laptop, start up Emacs, open a file with R code and ssh to the desktop:</p>

<p><code>  opt-x ssh -Y desktopip</code></p>

<p>Now, run R in the ssh buffer and link it to the R-code buffer</p>

<p><code>R opt-x ess-remote</code></p>

<p>That should do it. Now I have the speed of the desktop and the benefits of a laptop.</p>
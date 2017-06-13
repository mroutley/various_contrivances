---
title: Breakpoint regression
author: Matthew Routley
date: '2005-12-07'
slug: breakpoint-regression
categories:
  - code
tags: []
---

<p>In my investigations of ovule fates, I&#8217;ve needed to estimate regression parameters from discontinuous functions. A general term for such estimates is breakpoint regression. <a href="http://public.me.com/mroutley">OFStatisticalEstimates.pdf</a> demonstrates an approach using <a href="http://www.r-project.org">R</a> for such estimates in the context of seed-ovule ratios. The code includes a mechanism for generating seed-ovule data that illustrate the types of functions that need to be considered.</p>
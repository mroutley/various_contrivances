---
title: Dynamic State Variable Models in Ecology
author: Matthew Routley
date: '2004-04-14'
slug: dynamic-state-variable-models-in-ecology
categories:
  - evolution
  - code
tags: []
---

There's a powerful approach to modelling called dynamic state variable programming, covered in <a href="http://www.amazon.ca/exec/obidos/asin/0195122674/matthewroutle-20">Dynamic State Variable Models In Ecology</a> by Clark &amp; Mangel. I&#8217;ll post more about the approach sometime, but for now I wanted to make an example from the book available. The first chapter of the book includes a guide through the creation of a patch foraging model. A fully implemented version is available in True BASIC, but I've decided to use <a href="http://www.r-project.org/">R</a> for all of my modelling and analyses. Consequently, I've implemented the patch selection model from Clark &amp; Mangel in R. It is available from <a href="http://s3.amazonaws.com/mroutley_public/patchSelection.txt">http://s3.amazonaws.com/mroutley_public/patchSelection.txt</a> for anyone interested.
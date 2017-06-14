---
title: R module for ConTeXt
author: Matthew Routley
date: '2006-07-11'
slug: r-module-for-context
categories:
  - code
tags: []
---

<p>I generally write my documents in <a href="http://www.maths.lth.se/help/R/.R/library/utils/html/Sweave.html">Sweave</a> format. This approach allows me to embed the code for analyses directly in the report derived from the analyses, so that all results and figures are generated dynamically with the text of the report. This provides both great documentation of the analyses and the convenience of a single file to keep track of and work with.</p>

<p>Now there is a new contender for integrating analysis code and documentation with the release of an R module for <a href="http://wiki.contextgarden.net/Main_Page">ConTeXt</a>. I prefer the clean implementation and modern features of ConTeXt to the excellent, but aging, <a href="http://www.latex-project.org/">LaTeX</a> macro package that Sweave relies on. So, using ConTeXt for my documents is a great improvement.</p>

<p>Here's a simple example of using this new module. I create two randomly distributed, normal variables, test for a correlation between them, and plot their distribution.</p>

<pre><code>\usemodule[r]

\starttext
Describe the motivation of the analyses first.

Now create some variables.

\startRhidden
x &lt;- rnorm(1000, 0, 1)
y &lt;- rnorm(1000, 0, 1)
\stopRhidden

Are they correlated?

\startR
model &lt;- lm(y ~ x, data = test)
summary(model)
\stopR

Now we can include a figure.

\startR
pdf("testFigure.pdf")
plot(x, y)
dev.off()
\stopR

\startbuffer
\placefigure{Here it is}{\externalfigure[testFigure]}
\stopbuffer
\getbuffer

\stoptext
</code></pre>

<p>Processing this code produces a pdf file with all of the results produced from R, including the figure.</p>

<p>I had some minor difficulties getting this to work on my OS X machine, through no fault of the r module itself. There are two problems. The first is that, by default, write18 is not enabled, so ConTeXt can't access R directly. Fix this by editing <code>/usr/local/teTeX/texmf.cnf</code> so that &#8220;shell_escape = t&#8221;. The next is that the R module calls `texmfstart` which isn't directly accessible from a stock installation of TeX. The steps required are described in the &#8220;Configuration of texmfstart&#8221; section of the <a href="http://wiki.contextgarden.net/Mac_Installation">ConTeXt wiki</a>. I modified this slightly by placing the script in <code>~/bin</code> so that I didn't interfere with the installed teTeX tree. Now everything should work.</p>
---
title: Combining pdf files
author: Matthew Routley
date: '2005-10-23'
slug: combining-pdf-files
categories:
  - code
tags: []
---

<p>Recently, I needed to combine several pdf files into one. The <a href="http://the.taoofmac.com/space/HOWTO/Convert%20%28and%20Rotate%29%20Windows%20PDFs">The Tao of Mac</a> has a discussion of how to do this and I&#8217;m posting the code I used here so that I can find it again later.</p>

<pre><code>gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=out.pdf -c save pop -f *.pdf
</code></pre>

<p>Running this from a directory containing only the pdfs to be combined produces out.pdf.</p>
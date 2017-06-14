---
title: Resumes &amp; Spam Filters
author: Matthew Routley
date: '2006-09-11'
slug: resumes-amp-spam-filters
categories:
  - code
tags: []
---

<p>Since I&#8217;m looking for work, I found <a href="http://dev2dev.bea.com/blog/simonvc/archive/2006/11/sorting_candida.html">this post</a> rather interesting. They&#8217;ve applied a spam filter to resumes to automatically filter through candidates. The output is only as good as the reference resumes used to construct the filter, but still an intriguing idea. My results are below. Most importantly the probability of me not being hired is 1.15e-59, which is a very, very small number. Perhaps I should add this fact to my resume?</p>

<pre><code>I will now tell you what i think about this CV
The CV you entered fits better in the Hired group than the NotHired group.
CLASSIFY fails; success probability: 0.0000  pR: -58.9382
Best match to file #1 (Hired.css) prob: 1.0000  pR: 58.9382 
Total features in input file: 7478
#0 (NotHired.css): features: 61899, hits: 7125, prob: 1.15e-59, pR: -58.94
#1 (Hired.css): features: 794351, hits: 90156, prob: 1.00e+00, pR:  58.94
The CV you entered fits best into the Guru catagory.
CLASSIFY succeeds; success probability: 1.0000  pR: 8.1942
Best match to file #0 (Guru.css) prob: 1.0000  pR: 8.1942 
Total features in input file: 7478
#0 (Guru.css): features: 559355, hits: 66154, prob: 1.00e-00, pR:   8.19
#1 (Intergrator.css): features: 163555, hits: 17093, prob: 2.17e-29, pR: -28.66
#2 (Administrator.css): features: 241282, hits: 24729, prob: 8.45e-25, pR: -24.07
#3 (Developer.css): features: 485579, hits: 54104, prob: 6.39e-09, pR:  -8.19
</code></pre>
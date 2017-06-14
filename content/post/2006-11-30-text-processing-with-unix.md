---
title: Text processing with Unix
author: Matthew Routley
date: '2006-11-30'
slug: text-processing-with-unix
categories:
  - code
tags: []
---

<p>I recently helped someone process a text file with the help of Unix command line tools. The job would have been quite challenging otherwise, and I think this represents a useful demonstration of why I choose to use Unix.</p>

<p>The basic structure of the datafile was:</p>

<pre><code>; A general header file ;
1
sample: 0.183 0.874 0.226 0.214 0.921 0.272 0.117
2
sample: 0.411 0.186 0.956 0.492 0.150 0.278 0.110
3
...
</code></pre>

<p>In this case the only important information is the second number of each line that begins with “sample:”. Of course, one option is to manually process the file, but there are thousands of lines, and that’s just silly.</p>

<p>We begin by extracting only the lines that begin with “sample:”. <code>grep</code> will do this job easily:</p>

<pre><code>grep "^sample" input.txt
</code></pre>

<p><code>grep</code> searches through the input.txt file and outputs any matching lines to standard output.</p>

<p>Now, we need the second number. <code>sed</code> can strip out the initial text of each line with a find and replace while <code>tr</code> compresses any strange use of whitespace:</p>

<pre><code>sed 's/sample: //g' | tr -s ' '
</code></pre>

<p>Notice the use of the pipe (<code>|</code>) command here. This sends the output of one command to the input of the next. This allows commands to be strung together and is one of the truly powerful tools in Unix.</p>

<p>Now we have a matrix of numbers in rows and columns, which is easily processed with <code>awk</code>.</p>

<pre><code>awk '{print $2;}'
</code></pre>

<p>Here we ask <code>awk</code> to print out the second number of each row.</p>

<p>So, if we string all this together with pipes, we can process this file as follows:</p>

<pre><code>grep "^sample" input.txt | sed 's/sample: //g' | tr -s ' ' | awk '{print $2;}' &gt; output.txt
</code></pre>

<p>Our numbers of interest are in output.txt.</p>
---
title: Managing project files
author: Matthew Routley
date: '2006-03-27'
slug: managing-project-files
categories:
  - code
tags: []
---

<p>As I accumulate projects (both new and completed), the maintenance and storage of the project files becomes increasingly important. There are two important goals for a file structure: find things quickly and don’t lose anything. My current strategy is as follows:</p>

<p>Every project has a consistent folder structure:</p>

<pre><code>|-- analysis
|-- data
|-- db
|-- doc
|-- fig
`-- utils
</code></pre>

<p><em>analysis</em> holds the <a href="http://www.r-project.org">R</a> source files of the analysis. These, typically, are experiments and snippets of code. The main analyses are in the doc directory.</p>

<p><em>data</em> contains data files. Generally, these are csv files from clients.</p>

<p><em>db</em> is for sql dumps of databases and <a href="http://www.sqlite.org/">sqlite</a> files. I prefer working with databases over flat text files or Excel spreadsheets. These files are kept in the data folder and converted to sql databases for analyses.</p>

<p><em>doc</em> holds the analysis and writeup as a <a href="http://www.ci.tuwien.ac.at/~leisch/Sweave/FAQ.html">Sweave</a> file. This combines R and <a href="http://www.latex-project.org/">LaTeX</a> to create a complete document from one source file.</p>

<p><em>fig</em> is for diagrams and plots. Many of these are generated when processing the Sweave file, but some are constructed from other sources.</p>

<p><em>utils</em> holds scripts and binaries that are required to run the analysis.</p>

<p>This entire directory structure is maintained with <a href="http://subversion.tigris.org/">Subversion</a>, so I have a record of changes and can access the project files from any networked computer.</p>

<p>Finally, once a project is complete, I archive the project and construct a sha <a href="http://en.wikipedia.org/wiki/Checksum">checksum</a> of the zip file.</p>

<p><code>openssl dgst -sha1 -out checksums.txt archive.zip</code></p>

<p>This checksum allows me to verify that the archive remains stable over time. Coupled with a good backup routine, this should keep the project files safe.</p>

<p>This may seem elaborate, but data and their analyses are too important to be left scattered around a laptop’s hard drive.</p>

<p>One other approach I’ve considered is using the R package structure to maintain projects. <a href="http://www.maths.bris.ac.uk/~maman/computerstuff/Rhelp/Rpackages.html">This</a> is a useful guide, but the process seems too involved for my purposes.</p>
---
title: Stikkit from the command line
author: Matthew Routley
date: '2007-03-21'
slug: stikkit-from-the-command-line
categories:
  - code
tags: []
---

<p>Note – This post has been updated from 2007-03-20 to describe new installation instructions.</p>

<h2>Overview</h2>

<p>I’ve integrated <a href="http://www.stikkit.com/">Stikkit</a> into most of my workflow and am quite happy with the results. However, one missing piece is quick access to Stikkit from the <a href="http://en.wikipedia.org/wiki/Command_line_interface">command line</a>. In particular, a quick list of my undone todos is quite useful without having to load up a web browser.
To this end, I’ve written a <a href="http://www.ruby-lang.org/">Ruby</a> script for interacting with Stikkit. As I mentioned, my real interest is in listing undone todos. But I decided to make the script more general, so you can ask for specific types of stikkits and restrict the stikkits with specific parameters. Also, since the <a href="http://www.stikkit.com/api">stikkit api</a> is so easy to use, I added in a method for creating new stikkits.</p>

<h2>Usage</h2>

<p>The general use of the script is to list stikkits of a particular type, filtered by a parameter. For example,</p>

<pre><code>ruby stikkit.rb --list calendar dates=today</code></pre>

<p>will show all of today’s calendar events. While,</p>

<pre><code>ruby stikkit.rb -l todos done=0</code></pre>

<p>lists all undone todos. The use of -l instead of <code>--list</code> is simply a standard convenience. Furthermore, since this last example comprises almost all of my use for this script, I added a convenience method to get all undone todos</p>

<pre><code>ruby stikkit.rb -t</code></pre>

<p>A good way to understand stikkit types and parameters is to keep an eye on the url while you interact with Stikkit in your browser.
To create a new stikkit, use the <code>--create</code> flag,</p>

<pre><code>ruby stikkit.rb -c 'Remember me.'</code></pre>

<p>The text you pass to stikkit.rb will be processed as usual by Stikkit.</p>

<h2>Installation</h2>

<p>Grab the script from the <a href="http://code.google.com/p/stikkit-rb/">Google Code project</a> and put it somewhere convenient. Making the file executable and adding it to your path will cut down on the typing. The script reads from a .stikkit file in your path that contains your username and password. Modify this template and save it as ~/.sikkit</p>

<pre><code>
     ---
     username: me@domain.org 
     password: superSecret 
</code></pre>

<p>The script also requires the <a href="http://split-s.blogspot.com/2006/04/atom-10-parser-for-ruby.html">atom gem</a>, which you can grab with</p>

<pre><code>gem install atom</code></pre>

<p>I’ve tried to include some flexibility in the processing of stikkits. So, if you don’t like using <a href="http://en.wikipedia.org/wiki/Atom">atom</a>, you can switch to a different <a href="http://stikkit.com/api#responses">format</a> provided by Stikkit. The text type requires no gems, but makes picking out pieces of the stikkits challenging.</p>

<h2>Feedback</h2>

<p>This script serves me well, but I’m interested in making it more useful. Feel free to pass along any comments or feature requests.</p>
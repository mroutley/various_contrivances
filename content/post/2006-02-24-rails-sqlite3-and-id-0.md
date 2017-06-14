---
title: Rails, sqlite3, and id=0
author: Matthew Routley
date: '2006-02-24'
slug: rails-sqlite3-and-id-0
categories:
  - code
tags: []
---

<p>I’ve spent the last few days struggling with a problem with Plantae’s rails code. I was certain that code like this should work:</p>

<pre><code>class ContentController &lt; ApplicationController
  def new
    @plant = Plant.new(params[:plant])
    if request.post? and @plant.save
      redirect_to :action =&gt; 'show', :id =&gt; @plant.id
    else
       ...
    end
  end

  def show
    @plant = Plant.find(params[:id])
  end
  ...
end
</code></pre>

<p>These statements should create a new plant and then redirect to the show method which sends the newly created plant to the view.</p>

<p>The problem was that rails insisted on asking sqlite3 for the plant with id=0, which cannot exist.</p>

<p>After a post to the rails mailing list and some thorough diagnostics I discovered <a href="http://wiki.rubyonrails.org/rails/pages/HowtoUseSQLite">this</a> and realized I needed swig.</p>

<p>So, if anyone else has this problem:</p>

<pre><code>sudo port install swig
sudo gem install sqlite3-ruby
</code></pre>

<p>is the solution.</p>
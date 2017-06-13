---
title: Managing Email
author: Matthew Routley
date: '2005-12-02'
slug: managing-email
categories:
  - code
tags: []
---

<p>I recently lost control of my email. The combination of mailing lists, alerts, table of content notifications, and actual email from friends and colleagues was reaching a few hundred emails a day. The insanity had to stop! Here&#8217;s how I regained control.</p>

<h2>Goals</h2>

<p>Before describing my solution, let&#8217;s consider what a good email system should provide?</p>

<ul><li>Notifications of relevant new messages.</li>
<li>A process for keeping track of important and unanswered messages.</li>
<li>Automatic archiving with excellent search capabilities.</li>
<li>Portability and easy access.</li>
</ul><h2>Strategy</h2>

<p>I implemented my strategy as I switched to a <a href="http://mail.google.com">Gmail</a> account, which required that I catalogue and cancel all of my email subscriptions. Rather than re-subscribing to these, I redirected as many as possible to <a href="http://ranchero.com/netnewswire">NetNewsWire</a>. Many journals now provide feeds for their table of content alerts (e.g., <a href="http://www.nature.com/nature/newsfeeds.html">Nature</a>) and most of the important newsgroups are available through <a href="http://www.gmane.com/">Gmane</a>. The advantage of news feeds over email alerts is that I can easily group the alerts and choose when to refresh the subscriptions. Typically, I refresh my feed subscriptions in the morning as I caffeinate. I can simply flag important threads or articles for followup later if necessary and my Inbox is no longer cluttered.</p>

<p>Switching to Gmail also immediately solved several other issues with email. First, I no longer worry about storing and archiving email. All of it stays on Google&#8217;s servers. Second, this also solves the problem of deciding which messages to keep. Previously, for every new message I had to decide whether to delete it forever or store a copy. Although this only takes a few seconds for each message, when you receive hundreds of messages this can add up. Now, I don&#8217;t worry about it. I know that with the combination of Gmail&#8217;s search capabilities and my Mac&#8217;s <a href="http://www.apple.com/macosx/features/spotlight/">Spotlight</a> technology, I can find messages almost instantly. Third, Gmail is available from any webbrowser &#8212; now, so is my email.</p>

<p>That&#8217;s great so far, but I still have a variety of unfiltered email and I want to only be alerted to important or relevant messages. This is where <a href="http://www.apple.com/macosx/features/mail/">Mail.app&#8217;s</a> smart mailboxes and rules become important. The most important rule is that a message from someone who is not in my <a href="http://www.apple.com/macosx/features/addressbook/">Address Book</a> is immediately redirected out of my Inbox. I&#8217;ve also implemented a variety of <a href="http://mail.google.com/support/bin/answer.py?answer=12096&amp;topic=1565">aliases</a> that allows easy filtering of email from my Inbox. All of these filtered messages are gathered together in a folder which I, generally, peruse once a day.</p>

<p>Now I&#8217;m left with an Inbox containing only messages from people that I know. As new mail arrives, any mail that survives my filters is sent to <a href="http://growl.info/">Growl</a> and an unobtrusive notification apprises me of the sender and subject. I can then choose to ignore the message if I&#8217;m busy or switch to Mail and read the message if it appears to be important.</p>

<p>As I process my messages, I implement the <a href="http://www.amazon.ca/exec/obidos/redirect?link_code=ur2&amp;tag=matthewroutle-20&amp;camp=15121&amp;creative=330641&amp;path=ASIN%2F0142000280%2Fqid%3D1133552449%2Fsr%3D8-1%2Fref%3Dsr_8_xs_ap_i1_xgl">GTD</a> workflow: if responding takes less than two minutes, I respond; otherwise, the message is flagged for follow-up. Finally, I have two smart mailboxes: flagged messages; and messages received today. Since I&#8217;ve asked Mail to group messages by thread, today&#8217;s messages also pull in all of my previous correspondence on the subject. Messages in these two mailboxes are what appear in my main message window. When I switch to Mail all I see are flagged, and therefore important, messages and current conversations.</p>

<p>This all may seem elaborate, but I find it works well.</p>
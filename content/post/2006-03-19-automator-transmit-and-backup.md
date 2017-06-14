---
title: Automator, Transmit, and Backup
author: Matthew Routley
date: '2006-03-19'
slug: automator-transmit-and-backup
categories:
  - code
tags: []
---

<p>The Strongspace weblog has a <a href="http://weblog.strongspace.com/tips-and-tricks/automated-backups-with-transmit">useful post</a> about using <a href="http://www.panic.com/transmit/">Transmit</a> and <a href="http://www.apple.com/macosx/features/automator/">Automator</a> to make backups. One challenge with this approach is backing up files scattered throughout your home folder. The solution is the “Follow symbolic links” option when mirroring. I created a backup folder and populated it with aliases to the files I’m interested in backing up. Mirroring this folder to Strongspace copies the files to the server. The other option is to use the “Skip files with specified names” feature, but this rapidly filled up for me.</p>
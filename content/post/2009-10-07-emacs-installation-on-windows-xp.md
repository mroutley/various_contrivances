---
title: Emacs Installation on Windows XP
author: Matthew Routley
date: '2009-10-07'
slug: emacs-installation-on-windows-xp
categories:
  - code
tags: []
---

I spend a fair bit of time with a locked-down Windows XP machine. Fortunately, I'm able to install Emacs which provides capabilities that I find quite helpful. I've had to reinstall Emacs a few times now. So, for my own benefit (and perhaps your's) here are the steps I follow:

1. Download EmacsW32 patched and install in my user directory under Apps

    Available from <a href="http://ourcomments.org/Emacs/EmacsW32.html">http://ourcomments.org/Emacs/EmacsW32.html</a>

2. Set the environment variable for HOME to my user directory

    Right click on My Computer, select the Advanced tab, and then Environment Variables.

    Add a new variable and set Variable name to HOME and Variable value to C:\Documents and Settings\my_user_directory

3. Download technomancy's Emacs Starter Kit

    Available from <a href="http://github.com/technomancy/emacs-starter-kit">http://github.com/technomancy/emacs-starter-kit</a>

    Extract archive into .emacs_d in %HOME%

    Copy my specific emacs settings into .emacs_d\my_user_name.el
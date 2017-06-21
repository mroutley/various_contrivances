---
title: JSTOR import script
author: Matthew Routley
date: '2004-11-07'
slug: jstor-import-script
categories:
  - academic
  - code
tags: []
---

I've written a script that imports a <a href="http://www.jstor.org">JSTOR</a> citation page into <a href="http://bibdesk.sourceforge.net">BibDesk</a>. To use the script, I suggest adding it to your <a href="http://www.apple.com/applescript/scriptmenu/">script menu</a>. Then, with the JSTOR citation page as the active web page in <a href="http://www.apple.com/safari">Safari</a>, run the script and the citation will be added to the active <a href="http://bibdesk.sourceforge.net">BibDesk</a> file. I use the first author's last name and last two digits of the year as a cite key (e.g. Darwin59), you may want to change this to suit your style.

The script is written in <a href="http://www.perl.org">perl</a> and bracketed by two <a href="http://www.apple.com/applescript">Applescript</a> commands: one to extract the html source from the <a href="http://www.jstor.org">JSTOR</a> page and the other to add the citation to <a href="http://bibdesk.sourceforge.net">BibDesk</a>. Unfortunately, <a href="http://www.jstor.org">JSTOR</a> citation pages contain almost no semantic markup, so I am not convinced that the approach is entirely robust. However, so far it has worked well for me and might be useful to you. Any feedback is welcome.

<a href="http://s3.amazonaws.com/mroutley_public/JSTORImport.pl.txt">Download the script.</a> JSTORImport.pl.txt
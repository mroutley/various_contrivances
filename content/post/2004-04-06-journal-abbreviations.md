---
title: Journal abbreviations
author: Matthew Routley
date: '2004-04-06'
slug: journal-abbreviations
categories:
  - academic
  - code
tags: []
---

Until recently, I was able to use journal abbreviations in all of my manuscripts. Consequently, my .bib file contains only abbreviations in the journal field. Now I need to produce some bibliographies with full journal names. With a .bib file you can use macros to handle changing abbreviated names to full names. However, <a href="http://bibdesk.sourceforge.net">BibDesk</a> cannot use macros. Instead I wrote a perl script that searches through a .bib file and creates a new file with journal abbreviations changed to full names.

This script has been quite useful to me, so I decided to make it generally available <a href="http://s3.amazonaws.com/mroutley_public/longJournals">here</a> as longJournals. Feel free to modify it to suit your database. The important sections are near the top where the input and output files are declared and the substitution rules are listed. There are two types of substitution rules to handle some abbreviation conflicts (for example, Ecol. could be Ecology or Ecological). The first set of rules takes precedence over the second.

Rather than maintain two .bib files, I decided to use the abbreviated file as the main file and then periodically replace the long-journals file. The script could be improved to make it more flexible, but I only maintain one .bib file so it made sense to hardcode the file names and replacement arrays in the script. The copy linked to above has most of the substitution rules removed, since I assume they are not generally useful.

Suggestions are appreciated. Be sure to test out the script with a backup database first. Changes are not undoable.
---
title: Finance fixed their data and broke my case study
author: Matthew Routley
date: '2017-11-05'
slug: finance-fixed-their-data-and-broke-my-case-study
categories:
  - code
tags: []
---
The past few years, I've delivered an [introduction to using R workshop](https://github.com/mroutley/analytics_with_r) that relied on manipulating Ministry of Finance [demographic projections](https://www.fin.gov.on.ca/en/economy/demographics/projections/). 

Analyzing these data was a great case study for the typical data management process. The data was structured for presentation, rather than analysis. So, there were several header rows, notes at the base of the table, and the data was spread across many worksheets. 

![Leaving work from the Apple Watch](/images/finance_projections_table_6.png)

Sometime recently, the ministry released an update that provides the data in a much better format: one sheet with rows for age and columns for years. Although this is a great improvement, I’ve had to update my [case study](https://github.com/mroutley/analytics_with_r/commit/3ad3aac2ce979405c460acde743500f3203e2067), which makes it actually less useful as a lesson in data manipulation.

Although I've updated the main branch of the github repository, I've also created a [branch](https://github.com/mroutley/analytics_with_r/tree/2016_demog/case_study/population) that sources the [archive.org version](https://web.archive.org/web/20161014124140/https://www.fin.gov.on.ca/en/economy/demographics/projections/table6.html) of the page from October 2016. Now, depending on the audience, I can choose the case study that has the right level of complexity.

Despite briefly causing me some trouble, I think it is great that these data are closer to a good analytical format. Now, if only the ministry could go one more step towards [tidy data](https://en.wikipedia.org/wiki/Tidy_data) and make my case study completely unecessary.

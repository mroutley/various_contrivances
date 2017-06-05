---
title: Character assignments in phylogenetic analyses
author: Matthew Routley
date: '2004-01-09'
slug: character-assignments-in-phylogenetic-analyses
categories:
  - evolution
  - code
tags: []
---

<p>In some recent research (<a href="http://public.me.com/mroutley/SIandDichogamy.pdf">http://public.me.com/mroutley/SIandDichogamy.pdf</a>) I had to make inferences about families based on character states of the species within the family. One approach is to use a simple majority rule. For example, if more than half of the species possess character state x rather than y, then the family can be described as x. However, this approach seemed rather liberal, which led to a 2/3 majority criterion: if more than 2/3 of the species are x, the family is x; If less than 1/3 is x the family is y; otherwise the family is ambiguous.</p>

<p>A significant drawback to arbitrarily creating such criteria is that I had no idea what the consequences were for making Type I and Type II errors. Presumably, as the criterion becomes more stringent, Type I errors are less likely, but such uncertainty is not comforting. I decided a better approach would be to attempt a simulation study using different criteria coupled with a more sophisticated character state reconstruction algorithm.</p>

<p>The general approach was to create a family of twenty species and randomly assign a fixed proportion of each species one of two possible character states. The fixed probability chosen represented the decision criteria to be evaluated. For example, a 51% proportion is equivalent to the simple majority criterion. I then randomly generated 5,000 phylogenetic tree topologies for the family. To evaluate any given decision criterion, I compared the family characterization from the decision criterion to the ancestral-state reconstruction from <a href="http://links.jstor.org/sici?sici=0014-3820%28199712%2951%3A6%3C1699%3ALOASIA%3E2.0.CO%3B2-4">Schluter et al&#8217;s</a> maximum-likelihood analysis. The idea is that the maximum-likelihood reconstruction should be reasonably accurate, since it incorporates tree topology into its calculations. If the decision criterion and maximum-likelihood approaches yield similar answers, the decision criterion may be a good choice for describing families in the absence of species-level phylogenetic resolution.</p>

<p>I tested three decision criteria. Their results are: an 80% criterion was 98.1% accurate, 65% was 91.6%, and 55% was 60.8%. Clearly more stringent criteria are most similar to the more sophisticated maximum-likelihood analyses. However, stringency does exclude more data from the analysis as more families become ambiguously coded. A proper trade-off between stringency and sample size is required to make the best use of data.</p>

<p>I conducted these simulations with <a href="http://www.mesquiteproject.org">Mesquite</a> and the data file is available(<a href="http://public.me.com/mroutley/simulations.nex">http://public.me.com/mroutley/simulations.nex</a>).</p>
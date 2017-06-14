---
title: Analysis of Count Data
author: Matthew Routley
date: '2006-04-13'
slug: analysis-of-count-data
categories:
  - code
tags: []
---

<p>When response variables are composed of counts, the standard statistical methods that rely on the normal distribution are no longer applicable. Count data are comprised of positive integers and, often, many zeros. For such data, we need statistics based on Poisson or binomial distributions. I’ve spent the past few weeks analysing counts from hundreds of transects and, as is typical, a particular challenge was determining the appropriate packages to use for <a href="http://wwww.r-project.org/">R</a>. Here’s what I’ve found so far.</p>

<p>The first step is to get an idea of the dispersion of data points:</p>

<pre><code>  Means &lt;- tapply(y, list(x1, x2), mean)
 Vars &lt;- tapply(y, list(x1, x2), var)
 plot(Means, Vars, xlab="Means", ylab="Variances")
 abline(a=0, b=1)
</code></pre>

<p>For the Poisson distribution, the mean is equal to the variance. So, we expect the points to lie along the solid line added to the plot. If the points are overdispersed, a negative binomial link function may be more appropriate. The <code>pscl</code> library provides a function to test this:</p>

<pre><code>  library(pscl)
 model.nb &lt;- glm.nb(y ~ x, data=data)
 odTest(model.nb)
 summary(model.nb)
</code></pre>

<p>If the <code>odTest</code> function rejects the null model, then the data are overdispersed relative to a Poisson distribution. One particularly useful function is <code>glmmPQL</code> from the <code>MASS</code> library. This function allows for random intercepts and combined with the negative.binomial function of the same library, you can fit a negative binomial GLMM:</p>

<pre><code>  model.glmm.nb &lt;- glmmPQL(y ~ x1 + x2,
     random= ~ 1|transect, data=data,
     family=negative.binomial(model.nb$theta))
</code></pre>

<p>In this case, I use the Θ estimated from the <code>glm.nb</code> function in the <code>negative.binomial</code> call. Also useful are the <code>zeroinfl</code> function of the <code>pscl</code> library for fitting zero-inflated Poisson or negative binomial models and the <code>geeglm</code> function of <code>geepack</code> for fitting generalized estimating equations for repeated measures. Finally, <code>fitdistr</code> from <code>MASS</code> allows for estimating the parameters of different distributions from empirical data.</p>
---
date updated: 2021-12-02 13:38

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats'
---

# [[2001 Section 11 Dec 2]]


The three keys to scientific measurement:
- Quantity of interest, defined separately from th emeasure
- Measure with known statistical properties
- accurate uncertainty estimates


The BOOTSTRAP
- one way to do uncertainty. sample observations from the data with replacement and use these to display confidence.
- Define a measure. 
- Select $N$ resamples from a dataset with $n$ 
- for each of the $N$ generate the measure
- look at the $N$ measures as distribution
	- what is the variance of this? it's a property of the sample variance 

When do we bootstrap
- our data is iid.


is this the same as simulation???
- sims: do 1 MLE. it's an estimator of an MLE. do 1 SE. it's estimator of sampling distribution. which is a property of population variance
- What if we can't write out a likelihood
- $n$ sample size is smaller than we would like
- we want to convey the uncertainty

Pros:
- uncertainty for hard to sample distributions
- (nonparametric)

Cons:
- if initial sample has defect: might give confidene in the wrong thing
- if it takes 20 minutes to compute a measure, $N = 1000$ is very expensive
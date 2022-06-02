---
layout: post
title:  "Bayes Filter"
date:   2022-06-01 12:30:16 +0200
categories: BayesRule BayesFilter
---


### Bayes' rule:

$$\tag{1.1} p(A|B)=\frac{p(B|A)p(A)}{p(B)}$$

Prior : <br>

$$p(A)$$ 
the probability as the belief in the hypothesis before seeing the new evidence.

Posterior : <br>

$$p(A|B)$$ 
the probability of the hypothesis being true, if the evidence is present. 

Likelihood : <br>

$$p(B|A)$$ 
the probability of the evidence being present, given the hypothesis is true.

Marginal : <br>

$$p(B)$$ 
the probability of the evidence being present, whether the hypothesis is true or false.


### Bayes Filter:

From bayes' rule we have: <br>
$$p(Hypothesis|Evidence) = p(Hypothesis)* \frac{p(Evidence|Hypothesis)}{p(Evidence)}$$ 

$$posterior \propto prior * likelihood$$

We can obtain a **recursive state estimation** algorithm:
1. **Prediction**<br>
$$\underbrace{p(x_t|z_{1:t-1})}_{\text{prediction}}=\int \underbrace{p(x_t|x_{t-1})}_{\text{motion model}}\underbrace{p(x_{t-1}|z_{1:t-1})}_{\text{prev. posterior}}d_{x_{t-1}}$$

2. **Correction**<br>
$$\underbrace{p(x_t|z_{1:t})}_{\text{posterior}}\propto \underbrace{p(z_t|x_t)}_{\text{observation}}\underbrace{p(x_t|z_{1:t-1})}_{\text{prediction}}$$
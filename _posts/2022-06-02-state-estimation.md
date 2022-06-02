---
layout: post
title:  "State-Estimation"
date:   2022-06-02 12:30:16 +0200
categories: Bayes-filter
---


### Bayes' rule:

$$\tag{1.1} p(A|B)=\frac{p(B|A)p(A)}{p(B)}$$

Prior: $$p(A)$$ <br>
Posterior: $$p(A|B)$$ <br>
Likelihood: $$p(B|A)$$ <br>
Marginal: $$p(B)$$ <br>

### Bayes Filter:

From bayes' rule we have:

$$posterior \propto prior * likelihood$$

We can obtain a **recursive state estimation** algorithm:
1. **Prediction**<br>
$$\underbrace{p(x_t|x_{t-1})}_{\text{prediction}}=\int \underbrace{p(x_t|x_{t-1})}_{\text{motion model}}\underbrace{p(x_{t-1}|y_{1:t-1})}_{\text{prev. posterior}}d_{x_{t-1}}$$

2. **Correction**<br>
$$\underbrace{p(x_t|y_{1:t})}_{\text{posterior}}\propto \underbrace{p(y_t|x_t)}_{\text{observation}}\underbrace{p(x_t|y_{1:t-1})}_{\text{prediction}}$$
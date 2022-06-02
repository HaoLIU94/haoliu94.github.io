---
layout: post
title:  "Multi-Object-Tracking"
date:   2022-06-02 12:30:16 +0200
categories: Kalman-filter
---

### Kalman Filter:

**Prediction**

Motion prediction<br>
$$\bar{x}_{k|k-1}=F_{k-1}\bar{x}_{k-1|k-1}$$ 

Increase uncertainity by motion<br>
$$P_{k|k-1}=F_{k-1}P_{k-1|k-1}F^{T}_{k-1}+Q_{k-1}$$

**Update**

Measurement prediction<br>
$$\bar{z}=H_{k}\bar{x}_{k|k-1}$$

Innovation<br>
$$\varepsilon_{k}=z_{k}-\bar{z}_{k}$$

Innovation covariance<br>
$$S_k=H_kP_{k|k-1}H^T_k+R_k$$

Kalman gain<br>
$$K_k=P_{k|k-1}H^T_kS^{-1}_k$$

Weighted average<br>
$$\bar{x}_{k|k}=\bar{x}_{k|k-1}+K_k\varepsilon_k$$

Uncertainty reduction<br>
$$P_{k|k}=P_{k|k-1}-K_kH_kP_{k|k-1}$$

**Likelihood**

$$p(z_k|z_{1:k-1})=\mathcal{N}(z_k;\bar{z}_k, S_k)$$

---
layout: post
title: "Machine learning: neural networks"
---

This post is a lecture note about artificial neural networks.

$$g(x)=\frac{1}{1+e^{-x}}\,.$$

<div>
$$
\mathbf a^{(i)}=\left\{
\begin{array}{ll}
\mathbf x&i=1\,,\\
g\left(\Theta^{(i-1)}\mathbf a^{(i-1)}\right)&\text{else}.
\end{array}
\right.
$$
</div>

$$h(x,\Theta)=\mathbf a^{(L)}\,.$$

<div>
$$\delta^{(i)}=\left\{
\begin{array}{ll}
\mathbf a^{(L)}-\mathbf y&i=L\,,\\
\left[\left(\Theta^{(i)}\right)^\mathsf T\delta^{(i+1)}\right]\cdot g'\left(\Theta^{(i-1)}\mathbf a^{(i-1)}\right)&\text{else.}
\end{array}
\right.
$$
</div>

<div>
$$\delta^{(i)}=\left\{
\begin{array}{ll}
\mathbf a^{(L)}-\mathbf y&i=L\,,\\
\left[\left(\Theta^{(i)}\right)^\mathsf T\delta^{(i+1)}\right]\cdot\mathbf a^{(i)}\cdot\left(\mathbf1-\mathbf a^{(i)}\right)&\text{else.}
\end{array}
\right.
$$
</div>

Recall the regularized cost function of the logistic regression is

<div>
$$
J(\theta)
=
-\frac{1}{m}\left\{\ln\left[g\left(\mathbf X\theta\right)\right]^\mathsf T\mathbf y+\ln\left[1-g\left(\mathbf X\theta\right)\right]^\mathsf T\left(1-\mathbf y\right)\right\}
+\frac{\lambda}{2m}\sum_{j=1}^n\theta_j^2
\,.
$$
</div>

The neural network is a generalized version of logistic regression, whose regularized cost function is

<div>
$$
J(\Theta)
=
-\frac{1}{m}
\sum_{i=1}^m\sum_{k=1}^K
\left\{y_k^{(i)}\ln h\left(\mathbf x^{(i)};\Theta\right)_k+\left(1-y_k^{(i)}\right)\ln\left[1-h\left(\mathbf x^{(i)};\Theta\right)_k\right]\right\}
+\frac{\lambda}{2m}
\sum_{l=1}^{L-1}\sum_{i=1}^{s_l}\sum_{j=1}^{s_{l+1}}
\left(\Theta_{j,i}^{(l)}\right)^2
\,.
$$
</div>
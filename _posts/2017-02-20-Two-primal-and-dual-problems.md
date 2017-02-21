---
layout: post
title: "Two primal and dual problems in super resolution"
comments: true
description: "This is an interested thing"
keywords: "optimization"
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
### Problem 1
\[
     \min \parallel x \parallel_{1} +  \frac{\lambda}{2} \parallel Ax - y \parallel_2^2
\]
By introducing a slack variable,
$$
\min \parallel x \parallel_{1} + \frac{\lambda}{2} \parallel u \parallel_{2}^2 
$$
$$
\text{subject to} \quad u = Ax - y
$$
$$
\mathcal{L}(x,u,c) = \parallel x \parallel_{1} + \frac{\lambda}{2} \parallel u \parallel_{2}^2 +c^T( u - Ax + y)
$$
If \( \parallel A^Tc \parallel_{\inf} \leq 1 \)
$$
\min_{x} \mathcal{L}(x,u,c) = \frac{\lambda}{2} \parallel u\parallel_2^2 +c^T u + c^Ty := h_c(u)
$$
\begin{eqnarray}
\dot{x} & = \sigma(y-x) \\\
\dot{y} & = \rho x - y - xz \\\
\dot{z} & = -\beta z + xy
\end{eqnarray}



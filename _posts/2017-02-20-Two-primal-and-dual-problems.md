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
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  TeX: { equationNumbers: { autoNumber: "AMS" } }
});

</script>

### Problem 1
\begin{equation}
     \min \parallel x \parallel_{1} +  \frac{\lambda}{2} \parallel Ax - y \parallel_2^2
\end{equation}
By introducing a slack variable,
\begin{align}
\min \parallel x \parallel_{1} + \frac{\lambda}{2} \parallel u \parallel_{2}^2 \\\
\text{subject to} \quad u = Ax - y
\end{align}

\begin{align}
\mathcal{L}(x,u,c) = \parallel x \parallel_{1} + \frac{\lambda}{2} \parallel u \parallel_{2}^2 +c^T( u - Ax + y)
\end{align}

If \\( \parallel A^Tc \parallel_{\inf} \leq 1 \\)
\begin{align}
\min_{x} \mathcal{L}(x,u,c) = \frac{\lambda}{2} \parallel u\parallel_2^2 +c^T u + c^Ty := h_c(u)
\end{align}

\begin{align}
\nabla h_c (u) & = \lambda u + c
\end{align}
\begin{align}
\min_{x,u} \mathcal{L}(x,u,c) & = \frac{1}{2 \lambda} \parallel c \parallel^2 - \frac{1}{\lambda}\parallel c \parallel^2 + c^Ty \\\
& = c^Ty -  \frac{1}{2 \lambda} \parallel c \parallel^2
\end{align}
The dual is
\begin{align}
\max c^Ty -  \frac{1}{2 \lambda} \parallel c \parallel^2  \\\
\text{subject to} \quad \parallel A^Tc\parallel_{\infty} \leq 1
\end{align}

### Problem 2
\begin{equation}
\begin{aligned}
& \underset{x}{\min}
& & \parallel x \parallel_1 + \frac{\lambda}{2} \parallel Ax - y\parallel_2^2\\\
& \text{subject to}
& & x \geq 0
\end{aligned}
\end{equation}
\begin{equation}
\begin{aligned}
& \underset{x,u}{\min}
& & \parallel x\parallel_1 + \frac{\lambda}{2} \parallel u \parallel_2^2\\\
& \text{subject to}
& & x \geq 0\\\
& & & u = Ax - y
\end{aligned}
\end{equation}
\begin{align}
\mathcal{L}(x,u,c,\gamma) &= \mathbf{1}^{T}x + \frac{\lambda}{2} \parallel u \parallel_2^2 + c^{T}(u-Ax+y) - \gamma^T x\\\
& = (\mathbf{1}^{T} - c^{T}A - \gamma^{T}) x +\frac{\lambda}{2}\parallel u\parallel_2^2 +c^{T}u +c^Ty
\end{align}
\begin{align}
\inf_{x,u}\mathcal{L}(x,u,c,\gamma) &=\inf_{x}\left[(\mathbf{1}^{T} - c^{T}A - \gamma^{T}) x \right]+\inf_{u}\left[\frac{\lambda}{2}\parallel u \parallel_2^2 +c^{T}u +c^Ty\right]
\end{align}
if \\(\mathbf{1}^{T} - c^{T}A - \gamma^{T} = 0\\)
\begin{align}
\inf_{u} \mathcal{L}(x,u,c,\gamma) =\inf_{u}\left[\frac{\lambda}{2}\parallel u \parallel_2^2 +c^{T}u +c^Ty\right] = c^Ty -  \frac{1}{2 \lambda} \parallel c \parallel_2^2
\end{align}
The duals is 
\begin{equation}
\begin{aligned}
& \underset{x}{\max}
& & c^Ty -  \frac{1}{2 \lambda} \parallel c \parallel_2^2\\\
& \text{subject to}
& &   \mathbf{1} - A^Tc - \gamma = 0\\\
& & & \gamma \geq 0
\end{aligned}
\end{equation}
This is equavalent to 
\begin{equation}
\begin{aligned}
& \underset{x}{\min}
& & \frac{1}{2 \lambda} \parallel c \parallel_2^2 - c^Ty ,\\\
& \text{subject to}
& &   \mathbf{1} - A^Tc \geq 0
\end{aligned}
\end{equation}




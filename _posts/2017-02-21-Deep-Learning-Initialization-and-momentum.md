---
layout: post
title: "Initialization and Momentum in Deep Learning"
comments: true
description: "This is an interested thing"
keywords: "Deep Learning"
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  TeX: { equationNumbers: { autoNumber: "AMS" } }
});

</script>

## Nesterov's Accelerated Gradient
### Momentum
Traditional GD method:
\begin{equation}
\theta_{t+1} = \theta_{t} - \eta \nabla f(\theta_t)
\end{equation}

Classical Momentum
\begin{align}
v_{t+1} &= \mu v_{t} - \eta \nabla f(\theta_t)\\\
\theta_{t+1}& = v_{t+1}  + \theta_{t}
\end{align}

NAG
\begin{align}
v_{t+1} &= \mu v_{t} - \eta \nabla f(\theta_t + \mu  v_t)\\\
\theta_{t+1}& = v_{t+1}  + \theta_{t}
\end{align}

Classical Momentum and NAG become similar when \\( \eta \\) is small, when \\( \eta \\) is large, NAG uses smaller effective momentum for high curvature eigen-directions, which prevents oscillations. 

Adam
\begin{align}
u_{t+1} &= \beta_1 u_{t} + (1 - \beta_1) \nabla f(\theta_t)\\\
v_{t+1} &= \beta_2 v_t +  (1- \beta_2) \nabla f(\theta_t)^T \nabla f(\theta_t)\\\
\hat{u}\_{t+1} &= u_{t+1}/(1+\beta_1^{t})\\\
\hat{v}\_{t+1} &= v_{t+1}/(a+\beta_1^t) \\\
\theta_{t+1}& = \theta_t - \eta \hat{u}\_t/(\sqrt{\hat{v}_t + \epsilon})
\end{align}
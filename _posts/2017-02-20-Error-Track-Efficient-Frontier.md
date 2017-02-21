---
layout: post
title: "Error Track Efficient Frontier"
comments: true
description: "This is an interested thing"
keywords: "optimization", "Fanancial Mathematics"
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  TeX: { equationNumbers: { autoNumber: "AMS" } }
});

</script>

Error track model express the traditional mean-variance optimization in a robust way, the basic model is as follows:

\begin{align\*} 
\max_x x'\mu\\\
\text{subject to }\; &x'l= 0\\\
& x'\Sigma x = \sigma_{\epsilon}^2 
\end{align\*}

where \\(x = w - w_b\\) and \\(w_b\\) is the benchmark portfolio which used to track the relative error.

To solve this problem, we have:

\begin{align}
 \mathcal{L}(x,\lambda, \gamma) = -x'\mu - \lambda(\sigma_{\epsilon}^2 - x'\Sigma x)  + \gamma x'l 
\end{align}

This can be transformed into a system of equations:
\begin{align}
\frac{\partial L}{x}  = -\mu + \lambda \Sigma x + \gamma l = 0 \\\
\frac{\partial L}{\lambda} = \sigma_{\epsilon}^2 - x'\Sigma x = 0 \\\
\frac{\partial L}{\gamma} = x'l = 0
\end{align}

We can get:

\begin{equation}
x^* = \frac{1}{\lambda^\*}\Sigma^{-1}(\mu - \gamma^\* l)
\end{equation}

where\\( \gamma^\* = \frac{l'\Sigma^{-1}\mu}{l'\Sigma^{-1}l}\\)

\begin{equation}
\lambda^\* =\pm \frac{\sqrt{(\mu - \gamma^\* l)' \Sigma^{-1}(\mu - \gamma^* l)}}{\sigma_{\epsilon}}
\end{equation}

So the excess return is
\begin{equation}
\mu_{\epsilon} = x'\mu = \mu'x = \frac{1}{\lambda^\*}\mu'\Sigma^{-1}(\mu - \gamma^\* l) = \pm \sigma_{\epsilon} \frac{\mu'\Sigma^{-1}(\mu - \gamma^\* l)}{\sqrt{(\mu - \gamma^\* l)' \Sigma^{-1}(\mu - \gamma^\* l)}}
\end{equation}

Hence, the efficient frontier is two straight lines.




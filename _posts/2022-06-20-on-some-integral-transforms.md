---
layout: post
title: "On Some Common Integral Transformations (WIP)"
categories: Math
comments: true
mathjax: true
---

# Fourier and Laplace Transformations

It is often useful to map an function from its original function space to another via integration.

## Some Preliminaries: Fourier Series Representations

A fourier series allows functions to be represented as a sum of sines and cosines. A function must satisfy the Dirichlet conditions to be represented as a fourier series.

### Dirichlet Conditions

- The function must be periodic
- The function must be single valued and continuous except potentially at a finite number of finite discontinuities
- The function must have a finite number of maxima and minima within one period
- The integral over one period of $\vert f(x) \vert$ must converge

The integrals over one period of the product of any two terms have the following properties:

$$ \int_{x_0}^{x_0+L} \sin \left(\frac{2\pi r x}{L} \right) \cos \left(\frac{2\pi p x}{L} \right) dx = 0 \ \text{for all} \ r \ \text{and} \ p$$

$$ \int_{x_0}^{x_0+L} \cos \left(\frac{2\pi r x}{L} \right) \cos \left(\frac{2\pi p x}{L} \right) dx =
\begin{cases}
L & \text{for} \ r = p = 0 \\
\frac{L}{2} & \text{for} \  r = p > 0 \\
0 & \text{for} \ r \neq p
\end{cases}$$

$$ \int_{x_0}^{x_0+L} \sin \left(\frac{2\pi r x}{L} \right) \sin \left(\frac{2\pi p x}{L} \right) dx =
\begin{cases}
L & \text{for} \ r = p = 0 \\
\frac{L}{2} & \text{for} \  r = p > 0 \\
0 & \text{for} \ r \neq p
\end{cases}$$

The fourier series expansion of a function $f(x)$ can be written

$$ 
f(x) = \frac{a_0}{2} + \sum_{r=1}^{\infty} \left[ a_r \cos \left(\frac{2 \pi r x}{L} \right) + b_r \sin \left(\frac{2 \pi r x}{L} \right) \right]
$$

Where $a_0$, $a_r$, and $b_r$ are the fourier coefficients.
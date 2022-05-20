---
layout: post
title: "A CKKS (HEAAN) Implementation in Java (WIP)"
categories: CS
mathjax: true
---

## The Premise of Homomorphic Encryption
Homomorphic encryption allows computation on encrypted data. The Cheon-Kim-Kim-Song (CKKS) scheme, is one of these such encryption schemes that allows for the approximate arithmetic of numbers.

## Preliminary Math
### Polar Representation of Complex Numbers

A complex number comes in the form $x+iy$, in which $x, y \in \mathbb{R}$ and $i$ is the imaginary unit $\sqrt{-1}$. The polar representation of $x+iy$ comes from the complex exponential function which is defined as

$$e^z = 1 + z + \frac{z^2}{2!} + \frac{z^3}{3!} + \ldots$$

It follows that for  $z = i\theta$, where $\theta$ is a real angle in radians, that

$$e^{i\theta} = 1 + i\theta - \frac{\theta^2}{2!} - \frac{i\theta^3}{3!} + \ldots$$

$$ = 1 - \frac{\theta^2}{2!} + \frac{\theta^4}{4!} - \ldots + i \left( \theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} - \ldots \right)$$

$$=e^{i\theta} = \cos\theta + i\sin\theta$$

By means of this relation, $x+iy$ can be represented as $z = re^{i\theta}$, where $r = \lvert x+iy \rvert = \sqrt{x^2 + y^2}$ and $\theta = \arctan(\frac{y}{x})$

### The Roots of Unity
$z^2 = 1$ has the solution $z = \pm 1$. With the polar representation, we can now solve $z^n = 1$.
Rewriting the equation, $$z^n = e^{2ik\pi}$$ where $k \in \mathbb{Z}$. Taking the nth root of each side gives us $$z = e^{\frac{2ik\pi}{n}}$$

The solutions are then $$z_{1,2,\ldots,n} = 1, e^{2i\pi/n}, \ldots, e^{2i(n-1)\pi/n}$$ which correspond to the values of $0,1,2, \ldots n-1$ for $k$. The $\sin$ and $\cos$ functions are periodic which allows for integer multiples of k.

### Ring Theory

A group is a set with an operation that combines any two elements of the set to produce a third element of the set, such that the operation is associative, an identity element exists and every element has an inverse.

A ring is a set $R$ endowed with two binary operations, usually denoted $+$ and $\cdot$ such
that $R$ is an abelian group with respect to $+$
and for any $a, b, c \in R$, $a(bc) = (ab)c$, $a(b + c) = ab + ac$, and $(a + b)c = ac + bc$

In some cases, it is useful to impose conditions of having a multiplicative identity and commutativity with respect to multiplication.

Rings with these conditions are respectfully called unital rings and commutative rings.

### Cyclotomic Polynomials

An $n$th cyclotomic polynomial, for any positive integer n, is a unique irreducible polynomial with integer coefficients that is a divisor of $x^n-1$ and is not a divisor of $x^k-1$ for any $k < n$. The roots of the polynomial are the nth roots of unity of $e^{\frac{2ik\pi}{n}}$, where k goes through all positive integers not greater n and gcd(k,n) = 1.
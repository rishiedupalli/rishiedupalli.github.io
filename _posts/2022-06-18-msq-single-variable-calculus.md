---
layout: post
title: "Math Super Quick: Single Variable Calculus"
categories: Math
comments: true
mathjax: true
---

# Math Super Quick: Single Variable Calculus

Welcome to my first series of blog posts! Math Super Quick: Very surface level reviews of math.

## Limits

### Definition

Formally, if $\lim_{x \to a} f(x) = \ell$, then for any number $\epsilon$, however small, it must be possible to find a number $\eta$ such that $$\vert f(x) - \ell \vert < \epsilon$$ whenever $$\vert x - a \vert < \eta$$.

Confusing right?

Well, to put it more simply $\lim_{x \to a} f(x) = \ell$, means that as $x$ become arbitrarily close to $a$, $f(x)$ becomes arbitrarily close to $\ell$.

### Evaluating Limits


#### Special Cases

In most cases, the limit $\lim_{x \to a} f(x) = \ell$ is just going to be $f(a)$. Some complications may arise however: the function could be undefined or discontinuous for example.

- A limit may be $\pm \infty$. Ex: As $x \to 0, \frac{1}{x^2} \to \infty$.

![The graph of 1/x^2](/assets/images/IntroCalc/InfiniteLimit.png)

- A limit may be approached from two different sides. Ex: As $\lim_{ x \to \frac{\pi}{2}^- } \tan x = \infty$ and as $\lim_{ x \to \frac{\pi}{2}^+ } \tan x = -\infty$.

![The graph of tanx](/assets/images/IntroCalc/LandR.png)

- A limit only exists if the left and right limits are equal. The limit Does Not Exist (DNE) if they do not match.
- Technically, infinite limits do not exist.
- A limit does not exist in the case of an infinite oscillation when approaching a fixed point.

#### Some Identities

- $\lim_{x \to a} [f(x) + g(x)] = \lim_{x \to a} f(x) + \lim_{x \to a} g(x)$.
- $\lim_{x \to a} f(x)g(x) = \lim_{x \to a} f(x) \lim_{x \to a} g(x)$.
- $\lim_{x \to a}, cf(x) = c \lim_{x \to a} f(x)$, where $c$ is any arbitrary constant.
- $\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{\lim_{x \to a} f(x)}{\lim_{x \to a} g(x)}$, provided that $f(x)$ and $g(x)$ $\neq \infty$ or $0$.

### Continuity

A function is a continuous at a point $a$ when $\lim_{ x \to a^-} = \lim_{ x \to a^+} = f(a)$.

## Differentiation

### Definition

Formally, the $n$th derivative of a function is defined (forgive my abuse of notation) as the limit, $f^{(n)}(x) = \frac{d^{n}f(x)}{d^n x} = \lim_{\Delta x \to 0} \frac{ f^{(n-1)} (x + \Delta x) - f^{(n-1)} (x) }{ \Delta x  } $, where the symbol $f^{(n)}$ denotes the $n$th derivative of $f(x)$. In this atrocious notation, assume that the $0$th derivative is just $f(x)$ and $n > 0$ We have $f'(x) = f^{(1)} = \frac{df(x)}{dx}$, $f''(x) = f^{(2)} = \frac{d^2f(x)}{d^2x}$, and so on.

Geometrically, the derivative can be interpreted as the slope of a tangent line of $f(x)$ at the point $x$.
Physically, the derivative can be interpreted as the rate of change (e.g. the derivative of position is velocity, the derivative of velocity is acceleration).

### Differentials

Near a point, we can approximate change in $\Delta f$ that results from a small change $\Delta x$ in $x$ by $\Delta f = \frac{df(x)}{dx}\Delta x$.
This approximation improves as $\Delta x \to 0$. This is denoted by the differential $df = \frac{df(x)}{dx}dx$, which relates $df$ to $dx$.

### Evaluating Derivatives

Let c be any arbitrary constant.

- $\frac{d}{dx}( c )= 0$
- $\frac{d}{dx}( cx )= c$
- $\frac{d}{dx}( x^n ) = nx^{n-1}$ 
- $\frac{d}{dx}( e^{cx} ) = ce^{cx}$
- $\frac{d}{dx}( c^x ) = c^x \cdot \ln(a) $
- $\frac{d}{dx}( \ln(cx) ) = \frac{c}{x}$
- $\frac{d}{dx}( \sin(ax) ) = a\cos(ax) $
- $\frac{d}{dx}( \cos(ax) ) = -a\sin(ax) $
- $\frac{d}{dx}( \sec(ax) ) = a\sec(ax)\tan(ax) $
- $\frac{d}{dx}( \tan(ax) ) = a \sec^2(ax) $
- $\frac{d}{dx}( \csc(ax) ) = -a \csc(ax)\cot(ax) $
- $\frac{d}{dx}( \cot(ax) ) = -a\csc^2(ax)$
- $\frac{d}{dx}( \arcsin(\frac{x}{a}) ) = \frac{1}{\sqrt{a^2 - x^2}} $
- $\frac{d}{dx}( \arccos(\frac{x}{a}) ) = - \frac{1}{\sqrt{a^2 - x^2}} $
- $\frac{d}{dx}( \arctan(\frac{x}{a}) ) = \frac{a}{a^2 + x^2} $
- $\frac{d}{dx} [f(x) + g(x)] = \frac{d}{dx} f(x) + \frac{d}{dx} g(x) $


#### Product Rule

$f(x) = u(x)v(x)$.
$f'(x) = u(x)v'(x) + u'(x)v(x)$

#### Quotient Rule

$f(x) = \frac{u(x)}{v(x)}$. $f'(x) = \frac{ v(x)u'(x) - u(x)v'(x) }{ [v(x)]^2 }$

#### Chain Rule

$f(g(x)) = f'(g(x)) \cdot g'(x)$

#### Implicit Differentiation

Implicit differentiation is best seen via an example:

$$
\begin{align}
    2 &= x^3 - 3xy + y^3 \\

    0 \cdot \frac{dx}{dx} &= 3x^2 \cdot \frac{dx}{dx} - (3x (1 \cdot \frac{dy}{dx}) + (3 \cdot \frac{dx}{dx}) \cdot y) + 3y^2 \cdot \frac{dy}{dx} \\

    0 &= 3x^2 - (3x \cdot \frac{dy}{dx} + 3y ) + 3y^2 \cdot \frac{dy}{dx} \\

    0 &= 3x^2 - 3x \cdot \frac{dy}{dx} + 3y + 3y^2 \cdot \frac{dy}{dx} \\

    -3x^2 - 3y &= -3x \cdot \frac{dy}{dx} + 3y^2 \cdot \frac{dy}{dx} \\

    -3x^2 - 3y &= ( -3x + 3y^2 ) \frac{dy}{dx} \\
    \frac{-3x^2 - 3y}{-3x + 3y^2} &= \frac{dy}{dx} \\
    \frac{dy}{dx} &= \frac{x^2-y}{x-y^2}
\end{align}
$$

By linearity, we can treat the function as 3 separate derivatives. Using the constant, power, and product rules (letting $u(x) = 3x$ and $v(x) = y$ ), each term was differentiated with respect to x. Then, by factoring out and moving like terms, we are able to divide and solve for $\frac{dy}{dx}$. We are technically using the chain rule, multiplying by $\frac{dx}{dx}$ and $\frac{dy}{dx}$ when taking the derivatives. This was written explictly in this example, though one usually drops the $\frac{dx}{dx}$ when differentiating the x term.

### Special Points of Functions

Stationary points of a derivative occur when the derivative is equal to zero.

A minima occurs when a function increases in value in both directions away from it.

![The graph of x^2](/assets/images/IntroCalc/Minima.png)

A maxima occurs when a function decreases in both directions away from it.

![The graph of -x^2](/assets/images/IntroCalc/Maxima.png)

An inflection point occurs when the derivative switches signs. It is representative of a switch in concavity.

![The graph of x^3](/assets/images/IntroCalc/InflectionPoint.png)

### Theorems of Differentiation

#### Second Derivative Test

Let $f(x)$ be a function such that $f''(c) = 0$ and the second derivative exists on some interval containing c.
If $f''(c) > 0$. $f(c)$ is a **relative mininum**.
If $f''(c) < 0$. $f(c)$ is a **relative maximum**.

#### Extreme Value Theorem

If a function $f(x)$ is continuous on a finite close interval $[a,b]$, then $f(x)$ has both an absolute maximum and an absolute mininum on the interval $[a,b]$.

#### Rolle's Theorem

If a function $f(x)$ is continuos in the range $a \leq x \leq c$, is differentiable in the range $a < x < c$, and satisfies $f(a) = f(c)$, for at least one point $x = b$, where $a < b < c$, $f'(b) = 0$.

#### Mean Value Theorem

If a function $f(x)$ is continuos in the range $a \leq x \leq c$, is differentiable in the range $a < x < c$, then there exists a point c such that $f'(b) = \frac{f(c) - f(a)}{c - a}$ on the interval $(a,b)$.

#### Inverse Derivatives

If $f(x)$ is a one-to-one differentiable function, and its inverse $f^{-1}(x)$ is differentiable, then for a point $f(a) = b$, $(f^{-1})' (b) = \frac{1}{f'(a)}$.

### Applications of Derivatives

#### Linear Approximations

We can use a tangent line approximation to estimate the value a curve $y = f(x)$ at $a$ when $x$ is near $a$.
$f(x) \approx f(a) + f'(a)(x-a)$.

#### L'Hospital's Rule

When limits are in an indeterminate form ($\frac{0}{0}$, $\frac{\infty}{\infty}$, ... ), One can take the derivative of the numerator and denominator of a function and take the limit of those function to get the limit of the original function. This process can be repeated. $\lim_{x \to a} \frac{f(x)}{g(x)} = \lim_{x \to a} \frac{f^{(n)}(a)}{g^{(a)}(a)}$.

## Integration

### Definition

The definite integral of $f(x)$, the integrand, between the lower limit $ x = a$ to the upper limit $x = b$ is written $I = \int_a^b f(x) dx$.

$I$ is formally defined as subividing the interval $a \leq x \leq b$ into a large number of subintervals by defining intermediate points $\zeta_i$ such that $a = \zeta_0 < \zeta_1 < \zeta_2 < \ldots < \zeta_n = b$, and then forming the sum $S = \sum_{i=1}^n f(x_i)(\zeta_i - \zeta_{i-1})$, where $x_i$ is an arbitrary point that lies in the range $\zeta_{i-1} \leq x_i \leq \zeta_i$. Now, letting $n$ tending towards infinity, S will either tend to a unique limit or not. In the event the sum tends towards a unique limit, I, then the definite integral of $f(x)$ between $a$ and $b$ is defined as having the value of $I$.

The definite integral can be interpreted as the area under the function $f(x)$ between $a$ and $b$.
![The area underneath the curve x^2](/assets/images/IntroCalc/x2int.png)

#### Properties of Definite Integrals

- $\int_a^b 0 dx = 0$
- $\int_a^a f(x) dx = 0$
- $\int_a^c f(x)dx = \int_a^b f(x) dx + \int_b^c f(x) dx$
- $\int_a^b [f(x) + g(x)] dx = \int_a^b f(x) dx + \int_a^b g(x) dx$.
- $\int_a^b f(x) dx = - \int_b^a f(x) dx$

### Integration is Anti-differentiation

Let $F(X) = \int_a^x f(u) du$, in which the lower limit will remain fixed and the upper limit $x$ is now variable. This is essentially a restatement of $I = \int_a^b f(x) dx$, but the variable $x$ in the integrand has been replaced with a new dummy variable $u$. Using $F(X) = \int_a^x f(u) du$ and the properties of definite integrals, we obtain

$$
\begin{align}
F(x + \Delta x) &= \int_a^{x + \Delta x} f(u) du \\
&= \int_a^x f(u) du + \int_x^{x + \Delta x} f(u) du \\
&= F(X) + \int_x^{x + \Delta x} f(u) du \\
\frac{F(x + \Delta x) - F(x)}{\Delta x} &= \frac{1}{\Delta x} \int_x^{x+\Delta x} f(u) du.
\end{align}
$$


Letting $\Delta x \to 0$, we find that the LHS become $\frac{dF}{dx}$, and the RHS becomes $f(x)$ because when $\Delta x$ is small, the RHS becomes $f(x) \Delta x$ and in the limit $\Delta x \to 0$, no approximation is involved. Therefore, we have $\frac{dF(x)}{dx} = f(x)$. Or, $\frac{d}{dx} \left[ \int_a^x f(u) du \right] = f(x)$.

We can regard integration as the inverse of differentiation. Any $F(x)$ found by this method is called the indefinite integral of $f(x)$. As the lower limit $a$ is arbitrary, any two such functions differ at most by an additive constant. We write this when evaluating the integral as $\int f(x) dx = F(x) + c$, where c can be any arbitrary constant known as the constant of integration. We only include this constant when evaluating an indefinite integral.

The definite integral between fixed limits $x = a$ and $x = b$ can be written as $\int_a^b f(x) dx = F(b) - F(a)$.

### Evaluating Integrals

Letting $a$ and $b$ be constants and the integrals dependent on $n$ are valid for $n \neq -1$ and in the final two results having $\vert x \vert \leq a$, we have
- $ \int a dx = ax + c $
- $ \int ax^n dx = \frac{ax^{n+1}}{n+1} + c$
- $ \int e^{ax} dx = \frac{e^{ax}}{a} + c $
- $ \int \frac{a}{x} dx = a \ln(x) + c $
- $ \int a \cos(bx) dx = \frac{a \sin(bx)}{b} + c $
- $ \int a \sin(bx) dx = \frac{- a \cos(bx)}{b} + c $
- $ \int a \tan(bx) dx = \frac{-a\ln(\cos(bx))}{b} + c $
- $ \int a\cos{bx}\sin^n(bx)dx = \frac{a\sin^{n+1}(bx)}{b(n+1)} + c$
- $ \int a\sin{bx}\cos^n(bx)dx = \frac{-a\cos^{n+1}(bx)}{b(n+1)} + c$
- $ \int \frac{a}{a^2 + x^2} dx = \arctan(\frac{x}{a}) + c $
- $ \int \frac{1}{\sqrt{a^2 + x^2}} dx = \arcsin(\frac{x}{a}) + c $
- $ \int \frac{-1}{\sqrt{a^2 + x^2}} dx = \arccos(\frac{x}{a}) + c $
- $ \int \frac{f'(x)}{f(x)} dx = \ln(f(x)) + c $

#### Substitution

Recall the chain rule, $f(g(x)) = f'(g(x)) \cdot g'(x)$. Armed with the knowledge that integration is the inverse of differentiation, if we have an integrand of the form f(g(u))dg(u), our integral will evaluate to F(g(u)). This is called a u-substitution. I don't know how to and don't really want to explain it here but that is the gist of it.

#### Integration by Parts

Let $u = u(x)$. Let $v = v(x)$. Let dv = variable dv. Let du = variable du. $\int udv = uv - \int vdu$.

#### Improper Integrals

$I = \int_a^{\infty} f(x) dx = \lim_{b \to \infty} \int_a^b f(x) dx = \lim_{b \to \infty} [F(b) - F(a)]$.

### Some Applications of Integration

#### Average Value

The average value $m$ of a function between two limits $a$ and $b$ can be calculated as $m = \frac{1}{b-a} \int_a^b f(x) dx$.

#### Length of a Curve

The total length $s$ between 2 points $a$ and $b$ on a curve $f(x)$ is given by $s = \int_a^b \sqrt{1+ (\frac{dy}{dx})^2} dx$

#### Polar Area

In plane polar coordinates $r, \theta$ a curve is definies by its distance $r$ from the origin as a function of the angle $\theta$ between the line joining a point on the curve to the origin and the x-xis. The total area between two angles $\theta_1$ and $\theta_2$ is then given by $A = \int_{\theta_1}^{\theta_2} \frac{1}{2}r^2d\theta$.

## Sequences and Series

I going to skip to the more important parts of series, as this is more of an introduction to the applications of calculus.

### Taylor & Maclaurin Series

Let f(x) be a continuous and differentiable function. f(x) can be expressed as the sum of a series of terms. $f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x-a)^n$, where a is the center of the approximation. When a = 0, we have a Maclaurin series.

#### Some Standard Maclaurin Series

$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \ldots$ | $-\infty < x < \infty$
$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \ldots$ | $-\infty < x < \infty$
$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \ldots$ | $-\infty < x < \infty$

# Chapter III: The Z Transform

## Introduction

### Preliminaries: complex numbers

* real and imaginary part
* **modulus and phase**
* graphical interpretation
* Euler formula
* modulus and phase of $e^{jx}$

### Definition of Z transform

* The Z Transform of a signal $x[n]$, called $X(z)$, is defined as:
$$X(z) = \sum_{-\infty}^\infty x[n] z^{-n}$$

* It is defined only for the values of $z$ where the sum is finite
(called *region of convergence)*

* Notation:
$$\mathcal{Z}\left( x[n] \right) = X(Z)$$
$$x[n] \xrightarrow{Z} X(Z)$$

* Similar to the Laplace transform for analog signals

* The Z transform associates **a polynomial** to a signal (think Decision and Estimation class)
* Why?
    * Convolution of two signals = multiplication of polynomials
    * Short descriptions of complicated signals (i.e. exponential signals)


### Examples

$x[n] = {1, 2, 5, 7, 0}$, (with time origin in 1 or in 5)

$\delta[n]$, $\delta[n-k]$, $\delta[n+k]$

$\left(\frac{1}{2}\right)^n$

$x[n] = a^n u[n]$

$x[n] = -a^n u[-n-1]$

### Region of convergence

* For finite-support signals, the CR is the whole Z plane, possibly except 0 or $\infty$

* For causal signals, the CR is *the outside of a circle*:
$$|z| > r_1$$

* For anti-causal signals, the CR is *the inside of a circle*:
$$|z| < r_2$$

* For bilateral signals, both the causal and the anti-causal terms of the sum must converges ---> the CR is the area between two circles:
$$r_1 < |z| < r_2$$

* For finite-support signals, the two "circles" are $0$ and $\infty$

* Two different signals can have the same expression of $X(z)$, but with different RC!
    * RC is an essential part in specifying a Z transform
    * should never be omitted


### The Inverse Z Transform

* From a purely mathematical point of view, $X(z)$ is a complex function
* Proper definition of inverse transform is based on the theory of complex functions

$$X(z) = \sum_{-\infty}^\infty x[k] z^{-k}$$

* Multiply with $z^{n-1}$ and integrate along a contour C inside the Convergence Region:

$$\oint_C X(z) z^{n-1} dz = \oint_C \sum_{-\infty}^\infty x[k] z^{n-k-1} dz = \sum_{-\infty}^\infty x[k] z^{n-k-1} dz$$

* The Cauchy integral theorem says that:
$$ \frac{1}{2 \pi j} \oint_C z^{n-k-1} dz= 
\begin{cases}
1, &\mbox{if } k = n \\
0, &\mbox{if } k \neq n
\end{cases}
$$
 * And therefore:
$$x[n] = \frac{1}{2 \pi j} \oint_C X(z) z^{n-1} dz$$

* We will not use this relation in practice, but instead will rely on ** partial fraction decomposition**


### Properties of Z transform

#### 1. Linearity

If $x_1[n] \xrightarrow{Z} X_1(z)$ with RC1, and $x_2[n] \xrightarrow{Z} X_2(z)$ with RC2, then:
$$a x_1[n] + b x_2[n] \xrightarrow{Z} a X_1(z) + b X_2(z)$$
and CR is at least the intersection of RC1 and RC2.

Proof: use definition

#### 2. Shifting in time

If $x[n] \xrightarrow{Z} X(z)$ with RC1, then:
$$x[n-k] \xrightarrow{Z} z^{-k} X(z)$$
with same RC, possibly except $0$ and $\infty$.

Proof: by definition

* valid also for $k < 0$
* delay of 1 sample = $z^-1$

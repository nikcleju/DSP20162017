
# Chapter IV: Frequency Analysis of Discrete Systems

## IV.1 Reminder: Frequency analysis of analog signals

### Introduction

* Very useful to analyze signals in **frequency domain**
* The **spectrum** of a signal indicates the frequency contents
* Mathematical tools: 
    * periodicac signals: **Fourier series**
    * non-periodical signals: **Fourier transform**
    
### Analog periodical signals

* Periodical signal:
$$x(t) = x(t + T)$$

* The fundamental frequency is $$F_0 = \frac{1}{T}$$

* **The signal can be decomposed as a sum of complex exponential
signals, with multiples of the fundamental frequency, $k F_0$**
$$x(t) = \sum_{k=-\infty}^{\infty} c_k e^{j 2 \pi k F_0 t}$$

* The coefficients $c_k$ are the **spectrum** of the signal
$$c_k = \frac{1}{T} \int_{T/2}^{T/2} x(t) e ^{- j 2 \pi k F_0 t}$$

* The coefficients $c_k$ are complex values
    * their modulus = "amplitude spectrum"
    * their phase = "phase spectrum""

### Conditions for convergence

* When is the Fourier series convergent to the signal?
    * i.e. when is the relation correct, 
    * i.e. when is the sum actually equal to $x(t)$?

* Dirichlet conditions: the sum is convergent in all continuity points if:
    1. $x(t)$ is continuous or has a finite number of discontinuities
    in any finite interval
    2. $x(t)$ has a finite number of maxima and minima in any period
    3. $x(t)$ is absolutely integrable in any period, i.e.:
    $$\int_{T} |x(t)| dt  < \infty$$
    
* Weaker condition:
    * if $x(t)$ is square summable
	$$\int_T x(t)^2 dt < \infty$$
    * then the he difference $d(t) = x(t) - \sum_{k=-\infty}^{\infty} c_k e^{j 2 \pi k F_0 t}$
    has zero energy
    * Does not guarantee *pointwise* convergence
    
### Signal spectrum

* The coefficients $c_k$ are complex numbers
* If the signal is **real** $x(t) \in \mathbb{R}$, then the $c_k$ are **even**
    * $|c_k| = |c_{-k}|$
    * $\angle c_k = - \angle c_{-k}$
    * group the terms with $c_k$ with $c_{-k}$
--> **cosine with amplitude |c_k| and phase $\angle c_k$**

* Average power of signal = energy of coefficients
$$P_T = \frac{1}{T}\int_T |x(t)|^2 = \sum_{-infty}^{\infty} |c_k|^2$$

* Interpretation of Fourier series for real signal
    * **the signal is the sum of cosine signals with frequency
    $0, F_0, 2F_0 ...$, with amplitudes $|c_k|$ and phase $\angle c_k$**

* No other frequencies appear in spectrum --> spectrum is made of "lines"

### Time-frequency duality

* Time-frequency **duality**:
    * Real signal --> Even spectrum
    * Periodic signal --> Discrete spectrum

### Analog non-periodical signals

* The signal is composed of all frequencies (inverse Fourier transform)
$$x(t) = \int_{\-infty}^{\infty} X(F) e^{j 2 \pi f t} dF$$

* The frequency content is found by the Fourier transform
$$X(F) = \int_{\-infty}^{\infty} x(t) e^{- j 2 \pi f t} dt$$

* ( Can use instead $\Omega = 2 \pi F$)

* $X(F)$ is a complex function
    * $|X(F)|$ is the amplitude spectrum
    * $\angle X(F)$ is the phase spectrum

### Conditions for convergence

* When is the Fourier series convergent to the signal?
    * i.e. when is the relation correct, 
    * i.e. when is the sum actually equal to $x(t)$?

* Dirichlet conditions: the sum is convergent in all continuity points if:
    1. $x(t)$ is continuous or has a finite number of discontinuities
    2. $x(t)$ has a finite number of maxima and minima
    3. $x(t)$ is absolutely integrable:
    $$\int_{\infty}^{\infty} |x(t)| dt  < \infty$$
    
* Weaker condition:
    * if $x(t)$ is square summable
	$$\int_{\infty}^{\infty} x(t)^2 dt < \infty$$
    * then the he difference $d(t) = x(t) - \sum_{k=-\infty}^{\infty} c_k e^{j 2 \pi k F_0 t}$
    has zero energy
    * Does not guarantee *pointwise* convergence

### Signal spectrum

* $X(F)$ is a complex function
* If the signal is **real** $x(t) \in \mathbb{R}$, then the $X(F)$ is **even**
    * $|X(F)| = |X(-F)|$
    * $\angle X(F) = - \angle X(-F)$
    * group the terms with $c_k$ with $c_{-k}$
--> **cosine with amplitude |X(F)| and phase $\angle X(F)$**

* Signal energy is the same in time and frequency domains
$$E = \int_{\infty}^{\infty} |x(t)|^2 dt = \int_{\infty}^{\infty} |X(F)|^2 dF$$

* The power spectral density of $x(t)$ is 
$$S_{xx}(F) = |X(F)|^2$$


## IV.2 Frequency analysis of discrete signals

### Fourier series of discrete periodical signals

* A discrete signal of period $N$: $x[n] = x[n + N]$

* Decomposed as a **sum of complex exponentials**:
$$x[n] = \sum_{k=0}^{N-1} c_k e^{j 2 \pi k n / N}, n=0,1,... N-1$$

* Finding the coefficients:
$$c_k = \frac{1}{N} \sum_{n=0}^{N-1} x[n] e^{- j 2 \pi k n /N}$$


### Comparison with  analog Fourier series

* Compared to analog signals:
    * consider fundamental frequency $f_0 = 1/N$
    * only $N$ terms, with frequencies $k \cdot f_0$:
        * $0, f_0, 2 f_0, ... (N-1) f_0$
    * only $N$ distinct coefficients $c_k$
    * the $N$ coefficients $c_k$ can be chosen like $- \frac{N}{2} < k  \leq \frac{N}{2}$
    => the frequencies span the range $-1/2 ... 1/2$
$$-\frac{1}{2} < f_k \leq \frac{1}{2}$$
$$-\pi < \omega_k \leq \pi$$

    
### Basic properties of Fourier coefficients

1. Signal is **discrete** --> coefficients are **periodic** with period N
$$c_{k+N} = \frac{1}{N} \sum_{n=0}^{N-1} x[n] e^{- j 2 \pi (k+N) n} = \frac{1}{N} \sum_{n=0}^{N-1} x[n] e^{- j 2 \pi k n}$$

2. If signal is real $x[n] \in \mathbb{R}$, the coefficients are **even**:
    * $c_k^* = c_{-k}$
    * $|c_k| = |c_{-k}|$
    * $\angle c_k = \angle c_{-k}$
    
* Together with periodicity:
    * $|c_k| = |c_{-k}| = |c_{N-k}|$
    * $\angle c_k = - \angle c_{-k} = - \angle c_{N-k}$

### Expressing as sum of sinusoids

* Grouping terms with $c_k$ and $c_{-k}$ we get
$$x[n] = c_0 + 2 \sum_{k=1}^L |c_k| cos(2 \pi \frac{k}{N} + \angle c_k)$$
where $L = N/2$ or $L = (N-1)/2$ depending if $N$ is even or odd

* Signal = DC value + a finite sum of sinusoids with frequencies $k f_0$
    * $|c_k|$ give the amplitudes (x 2)
    * $\angle c_k$ give the phases


### Power spectral density

* The average power of a discrete periodic signal
$$P = \frac{1}{N} \sum_{n=0}^{N-1}|x[n]|^2$$

* Is the same in the frequency domain (with proof):

$$P = \sum_{k=0}^{N-1} |c_k|^2$$

* Power spectral density of the signal is
$$S_xx[k] = |c_k|^2$$

* Energy over one period is
$$E = \sum_{n-0}^{N-1} |x[n]|^2 = N \sum_{k-0}^{N-1} |c_k|^2$$

### Examples

* Examples:

$$x_1[n] = cos(\sqrt{5} \pi n)$$
$$x_2[n] = 2 sin(\frac{\pi}{3}n)$$
$$x_3[n] = \left\{ 1,1,0,0 \right\}$$


### Example in Python


~~~~{.python}
>>> import numpy as np
>>> from scipy.fftpack import fft, ifft
>>> x = np.array([1.0, 1.0, 0.0, 0.0])
>>> y = 1.0/4.0 * fft(x)
>>> y
array([ 0.50+0.j  ,  0.25-0.25j,  0.00+0.j  ,  0.25+0.25j])

~~~~~~~~~~~~~





### Properties of Fourier series

#### 1. Linearity

If the signal $x_1[n]$ has the Fourier series coefficients $\lbrace c_k^{(1)} \rbrace$, 
and $x_2[n]$ has $\lbrace c_k^{(2)} \rbrace$, then their sum has 

$a \cdot x_1[n] + b\cdot x_2[n] \leftrightarrow \lbrace a \cdot c_k^{(1)} + b\cdot c_k^{(2)} \rbrace$

Proof: via definition

### Properties of Fourier series

####  2. Shifting in time

If $x[n] \leftrightarrow \lbrace c_k \rbrace$, then
$$x[n - n_0] \leftrightarrow \lbrace e^{(-j 2 \pi k n_0 / N) c_k }\rbrace$$

Proof: via definition

* The amplitudes $|c_k|$ is not affected, shifting in time affects only the phase

### Properties of Fourier series

#### 3. Modulation in time
$$e^{(j 2 pi k_0 n / N} \leftrightarrow \lbrace c_{k-k_0} \rbrace$$

#### 4. Complex conjugation

$$x^*[n] \leftrightarrow \lbrace c^*_{-k} \rbrace$$

### Properties of Fourier series

#### 5. Circular convolution

Circular convolution of two signals $\leftrightarrow$ product of coefficients

$$x_1[n] \otimes x_2[n] \leftrightarrow \lbrace N \cdot c_k^{(1)} \cdot c_k^{(2)} \rbrace$$

Circular convolution:

$$x_1[n] \otimes x_2[n] = \sum_{k=0}^{N-1} x_1[k] x_2[(n-k)_N]$$

* takes two periodic signals of period N, result is the same
* Example at the whiteboard: how it is computed

### Properties of Fourier series

#### 6. Product in time

Product in time $\leftrightarrow$ circular convolution of Fourier series coefficients
$$x_1[n] \cdot  x_2[n] \leftrightarrow \sum_{m=0}^{N-1} c_m^{(1)} c_{(k-m)_N}^{(2)} = c_k^{(1)} \otimes c_k^{(2)}$$


### Fourier transform of discrete non-periodical signals

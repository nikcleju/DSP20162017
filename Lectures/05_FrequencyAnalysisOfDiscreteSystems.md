
# Chapter V. Frequency Analysis of Discrete Systems

### Response of LTI systems to harmonic signals

* We consider an LTI system with $h[n]$

* Input signal = complex harmonic (exponential) signal
$$x[n] = A e^{j \omega_0 n}$$

* Output signal = convolution
$$\begin{split}
y[n] &= \sum_{k=-\infty}^\infty h[n] x[k-n]\\
&= \sum_{k=-\infty}^\infty h[k] e^{-j \omega_0 k} A e^{j \omega_0 n}\\
&= H(\omega_0) \cdot x[n]
\end{split}$$

* $H(\omega_0)$ = Fourier transform of $h[[n]$ evaluated for $\omega = \omega_0$

### Eigen-function

* Complex exponential signals are **eigen-functions** (functii proprii)
of LTI systems:
    * output signal = input signal $\times$ a (complex) constant

* $H(\omega_0)$ is a constant that multiplies the input signal
    * Amplitude of input gets multiplies by $|H(\omega_0)|$
    * Phase of input signal is added with $\angle H(\omega_0)$

* Why are sin/cos/exp functions important?
    * If input signal = sum of complex exponential (= coses + sinuses),
    * since the system is linear,
    * then output = same sum of complex exponentials, each scaled with some coefficients

### Response to cosine and sine

* Cosine / sine = sum of two exponentials, via Euler

* System is linear and real => 
    * amplitude is multiplied by $|H(\omega_0)|$
    * phase increases by $\angle H(\omega_0)$

* See proof at blackboard

### Frequency response

* Names
    * $H(\omega)$ = frequency response of the system
    * $|H(\omega)|$ = amplitude response
    * $\angle H(\omega)$ = phase response

* Phase response might have jumps of $2 \pi$
* Stitching the pieces in a continuous function = phase *unwrapping*
    * Example: at blackboard
* Wrapped phase: $\in [-\pi, \pi]$, may have jumps of $2\pi$
* Unwrapped phase: continuous function, may go outside interval

### Permanent and transient response

* The above harmonic signals start at $n = -\infty$, not at 0.

* What if the signal starts at some time $n=0$?

* Total response = transient response + permanent response
    * transient response  goes towards 0 as $n \to \infty$
    * permanent response = the above 

* So the above relations are valid only in **permanent regime**
    * i.e. after the transient regime has passed
    * i.e. after the transient response has practically vanished
    * i.e. when the signal started very long ago (from $n = -\infty$)

* Example at blackboard

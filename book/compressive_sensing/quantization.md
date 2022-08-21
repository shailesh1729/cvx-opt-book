# Quantization

Sending measurement vectors over a communication channel
necessarily involves some sort of quantization.
The theory of quantized compressive sensing is quite
rich. In this section, we discuss some of the key
ideas from the field.

````{div}
The measurement quantization process can be written
as

```{math}
:label: eq-cs-q-measurement-quantization
\by = Q(\Phi \bx)
```
where $Q$ is the quantizer applied to the true real valued
measurements. Often, the quantization process can be
modeled simple as measurement noise:

```{math}
:label: eq-cs-q-quant-as-noise
\by = \Phi \bx + \bn
```
where $\bn$ is the measurement noise vector introduced
to model the quantization noise. Under this model,
one can simply lean on the theory of sparse recovery
under the presence of noise for stable recovery if
the quantization noise is energy limited. Specifically,
we can assume that

$$
\| \bn \|_2 \leq \epsilon
$$
for some $\epsilon > 0$ for a given quantization model.
In particular, for a uniform linear quantizer with
the step size $\delta$, one has

$$
\epsilon \leq \sqrt{\frac{M \delta^2}{12}}.
$$
````
Please revisit {ref}`sec:ssm:cs:noise:recovery`
for some basic recovery guarantees.

## 1-Bit Compressive Sensing

Our discussion below is limited to real valued
signals and sensing matrices.

In {cite}`boufounos20081`, the authors proposed
a very aggressive quantization strategy where
each measurement is reduced to a single bit.
In particular, we write the measurement as


```{math}
\by = \sgn (\Phi \bx)
```
where we are computing the sign of each measurement value
and transmitting this over the channel. Since the signs
of the measurements drop the amplitude information, hence
$\by$ is independent of the scale of $\bx$. In other words,
for any $\alpha > 0$, we have

$$
\sgn (\Phi (\alpha \bx)) = \sgn (\Phi \bx).
$$
Thus, we can only recover the signal $\bx$ up to a scale
factor. We resolve the issue of scale factor by insisting
that the recovery algorithm should construct a unit norm
signal. As a result of this restriction, our search space
is limited to the unit sphere. This vastly reduces the
reconstruction search space. 
We can easily see that in this quantization method,
the quantization noise cannot be modeled as an energy limited
component.

```{note}
In this section, we assume that the value $0$ has a
positive sign. Thus, there are only two possible values
of $\sgn(x)$ namely $+1$ and $-1$. This can be encoded
as a single bit over a communication channel.
```

### Consistent Reconstruction

The authors describe the notion of *consistent reconstruction*.
In {cite}`goyal1998quantized`, it is shown that consistent
reconstruction significantly improves the reconstruction
performance in quantized frame representations.

```{prf:definition} Consistent reconstruction
:label: def-cs-q-consistent-reconstruction

We say that the reconstructed signal is *consistent* with the
quantized measurements, if the reconstructed leads to
the same output if it is measured and quantized with the
same system.

In other words, if $\Delta$ is the reconstruction algorithm
and $\hat{\bx} = \Delta (\Phi, \by)$ is the reconstruction of $\bx$,
we say that $\hat{\bx}$ is a *consistent reconstruction* of $\bx$ if

$$
\by = Q(\Phi \bx) = Q (\Phi \hat{\bx}).
$$
```
Recall that each measurement before the quantization step
is an inner product between a row of the sensing matrix
and the signal. Thus, for consistent reconstruction in
the case of 1-bit compressive sensing, we require that
the inner product between each row of $\Phi$ and the
signals $\bx$ and $\hat{\bx}$ should have the same sign.
In the following, we explore how the reconstruction algorithm
can take advantage of the consistent reconstruction principle
to speed up the reconstruction process.

```{note}
Recall that we introduced the rows of the sensing matrix
as *sensing vectors* in {ref}`sec:ssm:sensing_matrix`.
In literature, often people call the rows of $\Phi$
as measurement vectors also. In that case the vector $\by$
is called the vector of measurements. Yes, indeed it can
get confusing. In our terminology, the rows of $\Phi$
are called sensing vectors and $\by$ is called the
measurement vector.
```

Let $\phi_i$ be the $i$-th row of $\Phi$. It is
clear that

$$
y_i \sgn( \langle \phi_i, \bx \rangle ) \geq 0.
$$

In the matrix notation, we can write this
as

$$
\bY \Phi \bx \succeq \bzero
$$
where $\bY = \diag (\by)$ is a diagonal matrix
comprising of the sign values in $\by$ on its
main diagonal.

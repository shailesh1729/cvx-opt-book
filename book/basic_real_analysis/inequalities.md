(sec:bra:inequalities)=
# Some Important Inequalities

````{prf:theorem}
:label: res-bra-l-t-inequality

Let $0 < \lambda < 1$. Then

```{math}
:label: eq-bra-l-t-inequality
t^{\lambda} \leq 1 - \lambda + \lambda t \Forall t \geq 0.
```

The inequality becomes equality only when $t = 1$.
````

```{prf:proof}
Define $f: \RR \to \RR$  with $\dom f = \RR_+$ by

$$
f(t) \triangleq 1 - \lambda + \lambda t - t^{\lambda}.
$$


Then,

$$
f'(t) = \lambda - \lambda t^{\lambda -1} = \lambda \left (1 - \frac{1}{t^{1-\lambda}} \right).
$$

In particular, note that $f'(1) = 0$ and:

$$
f'(t) \begin{cases}
> 0, &  \text{ if } t > 1\\
< 0, &  \text{ if } 0 < t < 1.
\end{cases}
$$

Thus, $f$ has a minimum value at $t=1$ which is $f(1) = 0$.
Thus, $f(t) \geq 0$ for all $t \geq 0$.

Thus,

$$
1 - \lambda + \lambda t - t^{\lambda} \geq 0
\iff t^{\lambda} \leq 1 - \lambda + \lambda t \Forall t \geq 0. 
$$


For $t=1$,

$$
1 - \lambda + \lambda t = 1 = 1^{\lambda}.
$$
Thus, the inequality indeed reduces to equality at $t=1$.
```

```{prf:definition} Conjugate exponent
:label: def-bra-conjugate-exponent


Let $p,q$ be extended real numbers with 
$p,q \in [1,\infty]$. 
Then, $p$ and $q$ are called *conjugate exponents* if

$$
\frac{1}{p} + \frac{1}{q} = 1.
$$

In particular $1$ and $\infty$ are conjugate
exponents in $\ERL$.
```

```{prf:example} Conjugate exponents
:label: ex-bra-conjugate-exponents-1

1. $p=1$ and $q=\infty$.
1. $p=2/3$ and $q=3$.
1. $p=2$ and $q=2$.
1. $p=3$ and $q=2/3$.
1. $p=\infty$ and $q=1$.
```

```{prf:theorem} Characterization of conjugate exponents
:label: res-bra-conjugate-exponent-charac

Let $p,q$ be extended real numbers with 
$p,q \in [1,\infty]$. 

The following are equivalent:

1. $p$ and $q$ are conjugate exponents.
1. $\frac{1}{p} = \frac{q - 1}{q}$.
1. $p = \frac{q}{q-1}$.
1. $\frac{1}{q} = \frac{p - 1}{p}$.
1. $q = \frac{p}{p-1}$.
```
```{prf:proof}
We get these results by simple arithmetic.

$$
\begin{aligned}
& \frac{1}{p} + \frac{1}{q} = 1\\
& \iff \frac{1}{p} = 1 - \frac{1}{q}\\
& \iff \frac{1}{p} = \frac{q - 1}{q}\\
& \iff p = \frac{q}{q-1}.
\end{aligned}
$$

The other two equalities are obtained
by simply interchanging $p$ with $q$.
```

## Cauchy Inequality

```{prf:theorem} Cauchy inequality
:label: res-bra-cauchy-inequality

$$
2 a b \leq a^2 + b^2.
$$
```

```{prf:proof}

Note that:

$$
\begin{aligned}
& (a - b)^2 \geq 0\\
& \iff a^2 -2 a b + b^2 \geq 0 \\
& \iff 2 a b \leq a^2 + b^2.
\end{aligned}
$$
```

## Interpolation Inequality for $e^x$.

```{prf:theorem}
:label: res-bra-interpolation-inequality-exp

If $t \in [0,1]$ then:

$$
e^{t a + (1 -t) b} \leq t e^a + (1 -t ) e^b.
$$
```

```{prf:proof}
This is a direct implication of the 
fact that $e^x$ is convex. 
```

## Young's Inequality

```{prf:theorem} Young's inequality
:label: res-bra-young-inequality

Let $p \in (1,\infty)$.
Let $q$ be the conjugate exponent of $p$.
Let $a, b \geq 0$, the
following holds true:

$$
ab \leq \frac{a^p}{p}  + \frac{b^q}{q}.
$$
```

Note that for the special case of $p=q=2$, we
obtain

$$
ab \leq \frac{a^2}{2} + \frac{b^2}{2}
$$
which is same as the Cauchy inequality.
Thus, Young's inequality is a generalization
of Cauchy inequality.

```{prf:proof}
For $a=0$ or $b=0$, the inequality is obvious.
We shall now consider the case where $a > 0$ and $b > 0$.

Let $\lambda = \frac{1}{p}$. Let $t = a^p b^{-q}$.
Putting this in {eq}`eq-bra-l-t-inequality`, we obtain:

$$
\begin{aligned}
&\left (a^p b^{-q} \right)^{\frac{1}{p}} \leq 1 - \frac{1}{p} + \frac{1}{p}a^p b^{-q}\\
&\iff ab^{-\frac{q}{p}} \leq \frac{1}{p}a^p b^{-q} + \frac{1}{q} \\
&\iff ab^{-\frac{q}{p}} b^q \leq \frac{1}{p}a^p + \frac{1}{q} b^q \\
&\iff ab \leq \frac{1}{p}a^p + \frac{1}{q} b^q.
\end{aligned}
$$
We used the fact that:

$$
-\frac{q}{p} + q = q \left (-\frac{1}{p} + 1 \right) = q \frac{1}{q} = 1. 
$$

Recall that {eq}`eq-bra-l-t-inequality` is an equality 
only if $t=1$ giving us:

$$
a^p b^{-q} = 1 \iff a^p = b^q.
$$
```
Following is an alternative proof.
This proof exploits the fact that $e^x$ is convex.
```{prf:proof}

For $a=0$ or $b=0$, the inequality is obvious.
We shall now consider the case where $a > 0$ and $b > 0$.

$$
\begin{aligned}
ab &= \exp (\ln (ab))\\
&= \exp ( \ln a + \ln b)\\
&=\exp \left (\frac{1}{p} p \ln a + \frac{1}{q} q \ln b \right )\\
&= \exp \left (\frac{1}{p} \ln (a^p) + \frac{1}{q}  \ln (b^q) \right )\\
&\leq \frac{1}{p} \exp (\ln (a^p)) + \frac{1}{q} \exp (\ln (b^q))\\
&= \frac{a^p}{p}  + \frac{b^q}{q}. 
\end{aligned}
$$
In this derivation, we used the fact that $e^x$ is strictly convex.
```

## Hölder's Inequality

```{prf:theorem} Hölder's inequality
:label: res-bra-holder-inequality

Let $p,q$ be conjugate exponents with $1 < p < \infty$. 
For any integer $n \geq 1$, assume that 
$a_1, \dots, a_n$ and $b_1, \dots, b_n$ are non-negative.

Then

$$
\sum_{k=1}^n a_k b_k \leq \left ( \sum_{k=1}^n a_k^p \right )^{\frac{1}{p}}
\left ( \sum_{k=1}^n b_k^q \right )^{\frac{1}{q}}.
$$
```

```{prf:proof}
Let 

$$
A = \left ( \sum_{k=1}^n a_k^p \right )^{\frac{1}{p}} 
\text{ and } B = \left ( \sum_{k=1}^n b_k^q \right )^{\frac{1}{q}}.
$$

If $AB = 0$ (i.e., either $A=0$ or $B=0$ or both)
then either all $a_i$ or all $b_i$ must be zero and the inequality 
is obvious. 

Now, consider the case $AB > 0$; i.e., $A > 0$ and $B > 0$.

Observe that:

$$
\sum_{k=1}^n \frac{a_k^p}{A^p} = 1 = \sum_{k=1}^n \frac{b_k^q}{B^q}.
$$

Letting h $a = \frac{a_k}{A}$ and $b = \frac{b_k}{B}$ and applying
{prf:ref}`Young's inequality <res-bra-young-inequality>`, we get:

$$
\frac{a_k}{A} \frac{b_k}{B} \leq  \frac{a_k^p}{p A^p} +  \frac{b_k^q}{q B^q}.
$$
Summing over $1 \leq k \leq n$, we obtain:

$$
\sum_{k=1}^n \frac{a_k}{A} \frac{b_k}{B}  \leq
\frac{1}{p} \sum_{k=1}^n \frac{a_k^p}{A^p}  + \frac{1}{q }\sum_{k=1}^n \frac{b_k^q}{B^q} 
= \frac{1}{p} + \frac{1}{q} = 1.
$$

Hence,

$$
\sum_{k=1}^n a_k b_k \leq A B \leq \left ( \sum_{k=1}^n a_k^p \right )^{\frac{1}{p}}
\left ( \sum_{k=1}^n b_k^q \right )^{\frac{1}{q}}
$$
as desired.
```


## AM-GM Inequalities
These inequalities establish relationship between
arithmetic mean and geometric mean of a set of
nonnegative real numbers.

We start with the simplest one.

```{prf:theorem} AM-GM inequality for two numbers
:label: res-bra-am-gm-inequality-2

Let $a,b \geq 0$. Then

$$
\sqrt{a b} \leq \frac{a + b}{2}.
$$
```

```{prf:proof}
We proceed as follows:

$$
& (a - b)^2 \geq 0\\
& \iff a^2 -2 a b + b^2 \geq 0 \\
& \iff 2 a b \leq a^2 + b^2\\
& \iff 4 a b \leq a^2 + b^2 + 2 ab\\
& \iff 4 a b \leq (a + b)^2 \\
& \iff ab \leq \left (\frac{a + b}{2} \right )^2\\
& \iff \sqrt{ab} \leq \frac{a + b}{2}.
$$
```


```{prf:theorem} Unweighted AM-GM inequality
:label: res-bra-unweighted-am-gm-inequality

Let $a_1,a_2,\dots, a_n \geq 0$. Then

$$
\left (\prod_{i=1}^n a_i \right )^{\frac{1}{n}} \leq 
\frac{1}{n} \left ( \sum_{i=1}^n a_i \right ).
$$
```


```{prf:proof}
If any of the numbers is 0, then the geometric mean is 0
and the inequality is satisfied trivially.
Thus, we shall assume that all numbers are positive. 

We prove this by Cauchy induction.
1. The base case for $n=2$ is proved in 
   {prf:ref}`res-bra-am-gm-inequality-2` above.
1. We show that if the inequality is true for some $n$,
   then it is also true for $2n$.
1. We then show that if the inequality is true for some $n$,
   then it is true for $n-1$ too.
1. Then, by principle of Cauchy induction, the proof is complete.


$(n) \implies (2n)$

Assume that the inequality holds true for any set of $n$ 
positive numbers. Now for $2 n$ numbers:

$$
\frac{a_1 + \dots + a_{2 n}}{2 n} 
= \frac{ \frac{a_1 + \dots + a_n}{n} + \frac{a_{n+1} + \dots + a_{2 n}}{n} }{2}.
$$

Since the inequality holds true for $n$, hence:

$$
\frac{a_1 + \dots + a_n}{n} \geq \sqrt[n]{a_1 \dots a_n}
\text{ and }
\frac{a_{n+1} + \dots + a_{2n}}{n} \geq \sqrt[n]{a_{n+1} \dots a_{2 n}}.
$$ 
Thus,

$$
\frac{a_1 + \dots + a_{2 n}}{2 n} 
\geq \frac{\sqrt[n]{a_1 \dots a_n} + \sqrt[n]{a_{n+1} \dots a_{2 n}}}{2}.
$$
The R.H.S. is an arithmetic mean of 2 numbers. 
Applying {prf:ref}`res-bra-am-gm-inequality-2`:

$$
\frac{\sqrt[n]{a_1 \dots a_n} + \sqrt[n]{a_{n+1} \dots a_{2 n}}}{2} 
\geq \sqrt{\sqrt[n]{a_1 \dots a_n} \sqrt[n]{a_{n+1} \dots a_{2 n}}}
= \sqrt[2n]{a_1 \dots a_{2n}}.
$$

Combining, we get the desired result:

$$
\frac{a_1 + \dots + a_{2 n}}{2 n}  \geq \sqrt[2n]{a_1 \dots a_{2n}}.
$$


$(n) \implies (n-1)$

By induction hypothesis, for any $n$ positive numbers, we have:

$$
\frac{a_1 + \dots + a_n}{n} \geq \sqrt[n]{a_1 \dots a_n}.
$$

Choose:

$$
a_n = \frac{a_1 + \dots + a_{n-1}}{n-1}.
$$
Then

$$
\frac{a_1 + \dots + a_n}{n} 
= \frac{a_1 + \dots + \frac{a_1 + \dots + a_{n-1}}{n-1}}{n}
= \frac{a_1 + \dots + a_{n-1}}{n-1}.
$$

Thus, we have:

$$
\frac{a_1 + \dots + a_{n-1}}{n-1} \geq 
\sqrt[n]{a_1 \dots a_{n-1} \cdot \frac{a_1 + \dots + a_{n-1}}{n-1} }. 
$$

Taking $n$-th power on both sides, we get:

$$
& \left ( \frac{a_1 + \dots + a_{n-1}}{n-1} \right )^n
\geq a_1 \dots a_{n-1} \cdot \frac{a_1 + \dots + a_{n-1}}{n-1}\\
& \implies \left ( \frac{a_1 + \dots + a_{n-1}}{n-1} \right )^{n-1}
 \geq a_1 \dots a_{n-1} \\
 & \implies \frac{a_1 + \dots + a_{n-1}}{n-1} 
  \geq \sqrt[n-1]{a_1 \dots a_{n-1}}
$$
as desired. The division by $\frac{a_1 + \dots + a_{n-1}}{n-1}$ 
is valid since it is a positive number. 

By Cauchy induction, the proof is complete.
```

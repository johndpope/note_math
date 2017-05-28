# Calculus Note - Sequences and Series

[TOC]

## Goals to learn Series

We'll introduce several methods (tests) to solve the following problems,

1. Determine whether a series is convergent or divergent
2. Estimate the sum of a series if convergent

## Integral Test

###Convergence

For some series, we can extract the sum by getting the limit of it's partial sum, or canceling most of the terms in the series. However more often, it isn't easy to find a simple formula for partial sum, thus difficult to exact sum of a series. 

**The Integral Test** Suppose $f$ is a continuous, positive, decreasing function on $[1, \infty)$ and let $a_n=f(n)$. Then the series $\sum_{n=1}^\infty a_n$ is convergent if and only if the improper integral $\int_1^\infty f(x) dx$ is finite.

> NOTE: when we use the integral test, it's not necessary to start the series of integral at $n=1$.

#### Example

1. $\sum_{n=1}^\infty \frac{1}{n^2}$ is convergent since  $\int_1^\infty \frac{1}{x^2} dx$ is finite.
2. $\sum_{n=1}^\infty \frac{1}{\sqrt n}$ is divergent since $\int_1^\infty \frac{1}{\sqrt x} dx$ is infinite.
3. A general rule for 1 & 2, **$\sum_{n=1}^\infty \frac{1}{n^p}$ is convergent if $p>1$ and divergent if $p \le 1$**.
4. $\sum_{n=1}^\infty \frac{\ln n}{n}$ is divergent since $\int_1^\infty \frac{\ln x}{x} = \vert_1^\infty \frac{(\ln x)^2}{2} = \infty$

### Estimating the Sum

When estimating the sum of a series with its partial sum of first n elements, we want to know how close the estimation is. 

We introduce the *remainder* as the error of estimation, which is defined by $R_n = s - s_n = \sum_{i=n+1}^\infty a_i$. The boundaries of the remainder,

$\int_{n+1}^\infty f(x) dx \le R_n \le \int_{n}^\infty f(x) dx$

![屏幕快照 2017-05-28 下午6.56.04](/Users/ferris/Desktop/屏幕快照 2017-05-28 下午6.57.02.png)

#### Example

Approximate the same of series $\sum \frac{1}{n^3}$ by using the sum of the first 10 terms. Estimate the error. How many terms are required to ensure the sum is accurate to within 0.0005? 

$\int_{11}^\infty  \frac{1}{x^3} dx \le R_ {10} \le \int_{10}^\infty \frac{1}{x^3} dx$

$\frac{1}{2 \times 11^2} \le R_{10} \le \frac{1}{2 \times 10^2}$

The error is within 0.005. To ensure the error is within 0.0005, we need $\frac{1}{2 \times x^2} \le 0.0005$, which means $x \ge 32$.

## Comparison Tests

### Convergence

**The Comparison Test** Suppose that $\sum a_n$ and $\sum b_n$ are series with positive terms. If $\sum b_n$ is convergent and $a_n \le b_n$ for all n, then $\sum a_n$ is also convergent. If $\sum b_n$ is divergent and $a_n \ge b_n$ for all n, then $\sum a_n$ is also divergent.

> We only need to verify $a_n \le b_n$ or $a_n \ge b_n$ for $n \ge N$ where N is some fixed number, because the convergence is not affected by a finite number of terms.

#### Example

1. $\sum \frac{5}{2 n^2 + 4 n + 3} \le \sum \frac{5}{2} \frac{1}{n^2}$ for all n≥1 thus is convergent
2. $\sum \frac{\ln k}{k} \gt \sum \frac{1}{k}$ for k≥3 thus is divergent

**The Limit Comparison Test** Suppose $\sum a_n$ and $\sum b_n$ are series with positive terms. If $\lim_{n \to \infty} \frac{a_n}{b_n} = c$ where c is a finite number and $c>0$, then either both series converge or both diverge.

#### Example

1. $a_n = \sum \frac{1}{2^n - 1}, b_n = \sum \frac{1}{2^n}, \lim_{n \to \infty} \frac{a_n}{b_n} = 1$, because $b_n$ is a convergent geometric series, $a_n$ is convergent
2. $a_n = \frac{2 n^2 + 3 n}{\sqrt 5 + n^5}, b = \frac{2 n^2}{n^{5/2}} = \frac{2}{n^{1/2}}, \lim_{n \to \infty} \frac{a_n}{b_n} = 1$ because $b_n$ is a divergent p-series, $a_n$ is convergent

### Estimating the Sum

#### Example

Use sum of first 100 terms the estimate the sum of series $\sum \frac{1}{n^3 + 1}$, estimate the error. 

$R_n = R_{100} \le \int_{100}^{\infty} \frac{1}{x^3 + 1} \lt \int_{100}^{\infty} \frac{1}{x^3} = 0.00005$

## Alternating Series

An **alternating series** is a series whose terms are alternately positive and negative. For example 

$1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + ... = \sum (-1)^{n+1} \frac{1}{n}$

### Convergence

**Alternating Series Test** If the series $\sum_{n=1}^\infty (-1)^{n-1} b_n, b_n \gt 0$ satisfies

- $b_{n+1} \le b_n$ for all n
- $\lim_{n \to \infty} b_n = 0$

then the series is convergent.

![屏幕快照 2017-05-28 下午6.54.58](/Users/ferris/Desktop/屏幕快照 2017-05-28 下午6.54.58.png)

#### Example

1. $\sum (-1)^{n+1} \frac{1}{n}$ satisfies both conditions thus is convergent
2. $\sum \frac{(-1)^n 3n}{4n - 1}$ is alternating but the limit of the term is $\frac{3}{4}$ thus is divergent
3. $\sum (-1)^{n+1} \frac{n^2}{n^3 + 1}$, to verify condition 1, take the derivative of the term we have $f'(x) = \frac{x(2 - x^3)}{(x^3 + 1)^2} < 0$ for $x \gt 2$, it's easy to verify condition 2 is satisfied, so the series is convergent

### Estimating Sums

**Alternating Series Estimation Theorem** For a convergent alternating series, the remainder

$| R_n | = | s - s_n| \le b_{n+1}$

#### Example

Find the sum of the series $\sum \frac{(-1)^{n}}{n!}$ correct to three decimal places.

From $|R_n| \le \frac{1}{(n+1)!} \lt 0.001$ we have $n+1 \ge 7$ so $s_6$ is correct to three decimal places.

## Absolute Convergence and The Ratio and Root Tests

**Definition** A series $\sum a_n$ is called **absolutely convergent** if the series $\sum |a_n|$ is convergent, and **conditionally convergent** if it's convergent but not absolutely convergent. 

**Theorem** If a series is absolutely convergent $\Rightarrow$ it is convergent.

For example, $\sum \frac{\cos n}{n^2} \le  \sum |\frac{\cos n}{n^2}| \le \sum \frac{1}{n^2}$ thus is convergent.

### Convergence

**The Ratio Test** If $\lim_{n \to \infty} |\frac{a_{n+1}}{a_n}| = L$, then $\sum a_n$ is aboslutely convergent if $L<1$, divergent if $L>1$, no conclusion if $L=1$. The idea is to compare $\sum a_n$ with a geometric series.

**The Root Test** If $\lim_{n \to \infty} \sqrt [n] {|a_n|} = L$, then $\sum a_n$ is aboslutely convergent if $L<1$, divergent if $L>1$, no conclusion if $L=1$. The idea is to compare $\sum a_n$ with a geometric series.

#### Example

1. $\sum (-1)^n \frac{n^3}{3^n}$ is absolutely convergent since $|\frac{a_{n+1}}{a_n}| = \frac{1}{3} (1 + 1/n)^3 \to \frac{1}{3} \lt 1$
2.  $\sum \frac{n^n}{n!}$ is divergent since $|\frac{a_{n+1}}{a_n}| = (1 + 1/n)^n \to e \gt 1$
3. For $\sum (\frac{2n+3}{3n+2})^n$, $\sqrt [n] {|a_n|} \to 2/3 <1$, thus is absolutely convergent

## Strategy for Testing Series

1. If the series is of the form $\sum 1/n^p$ , it is a p-series, which we know to be convergent if $p>1$ and divergent if $p \le 1$.
2. If the series has the form $\sum a r^{n-1}$ or $\sum a r^n$ , it is a geometric series, which converges if $|r| < 1$ and diverges if $|r| \ge 1$. Some preliminary algebraic manipulation may be required to bring the series into this form.
3. If the series has a form that is similar to a p-series or a geometric series, then one of the comparison tests should be considered.
4. If you can see at a glance that $\lim_{n \to \infty} a_n \ne 0$, then the Test for Divergence should be used.
5. If the series is of the form $\sum (-1)^{n-1} b_n$ or $\sum (-1)^n b_n$, then the Alternating Series Test is an obvious possibility.
6. Series that involve factorials or other products (including a constant raised to the nth power) are often conveniently tested using the Ratio Test.
7. If $a_n$ is of the form $(b_n)^n$, then the Root Test may be useful.
8. If $a_n = f(n)$, where $\int_1^{\infty} f(x) dx$ is easily evaluated, then the Integral Test is effective (assuming the hypotheses of this test are satisfied).

> See P746 in `Calculus 8th edition` for some exercises.

## Power Series

A **power series** is a series of the form $\sum_{n=0}^{\infty} c_n x^n$ where the $c_n$ are constants called the **coefficients** of the series. A power series may converge for some values of $x$ and diverge for other values of $x$. 

More generally, $\sum_{n=0}^{\infty} c_n (x-a)^n$ is called a **power series in (x-a) or a power series centered at a**.

In general, the Ratio Test (or sometimes the Root Test) should be used to determine the convergence.

#### Example

*Example 1* For what values of x is the series $\sum  n! x^n$ convergent? We use the Ratio Test. 

$|\frac{a_{n+1}}{a_n}| = (n+1) |x$, so the series converge only if $x=0$.

*Example 2* For what values of x does the series $\sum \frac{(x - 3)^n}{n}$ converge?

$|\frac{a_{n+1}}{a_n}| \to |x - 3|$, when $2 < x < 4$ the series converge. The Ratio Test gives no information when the ratio is 1, so we should consider them. When $x=4$ the series becomes a harmonic series which diverge. When $x=2$ then series is an alternating series which converge. So when $2 \le x \lt 4$ the series converge.

### Representations of Functions as Power Series

> You might wonder why we would ever want to express a known function as a sum of infinitely many terms. We will see later that this strategy is useful for integrating functions that don’t have elementary antiderivatives, for solving differential equations, and for approximating functions by polynomials.



## Taylor and Maclaurin Series













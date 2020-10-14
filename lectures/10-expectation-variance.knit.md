---
title: "Expectation & Variance<br>Chapters 3 & 4"
output: ioslides_presentation
editor_options: 
  chunk_output_type: console
---
  
<style>
  b, strong{
    color: #25679E;
  }
  table.rmdtable{
    width:unset;
    border-collapse:collapse;
    border-style:solid;
    border-width:3px;
    margin-bottom:1em;
    margin-left:auto;
    margin-right:auto;
  }
  table.rmdtable th, table.rmdtable td{
    padding:.5em;
    background:white;
    color:black;
    border-style:solid;
    border-width:1px;
    border-color:#000000;
  }
  slide{
  padding-bottom:.5em;
  }
  slides > slide > hgroup + article{
    margin-top:1em;
  }
</style>



## Data types

##   

![](./assets/Screenshotfrom2019-09-2006-52-06.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-10.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-11.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-13.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-15.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-17.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-18.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-21.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-23.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-29.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-35.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-38.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-40.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-42.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-43.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-46.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-50.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-52.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-53.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-54.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-55.png){width=100%}


##   

![](./assets/Screenshotfrom2019-09-2006-52-57.png){width=100%}

## 

![](./assets/Screenshotfrom2019-09-2008-05-02.png){width=100%}

## 

![](./assets/Screenshotfrom2019-09-2008-04-58.png){width=100%}


## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median | | |
| Mean (expectation) | | |
| Variance | | |
| IQR | | |
| Length of middle 95% | | |


## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median |$x \text{ such that } P(X\leq x)=P(X>x)=0.5$ | Middle value in sample |
| Mean (expectation) | | |
| Variance | | |
| IQR | | |
| Length of middle 95% | | |

## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median |$x \text{ such that } P(X\leq x)=P(X>x)=0.5$ | Middle value in sample |
| Mean (expectation) | $E[X] = \int x\, f(x)\, dx$ | $\bar{X}_N = \frac{1}{N}\sum_{i=1}^N x_i $ |
| Variance | | |
| IQR | | |
| Length of middle 95% | | |

## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median |$x \text{ such that } P(X\leq x)=P(X>x)=0.5$ | Middle value in sample |
| Mean (expectation) | $E[X] = \int x\, f(x)\, dx$ | $\bar{X}_N = \frac{1}{N}\sum_{i=1}^N x_i $ |
| Variance |  $E[X] = \int (x-E[X])^2\, f(x)\, dx$  | $\frac{1}{N-1}\sum_{i=1}^N (x_i-\bar{X}_N)^2$ |
| IQR | | |
| Length of middle 95% | | |

## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median |$x \text{ such that } P(X\leq x)=P(X>x)=0.5$ | Middle value in sample |
| Mean (expectation) | $E[X] = \int x\, f(x)\, dx$ | $\bar{X}_N = \frac{1}{N}\sum_{i=1}^N x_i $ |
| Variance |  $E[X] = \int (x-E[X])^2\, f(x)\, dx$  | $\frac{1}{N-1}\sum_{i=1}^N (x_i-\bar{X}_N)^2$ |
| IQR | $X_{0.75}-X_{0.25}$ | $\hat{Q}_3-\hat{Q}_1$ |
| Length of middle 95% | | |

## Summary of distribution vs summary of a sample

| Summary Measure | Distribution | Sample |
|:---|:---:|:---:|
| Median |$x \text{ such that } P(X\leq x)=P(X>x)=0.5$ | Middle value in sample |
| Mean (expectation) | $E[X] = \int x\, f(x)\, dx$ | $\bar{X}_N = \frac{1}{N}\sum_{i=1}^N x_i $ |
| Variance |  $E[X] = \int (x-E[X])^2\, f(x)\, dx$  | $\frac{1}{N-1}\sum_{i=1}^N (x_i-\bar{X}_N)^2$ |
| IQR | $X_{0.75}-X_{0.25}$ | $\hat{Q}_3-\hat{Q}_1$ |
| Length of middle 95% | $X_{0.975}-X_{0.025}$ | |

## Quantile function

If $F_X(x)$ is the CDF of a random variable $X$, then
\[
F_X(a) = P(X\leq a)
\]


## Quantile function

If $F_X(x)$ is the CDF of a random variable $X$, then
\[
F_X(a) = P(X\leq a)
\]

<img src="10-expectation-variance_files/figure-html/unnamed-chunk-2-1.png" width="720" />




## Expectation

### The expected value is meaningful for outcomes for which addition and subtraction is meaningful

## Expectation

### The expected value is meaningful for outcomes for which addition and subtraction is meaningful

+ Interval variables
+ Ratio variables

## Expectation

### The expected value is meaningful for outcomes for which addition and subtraction is meaningful **or binary variables**

+ Interval variables
+ Ratio variables
+ Binary variables (will get to this is a bit)

## Expectation

### The expected value of mutli-category ordinal variables can be meaningful if one assigns **scores** to each candidate outcome. 

## Expectation

### The expected value of mutli-category ordinal variables can be meaningful if one assigns **scores** to each candidate outcome. 

| Outcome | Score |
|:---:|:---:|
| Low | 0 |
| Medium | 2 |
| High | 5 |

## Expectation

### The expected value of mutli-category ordinal variables can be meaningful if one assigns **scores** to each candidate outcome. 

| Outcome | Score |
|:---:|:---:|
| Low | 0 |
| Medium | 2 |
| High | 5 |

The selection of **scores** is a researcher decision which can be  controversial.

## Expectation

For a random variable $X$,

### Conceptually & Simulation

$$E[X] = \lim_{n\to\infty} \frac{X_1+X_2+\cdots+X_n}{n}$$

### Mathematically

$$E[X] = \left\{\begin{array}{ll}\sum_x x\,P(X = x) & \text{if discrete} \\
\int x f_X(x)\,dx & \text{if continuous} \end{array}\right.$$

## Expectation

If $X$ is a Bernoulli random variable,

$$E[X] = 0\cdot P(X = 0) + 1\cdot P(X = 1) = P(X=1) $$

(This is why expectation is meaningful for binary outcomes.)

## Expectation

If $X$ is a binomial random variable,

$$E[X] = \sum_{x=0}^N x{N \choose x}p^x(1-p)^{(N-x)} $$

What does this simplify to?

## Expectation

If $X$ is a Poisson random variable,

$$E[X] = \sum_{x=0}^{\infty} x\frac{e^{-\lambda}\lambda^x}{x!} $$

What does this simplify to?  (Use the fact that $e^t = \sum_{i=0}^{\infty}\frac{t^i}{i!}$.)
What does this simplify to?

## Expectation

If $X$ is a uniform random variable,

$$E[X] = \int_{a}^b x(b-a)^{-1}\,dx $$

What does this simplify to?


## Expectation

If $X$ is a normal random variable,

$$E[X] = \int_{-\infty}^{\infty} x\frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{\sigma^2}}\,dx $$

What does this simplify to?

## Expectation

+ Does not always exist.


## Expectation

+ If we create a new random variable with addition, 
$$
\begin{align*}
D &= U + V \\
&\text{then} \\
E[D] &= E[U] + E[V]
\end{align*}
$$

## Example

$$
\begin{align*}
U &= \text{Number of dropped calls in Nashville}\\
V &= \text{Number of dropped calls in Atlanta}\\
D &= U + V \\
&\text{then} \\
E[D] &= E[U] + E[V]
\end{align*}
$$

## Example

**Note:** The random variables need not be independent.

$$
\begin{align*}
U &= \text{Number of dropped calls in Nashville}\\
V &= \text{Number of dropped calls at Vanderbilt}\\
D &= U + V \\
&\text{then} \\
E[D] &= E[U] + E[V]
\end{align*}
$$

## Expectation

+ If we create a new random variable with multiplication, 
$$
\begin{align*}
&\text{ If } U \text{ and } V \text{ are independent, and} \\
&D = U \cdot V \\
&\text{then} \\
&E[D] = E[U] \cdot E[V] \\
\end{align*}
$$


## Special case

+ If we create a new random variable by multiplying a constant, say  $u$
$$
\begin{align*}
&D = u \cdot V \\
&\text{then} \\
&E[D] = E[u] \cdot E[V] = u \cdot E[V] \\
\end{align*}
$$

## Example

$$
\begin{align*}
&V = \text{Weight time in minutes}\\
&D = \frac{1}{60} \cdot V = \text{Weight time in hours} \\
&\text{then} \\
&E[D] = \frac{1}{60} \cdot E[V] \\
\end{align*}
$$

## Expectation

+ If we create a new random variable with function transformation, 
$$
\begin{align*}
&D = g(V) \\
&\text{then} \\
&E[D] = E[g(V)] = \left\{\begin{array}{ll} \sum g(v)P(V = v) & \text{if discrete} \\ \int g(v)f_V(v)\, dv & \text{if continuous} \end{array}\right. \\
\end{align*}
$$


## Example

+ If we create a new random variable with log transformation, 

$$
\begin{align*}
&V = \text{Number of twitter followers}\\
&D = log(V) \\
&\text{then} \\
&E[D] = E[log(V)] = \sum_{v=0}^{\infty} log(v)P(V = v) \\
\end{align*}
$$

## Expecation

Suppose

$$g(V) = (V - E[V])^2$$

## Expecation

The expectation

$$E[g(V)] = E[(V - E[V])^2]$$

is a special quanity called the **variance**.

## Variance

$$\begin{align*}
V[X] &= E[(X - E[X])^2]\\
&= E[X^2] - E^2[X]\\
\end{align*}$$

$$\text{Notation: } E^2[X] = (E[X])^2$$

## Variance

If $c$ is a constant and $U$ is a random variable, 

+ What is $V[cU]$?
+ What is $V[c + U]$?

If $U$ and $W$ are independent random variables,

+ What is $V[U + W]$?

## Another special expecation

### Covariance

$$ COV[U,W] = E\left[\,(U - E[U])\,(W - E[W])\,\right]$$
 
+ If we create a new random variable with function transformation, 

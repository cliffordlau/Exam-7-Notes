# A7 Testing the Assumptions of Age-to-Age Factors - G. Venter

## Cliff's Summary

Standards used in this paper

* The $n$ for this paper excludes the first column

* Coefficient $> 2 \sigma$ is significant

Know the adj SSE, AIC and BIC

Know the 6 implications

1) Statistical significance of $f(d)$

2) Is there a better estimate for $q$ than $f \times c$

    * [Number of parameters](#para-num)
    
    * [BF parameters](#bf-para)

3) Check residuals against $c(w,d)$

4) Stability of $f(d)$ down the column

5) No correlation among columns

    * Know the calculation for test

6) No particularly high or low diagonals


### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Concepts**

* 2011 #4: Implication 1
* 2012 #5: Mack assumptions

**Implication Tests**

* 2014 #4: Implication 5 correlation tests
* 2015 #5: Implication 5 correlation tests

## Definitions and Assumptions

**Definitions**

| Notations | Definitions |
| --------- | ----------- |
| $w$       | AYs         |
| $d$       | Dev period; $d=0$ is age @ end of year 1  |
| $c(w,d)$  | Cumulative losses for AY $w$ age $d$ |
| $q(w, d+1)$ | Inc losses for AY $w$ age $d$ to $d+1$ |
| $f(d)$    | Col parameters; LDFs or % paid; applies to whole col |
| $h(w)$    | Row parameters; Ult losses; applies to whole row |

**Mack's assumptions**

1) $\operatorname{E}[q(w,d+1) \mid \text{Data to } w+d] = f(d) \: c(w,d)$

    * Expected incremental development is $\propto$ reported losses

2) $c(w,d)$ is $\perp\!\!\!\perp$ of $c(v,g)$ $\forall$ $d,g,v,w$ given $v \neq w$

    * AY's losses are $\perp\!\!\!\perp$ of other AYs' losses

3) $\operatorname{Var}[q(w,d) \mid \text{Data to } w+d] = a[d,c(w,d)]$

    * Variance of incremental losses is a function of reported losses and age
    
    * Different $a(\cdots)$ change the $\hat{f}$ estimate
    
    * Mack assumes $\operatorname{Var}(q) = ac$, variance is $\propto$ cumulative losses
    
        * $f = \dfrac{\sum_w c \frac{q}{c}}{\sum_w c}$
        
        * Volume weighted LDF - 1

## 6 Testable Implications

Compare different fit of the models based on adjusted $SSE$ (actual vs projected x 1st column)

1) $\dfrac{SSE}{(n-p^2)}$

2) $AIC \approx SSE \times e^{2p/n}$

    * Can be too permissive of over-parameterization for large data sets

3) $BIC \approx SSE \times n^{p/n}$

* $n =$ # of predicted data points **EXCLUDING 1st column**

    * Exclude because when we do reserving we don't predict anything from the first column

* $p =$ # of parameters

* $SSE = \sum (A - E)^2$

    * Here you exclude the first column when calculating the difference

***

**6 Testable Implications**

1) Statistical significance of $f(d)$

2) Is there a better estimate for $q$ than $f \times c$

3) Check residuals against $c(w,d)$

4) Stability of $f(d)$ down the column

5) No correlation among columns

6) No particularly high or low diagonals

## Implication 1: Significance of Factors

Check if the coefficient is $> 2 \sigma$ for 95% sure they are $\neq 0$

* Can do $1.65 \sigma$ for 90% confidence

## Implication 2: Superiority of Alternative Emergence Patterns

### Parameters

Alternative projection on a $m \times m$ triangle

<a name="para-num"></a>

| $\mathbf{q(w,d)}$ | Parameters | Comments |
| ------ | ---------- | --- |
| $f(d) c(w,d) + g(d)$ | $2m - 2$ | e.g. Least Squares |
| Chainladder | $m - 1$ | | 
| $f(d)h(w)$ | $2m-2$ | e.g. BF |
| $f(d)h$ | $m-1$ | e.g. Cape Cod |

* The -2 for the BF is due to $f(0)$ and constant

* Can further reduce parameters by combining some row and column parameters

* If BF is better $\Rightarrow$ Loss emergence is more accurately represented as fluctuating around a proportion of expected ultimate losses rather than proportion of reported losses

* Cape Cod works when the loss ratio is stable

### Variance Assumptions

Minimize sum of squared error for the optimal parameters:

* e.g. error term for BF: $\varepsilon(w,d) = q(w,d) - f(d)h(w)$

Different variance assumption for $\varepsilon$ $\Rightarrow$ different parameters

$\operatorname{Var}(\varepsilon) = f^p h^q$

* $p$ & $q$ typically in (0,1,2)

* Weights will be $\dfrac{1}{f^p h^q}$ (inversely proportional to variance)

* $f(d)$ = weighted average of $\frac{q}{h}$

* $h(w)$ = weighted average of $\frac{q}{f}$

#### BF

<a name="bf-para"></a>

| Method | $\mathbf{\operatorname{Var}(q)}$ | $\mathbf{f(d)}$: Col Parameters | $\mathbf{h(w)}$: Row Parameters |
| ------------------ | ------------------ | ------------------ | ------------------ |
| BF (Constant Var, Least Square) | $a(d); p=q=0$ | $f(d) = \dfrac{\sum_w h^2 \frac{q}{h}}{\sum_w h^2}$ | $h(w) = \dfrac{\sum_d f^2 \frac{q}{f}}{\sum_d f^2}$ |
| Cape Cod | $a(d); p=q=0$ | $f(d) = \dfrac{\sum_w h^2 \frac{q}{h}}{\sum_w h^2}$ | $h = \dfrac{\sum_\Delta f^2 \frac{q}{f}}{\sum_\Delta f^2}$ |
| BF (Var $\propto$ $fh$)| $a(d) \cdot f \cdot h; p=q=1$ | $f^2(d) = \dfrac{\sum_w h (\frac{q}{h})^2}{\sum_w h}$ | $h^2(w) = \dfrac{\sum_d f (\frac{q}{f})^2}{\sum_d f}$ |

* $f(d)$ is % losses paid @ $d$

    * Estimate by $\frac{q}{h}$

* $h(w)$ is estimate of ultimate losses

    * Estimate by $\frac{q}{f}$

* $f(d)$ $\sum \downarrow$; $h(w)$ $\sum \rightarrow$ (for the constant var BF)

* Need to seed one of them and iterate until convergence

* Use the above to estimate the parameters and then calculate the unpaid

* When combining parameters, don't count the $f(0)$ and always subtract 1

#### Chainladder

$\operatorname{E}[q(w,d+1)] = f(d)c(w,d)$

* $n = \sum \limits_{i=1}^{m-1} i = \dfrac{m(m-1)}{2}$ = predicted data point?

* $p=m-1$ since we dont' predict the first column

* $m =$ dimension

| $\mathbf{\operatorname{Var}(q)}$ | $\mathbf{f(d)}$ |
| ---------------------------- | ---------------------------------- |
| $a(d) c$      | $f(d) = \dfrac{\sum c \frac{q}{c}}{\sum c}$       |
| $a(d) c^2$    | $f(d) = \dfrac{\sum 1 \frac{q}{c}}{\sum 1}$       |
| $a(d)$        | $f(d) = \dfrac{\sum c^2 (\frac{q}{c})}{\sum c^2}$ |

* $f(d)$ LDF minus 1

    * Estimate by $\frac{q}{c}$
    
## Implication 3: Linearity

The forecast incremental losses doesn't have to be linear

Test for linearity to make sure the residuals are not a sequence of positive then negative and vice versa

## Implication 4: Stability

Look at empirical LDFs $f(d)$ down a column

* Use the entire history if factors are stable

* Take more recent average if unstable or follow a trend

## Implication 5: No Correlation on Columns

Calculate Pearson correlation for every pair of columns with at least 3 LDFs

* This is a test on the LDFs

* Test with only 2 LDFs will either be 1 or -1

Correlation $r = \dfrac{\sum \tilde{x} \tilde{y}}{\sqrt{\sum \tilde{x}^2\sum \tilde{y}^2}}$

* $\tilde{x} = x - \bar{x}$

* $\tilde{y} = y - \bar{y}$

Test statistics: $T = r \sqrt{ \dfrac{n-2}{1-r^2} }$

* $T \sim t_{n-2}$

* Look up the t-value from table for 90%

* If the absolute value of $T <$ table value $\Rightarrow$ Not correlated

Perform test for all columns (with 3 or more LDFs pair)

* Correlations within the triangle if more than $0.1 m + \sqrt{m}$ pairs are correlated

* m = # of pair tested

## Implication 6: No High of Low Diagonals

Run regression that includes a variable for each diagonal

Each $q(w,d)$ is regressed against the cumulative losses at the prior period + dummy variable for which diagonal it is in

* $q(w,d) ~ c(w,d-1) + diagonal_{year}$

* If diagonal significatly high or low $\Rightarrow$ Dummy variable should have a statistically significant coefficient

* Same criteria where it is significant if coefficient is double the $\sigma$

Deficiceny of this method is that the diagonal effect is additive

* More likely to see multiplicative impact. e.g. from inflation

* This can be implement with a regression on the logarithm of the losses

### Diagonal Trend as Inflation

Model $q(w,d)$ with a diagonal parameter $w+d$

$\operatorname{E}[q(w,d)] = f(d)h(w)g(w+d)$

Model constant CY trend to reduce the parameters:

$g(w+d) = (1+j)^{w+d}$

## Past Exam Questions

n/a
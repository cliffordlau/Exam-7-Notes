# A8 LDF Curve-Fitting and Stochastic Reserving: A Maximum Likelihood Approach - D. Clark

## Cliff's Summary

Memorize the CDF for [loglogistic](#Loglogistic) and [weibull](#Weibull)

We use the **average age** of the period here

Know how to calculate reserves given the $G(x)$ and for each of the 2 methods given:

* Growth function distribution and parameter (might have to estimate)

* LDF or Cape Cod

* Data (e.g. paid to date for each AY)

* Test for truncation by looking at age twice the triangle

Other use of the model

### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Reserve Calculation**

* $\star$ [2011 #2](#2011-2): Cape Cod truncated and reserve CoV
* 2012 #2: Cape Cod method and reserve CoV
* $\star \star$ [2013 #3](#2013-3): LDF method with $\sigma^2$ calc
* 2013 #10: Stanard-Buhlmann
* 2014 #5: plug and play LDF and Cape Cod method with Benktander
* [2015 #2](#2015-2): LDF Method and concept where if we switch to Cape Cod the CoV should go down as it incorporates additional information

**Other**

* 2012 #3: Residual plot from projection and assumptions

## Expected Loss Emergence

$x =$ **average age** of AY (e.g. 6mo for the most recent instead of 12mo) <span style="color:red">Note</span>

% paid to date growth function: $G(x \mid \omega, \theta)$ <span style="color:red; background-color:yellow">Memorize Formula</span>  

* <a name="Loglogistic"></a>**Loglogistic**: $G(x \mid \omega, \theta) = \dfrac{x^{\omega}}{x^{\omega} + \theta^{\omega}}$

* <a name="Weibull"></a>**Weibull**: $G(x \mid \omega, \theta) = 1- \operatorname{exp}\left\{ { - \left( \dfrac{x}{ \theta } \right)^{\omega}} \right \}$

* The curves move smoothly from 0 to 1

Advantages:

* Uses only 2 column parameters: $\theta$ for mean; $\omega$ for s.d.

* Can use data @ different age

* Output is a smooth curve $\Rightarrow$ Can interpolate between ages and estimates a tail

***

**Expected Ultimate Loss**

Method 1: Cape Cod $Premium_{AY} \times ELR$

* Having a single row parameter $h$

Method 2: LDF $ULT_{AY}$

* Having a $h(w)$ for each row

**Estimate Future Emergence**

Method 1: $[G(y \mid \omega, \theta) - G(x \mid \omega, \theta)] \times [Premium_{AY} \times ELR]$

Method 2: $[G(y \mid \omega, \theta) - G(x \mid \omega, \theta)] \times ULT_{AY}$

## Distribution of Actual Loss Emergence and Maximum Likelihood

Parameter estimation with MLE

### Process Variance

For each incremental loss, $\operatorname{Var}(c_i) \propto \operatorname{E}[c_i]$

* $\operatorname{Var}(c_i) = \sigma^2 \operatorname{E}[c_i]$

* $c_i$ is the **incremental** loss here <span style="color:red">Note</span>

* $\sigma^2$ is the **same for the entire triangle**

$\dfrac{Variance}{Mean} = \sigma^2 = \dfrac{1}{n-p}\sum\limits_{i \in \Delta}^n\dfrac{(c_i - \mu_i)^2}{\mu_i}$ <span style="color:red; background-color:yellow">Memorize Formula</span>

* $n =$ # of data points in triangle

* $p =$ # of parameters

    * Cape Cod $p=3$ ($\omega, \theta, ELR$)
    * LDF $p=2 +$ # of AYs ($\omega, \theta,$ row parameters)

* $c_i =$ actual incremental loss emergence

* $\mu_i =$ expected incremental loss emergence

***

Variance relationship in other papers

* Mack (1994):  
CL method assumes $\operatorname{Var}\left (c_{i,k+1} \mid c_{i,1} \cdots c_{i,k}\right ) = \alpha_k^2 \: c_{i,k}$  
Constant is same for each column (development period)
n includes all here?

* Venter Factors:  
BF method assumed variance $\propto$ expected losses in a cell
Constant varied by column
n = predicted?

***

$C_i \sim ODP(\lambda_i, \sigma^2)$

* Use ODP so that variance $\neq$ mean

* $C_i = \sigma^2 X$ where $X \sim Poi(\lambda_i)$

* $\operatorname{E}[C_i] = \sigma^2 \lambda_i = \mu_i$

* $\operatorname{Var}(C_i) = \sigma^2 \mu_i$

Potential issue with ODP is that some granularity is lost since reserves are estimated in multiple of $\sigma^2$. However $\sigma^2$ is generally small so little precision is lost

### MLE 

<span style="color:red; background-color:yellow">Not super testable</span>

$l = \sum \limits_{i \in \Delta} c_i \operatorname{ln}(\mu_i) - \mu_i$ <span style="color:red; background-color:yellow">Memorize Formula</span>

* $\sigma^2$ was assumed to be a known constant

* Plug in $\mu_i$ for the different methods and then maximize $l$ by $\dfrac{\partial l}{\partial ELR} = 0$ or $\dfrac{\partial l}{\partial ULT_{AY}} = 0$

### Parameter Variance

<span style="color:red; background-color:yellow">Not super testable</span>

Covariance matrix = $\Sigma = -\sigma^2 \times I^{-1}$

* Information matrix $I$: Use 2^nd^ derivative matrix of $l$ vs each parameter

* $3 \times 3$ matrix for Cape Cod

* $(n+2) \times (n+2)$ for LDF

## Variance of the Reserves

**Process Variance of $R$**

$\sigma^2 \sum_i \mu_i$

* Technically testable if given $\sigma^2$ <span style="color:red">Not sure how</span>

**Parameter Variance of $R$**

$\operatorname{Var}(\operatorname{E}[R]) = (\partial R)'\Sigma (\partial R)$

* $\partial R$ = vector that is the derivative of the reserve by each parameter

* Calculation heavy, not testable

## Key Assumptions

1) Incremental losses $iid$

    * Can test this by looking at residuals

2) $\dfrac{Variance}{Mean}$ scale parameter $\sigma^2$ is fixed and known

    * Technically this should be estimated with the other parameters but will makes things intractable

3) Variance estimates are based on the approximation to the Rao-Cramer lower bound

    * Variance based on information matrix $I$
    
    * $I$ is exact only when using linear functions
    
    * In our case this is simply a lower bound
    
    * We are using approximated parameters

The above temper the volatility in the model, actual results can be more variable

Model only works for positive expected incremental losses. But a negative loss here or there is fine as well

## LDF Method (Method 2)

Can use either [Loglogistic](#Loglogistic) or [Weibull](#Weibull) for $G(x)$

Estimate $\theta$ and $\omega$ with MLE

$\mu = ULT_{AY} \times [G(y) - G(x)]$

Calculate $\sigma^2 = \dfrac{1}{n-p}\sum\limits_{i \in \Delta}^n\dfrac{(c_i - \mu_i)^2}{\mu_i}$

* n = all data points (not just the predicted like in Venter)

* p = 2 + 10 AYs

* This is for **incremental** losses

**Residual Review**

Residuals = $r_i = \dfrac{c_i - \mu_i}{\sigma \sqrt{\mu_i}}$

* Divide by the square root of the variance $\sigma^2 \mu$ for ODP?

Plot $r$ vs age, expected loss (test constant var/mean assumption)

### Reserve Estimate

**Untruncated**

1) Get G(x): % paid(reported) to date
2) Paid to date (reported to date) $\div$ G(x) = Ultimate

**Truncated** @ age $x_t$

To cut of the tail at some point and stop the development

Remember to subtract 6 months

Use $G'(x) = \dfrac{G(x)}{G(x_t)}$ instead just like above

***

Process Variance = $\sigma^2 \sum_i \mu_i = \sigma^2 \times \text{Unpaid}$

Parameter variance is huge and computational intensive as it requires inverting a big matrix

## Cape Cod Method (Method 1)

Needs exposure base (e.g. on-level and trended EP) that allow us to assume a constant ELR across AYs

Estimate $\theta$ and $\omega$ with MLE

Estimate ELR with below:

$ELR = \sum_{AY} \dfrac{\text{Losses Paid to Date}}{\underbrace{G(x)}_{\text{Expected portion paid}} \times Premium}$

* Do not truncate when calculating ELR

$\mu = ULT_{AY} \times [G(y) - G(x)]$

Calculate $\sigma^2 = \dfrac{1}{n-p}\sum\limits_{i \in \Delta}^n\dfrac{(c_i - \mu_i)^2}{\mu_i}$

* n = all data points (not just the predicted like in Venter)

* P = 3

Check if the assumption of one expected LR is reasonable by looking for any upward or downward trends in the ultimate LR

### Reserve Estimate

**Untruncated**

Reserve = On-level Premium $\times ELR \times [1 - G(x)]$

**Truncated** @ age $x_t$

Reserve = On-level Premium $\times ELR \times [(G(x_t) - G(x)]$

***

Similar story for the process variance and parameter variance as the LDF method.

The Covariance matrix is smaller just $3 \times 3$

Parameter variance is smaller than the LDF method since we have more information in the Cape Cod method (?)

## Other Use of Model {.tabset}

### Variance of Prospective Losses

Estimate variance for the **next u/w year**

Need to be given the $\operatorname{Var}(ELR)$

Process Variance: $\sigma^2 R$

Parameter Variance: $\left(\sqrt{\operatorname{Var}(ELR)}\times Premium \right)^2$

Total Variance: Process Variance + Parameter Variance

CoV: $\dfrac{\sqrt{Total \: Variance}}{R}$

### Calendar Year Development

Calculate $[G(x+12) - G(x)] \times Ultimate$

No truncation here

Sum for all AYs and compare with actual calendar year emergence

Can calculate the s.d. to see if it's in range (process var is still $\sigma^2 \times$ estimate)

### Variability in the Discounted Reserves

CV will be smaller since the tail with the most variability gets discounted the most

## Comments and Conclusion

* Can use data in table format

* Use the CV from the model even if select a different reserve

    * Not okay since you don't trust the reserve estimate
    
    * Okay since the s.d. is a selection and the CoV from this model is a reasonable basis
    
* Curve was selected because:

    * The move smoothly from 0 to 1
    
    * Closely match empirical data
    
    * 1st and 2nd derivative are calculable
    
    * Others can be used as well
    
## Past Exam Questions

<a name="2011-2"></a>
![](questions/2011-2Q.png)
![](questions/2011-2A.png)

<a name="2013-3"></a>
![](questions/2013-3Q.png)
![](questions/2013-3A.png)

<a name="2015-2"></a>
![](questions/2015-2Q.png)
![](questions/2015-2A.png)
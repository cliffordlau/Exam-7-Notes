# A10 Bootstrap Modeling: Beyond the Basics - Shapland Leong

## Cliff's Summary

Flow of the paper: Parametize $\rightarrow$ Bootstrap $\rightarrow$ Practical Issues $\rightarrow$ Correlations

Remember this uses **incremental** triangles

**Parametize**

$m_{wd} = \operatorname{exp} \left [\alpha_w + \sum_j \beta_j \right]$

$\operatorname{Var}[q(w,d)] = \phi m_{wd}^z$

Parametize with GLM or Wtd average

**Bootstrap**

Create sample trianlge from mean and randomly sampled residuals $\Rightarrow$ Estimate parameters from sampled triangle $\Rightarrow$ Calculate mean and variance of the sampled triangle $\Rightarrow$ Draw losses from gamma

Dispersion factor with [standard](#std-dispersion), [England & Verrall](#EV-dispersion), and [standardized](#standardized-dispersion)

**Practical Issues**

* Negative incremental values (fit and simulate)
* Non-zero sum of residuals
* N-year wtd average
* Missing values
* Outliers
* Heteroskedasticity
* Partial latest year exposure or partial diagonal
* Expsoure adjustment
* Parametric bootstrap

**Diagnostics**

**Other**

* Multiple models
* Model outputs
* Correlations

### Types of Exam Questions

**Exercises**

1. $\star$ Use simplied GLM and then back out the GLM parameters
2. Reduce parameters
3. Minimize square error for GLM
4. Benefit of simplified GLM
5. Residuals
6. Dispersion
7. Dispersion with hat matrix adj
8. Simulate loss
9. Setup GLM
10. Negative values
11. Simulat ngative
12. Partial triangle
13. Stratified
14. Dealing with correlation
15. Outliers

**Practical Issues**

* 2013 #7: negatvie values
* 2014 #7: List 4 practical issues and solutions
* 2015 #10: Heteroscedasticity, why important, adjustments description
* 2015 #11: Negative values, outliers, exposure level

**Diagnostics**

* $\star$ 2014 #9: Evaluate the results given mean unpaid, s.e., CoV by AYs

## Introduction

Same notations as Venter

* $q(w,d)$: incremental loss for AY $w$ from age $d-1$ to $d$

* $c(w,d)$: cumulative loss

**Advantages**

* Generates a distribution of the estimate of unpaid claims

* Can be tailored to statistical features of our data

* Reflects that loss dist^n^ are usually skewed to the right

**Disadvantages**

* Takes more time to create, but okay once set up

Chainladder assumes 1) LDFs are the same for each row 2) Each AY has a parameter representing it's value, e.g. CL project based on level of losses to date

### Loss Distribution

![]("figures/Exam-7-Notes-1.png")

<a name="loss-dist"></a>
**Mean** losses for $q(w,d)$:

$m_{wd} = \operatorname{exp} \left [\alpha_w + \sum_j \beta_j \right]$

* $\alpha_i$ and $\beta_j$ are selected to minimize error between $\operatorname{ln}(actual) - \operatorname{ln}(forecast)$

Equivalence for using Venter notation:

* $h(w) = e^{\alpha}$

* $f(d) = e^{\sum \beta}$

**Variance**

$\operatorname{Var}[q(w,d)] = \phi m_{wd}^z$

* $\phi$: Dispersion factor

    * Estimate from residual
    
* $z$: Error distribution

    * Paper focus on $z = 1$ for Over Dispersed Poisson (ODP)

| z | Distribution     |
| - | ---------------- |
| 0 | Normal           |
| 1 | Poisson          |
| 2 | Gamma            |
| 3 | Inverse Gaussian |

## Parameterize with GLM

For a $3\times 3$ triangle:

**Log Actual incremental losses**

$Y = \begin{bmatrix}
    ln[q(1,1)] \\
    ln[q(2,1)] \\
    ln[q(3,1)] \\
    ln[q(1,2)] \\
    ln[q(2,2)] \\
    ln[q(1,3)] \\
\end{bmatrix}$

**Solution Matrix $W$**

$\begin{array}{ccccc}
  W & = & X &\times & A \\
  & & \alpha_1 \:\:\: \alpha_2 \:\:\: \alpha_3 \:\:\: \beta_2 \:\:\: \beta_3 & &\\
  \begin{bmatrix}
    ln[m_{11}] \\
    ln[m_{21}] \\
    ln[m_{31}] \\
    ln[m_{12}] \\
    ln[m_{22}] \\
    ln[m_{13}] \\
  \end{bmatrix}
    & =
      &
      \begin{bmatrix}
        1 & - & - & - & - \\
        - & 1 & - & - & - \\
        - & - & 1 & - & - \\
        1 & - & - & 1 & - \\
        - & 1 & - & 1 & - \\
        1 & - & - & 1 & 1 \\
      \end{bmatrix}
        & \times
          &
          \begin{bmatrix}
            \alpha_1 \\
            \alpha_2 \\
            \alpha_3 \\
            \beta_2 \\
            \beta_3 \\
          \end{bmatrix}
\end{array}$

* $W =$ Solution Matrix

* $X =$ Design Matrix

    * Defines the parameters used to estimate the losses

* $A =$ parameters

    * Solve for $A$ by minimizing the difference^2^ (SSE) between $W$ and $Y$
    
    * Use recursive Newton-Raphson method to find the best fit parameters
    
    * Paper did no cover in what sense these parameters are best fit (Not SSE?)

## Simplified GLM

GLM model = Chainladder w/ volume-weighted averages when:

* Variance $\propto$ Mean
* $\varepsilon \sim$ Poisson; Poisson error
* Parameter for each row and column (x 1^st^ column)

Benefits:

* Replace GLM fitting with much simpler calculation
* LDFs are easier to explain
* Still works even when there are negative incremental values

### Residuals (Pearson)

<a name="pearson-res"></a><span style="color:red; background-color:yellow">Memorize Formula</span>  
$\begin{array}
  Rr_p & = & \dfrac{A - E}{\sqrt{\operatorname{Var}(A)}} & \\
  & = & \dfrac{q(w,d) - m_{wd}}{\sqrt{\phi m_{wd}}} & \text{Mean & Var Assumptions Above}\\
  & \propto & \dfrac{q(w,d) - m_{wd}}{\sqrt{m_{wd}}} & \text{Since }\phi \text{ is constant for all}\\
\end{array}$

* [Mean & Var](#loss-dist)

* Note the residual for the 2 corners of the triangle are going to be 0 because only the row parameter or column parameter are used

## Bootstrap Procedures

Once we have the mean and residuals in each cell, repeat below:

1) Create a sampled $triangle^*$ from the residuals and the means

    * Sample from residuals since data needs to be $iid$ for bootstrap
    
    * Use [Pearson residuals](#pearson-res)
    
    * Simulated loss: $q^*(w,d) = m_{wd} + r_p \sqrt{m_{wd}^z}$ <span style="color:red; background-color:yellow">Memorize Formula</span>
    
        * Simulate by sampling residuals with replacement
    
    * Estimate $\phi$ for step 4: $\phi = \dfrac{\sum r^2}{n-p}$
        
        * This can vary see [Dispersion Factor](#dispersion) section
        
2) Determine parameters from $triangle^*$: $(\alpha_i, \beta_j)$

    * Use either GLM or Simplified GLM to project ultimate loss

3) Calculate mean and variance: $(m_{wd}, \phi m_{wd})$

    * For GLM use $m_{wd} = \operatorname{exp} \left [\alpha_w + \sum_j \beta_j \right]$
    
    * For Simplified GLm, back out the $c^*(w,d)$ by $\dfrac{Ult_w}{CDF_d}$ then get the $m_{wd}$
    
    * For variance $\phi m_{wd}^z$

4) Add process variance: draw losses from $Gamma(m_{wd}^*,\phi m_{wd}^*)$

    * Randomly draw from the distribution for each cell

5) Calculate simulated unpaid: sum of bottom half of triangle

## Dispersion Factor
<a name="dispersion"></a>

<a name="std-dispersion"></a>**Standard**

$\phi = \dfrac{\sum r_{wd}^2}{n-p}$

* $n =$ # of data points (including first column)

* $p =$ # of parameters

    * $2m-1$: one for each row, one for each column minus first column
  
<a name="EV-dispersion"></a>**England & Verrall**

Degrees of freedom adjustments

$\phi^{EV} = \dfrac{\sum \left(r^{EV}_{wd}\right)^2}{n-p}$

* $\begin{array}{llllc}
    r_{wd}^{EV} & = & r_{wd} &\times &f \\
    & = & r_{wd} &\times &\sqrt{\dfrac{n}{n-p}}\\
  \end{array}$

<a name="standardized-dispersion"></a>**Standarized Residuals**

Pinheiro proposed to standardized residuals so they all have same variance

$\phi^H = \dfrac{\sum \left(r_{wd}^H \right)^2}{n}$

* $\begin{array}{lllc}
    r_{wd}^H &= r_{wd} &\times &f_{wd}^H \\
    &= r_{wd} &\times &\sqrt{\dfrac{1}{1-H_{ii}}} \\
  \end{array}$

* $H_{ii}$ is the diagonal of the Hat Matrix Adjustment Factor: $H = X (X^TWX)^{-1}X^TW$

    * The diagonal is labelled by going down the column of the triangle from left to right
    
    * The denominator might actually be $n-2$ but for the purpose of exam just use $n$ as stated in the paper
    
## Variations to the ODP Bootstrap

**Use incurred loss triangle**

* Convert ultimate from incurred to a payment stream based on paid analysis
* Correlate the simulations from the 2 method so that if we have large payment @ an older age, the incurred should be large as well

**Use BF Ult for recent years**

* Have the a-priori varies based on some $\sigma$

**Generalizing the ODP Model**

* Reduce # of parameters

    * Combine accident years
    
    * Use just 1 development year since the column parameters is just a measure of decay and can be used for multiple columns
    
* Add calendar year trend parameter $\gamma_k$ for each column except for the first

* Must use GLM to determine the parameters

## Practical Issues

### Negative Incremental Values

How to deal with negative incremental values in the triangle

#### Model Fitting

**Method 1**: $-ln(-q(w,d))$

* Works when there are a few cells with negatives

* Doesn't work when the column sum to a negative value

**Method 2**: Add a constant $\Psi$

* Add $\Psi$ to every cell before running GLM then subtract $\Psi$ from each incremental loss once the means are calculated

* $ln[m_{wd} + \Psi] = \eta_{wd}$

* Can use this method combined with method 1 to take care of the extra large negative ones

**Method 3**: Simplified GLM

* Use Chainladder with volume weighted average LDFs

* Only if the assumptions fit

* Need to make use the absolute value for the residual and re-sampling formula:

    * $r_{wd} = \dfrac{q(w,d)-m_{wd}}{\sqrt{abs(m_{wd})}}$

    * $q^*(w,d) = m_{wd} + r_p \sqrt{abs(m_{wd})}$
    
#### Simulating Negative Values

**Adjustment to the *Gamma* Distribution**

Use $Gamma(-m_{wd}, -\phi m_{wd}) + 2m_{wd}$

* Maintaining the right tail but also having the mean of $m_{wd}$

* Just doing $-Gamma(-m_{wd}, -\phi m_{wd})$ doesn't work since the tail would be flipped

**Extreme Outcomes from Negative Values**

Column with negative mean can results in vary large LDFs, 4 options to deal with that:

1) ***Remove the extreme iterations***

    * But beware of understating the the likelihood of extreme outcomes

2) ***Recalibrate*** the Model

    * Review data used and parameter selection (e.g. remove the first AY as it does not represent current behavior)

3) ***Limit Incremental Losses Below 0***

    * Either in the original triangle, sampled or simulated loss (process var step); Replace with 0

    * Can just do it in certain columns

4) **Understand**

    * Understand why this is happening. e.g. if due to S&S then you can just model them separately and then correlated them during simulation

### Non-Zero Sum of Residuals

Since we assume $iid$ and constant $\sigma$, the sum of residuals should be 0

Not necessarily the case since this is just a sample

Consequence is that the simulated outcomes will be higher than the means

2 Options

* Keep it if we believe this to be characteristics of the data set

* Add a constant to each residual so that it sums to 0 and then sample from the adjusted residuals

### Using N-year Weighted Average

**GLM**

* Exclude the older diagonals so that we have $N+1$ diagonals of data to get $N$ diagonals of LDFs

* Will have less CY parameters

**Simplified GLM**

1) Get *N*-year weighted average

2) Exclude the diagonals not used for the LDFs ***when determining the residuals***

3) Sample residuals for the entire triangle ***when sampling for bootstrap*** since you need cumulative losses for each row

***

The 2 methods will results in different results

* GLM: Models the incremental losses in the trapezoid

* Simplified GLM: Model the same losses but in relation to the cumulative losses, which include the non-modeled losses in the diagonals excluded

### Missing Value

Solution

* Estimate from surrounding values

* Modify LDFs to exclude missing value

Won't have residual for this cell

### Outliers

Remove extreme values that are not representative of the variability of the losses

* Remove a whole row or,

* Just remove the value and treat them as missing values or,

* Exclude in LDFs but continue to use them when calculating residuals and use them for the re-sampling

### Heteroskedasticity

Non constant variance (bootstrap assumes residuals are $iid$)

**Stratified Sampling**

Split the triangle into groups with similar variance and only sample residuals that are in the group

*Cons*: each group may not be that large

**Hetero-Adjustment**

Group the residuals then calculate the $\sigma$ of the residuals in each group and scale up

Hetero-adjustment factor: $h^i$ = the largest $\sigma$ $\div$ each group's $\sigma$

$r_{wd}^{i,H} = r_{wd} \times f_{wd}^H \times h^i$

* Residual $\times$ Hat Matrix Factor $\times$ Hetero Factor

Need to divide the sampled residual by $h^i$ to reflect the variability of group $i$

* $q^{i*}(w,d) = m_{wd} + \dfrac{r^{i*}}{h^i}\sqrt{m_{wd}}$

### Heteroecthesious Data

Accident years have different level of exposures

**Partial First Development Period**

Only want partial accident year

No impact to residuals for bootstrap

2 options:

* Reduce the mean of the incremental cells by pro ration in the process variance step

* Prorate after the process variance step

**Partial Last Calendar Period**

Latest diagonal is partial

* Simplified GLM

    * Determine LDF excluding latest diagonal then interpolate LDFs for ultimate
    
* GLM

    * Adjust the exposure in the last diagonal to make them consistent with the rest of the triangle (probably means adjusting annualizing the loss)

Then prorate the losses similar to the first scenario

### Exposure Adjustment

Consider dividing the losses by the exposure in each AY if there are significant changes in exposure and model pure premium

Multiply the PP results by the exposure after the process variance step

### Parametric Bootstrapping

Might not have enough data to sufficiently represent the tail

Fit a distribution to the residual and sample from the distribution instead

## Diagnostics {.tabset}

Judge the quality of the model

1) Test Assumptions in model

2) Gauge quality of model fit

3) Guide the adjustments of model parameters

### Residual Graphs

Graph residuals vs CY, AY, Age, forecast loss

Want to see random variability around zero

### Normality Test

Normality is not required, only need this if we're doing parametric bootstrap with normal distribution

Plot residuals against the normal best fit based on the percentiles

Use p-value > 5% as the test

Or use something that penalize number of parameters

* $AIC = 2p + n \left [ 1 + \operatorname{ln}(2\pi\dfrac{RSS}{n})\right]$

* $BIC = n \operatorname{ln}\left( \dfrac{RSS}{n}\right) + p \operatorname{ln}(n)$

* $RSS$ = actual residual - expected residual from normal

### Outlier

Remove true outliers but do not want to remove points that are realistic extreme scenarios

Use box & whisker plot

* Shows 25%ile to 75%ile
* Whiskers are 3 times the inter quartile range

### Parameter Adjustments

Test model with different sets of parameters

* Don't need unique parameter for each row and column

### Review Model Results

Read summarized output by AYs

* Mean, s.e., CoV, Min, Max, Median

* The all year s.e. should be greater than any individual year

* The all year CoV should be less than the CoV for any individual year

* CoV should be highest for older years due small mean unpaid

* CoV also high for most recent AY due to higher volatility

    * Larger parameter uncertainty or volatility from CL method
    
* Check min max for reasonability

For the triangles:

* Check incremental means as well in triangle form

* Check s.d. of incremental values

## Using Multiple Models

Use different methods (Paid/Inc'd Dev, BF, etc) by assigning weights by AYs

**Method 1**:  
In the process variance step of bootstrap, use the same underlying U(0,1) to draw from each model then weight the models by the %

**Method 2**:  
Run each model independently for each simulation (i.e. use different U(0,1)) then for each AY use the weights to randomly select one of the modeled results. Results will be a mixture of the various models

Important to review the statistics in the above section for each output

Fit the unpaid claim distribution to Normal, LogNormal, and Gamma. Then compare with the fit based on the actual residuals on various statistics <a name="pearson-res"></a><span style="color:red">Not sure what distribution this is talking about</span>

### Other Model Outputs

**Estimated Cash Flow Results**

Since bootstrap generates simulation for each cell in the bottom half of the triangle we can use this to get cash flow forecasts by CY and the percentiles as well

**Estimated Ultimate Loss Ratio Results**

We can estimate the variability of ultimate loss ratio since we vary and simulate the whole "square"

**Distribution Graphs**

Draw a distribution of the simulated unpaid in a histogram

Can also smooth the histogram with Kernel density function

* For each point it takes a weighted average of the points around it; giving less weight to points further from it

## Correlation

Correlate the loss distribution over several LoB

* Multivariate distribution requires the same underlying distribution which doesn't work here for ODP

**Location Mapping**

When sampling the residuals, sample from the same place in the triangle for all the lines we want to correlate

Disadvantages:

* Requires all LoB to have the same size triangle with no missing values or outliers

* Cannot stress the correlations among the LoBs

**Re-Sorting**

Use Iman-Conover algorithms or Copulas

Advantages:

* Can accommodate different shapes and sizes

* Can make different correlation assumptions

* Can strengthen the correlation for extreme events (e.g. Copulas)

Calculate correlation matrix using Spearman's Rank Order

* Re-sorting based on the ranks of unpaid claims by AYs

***

Using residuals to correlate LoBs (Both location mapping  & re-sorting) are both liable to create correlations close to zero

Reserve Risk:

* Correlate total unpaid by correlating the incremental paid. May or may not be a reasonable approximation

Pricing Risk:

* Correlate loss ratios over time

* Not as likely to be close to zero

* Use different correlation assumption than for reserve risk

## Miscellaneous

**Model Testing**

Based on testing from General Insurance Reserving Oversight Committee, the ODP Bootstrap with England & Verrall residual out perform the Mack model by forecasting the 99%-ile better

* ODP losses only exceed 99%-ile ~3% of the time compare to Mack's 8-13%

**Future Research**

* Test ODP bootstrap on realistic data from CAS loss simulation model

* Expand ODP bootstrap with Munich Chainladder, claim counts and severity

* Research other risk analysis measures and use for ERM

* Use for SII requirements

* Research in correlation matrix (difficult to estimate)

## Past Exam Questions

n/a
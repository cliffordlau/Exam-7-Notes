# A5 Claims Development by Layer - R. Sahasrabuddhe

## Cliff's Summary

Setup base triangle and then convert the base LDFs to any layer

Main formulas to memorize:

* $LEV(X; \Phi \sim Exp(\theta)) = \theta \: \left[ 1 - \operatorname{exp}\left\{-\left(\dfrac{x}{\theta}\right)\right\} \right]$

* $\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{n\infty})}{LEV(X;\Phi_{ij}) \div LEV(B;\Phi_{nj})}
 \end{align}$

Know the assumptions used

### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Setup Base Triangle**

* 2013 #5: set up base triangle with trend and all

    * Can start trend from bottom left cell

## Introduction

**2 Key Ideas**:

1) Convert a triangle to one level of trend and layer of losses

    * This is then used to determine LDFs at this base layer
    
    
2) Convert LDFs at a Base layer to LDFs at any other layer

***

Claim size models is the distribution for individual claims

* Exponential in this paper

* Different distribution for each column in the triangle

* Requires a distribution of losses at each age, which can be difficult (Last section try to address this)

**Notation**

$B$: Base layer, LDFs are determined at this layer

$X$: Layer of interest, ultimately we want LDFs for this layer

$\Phi_{ij}$: Cumulative loss dist^n^ in row $i$ age $j$

$LEV(X; \Phi_{ij})$: Limited expected value, average loss with dist^n^ $\Phi_{ij}$ capped at $X$

$F_{ij}^X$: LDF to ultimate for cell $ij$ with losses capped at $X$

### 1. Setup Base Layer Triangle

Setup a consistent base layer triangle for LDFs selection

**Step 1**: Setup the trend triangle: Trend = AY Trend $\times$ CY Trend

Adjust for CY trend before calculating

* No adjustment needed if only AY trend is present <span style="color:red">Really?</span>

These are ground up trend, which is consistent if taken from external sources

Trend to the last row of the triangle

* Don't stop just at the diagonal

* The 1.000 typically starts at the top left corner but it doesn't have to

This applies the trend to cumulative loss which is problematic

* Cumulative trend depends on the incremental trend and the emergence pattern

**Step 2**: Determine *unlimited* mean for each cell in triangle (Avg sev paid to date)

i) Based on **mean** for the **latest AY** (bottom row)

    * $\operatorname{E}[C_{nj}] = \theta_j$

    * $C_{nj} \sim \Phi_{nj} = Exp(\theta_j)$
    
ii) **Detrend** back up from the bottom row to fill the whole square

    * Usually just need four points per the LDF conversion formula

**Step 3**: Calculate LEV for each cell in triangle $L$ and the last row for $B$

<span style="color:red;background:yellow">Memorize Formula</span>

$LEV(X; \Phi \sim Exp(\theta)) = \theta \: \left[ 1 - \operatorname{exp}\left\{-\left(\dfrac{x}{\theta}\right)\right\} \right]$

* Use the "square" of mean $\theta$ calculated from Step 2

**Step 4**: Calculate the adjusted triangle

Convert triangle of actual losses by dividing it's LEV at layer $L$ then times it's LEV at layer $B$

<span style="color:red;background:yellow">Memorize Formula</span>

$C_{ij}' = \underbrace{C_{ij}^L}_{\text{Cum paid @ L}} \times \underbrace{\dfrac{LEV(B;\Phi_{nj})}{LEV(L;\Phi_{ij})}}_{\text{ILF w/ on-level to }n}$

**Step 5**: Select base layer LDFs

### 2. Convert LDFs from Base Layer

Convert LDFs from base layer to LDFs at any other layer

At this step we should already have $F_{nj}^B$ selected from the base triangle created above

<span style="color:red;background:yellow">Memorize Formula</span>

$\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{n\infty})}{LEV(X;\Phi_{ij}) \div LEV(B;\Phi_{nj})}
 \end{align}$

* Without trend, you can basically just take the middle part as the LDFs

* However, we trust the LDF from the analysis of losses limited to $B$ more and less so with the distribution function $\Phi$

![](figures/Exam-7-Notes-13.png)

## LDFs for XS Layers

$\begin{align}
  F_{ij} = F_{nj}^B \times \frac{ \left[{\color{blue}{LEV(Y;\Phi_{i\infty}) - }} LEV(X;\Phi_{i\infty})\right]\div LEV(B;\Phi_{n\infty})}{ \left[ {\color{blue}{LEV(Y;\Phi_{ij}) - }} LEV(X;\Phi_{ij}) \right] \div LEV(B;\Phi_{nj})}
\end{align}$
 
## Other Practical Uses
 
If we don't have the severity distribution by age, we can work with the severity at ultimate and estimate $R_j(X,B)$, for lower layers $X < B$
 
$\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{ {\color{red}i} \infty})}{R_j{(X,B)}}
 \end{align}$
 
 * Note the $i$ in the second part of the numerator (I guess it's to be consistent with formula below)
 
 * $R_{j}(X,B) = \dfrac{LEV(X;\Phi_{ij})}{LEV(B;\Phi_{ij})}$
 
    * $j$ is on the diagonal (?)
    
    * This needs to be estimated
    
 * Assumes $\dfrac{LEV(B; \Phi_{n \infty})}{LEV(B; \Phi_{nj})} \approx \dfrac{LEV(B; \Phi_{i \infty})}{LEV(B; \Phi_{ij})}$
 
    * Ratio of losses at different cost layers is immaterial
    
    * The expected LDF in different AYs are similar when losses are capped at $B$
    
    * Reasonable assumption with low inflation

* See how this change pictorially

**Estimate $R_j(X,B)$**

$U_i \leq R_j(X,B) \leq U_i \cdot F_{ij}^{\infty} \leq 1$

* $U_i = R_{i\infty}(X,B) = \dfrac{LEV(X;\Phi_{i\infty})}{LEV(B;\Phi_{i \infty})}$

* We expect $U_i$ to $\downarrow$ for more recent AYs due to loss trend; Larger % of losses  pierce the lower layer

* $U_i$ increases as we move cross maturity (<span style="color:red">not sure how this works as these are ult...</span>)

* $U_i$ is the ratio at ultimate of limited means; same as $R_{i \infty}$

Example from text:

* Select a decay from 1.000 and approaches $U_i$ as maturity increase

* Overlay with empirical $R_j(X,B)$ along the diagonal

Estimate doesn't work when:

* There is expected negative development

* XS layer develops more quickly than a working layer

## Issues with Assumptions

Three assumptions that are **likely reasonable**

1) Must select a basic limit $B$

2) Needs an ultimate claim size model

    * Or use ILFs
    
    * Just have to accurate around the basic limit and policy limit since that's where we calculate expectations
    
3) Need to create a triangle of losses at basic limit and one cost level

    * We do this in the step converting the base triangle

Two assumptions that are **more tenuous**

1) Requires robust claim size model at each age

    * Ultimately we need the ratio of limited losses at different layers right, not the absolute value
    
2) Trend

    * Trend should be applied to the incremental losses
    
    * Not clear how to apply trend to reported losses (by day of reserve or payment?)
    
## Past Exam Questions

n/a
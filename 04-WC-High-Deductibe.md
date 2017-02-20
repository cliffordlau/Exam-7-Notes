# A4 A Model for Reserving Workers Compensation High Deductibles - J. Siewert

## Cliff's Summary

Know the 6 methods and their pros and cons:

1) Loss Ratio Method

2) Implied Development

3) Direct Development

    * $XSLDF_t^{L} = \dfrac{Ult_{XS}}{S_t^{XS}} = \dfrac{Ult \cdot \chi}{\frac{Ult}{LDF_t} - \frac{Ult\cdot(1-\chi)}{LDF_t^L}}$
    
4) Credibility Weight Method

5) Development Method

    * Severity needs to be trended
    
    * Claim counts are developed separately ground up
    
    * Severity LDF formulas, know them well to manipulate and know what formula requires what
    
        * $LDF_t^L = LDF_t \dfrac{R^L}{R_t^L}$
    
        * $XSLDF_t^L = LDF_t \dfrac{(1-R^L)}{(1-R_t^L)}$
    
        * $LDF_t = R^L_t \cdot LDF^L_t + (1 - R^L_t) \cdot XSLDF^L_t$
    
        * $\dfrac{ILDF^L_t}{ILDF_t} = \Delta R^L_t = \dfrac{R^L_{t+1}}{R^L_t}$

        * $\dfrac{IXSLDF^L_t}{IXSLDF_t} = \Delta (1 - R^L_t) = \dfrac{1 - R^L_{t+1}}{1 - R^L_t}$

6) Distribution Method

### Types of Exam Questions

**Concepts**

* 1998 - #41: Discuss methods and pros/cons
* 2000 - #4: Relativities relationship
* 2001 - #11: Development method process
* 2002 - #28 b: Pros/cons implied development
* 2005 - #19 b c: Inflation index limit, implied dev advantages
* 2006 - #6: LR approach advantage
* 2008 - #12 b: LR method pros and cons
* 2011 - #6 c: BF pros (more stable and can be tied to pricing estimates)

**Simple Plug and Play Calculations**

* 1999 - #29: Service revenue calc = utl $\times$ loss multiplier - known recoverables
* 2001 - #23: Loss ratio method for aggregate loss charge
* 2002 - #28 a c: XS deductible IBNR reserve and service revenue
* 2003 - #8: Loss ratio method for losses XS aggregate limit
* $\star$ [2004 - #21](#2004-21): IBNR using LR, implied, direct, BF
* 2005 - #19 a: Implied LDF method
* 2008 - #12 a: LR method both occ and aggregate
* 2010 - #3: Back out limited LDF
* $\star$ [2010 - #9](#2010-9): XS limited LDF based on relativity
* 2012 - #6: Get unlimited with limited and XS and relativity with the formula
* $\star$ [2014 #6](#2014-6): Use incremental formula and also the combined formula
* 2015 #6 a b: LR and implied dev method

**Full Calcualation**

* $\star$ [2007 - #41](#2007-41): XS and limited implied LDF calc from ground up with aggregate limit
* 2009 - #7: implied and direct development from triangle of unlimited and XS
* 2011 - #6 a b: Direct development and BF (slightly erroneous question)
* $\star \star$ [2015 - #6 c](#2015-6): Calculate layer between

## Introduction

WC high deductible reserving with occurrence and/or aggregate deductible

## 1. Loss Ratio Method

**Per Occurrence Expected XS loss**

$P \cdot E \cdot \chi$

* $P$ = Premium

* $E$ = Expected ground up loss ratio

* $\chi$ = Occurrence charge = % of losses above deductible

**Expected Loss XS Aggregate**

$P \cdot E \cdot (1-\chi) \cdot \varphi$

* $\varphi$ = Aggregate charge = % of losses in deductible layer that exceed the aggregate

***

$\chi$ and $\varphi$ are from industry tables

* Specific to the deductible, aggregate, and size of expected losses

These are ultimate loss estimate

**Advantages**

* Useful when little data is available

* Ties to pricing

* Can include industry experience

**Disadvantages**

* Ignores actual emergence

* May not properly reflect account characteristics

## 2. Implied Development

Ultimate excess loss = ultimate unlimited loss - ultimate limited loss

* Need to make sure LDFs and development are consistent with the different layers

* Adjust the deductible for inflation when selecting limited LDFs; Else it distorts the LDFs

**Advantages**

* Get estimate for early period with no losses

* Limited factors are more stable

**Disadvantages**

* Weakness: Does not directly estimate the XS loss

## 3. Direct Development

Determine LDFs for XS layer with unlimited LDFs, limited LDFs and $\chi$

$XSLDF_t^{L} = \dfrac{Ult_{XS}}{Y_t^{XS}} = \dfrac{Ult \cdot \chi}{\frac{Ult}{LDF_t} - \frac{Ult\cdot(1-\chi)}{LDF_t^L}} = \dfrac{\chi}{\frac{1}{LDF_t} - \frac{(1-\chi)}{LDF_t^L}}$

* Based on $\underbrace{Y_t \cdot LDF_t}_{100\%} = \underbrace{Y^L_t \cdot LDF^L_t}_{100\% - \chi} + \underbrace{XSY_t^L \cdot XSLDF^L_t}_{\chi}$

* Can't use the actual losses to date for this as it'll just be equal to the implied method mathematically

**Disadvantages**

* LDFs large and volatile, not recommend this method

## 4. Credibility Weighting Techniques / Bornhuetter-Ferguson

Ultimate Loss: $L = Z\underbrace{(O_t \cdot XSLDF_t^{L})}_{\text{Inc'd to Date } \times \text{ XS LDF}} + (1 - Z)\underbrace{E}_{\text{Method 1}}$

* $Z = \frac{1}{XSLDF_t^L}$ then we have the BF method

## 5. Development Method

**Data**

Ground up WC claims level data

Indemnity, medical and ALAE together

Can split the data by account, injury, and state as a future step

### Severity Trend

Important to account for loss trend when capping losses

Apply different limits to the historical data by AYs or else there will be more and more losses piercing the limiting layer $\Rightarrow$ Distorting the LDFs

1) Look at average severity of unlimited losses by AY and fit an exponential curve

    * Can use different trend for different years
    
    * Can adjust for large losses as well
    
2) Cap the historical losses at lower amount to compensate for the loss trend by detrending the historical layer

### Claim Count Development

Split the development of claim count dev from severity dev and focusing on **ground up** claims

**Advantages**:

* Most claims are reported not too deep in the tail even if the full severity in not yet known

* If you only count claims once they pierce the deductible layer you have to deal with uncertain claim count development deep into the tail

* If your claim counts depend on the limits, every time you update the severity trend assumptions the claim counts will change

### Severity LDFs

**Definition**

$R_t^L = \dfrac{\text{Limited Sev @ t}}{\text{Unlimited Sev @ t}}$

* Relativity starts close to 1.00, and drops over time before reaching the ultimate relativity

* The losses limited at higher limits start with a very high relativity (close to 1.00), and take longer to come down

$R^L = \dfrac{\text{Limited Sev @ Ult}}{\text{Unlimited Sev @ Ult}}$

**Key Relationships**

$LDF_t^L = LDF_t \dfrac{R^L}{R_t^L}$ <span style="color:red;background:yellow">Memorize Formula</span>

* $\cdots = \dfrac{C \cdot S^L}{C_t \cdot S^L_t} = \dfrac{C \cdot S \cdot R^L}{C_t \cdot S_t \cdot R^L_t} = \dfrac{C \cdot S}{C_t \cdot S_t } \times \dfrac{R^L}{R^L_t} = \cdots$

* $C$ is claim count and $S$ is severity

$XSLDF_t^L = LDF_t \dfrac{(1-R^L)}{(1-R_t^L)}$ <span style="color:red;background:yellow">Memorize Formula</span>

$LDF_t = R^L_t \cdot LDF^L_t + (1 - R^L_t) \cdot XSLDF^L_t$ <span style="color:red;background:yellow">Memorize Formula</span>

* This formula doesn't require $R^L$
* Formula only work once claim reporting is finished
* Relativity based on average from historical losses

**Incremental LDFs**

$\dfrac{ILDF^L_t}{ILDF_t} = \Delta R^L_t = \dfrac{R^L_{t+1}}{R^L_t}$

* Difference of limited and unlimited incremental LDFs is driven by the change in relativity
* With $R_t$ and $R_{t+1}$ we can get the limited or unlimited LDF given one or the other

$\dfrac{IXSLDF^L_t}{IXSLDF_t} = \Delta (1 - R^L_t) = \dfrac{1 - R^L_{t+1}}{1 - R^L_t}$

## 6. Distribution Model

Model severity of losses @ each age with Weibull

* Parameters different @ different ages; make sure they are consistent

* This will maintain the relationships of the limited and unlimited over time

* Can easily interpolate among limits and years

* Mean of Weibull = $\theta \cdot \Gamma (1 + \frac{1}{\omega})$

Can then use the distribution and then applies all the relationships discussed in 5

## Aggregate Limits

Use collective risk model with Poisson and Weibull to build out a table with excess loss for each deductible and aggregate

Need 4 inputs: expected unlimited, age, deductible and aggregate limit

The paper shows calculating the reserve as just the expected aggregate loss $\times$ % unreported

* Doesn't take into account if the aggregate is about to be pieced of not

Appendix discuss calculation with Table M

## Past Exam Questions

<a name="2004-21"></a>
![](questions/2004-21Q.png)
![](questions/2004-21A.png)

<a name="2007-41"></a>
![](questions/2007-41Q.png)
![](questions/2007-41A.png)

<a name="2010-9"></a>
![](questions/2010-9Q.png)
![](questions/2010-9A.png)

<a name="2014-6"></a>
![](questions/2014-6Q.png)
![](questions/2014-6A.png)

<a name="2015-6"></a>
![](questions/2015-6Q.png)
![](questions/2015-6A.png)

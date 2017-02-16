# (PART) Enterprise Risk Management {-}

# C1 ERA 1.1 - 1.3 Introduction - Brehm, et al.

## Cliff's Summary

[Requirements](#erm-req-promo) to promote ERM

[Definition](#erm-def) of ERM

7 [key aspect](#key-aspect) of ERM

4 [categories](#categories) of risk

Enterprise risk model process

1. [Diagnose](#diagnose): Assess all risk and considergeneral environment, industry, and firm specific items

2. [Analyze](#analyze) what risk are critical and consider correlations; Select measures consistent with management's veiw of risk and prioritize

3. [Implement](#implement) ways to manage the risk: avoid, reduce frequency, mitigate severity, transfer, or retain

4. Monitor the process, update when there's new risk, new ways to control or new options to transfer/treating the risk

[Goal](#ermodel-goal) of enterprise risk model

Model [quality](#quality)

4 [key elements](#key-elements) of enterprise risk model: underwriting risk, reserving risk, asset risk and dependencies

* Know the different component of u/w risk
* Different asset class modeling
* Source of dependencies

Approach to [setting capital](#setting-cap) based on default avoidance or threshold lower than probability of ruin

Risk measures do not tell us how much capital to hold; They tell us for a given level of capital, what the risk to the company is

Risk model can also be used to allocate capital to BUs and investment function to calculate risk-adjusted performance

## 1.1 Historical Context

RBC (from 1990s) was the precursor to scenario testing and Dynamic Financial Analysis (DFA) but DFA didn't pan out

DFA requires support from many functions and was not widely used due to lack of natural champion

ERM as of 2007:

* IAIS began development of an approach of rating insurer based on Basel II. See 2004 IAA document

* CA and AUS require use of internal risk models

* UK implemented Individual Capital Adequacy Standards (ICAS): A firm is required to undertake regular assessments of the amount and quality of capital which in their view is adequate for the size and nature of their business

* NAIC is moving towards a new audit paradigm: **C**apital adequacy, **A**sset quality, **R**eserves, **R**einsurance, **M**anagement, **E**arnings and **L**iquidity (**CARRMEL**)

* 2005 S&P stated that a firm's EMR program will become a critical component in its rating methodology

<a name="erm-req-promo"></a> ERM needs an internal champion with **quantitative skills**, **operational experience** and **political skills** to work across organizational silos

## 1.2 Overview of ERM

<a name="erm-def"></a> **Definition**:  
ERM is the process of systematically and comprehensively identifying critical risk, quantifying their impacts and implementing integrated strategies to maximize enterprise value

### Key aspects of ERM

<a name="key-aspect"></a>
ERM is:

1) A **process**, not a one time analysis
2) **Enterprise wide** basis
3) Focus on **critical** or **material** risk

Risk:

4) Has upside and downside, it's when actual outcome $\neq$ expected
5) Must be **quantified**; **Dependencies** must be evaluated and quantified
    
Strategies:

6) Are developed to **Avoid**, **mitigate**, or **exploit** risk factors
7) Are evaluated as a **tradeoff** of **risk and return**, to maximize firm value
    
### 4 Categories of Risk

<a name="categories"></a>

**Insurance Hazard**:

* Unique to insurers that is intentionally taken on to make a profit
* *In-force* exposures: *accumulation* (CAT); *underwriting* (non-CAT)
* *Past* exposures (reserve)
    
**Financial Risk**:

* *Assets* of insurance company
* Insurers tend to have high $\frac{Asset}{Equity}$ ratio
    
**Operational Risk**:

* *Execution* risks of the company
* Not as responsive, amenable to quantitative modeling
    
**Strategic Risk**:

* About *choices*, making the right or wrong or no strategic choices
X* Not as responsive, amenable to quantitative modeling
    
### ERModel Process

Diagnose $\Rightarrow$ Analyze $\Rightarrow$ Implement $\Rightarrow$ Monitor

#### 1) Diagnose

<a name="diagnose"></a>

High level risk assessment

All risks are considered but start to **develop threshold** for risk that will be considered material of significant ([Key aspect 3](#key-aspect))

**General Environment**

* Political uncertainties  
(democratic changes, war, revolution)

* Government policy  
(fiscal, monetary changes, regulation)

* Marcoeconomic environment  
(inflation, interest rates)

* Social  
(terrorism)

* Natural  
(CAT)

**Industry**

* Input market  
(supply, quality)

* Product market  
(demand)

* Competitive uncertainties  
(new entrants, rivalry)

**Firm Specific**

* Operating  
(labor, supply)

* Liability  
(products, employment)

* R&D

* Credit

* Behavioral
  
#### 2) Analyze

<a name="analyze"></a>

Analyze risk identified in step 1 for materiality and prioritize

**Critical Risk**:

* Risk with potential to exceed the company's threshold are modeled  

* Preferably *quantified* with a probability distribution of outcomes

**Correlations** must be recognized

Selected measures must be **consistent** with management's view toward risk

**Prioritize** risk factors that contribute to adverse scenarios above the critical threshold

#### 3) Implement

<a name="implement"></a>

Focus on **managing** risks identified and analyzed as material

5 potential actions to manage risk:

* **Avoidance**
* **Reduction** in chance of **occurrence**
* **Mitigate** effect given occurrence
* **Eliminate** or **transfer** of the consequences
* **Retention**

Speculative risk factor may provide an opportunity to capitalize on the risk, rather than manage it away

* Perform a risk/return trade-off analysis

#### 4) Monitor

Management need to monitor the process, compare to expectations

Need to update plans and model as company or market or competitors change

* New risk to address
* New ways to control them
* New options for treating or transferring risk

## 1.3 ERModel Overview

<a name="ermodel-goal"></a>Goal: **understand** and **quantify** the relationships among the risks to the business that arise from: asset, liabilities and underwriting

All are affected by *internal decisions* & *external factors*

Modeling will help with management functions and strategic decisions:

* Planning growth
* Valuing companies for M&A
* Determining capital need
* Setting reinsurance strategies
* Identifying sources of significant risk
* Managing asset mix

### Quality of Models

Good Model:

* Show risk and reward for a range of different strategies
* Recognizes its own imperfection

Weak Model:

* Over(under)state risks $\leadsto$ Overly cautious (aggressive) choices

Data quality will affect suitability of the model; require assumptions from the modeler

<a name="quality"></a> Elements that differentiate model quality:

* Model reflects **relative importance** of various risks
* Model includes **dependencies**
* *Modelers* have a **deep knowledge** of the **fundamentals** of those risks
* *Modelers* have a **trusted relationship** with senior management
* Take into account the uncertainty from other models (CAT, ESG, credit risk) that are used as inputs
* Operational risks have to be modeled in bulk using informed judgement as we might not be able to model them in a detailed fashion

### Key Elements of ERM

<a name="quality"></a>

1. Underwriting Risk
    * Loss Frequency and Severity Dist^n^
    * Pricing Risk
    * Parameter Risk
        * Estimation Risk
        * Projection Risk
        * Event Risk
        * Systematic Risk
    * CAT Model Uncertainty
2. Reserving Risk
3. Asset Risk
4. Dependencies (Correlation)

***

#### Underwriting Risk

Focus on day to day losses and CAT losses

**Loss Frequency and Severity Distribution**

Use statistical methods to:

* Estimate parameters
* Test quality of fit
* Understand uncertainties that remain

**Pricing Risk**

Risk from not charging the right price

* Deficiency may exist for many years for long tailed lines $\Rightarrow$ Accumulation of reserve deficit

* Model should include u/w cycle

**Parameter Risk**: Risk of parameters used being incorrect

Estimation Risk:

* Error in estimate since it's based on available data

Projection Risk:

* Error on forecast of future value even we fit the historical data accurately
* Error on ultimate losses, future trends
* Unexpected change in external risk conditions (Linked to event risk)

Event Risk:

* Causal link between a large unpredictable event and losses to an insurer
* E.g. Asbestos where exposure existed unknown for many years comes to light
* New cause of loss emerges that was previously regarded as not covered (environmental, CD)
* Regulator or court expands coverage by barring important exclusions
* New entrant into market reduces rates

Systematic Risk:

* Risk operate simultaneously on a large # of policies, undiversifiable
* e.g. inflation

**Catastrophe Modeling Uncertainty**

Differences between commercial models and different versions of the same model

Company not able to provide data required by the model

Parameter risk and correlations

*** 

#### Reserving Risk

Adverse development can be significant specially for long tailed lines

$\uparrow$ reserve uncertainty $\Rightarrow$ $\uparrow$ capital requirement

UPR should be part of u/w risk

Likely the most important part of the model, including the uncertainty in the parameters

Model should be able to be test for quality of fit measures

***

#### Asset Risk

Focus on issues the specific market the company operates in

Main asset classes: **equities**, **fixed income**, **real estate**

*  FX and inflation are closely related to asset modeling as well

Asset liability matching

* Can offset insurance risk and investment risk
* Doesn't work well for P&C to match the short duration of liabilities 
* P&C liabilities are inflation sensitive as well

Efficient Frontier: $\sigma$ vs $\operatorname{E}[Return]$

* See how it changes by modifying reinsurance structure or asset mix

**Modeling Considerations**

* *Bonds*:  
Model with arbitrage free models  
Should capture historical features of bond markets (high auto-correlations and dist^n^ of yield spreads)

* *Equities*:  
Incorporate correlations with bonds  
Geometric Brownian motion model with additional volatility is more realistic

* *FX*:  
First model interest rates of the currencies then model the FX rates

***

#### Dependencies

Important to capture dependencies or else the model will be unrealistically stable

**Sources of Dependencies**:

* Macro econ conditions, affect many risks. Use ESG
* U/w cycle, loss trends and reserve development can impact across lines
* CAT and other extreme events like the 2008 financial crisis
* Difficult to quantify

Use copulas to capture different forms of dependency

* Correlation is too simplistic and does not capture the dependencies in the tail

***

### Setting Capital Requirements

<a name="setting-cap"></a>

Policyholders wants more capital $\Leftrightarrow$ Shareholders want higher return (less capital)

Set capital to maximize insurer's value $\Rightarrow$ Unifies the competing requirements of prudence and efficiency

Approaches to set capital requirements:

**1. Default Avoidance**: Focused on the **tail** and protecting **policyholders**

Caveat:

* S/h will be hurt at much lower loss amount
* We have the least confidence in the tail of the model

$\hookrightarrow$ More feasible and relevant to focus on thresholds less extreme than default

**2. Lower Threshold than Probability of Ruin**:

* Probability of downgrade
    * Significant loss $\leadsto$ $\downarrow$ financial rating $\leadsto$ $\downarrow$ franchise value > loss itself
* Sufficient capital to service renewals
* Survive and thrive after major CAT

### Convert Probability to Loss

Converting Probability Levels to Financial Loss Amounts

* Smallest amount of loss, $\alpha \%$ of the time $\Rightarrow$ $VaR_{100 - \alpha \%}$

* Average loss, $\alpha \%$ of the time $\Rightarrow$ $TVaR_{100 - \alpha \%}$

* 1-in-$x$ years event loss no more than $y \%$ of capital $\Rightarrow$ $\dfrac{100}{y} \times TVaR_{1 - \frac{1}{x}}$

**Important**: Risk measures do not tell us how much capital to hold; They tell us for a given level of capital, what the risk to the company is

### Risk Adjusted Performance

Allocate capital to business units $\Rightarrow$ Calculate the rate of return $\dfrac{\text{Profit}}{\text{Capital}}$ for that unit $\Rightarrow$ Compare RoR across BUs

Can also allocate risk capital to investments $\Rightarrow$ Compare riskiness of investments and u/w

* Need to make sure risk measures are consistent
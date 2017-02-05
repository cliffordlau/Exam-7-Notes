# A12 Reinsurance Loss Reserving - Patrik

## Cliff's Summary

Know the 7 problems of reinsurance reserving

* General theme: Heterogeneity, lower frequency, lack of detailed exposure information

Know the components of reinurance reserve

Reinsurance reservering procedure:

* Partition $\Rightarrow$ Development Patterns $\Rightarrow$ Estimate $\Rightarrow$ Monitor and AvE

* Partition priority

* Considerations for short vs medium vs long tail lines

    * Know SB well and how to adjust the premium
    
    * Know the credibility weighted method

* AvE

### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Concepts**

* 1996 #10: Problems of reinsurance reserving
* 1999 #9: Partition consideration
* 1999 #10: Fidelity proportional is short tail
* 2000 #68 b c: SB incorporates reported loss in the ELR but difficult to adjust ELR to a prior estimate for each year
* 2001 #54: pros and cons of CL and BF
* 2002 #42: SB vs BF similarity and difference
* 2004 #49 c d: SB vs BF pros and cons
* 2006 - #45: Which method to use SB vs CL
* 2007 - #21: Discuss how SB is a special case of BF
59
* $\star$ 2008 - #35: Reason of report lag and upward development due to modal value claim reserve
* $\star$ 2008 - #37: Industry data vs internal
    * Industry: thin internal data; volatile from rate changes; rate change history not credible; shift in underlying policies
    * Internal: Rate change not reflected in industry; industry composition different from reinsurer; Underlying policies not represented in Sch P data; believe data is credible and representative of the specific business involved
* $\star$ 2009 - #32: How to partition data
    * Fac vs treaty $\Rightarrow$ LoB; Don't split by cedant as data too thin
    * Diagnostics: Look at reporting pattern and amount of data for credibility; discuss with u/w and claims
* 2011 #10 b: SB pros and cons
* 2011 #11: report lag; upward developement; standard method not work; industry data not work
* 2012 #10 b-d: SB vs CL
* 2012 #11: problems of reinsurance reserving
* 2013 #10 c: SB vs CL
* 2014 #13: problems of reinsurance reserving
* $\star$ 2015 #12: Discuss problems of reinsurance reserving based on data given
    * Reporting lag (claims below reporting threshold)
    * Persistent upward development (upward development of ALAE by looking at ratio)
    * Heterogeneity patterns (each AYs have different retention)
* 2015 #13 b: Reason to adjust EP for SB (e.g onlevel so LR for each AY is comparable, adjust for varying rate as SB assumes constant ELR)

**Calculations**

* 1997 #11: SB (Use adjusted onlevel premium)
* 1998 #35: IBNR with CL, BF, SB
* 2000 #68 a: SB
* 2001 #53: SB
* 2003 #44: SB
* 2004 #49 a b: CL and SB
* 2005 #38: SB
* $\star$ 2007 - #3: Credibility weight SB and CL, remember to use $Z_k = p_k \cdot CF$
* 2007 - #22 a b: CL and SB
* 2008 - #36: SB
* 2009 - #31: SB
* 2011 #10 a c: SB and credibility weighted
* $\star$ 2012 #10 a: SB method, need to consider age of policy on risk attaching vs loss occurring basis, also take out expense from premium
* 2013 #10 a b: SB and credibility weighted SB and CL
* 2014 #14: SB
* 2015 #13 a: SB

## 7 Problems with Reinsurance Reserving

Problem 1: **Longer report lag of claims**

* Claim must be perceived as report-able to the reinsurer by the cedant (e.g. half of the attachment point) and then flow through cedent's system to reinsurer

* Cedant may undervalue the claim for a long time and thus not report to the reinsurer

* Extreme delays in discovery or reporting for mass tort claims

Problem 2: **Persistent Upward Development of Most Claim Reserves**

* Economic and social inflation

* Tendency to underestimate LAE

* Tendency of claims to reserve at the modal value

    * Not initially clear which of a group of similar claims will become large so choose the same mostly likely value for all
    
    * Modal value likely under attachement point of treaty so reinsurer does not learn about claim until it is known to be large, which may be several years after reported to primary insurer

Problem 3: **Reporting Pattern Differ Greatly**

* Differ by: LoB, contract type, contract terms, cedant, intermediary

* Extremely heterogeneous exposures

* Extreme fluctuation in historical loss data due to low frequency and report lags

* Less information on the underlying exposure than primary carrier

Problem 4: **Industry Statistics Not Useful**

* Due to heterogeneity exposures

* Sch P doesn't break down the exposure fine enough and ISO not directly applicable

* Reporting lag grows with attachment point

Problem 5: **Reports Received Lack Important Information**

* Proportional covers require only summary claims info

* Might only have u/w year info (no AY or PY)

* Need exposure measure

    * Can use reinsurance premium but often it is allocated to primary lines using a fixed percentage. If % not correctly reflect loss exposure, premium by line may be distorted
    
* Reporting is typically done with a quarter lag so always missing a quarter of premium

Problem 6: **Data Coding and IT System Problems**

* Due to the heterogeneity in coverage

* Might have grown in size and complexity faster than data system could handle

Problem 7: **Reserve to Surplus Ratio is Higher for Reinsurer**

* Management problem

* Management may underestimate level of reserves need until claims emerge and difficulty with actuary convincing management to post the appropriate reserve

***

Standard techniques requires: Homogeneous book, sufficient frequency, and detailed exposure info (Problems 3, 4, 5); Difficult to supplement with industry info

## 6 Components to a Reinsurance Loss Reserve

1) **Case reserve** reported by *cedent*

    * Summary reporting for proportional contracts
    
    * Individual case reports for XS contracts
    
2) **Additional Case reserve** from reinsurer

3) **IBNER**

4) **Pure IBNR**

5) **Discount** for future investment income

    * For tabular discount as well as for tax purposes
    
6) **Risk Load**

    * For adverse deviation so uncertain income doesn't flow into profits too quickly
    
## Reinsurance Reserving Procedure

Partition $\Rightarrow$ Development Patterns $\Rightarrow$ Estimate $\Rightarrow$ Monitor and AvE

### Portfolio Partition

Data needs to be split into reasonably **homogenous** exposure groups that are relatively **consistent over time** with respect to mix of business (exposures)

Variables to consider when partitioning data in approximately priority order:

**LoB**  
**Contract type** (fac, treaty, finite)  
**Types of Cover** (QS, SS, XS per risk/occ, agg XS, CAT, LPT)   
**Primary LoB** (for cas)  
**Attachment Point** (for cas)  
**Contract terms** (flat-rates, retro rated, sunset clause, LAE share, CM, Occ)  
**Type of cedant** (Small, large, E&S)  
**Intermediary** (brokers)

![](figures/FullSizeRender.jpg)

Need to **balance** *homogeneity* with *credibility* of data

Review loss statistics and reporting pattern to see if data is still credible

### Analyze Distorical Data and Projection

**Backwards** looking (Step 2):  
Analyze the historical development patterns. If possible, consider individual case reserve development and the emergence of IBNR claims separately

* Use long periods where practical and curve fit where practical

**Forward** looking projection (Step 3):  
Estimate the future development. If possible, estimate the bulk reserve for IBNER and pure IBNR separately

#### Short Tailed Lines

Settlement is quick, basic methods work fine

For property, beware of recent CATs

Exclude the high layers for XS property

Exclude construction for Fac Prop

Fidelity proportional is short tail as well

Book LR for new lines and maybe allocate claims to AY for reserving

#### Medium Tailed Lines

Average dollar lag of 1-2 years and nearly complete within 5 years

XS Property (separate from working layers), Construction (separate from other), Surety, XS Fidelity, Marine, Agg XS (non-casualty)

Surety should estimate gross and recovery separately as the recovery has a longer tail

Chainladder works fine for paid and incurred with or without ACR

#### Long Tailed Lines

Any time of casualty reinsurance, XS Cas is the longest before APH

APH should be analyzed separately:

* Use different methods specifically for APH

* Separate commuted contracts

***Chainladder***:

* Don't use, too much leverage

***BF***:

* Better than CL

* Dependent on selected LR

    * Consider u/w cycle in selecting LR since AY LR is strongly correlated to the place in the reinsurance profitability cycle

    * May use LR from pricing work
    
***Stanard Buhlmann***:

* Must on-level the historical premium and adjust to be pure premium

    * Remove commissions and brokerage and internal expenses (but might not worth the effort)

    * Remove any suspected rate level differences

* $ELR = \dfrac{\sum C_k}{\sum E_k p_k}$

    * $C_k$: reported to date; $E_k$: Adj Prem; $p_k$: expected % reported to date

* Estimate ELR using actual incurred loss

* Sensitive to the accurary of the onlevel EP
    
***Credibility IBNR Estimates***:

Weight the CL method with SB or BF

* $R_k = Z \cdot R_{CL} + (1-Z) \cdot R_{SB}$

* $Z_k = p_k \cdot CF$, $CF \in [0,1]$

* $CF$ is the credibility factor, Benktander = 1, BF = 0\

***Alt Methods***:

Fit losses reported to date to a curve

Model claim counts or use stochastic model (Bootstrap). Caveat being that it might be difficult to explain to management

### Monitoring and Testing Predictions

Compare AvE over quarters and do this for several quarters to see if any trends become apparent

Expected = $\dfrac{\text{Expected % Reported in Period}}{\text{Expected % Unreported}} \times IBNR$

Sometime difficult to tell if the difference is large or small

Look for deviations over time and look for trends

It could be IBNR is too small, claims are paying faster than expected, or just random fluctuation

## Past Exam Questions

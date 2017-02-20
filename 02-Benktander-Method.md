# Credible Claims Reserve: The Benktander Method - T. Mack

Know the GB method formula (\@ref(prp:GB-method))and properties

* Recognize actual emergence faster

## Gunnar Benktander Method (GB)

\BeginKnitrBlock{proposition}\iffalse{-91-66-101-110-107-116-97-110-100-101-114-32-82-101-115-101-114-118-101-93-}\fi<div class="proposition"><span class="proposition" id="prp:GB-method"><strong>(\#prp:GB-method) \iffalse (Benktander Reserve) \fi </strong></span>Reserve under the Benktaner Method

$R_{GB} = q_kU_{BF}$

* $q_k = (1 - p_k)$ = % unpaid loss @ $k$

* $U_{BF} = C_k + q_kU_0$

* Weight on $U_0$ is $q_k^2$</div>\EndKnitrBlock{proposition}

\BeginKnitrBlock{remark}<div class="remark">\iffalse <span class="remark"><em>Remark. </em></span> \fi Benktander recognizes actual emergence faster $\Rightarrow$ Less weight on the a-priori

* BF reduces the use of actual loss to the extent of the complement credibility

$\begin{align}
  U_{GB} &= (1-q_k)U_{CL} + q_kU_{BF} & \cdots (1)\\
  &= (1-q_k^2)U_{CL} + q_k^2 U_0 & \cdots (2)\\
\end{align}$

1. Crediblity weight $U_{BF}$ and $U_{CL}$

2. Crediblity weight $U_{CL}$ and a priori</div>\EndKnitrBlock{remark}

### Method Comparison

Table: (\#tab:GB-CL-BF-Comp) Comparison of Ulltimate Loss and Reserve for Different Methods

| Method | Ultimate ($U$) | Reserve ($R$) |
| ------------------------ | ------------------------ | ------------------------ |
| Chain Ladder | $\dfrac{C_k}{p_k}$ | $q_k U_{CL} = q_k \dfrac{C_k}{p_k}$ |
| BF Method | $C_k + q_kU_0$ | $q_k U_0$ |
| GB Method | $C_k + q_kU_{BF}$ | $q_k U_{BF}$ |

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:GB-iterate"><strong>(\#thm:GB-iterate)</strong></span>For an arbitrary starting point $U^{(0)} = U_0$ and the iteration rule $R^{(m)} = q_k U^{(m)}$ and $U^{(m+1)} = C_k + R^{(m)}$, $m = 0, 1, 2, ...$ 

gives credibility mixtures

$$U^{(m)} = (1-q^m_k)U_{CL} + q^m_k U_0$$

$$R^{(m)} = (1-q^m_k)R_{CL} + q^m_k R_{BF}$$

between $BF$ and $CL$ which start at $BF$ and lead via $GB$ to $CL$ for $m= \infty$</div>\EndKnitrBlock{theorem}

### MSE

MSE of Benktander is almost as small as the MSE of the optimal credibility in most cases

$MSE(R_{GB}) < MSE(R_{BF})$

* When $p_k \in [0, 2c^*]$; $c^*$ is the optimal credibility

    * $R_{GB}$ doesn't have the lowet $MSE$ only when $p_k > 2c^*$

* Doesn't hold if $c^*$ is small and $p_k$ is large

\BeginKnitrBlock{remark}<div class="remark">\iffalse <span class="remark"><em>Remark. </em></span> \fi $MSE(R_c) = \mathrm{E}[R_c - R]^2$

* $R_c = c R_{CL} + (1-c)R_{BF}$

* $R = U - C_k = C_n - C_k$

Where:

* $c = 0$ for $BF$

* $c = p_k$ for $GB$

* $c = c^*$ for optimal credibility where $c \in [0, 1]$</div>\EndKnitrBlock{remark}

## Notation

$U =$ Ultimate Loss

$R =$ Estimate of Unpaid losses

$U_0 =$ a priori estimate of Ultimate Losses

$p_k =$ % of total losses **paid** at $k$

$q_k = 1 - p_k =$ %  of total losses **unpaid** a $k$

$C_k =$ Actual paid losses at $k$

## Past Exam Questions

<div class="rmdcaution">
<p>Haven't done TIA practice questions</p>
</div>

**Concepts**

* 2006 - #16 b c: GB method vs BF and dev

    * Lower MSE and gives weight to both a-priori and emerged

* 2007 - #46 b-c: BF weight, BF drawback, GB advantages over BF

* 2008 - #10 b-c: Comparison of methods and GB as credibility weight

* 2013 - #4 b: GB approaches CL as more iterations are done

**Simple Plug and play**

* 2004 - #31: GB method ultimate

* 2005 - #16: GB method ultimate

* 2006 - #16 a: GB method ultimate

* 2012 - #1 a: GB BF Dev

* $\star$ 2014 - # 5: Credibility weight methods from the Clark paper on LDF curve fitting

    * Weight to the Dev method is $(1-q_k)$

**Other**

* 2012 - #1 b (fig \@ref(fig:2012-1)): Minor arithmetic

* 2013 - #4 a: Back out LDFs with BF and GB methods

### Question Highlights

<div class="figure">
<img src="questions/2012-1Q.png" alt="2012 Question 1" width="100%" />
<p class="caption">(\#fig:2012-1)2012 Question 1</p>
</div><div class="figure">
<img src="questions/2012-1A.png" alt="2012 Question 1" width="100%" />
<p class="caption">(\#fig:2012-1)2012 Question 1</p>
</div>

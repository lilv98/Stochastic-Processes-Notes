# Quick Review of Probability

## Chapter 1: Basic  Probability Theory Combinations

### 1.1. What is Probability Theory?

* We define random phenomena as events and experiments whose outcomes can not be predicted with certainty.

* Two interpretations of property:

  * Relative Frequency: If we flip a fair coin a large number of times, it will come to heads about 50% of the time

  * Subjective Personal Belief: Probability is the quantification of our belief something would happen.

  These two interpretations coincide and the theory of Probability provides a solid framework to study random phenomena with **3 Axioms of Probability**.

### 1.2. Random Experiments and Probability

#### 1.2.1 Random Experiments

* Def1: A **random experiment** is the process of observing something uncertain.
* Def2: An **outcome** is a result of a random experiment.
* Def3: The set of all possible outcomes is called the **sample space**.
* Def4: When we repeat an experiment several times, we call each one a **trial**.
* Def5: An **event** is a subset of the sample space.
  
#### 1.2.2 Probability

##### a. Def

We assign a probability measure $P(A)$ to an event $A$.

This is a value set between 0 and 1 that shows how likely the event is and is such that:

* If $P(A)$ is close to $0$, then the event $A$ is unlikely to occur.
* If $P(A)$ is close to 1, then the event $A$ is likely to occur.

##### b. Axioms of Probability

* Axiom 1: For any event $A$, $P(A)\geq 0$.

* Axiom 2: Probability of the sample space $S$ is $P(S)=1$.

* Axiom 3: If $A_1, A_2, A_3, \dots$ are disjoint, then
  $$
  P(A_1\cup A_2\cup A_3\dots) = P(A_1)+P(A_2)+P(A_3)+\dots
  $$

#### 1.2.3 Finding Probabilities

* To find the probability of an event, we usually follow these two steps:

  * We use the specific information we have about the random experiment.
  * We then use the probability axioms.

* Follow-up properties

  * Inclusion-Exclusion Principle
  $$
  P(A\cup B) = P(A)+P(B)-P(A\cap B) \\
    P(A\cup B\cup C) = P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)
  $$

  * $P(A^c) = 1-P(A)$
  
  * Probability of the empty set $P(\empty)=0$
  
  * For any event $A$, $P(A)\leq 1$

#### 1.2.4 Discrete Probability Model

* Consider a sample space $S$, if $S$ is a countable set, this refers to discrete probability model. Since $S$ is countable, we can list all the element in $S$ as:
  $$
  S=\{s_1, s_2, s_3, \dots\}
  $$

* If $A\sub S$ is an event, then $A$ is also countable and by the $3^{rd}$ Axiom, we can write
  $$
  P(A) = P(\bigcup_{s_j\in A}\{s_j\})=\sum_{s_j\in A}{P(s_j)}
  $$

* Bottom line: We sum the probability of individual elements in that set to find the probability of an event.

* Consider now a finite sample space with equally likely outcomes.
  $$
  P(s_i)=P(s_j)~~~~~~\text{    for all }i, j\\
  Then~~~~P(s_i)=\frac 1 N ~~~~~\text{for all }i\in\{1,2,3,\dots, N\}
  $$

* If $A$ is an event with cardinality $|A|=M$, we have $P(A)=\sum_{s_j\in A} P(s_j)=\frac M N = \frac{|A|}{|S|}$

* Finding Probability of $A$ reduces to a counting problem.

#### 1.2.5 Continuous Probability Models

* Consider a scenario where the sample space is uncountable.    For example   $S=[0,1]$

* A simple example: In uniform distribution , the probability of an interval is directly proportional to the length of the interval.

#### 1.2.6 Conditional Probability

* Absolute Probability $P(R)$
* Conditional Probability $P(R|C)$

##### 1.2.6.1 Calculation of Conditional Probability

Def: If $A$ and $B$ are events in the sample space $S$, the conditional Probability of $A$  given $B$, when $P(B)>0$ is:
$$
P(A|B) = \frac{P(A\cap B)}{P(B)}
$$

##### 1.2.6.2 Axioms of Probability revisited

* The axioms of Probability can be rewritten with conditional probability:
  * Axiom 1: $P(A|B)\geq 0$
  * Axiom 2: $P(B|B)=1$
  * Axiom 3: If $A_1, A_2, \dots$ are disjoint, $P(A_1\cup A_2\cup \dots|B)=P(A_1|B)+P(A_2|B)+\dots$

##### 1.2.6.3 Useful results for conditional probability

* $P(A^c|B)=1-P(A|B)$
* $P(\empty|B)=0$
* $P(A\cup B|C)=P(A|C)+P(B|C)-P(A\cap B|C)$
* when $A$ and $B$ are disjoint, $P(A|B)=0$
* when $B$ is a subset of $A$, $P(A|B)=1$
* When $A$ is a subset of $B$, $P(A|B)=\frac{P(A)}{P(B)}$

##### 1.2.6.4 Chain Rule for Conditional Probability

The chain rule is given as:
$$
P(A\cap B)=P(A)\cdot P(B|A) = P(A)\cdot P(A|B)
$$
A generalization is given by:
$$
P(A_1\cap A_{2} \cap A_{3} \ldots \cap A_{n})=P(A_{1}) \cdot P(A_{2}| A_{1}) \cdot P(A_{3} | A_{2}, A_1) \dots P(A_{n} | A_{n-1}, A_{n-2}, \cdots A_{1})
$$

##### 1.2.6.5 Independence

* events $A$ and $B$ are independent if $P[A \cap B]=P(A) \cdot P(B)$

* Difference between Independence and Disjointedness:

  | Concept     | Meaning                                    | Formulas                                        |
  | ----------- | ------------------------------------------ | ----------------------------------------------- |
  | Disjoint    | $A$ and $B$ cannot occur at the  same time | $A\cap B=\empty$                                |
  | Independent | $A$ gives no information about  $B$        | $P(A\|B) = P(A), P(B\|A)=P(B)$ |

* Three events $A, B$, and $C$ are independent if all of the following hold:
  $$
  \begin{aligned}
  & P(A \cap B)=P(A) \cdot P(B) \\
  &P(B \cap C)=P(B) \cdot P(C) \\
  &P(A \cap C)=P(A) \cdot P(C)\\
  &P(A \cap B \cap C)=P(A) \cdot P(B) \cdot P(C)
  \end{aligned}
  $$

* Useful Results for independent Events:
  * If $A$ and $B$ are independent then:
    * $A$ and $B^{c}$ are independent.
    * $A^c$ and $B^{c}$ are independent.
    * $A^c$ and $B$ are independent.

* If $A_{1}, A_{2}, \ldots, A_{n}$ are independent then:

$$
P(A_{1} \cup A_{2} \ldots \cup A_{n})=1-\left(1-P(A_1)\right)\left(1-P(A_2)\right) \ldots
(1-P(A_n))
$$

##### 1.2.6.6 Law of Total Probability

* If $B_1, B_2, \ldots$ is a partition of sample space $S$, for any event $A$, we have:
  $$
  P(A) = \sum_iP(A\cap B_i) = \sum_iP(A|B_i)\cdot P(B_i)
  $$

##### 1.2.6.7 Bayes Rule

* This rule allows us to calculate $P(B|A)$ from $P(A|B)$

* Recall for two events $A$ and $B$, we have:
  $$
  P(B|A)P(A)=P(A\cap B)=P(A|B)P(B)
  $$
  Thus:
  $$
  P(B|A)=\frac{P(A|B)\cdot P(B)}{P(A)}
  $$

* If $B_1, B_2, B_3, \ldots$ form a partition of the sample space $S$ and $A$ is any event with $P(A)\neq 0$, we have:

$$
P(B_i|A)=\frac{P(A|B_i)\cdot P(B_i)}{\sum_j{P(A|B_j)\cdot P(B_j)}}
$$

##### 1.2.6.8 Conditional Independence

* Def: Two events $A$ and $B$ are conditional independent given an event $C$ with $P(C)>0$, if:
  $$
  P(A\cap B|C)=P(A|C)\cdot P(B|C)
  $$

* Consequence: Recall that $P(A|B) = \frac{P(A\cap B)}{P(B)}$

  Conditioning on $C$, we can write:
  $$
  P(A|B,C) = \frac{P(A\cap B|C)}{P(B|C)} =\frac{P(A|C)\cdot P(B|C)}{P(B|C)} = P(A|C)
  $$

#### 1.2.7 Combinations: Counting Methods

##### a. Finding Probability using Counting Methods

* Recall: For discrete sample space with equally likely outcomes, the probability of an event $A$ is given by $P(A)=\frac{|A|}{|S|}$
* Finding the probability $P(A)$ reduces to a counting problem

##### b. Multiplication Principle

* Suppose that we perform $r$ experiments such that the $k^{th}$ experiment has $M_k$ possible outcomes for $k=1,2,\dots, r$, then there are a total of $M_1\times M_2\times M_3\times\dots\times M_r$ possible outcomes for the sequence of $r$ experiments.

##### c. Important Terminology

* Sampling: choosing an element/sample at random from a given set in which each element has an equal chance of being picked/chosen.
* With Replacement: while drawing samples from a set, if we put each element back in the set after each draw, we say that we have sampling with replacement.  **(repetitions are allowed)**

* Without Replacement: while drawing multiple samples from a set, we do not put back each drawn sample after every draw. **(No repetitions allowed)**
* Ordered: Sampling in which ordering matters.
* Unordered: Sampling in which ordering does not matter.

##### d. Ordered Sampling with Replacement

* We need to make $k$ draws from a set of $n$ elements in which ordering matters and repetitions is allowed.

  Thus the total number of ways of choosing $k$ objects from a set with $n$ elements is $n^k$.

##### e. Ordered Sampling without Replacement (Permutations)

* When ordering matters and repetitions are not allowed, the total number of ways of choosing $k$ objects from a set with $n$ elements is given by:
  $$
  \frac{n!}{(n-k)!}=P_k^n~~~~~~for~~~ 0\leq k\leq n
  $$

##### f. Unordered Sampling without Replacement (Combinations)

* We want to make $k$ draws from a set of $n$ elements in which ordering does not matter and repetition is not allowed.

* This means that we have to choose a $k$-element subset of $A$ and is also called $k$-combination of the set $A$, denoted by $n \choose k$, which is also the Binomial Coeffecient.

* The difference between $n \choose k$ and $P_k^n$ is ordering.

* For any $k$-element subset of $A$,  we can order the elements in $k!$ ways

  Thus ${P_k^n=k!}{{n} \choose {k}}=\frac{n!}{(n-k)!}$

##### g. Unordered Sampling with Replacement

Theorem:

* The number of distinct $k$ samples from an $n$-element set such that repetition is allowed and ordering does not matter is the same as the number of distinct solutions for the equation:
  $$
  x_1+x_2+\dots+x_n=k~~~where~~x_i\in \{0,1,2,3,\dots\}
  $$

* And this number of distinct solutions is given by ${n+k-1 \choose k}={n+k-1\choose n-1}$

* Example:

  10 passengers get on an airport shuttle at the airport. The shuttle has a route that includes 5 hotels and each passenger gets out of the shuttle at his/her hotel. The driver records how many passengers leave the shuttle at each hotel.

  Q: How many different possibility exist?

  A: Let $x_i$ be the number of passengers that get off the shuttle at hotel $i$, then we have:
  $$
  x_1+x_2+x_3+x_4+x_5=10~~~~~~with ~~x_i\in\{0,1,2,\dots,10\}
  $$
  Therefore the number of solution is
  $$
  {5+10-1\choose 10} = {14\choose 10}= \frac{14!}{10!4!}
  $$

## Chapter 2: Discrete Random Variables

### 2.1 Intro

* A random variable is a real-valued variable whose value is determined by an underlying random experiment.
* Example：
  * Toss a coin 5 times
  * Sample space $\{TTTTT,TTTTH, \dots, HHHHH\}$.
  * Let us assume that we focus on the number of heads
  * So we can define a random variable (RV) whose value is the number of observed heads
  * $x$ can take values $0,1,2,3,4,5$
* Definition:
  * A random variable $X$ is a function from the sample space to the real numbers $X: S\rightarrow \mathbb{R}$
  * The range of a random variable $X$, $Range(X)$ or $R(X)$ is the set of possible values that $X$ can take
  * Categories of RVs
    * Three classes of RVs: Discrete, Continuous, Mixed
    * $X$ is a discrete RV if its range is countable.

### 2.2 Probability Mass Function (PMF)

* Def: $A={X=X_k}$ is defined as the set of outcomes $s$ in the sample space $S$ for which the value of $X$ is $x_k$

$$
A=\{s\in S|X(s)=x_k\}
$$

* Let $X$ be a discrete RV with range $R_X = \{x_1, x_2, \dots\}$ (Finite or countably infinite), the function $P_X(x_k)=Proba(X=x_k)~~~for ~~k=1,2,3,\dots$ is called the PMF of RV $X$
* Property of PMF
  * $0\leq P_X(x)\leq 1$ for all $x$
  * $\sum_{x\in R_x}P_X(x)=1$
  * For any set $A\sub R_X$, $P(X\in A) = \sum_{x\in A}P_X(x)$
  
### 2.3 Independent RVs

* Consider two RVs $X$ and $Y$

  If $P(X=x, Y=y) = P(X=x)\cdot P(Y=y)$ for all $x$ and $y$, Then $X$ and $Y$ are said to be independent RVs.

* Can be generalized to more than two RVs.

  Consider $n$ RVs $X_1, X_2, \dots, X_n$, If $P(X_1=x_1, X_2=x_2, \dots, X_n=x_n) = P(X_1=x_1)\cdot P(X_2=x_2)\dots \cdot P(X_n=x_n)$ for all $x_1, x_2, \dots, x_n$, then $X_1, X_2, \dots, X_n$ are independent.

### 2.4 Cumulative Distribution Function (CDF)

* Def: The CDF of a RV $X$ is defined as $F_X(x)=P(X\leq x)$ for all $x\in \mathbb R$

* Properties of CDF

  Let $X$ be a discrete RV with range $R_X = \{x_1, x_2, x_3, \dots\}$ with $x_1<x_2<\dots$

  * $F_X(x)$ for $x<x_1$ is equal to zero $\Rightarrow$ CDF starts always of zero, i.e. $F_x(-\infin)=0$

  * CDF is the form of a staircase. It jumps at each point in the range (i.e. CDF stays flat between $x_k$ and $x_{k+1}$), so we can write:

    * $F_X(x)=F_X(x_k)$ for $x_k\leq x\leq x_{k+1}$

    * $F_X(x_k)-F_X(x_k-\varepsilon)=P_X(x_k)$ for small $\varepsilon$

    * $y\geq x \Rightarrow F_Y(y)\geq F_X(x) \Rightarrow$ CDF is always an increasing function.

    * As $x\rightarrow +\infin$, $F_X(x)\rightarrow 1$

    * If we have the PMFof $X$, we can calculate the CDF
      $$
      F_X(x) = \sum_{x_k\leq x}P(X=x_k) = \sum_{x_k\leq x}P_X(x_k)
      $$

    * For all $a\leq b$, we can write $P(a<x\leq b)=F_X(b)-F_X(a)$
  
### 2.5 Expectation

* The average of a RV is also called mean or expected value

* Def: Let $X$ be a discrete RV with range $R_X=\{x_1, x_2, \dots\}$, then the expected value of $X$ is defined as
  $$
  E(X)=\sum_{x_k\in R_X}x_k~ P_X(x_k)
  $$
  which is the weighed average of the values of RV $X$ in the range

* Properties: Expectation is **Linear**
  * $E(ax+b)=aE(x)+b$ for all $a,b\in \mathbb R$
  * $E(X_1+X_2+\dots +X_n) = E(X_1)+E(X_2)+\dots+E(X_n)$  for any set of RVs $X_1, X_2, \dots, \_Xn$, regardless of the fact that $X_1, X_2, \dots, X_n$ are independent or not.

### 2.6 Functions of RVs

#### a.Def

* If $X$ is a RV and $Y=g(X)$ then $Y$ is also a RV

* So we can also talk about the range of $Y$, PMF of $Y$ and CDF of $Y$.

* The range of $Y$, $R_Y$ is given by $R_Y=\{g(x)|x\in R_X\}$

* Assuming that we know the PMF of $X$, then we can write the PMF of $Y$ as
  $$
  P_Y(y) = P(Y=y) = P(g(X)=y) = \sum_{x|g(x)=y}P_X(x)
  $$

#### b. Expected value of a function of a RV

$$
E(g(X))=\sum_{x_k\in R_X}g(x_k)\cdot P_X(x_k)
$$

#### c. Variance

* Variance is a measure how spread out the distribution of a RV is.

* Definition:
$$
\sigma_x^2=Var(X)=E\left((X-\mu_X)^2\right) = \sum_{x_k\in R(X)}(x_k-\mu_X)^2P_X(x_k) = E(X^2)-E^2(X) = \sum_{x_k\in R(X)}x_k^2P_X(x_k)-\mu_X^2
$$

* We also define the standard deviation of RV
  $$
  SD(X) = \sigma_X=\sqrt{Var(X)}
  $$

* Properties
  * $Var(aX+b)= a^2Var(X)$
  * If $X_1, X_2, \dots, X_n$ are independent RVs, then $Var(X_1+X_2+\dots+X_n)=Var(X_1)+Var(X_2)+\dots+Var(X_N)$

### 2.7 Special Distributions

#### a. Bernoulli Distribution (number of successes in 1 trial)

* Bernoulli RV is a RV that takes only two values say 0 and 1

* The PMF of $X\sim Bernoulli(P)$ is given by
  $$
  P_X(x) = \left\{
  \begin{array}{rcl}
  &p&for~~ x=1\\
  &1-p &for ~~x=0\\
  &0&otherwise
  \end{array}
  \right.
  $$

* Bernoulli RV is also called the Indicator RV

* The indicator RV $I_A$ for an event $A$ is defined as
  $$
  I_A = \left\{
  \begin{array}{rcl}
  &1&\text{for the case of event}~ A~ \text{occuring}\\
  &0 &otherwise
  \end{array}
  \right.
  $$
  Indicator RV for an event $A$ has Bernoulli distribution with parameter $p=P(A)$

  So we can write $I_A \sim Bernoulli\left(P(A)\right)$

#### b. Geometric Distribution (number of trials until the first success)

$$R_X=\{1,2,3,4,\dots\}$$

$$P_X(k) = p(1-p)^{k-1}$$

* Remark: some books define the Geometric RV $Y$ as the number of failures before observing the first success

  $$R_Y=\{0, 1,2,3,4,\dots\}$$

  $$P_Y(k) = p(1-p)^k~~~~~for~k=0,1,2,\dots$$

#### c. Binomial Distribution (number of successes in $n$ trials), $X\sim B(n,p)$

$$R_X=\{1,2,3,4,\dots,n\}$$

$$P_X(k) = {n\choose k} p^k(1-p)^{n-k} ~~~~~~for ~~k=0,1,2,\dots, n$$

* Lemma: Binomial RV is a sum of Bernoulli RVs

  If $X_1, X_2, \dots, X_n$ are independent $Bernoulli(p)$RVs, then the RV

  $X = X_1+X_2+ \dots+ X_n$ has a $Binomial(n,p)$

* Implication: $X\sim B(n,p), Y\sim B(m,p), Z=X+Y$

  Then $Z\sim B(n+m,p)$

#### d. Negative Binomial (Pascal) Distribution (number of trials until $k^{th}$ success), $X\sim Pascal(k,p)$

$$R_X=\{k, k+1, k+2,\dots\}$$

$$
P_X(x) = \left\{
\begin{array}{rcl}
&{x-1\choose k-1}p^k(1-p)^{x-k}&for~~ k\in R_X\\
&0&otherwise
\end{array}
\right.
$$

#### e. Hypergeometric Distribution

* You have a bag that contains $b$ blue balls and $r$ red balls. Choose randomly without replacement $k\leq b+r$ balls. Let $X$ be the number of blue balls that you randomly picked.

* $R_X=\{max(0,k-r), max(0, k-r)+1, \dots, min(k,b)\}$

* In general $X$ is said to be a Hypergeometrix RV with parameters $b$ and $r$ shown as
  $$
  X\sim Hypergeometric(b,r,k)
  $$

  $$
  P_X(x) = \left\{
  \begin{array}{rcl}
  &\frac{{b\choose x}{r\choose k-x}}{b+r\choose k}&for~~ x\in R_X\\
  &0&otherwise
  \end{array}
  \right.
  $$

#### f. Poisson Distribution

* A RV $X$ is said to be a Poisson RV with parameter $\lambda$ shown as $X\sim Poisson(\lambda)$ if its range is $R_X=\{0, 1,2,3,4,\dots\}$, and
  $$
  P_X(x) = \left\{
  \begin{array}{rcl}
  &\frac{e^{-\lambda}\lambda^k}{k!}&for~~ k\in R_X\\
  &0&otherwise
  \end{array}
  \right.
  $$

* Remark: The Poisson distribution can be viewed as an approximation of the Binomial distribution

* Theorem: Let $X\sim B(n,p=\frac \lambda n)$ with a fixed $\lambda>0$. Then for any $k=0,1,2\dots$, we have
  $$
  \lim_{n\rightarrow+\infin}P_X(k)=\frac{e^{-\lambda}\lambda^k}{k!}
  $$

#### g. Expectation of special distributions

$$
X\sim Bernoulli(p)\Rightarrow \left\{
\begin{array}{rcl}
&E(X)=p \\
&Var(X)=p(1-p)
\end{array}
\right.
$$

$$
X\sim Geometric(p)\Rightarrow
\left\{
\begin{array}{rcl}
&E(X)=\frac 1 p  \\
&Var(X)=\frac{1-p}{p^2}
\end{array}
\right.
$$

$$
X\sim Poisson(\lambda)\Rightarrow \left\{
\begin{array}{rcl}
&E(X)=\lambda\\
&Var(X)=\lambda
\end{array}
\right.
$$

$$
X\sim Binomial(n,p)\Rightarrow \left\{
\begin{array}{rcl}
&E(X)=np \\
&Var(X)=np(1-p)
\end{array}
\right.
$$

$$
X\sim Pascal(k, p)\Rightarrow
\left\{
\begin{array}{rcl}
&E(X)=\frac k p \\
&Var(X)=\frac{k(1-p)}{p^2}
\end{array}
\right.
$$

$$
X\sim Hypergeometric(b,r,k)\Rightarrow E(X)=\frac{kb}{b+r}
$$

## Chapter 3: Continuous RVs

### 3.1 Introduction

* Continuous RVs have a range in the form of :
  * interval on the real number line
  * Union of non overlapping interval on real line
  
### 3.2 CDF and Probability Density Function (PDF)

* **CDF**

  * Def: A RV $X$ is said to be continuous if $F_X(x)$ is a continuous function for all $x\in \mathbb R$
  * The CDF of a continuous  function does not have jumps. (this is consistent with $P_X(x)=0$)

* **PDF**

  * For continuous RVs, the CDF works but PMF does not since $P(X=x)=0$

  * Instead, we introduce the PDF

  * For continuous RV, we define the function $f_X(x)=\lim_{\Delta\rightarrow 0^+}\frac{P(x<X\leq  x+\Delta)}\Delta$

    Note that $P(x<X<x+\Delta)=F_X(x+\Delta)-F_X(x)$

    Thus, we get $f_X(x) = \frac{dF_X(x)}{dx}=F'_X(x)$

  * For a uniform RV

$$
f_X(x) = \left\{
\begin{array}{rcl}
&0& for ~~x<a\\
&\frac 1{b-a} &for ~~a\leq x<b\\
&0&for ~~x\geq b
\end{array}
\right.
$$

* Properties of PDF

  Consider a continuous RV with PDF $f_X(x)$, we have:

  * $f_X(x)\geq 0$ for all $x\in \mathbb R$
  * $\int_{-\infin}^{+\infin}f_X(x)dx=1$
  * $P(a<x\leq b)=F_X(b)-F_X(a)=\int_a^bf_X(x)dx$
  * More generally for a set $A$, $P(x\in A)=\int_Af_X(x)dx$
  * Range of $X$ is defined as $R_X=\{x|f_X(x)>0\}$
  
### 3.3 Expected value and variance

#### a. basics

* Def: $\mu_X=E(X)=\int_{-\infin}^{+\infin}xf_X(x)dx$

* More generally: $E\left(g(X)\right)=\int_{-\infin}^{+\infin}g(x)f_X(x)dx$

* $\sigma_X^2=Var(X)=E\left((X-\mu_X)^2\right) = E(X^2)-E^2(X)$

* Define a **Standard RV**:

  For any RV $X$, we can define/introduce its standard RV
  $$
  Z=\frac{X-\mu_X}{\sigma_x}
  $$
  $E(Z)=0, Var(Z)=1$

#### b. Moment Generating Function (MGF)

* Moments (centered around $\mu_X$): $E\left((X-\mu_X)^n\right)$
* Moments (centered around zero): $E\left(X^n\right)$
* Moment Generating Function (MGF)
  * Def: The MGF of a RV $X$ is defined as

$$
M_X(s)=E(e^{sX})=\int_{-\infin}^{+\infin}e^{sx}f_X(x)dx~~~~~for ~~s\in[a,b]~~~\text{where this integral converges}
$$

* Properties of MGF

$$
M_X(s)=E(e^{sX})=E(1+sx+\frac{s^2X^2}2+\frac{s^3X^3}{3!}+\dots)=\sum_{k=0}^{+\infin}\frac{s^k}{k!}E(X^k)
$$

​where $E(X^k)$ is the Moments of RV $X$.

* $M_X(s)|_{s=0}=E(e^{0X})=1$
* $\frac{dM_X(s)}{ds}|_{s=0}=E(Xe^{sX})|_{s=0}=E(X)$, which is the First Moment of $X$
* $E(X^n)=\frac{d^nM_X(s)}{ds^n}|_{s=0}$

* Example:
  $$
  f_X(x)=\frac 1{\pi(1+x^2)}~~for~~ x\in \mathbb R
  $$
  This is Cauchy PDF
  $$
  M_X(s)=E(e^{sX})=\int_{-\infin}^{+\infin}\frac{e^{sx}}{\pi(1+x^2)}dx\stackrel{{\text{does not converge}}}{\longrightarrow}+\infin
  $$
  In this example, MGF does not exist

#### c. Characteristic Function (CF)

We can use CF for above example
$$
\Phi_X(\omega)=E(e^{j\omega x})=\int_{-\infin}^{+\infin}{e^{j\omega x}}f_X(x)dx~~~~~\text{with}~~j^2=-1
$$

* Properties of CF
  $$
  |\Phi_X(\omega)|=|E(e^{j\omega x})|=|\int_{-\infin}^{+\infin}{e^{j\omega x}}f_X(x)dx|\leq \int_{-\infin}^{+\infin}|{e^{j\omega x}}|\cdot |f_X(x)|dx=\int_{-\infin}^{+\infin}f_X(x)dx=1
  $$

  $$
  E(X^n)=(-j)^n\frac{d^n\Phi_X(\omega)}{d\omega^n}|_{\omega=0}
  $$

### 3.4 Function of Continuous RV

* If $X$ is a continuous RV, then $Y=g(X)$ is also a RV.
* Typically, we start by finding the CDF of $Y$ $\Rightarrow$ we differentiate CDF to deduce the PDF of $Y$.

#### a. Method of Transformations

**Theorem 1**: Suppose that $X$ is a continuous RV and $g: \mathbb R\rightarrow \mathbb R$ is a strictly monotonic differentiable function. Let $Y=g(X)$. Then the PDF of $Y$ is given by:
$$
f_Y(y) = \left\{
\begin{array}{rcl}
&\frac {f_X(x_1)}{|g'(x_1)|}=f_X(x)\cdot |\frac{dx_1}{dy}| &\text{with} ~~g(x_1)=y\\
&0&\text{if} ~~g(x)=y ~~ \text{doesn't~have~a~solution}
\end{array}
\right.
$$

* We can extend the previous Theorem to a more general case for $g$ not monotonic. We can divide $g$ into finite number of monotonic differentiable parts.
  
**Theorem 2**: Consider a continuous RV $X$ with domain $R_X$. Let $Y=g(X)$. Suppose that we can partition $R_X$ into a finite number of intervals such that $g(X)$ is strictly monotone and differentiable on each partition. Then the PDF of $Y$ is given by
$$
f_Y(y)=\sum_{i=1}^n\frac{f_X(x_i)}{|g'(x_i)|}=\sum_{i=1}^nf_X(x_i)|\frac{dx_i}{dy}|\\
\text{with~~} x_1, x_2, \dots, x_n \text{~~are real solutions for~~} g(x)=y
$$

#### b. Examples

* Exp1: RV $X$ with PDF $f_X(x)= 4x^3$ for $0<x\leq 1$ and $f_X(x)=0$ otherwise.

  * Q: Find the PDF of $Y=\frac 1 X$

  * A1: $R_Y=[1,+\infin)$

    ​Use method of transformation

    ​$f_Y(y)=\frac{f_X(x_1)}{|g'(x_1)|}$ with $x_1=g^{-1}(y)=\frac 1 y$

    ​Thus
    $$
    f_Y(y)=
    \left\{
    \begin{array}{rcl}
    &\frac{f_X(x_1)}{|-\frac 1{x^2}|}=\frac{\frac 4 {y^3}}{y^2}=\frac 4{y^5} ~~~&for~~y\geq1\\
    &0&\text{otherwise}
    \end{array}
    \right.
    $$

  * A2: CDF-based approach
    $$
    F_Y(y)=P(Y\leq y)=P(\frac 1 X\leq y)=P(X\geq \frac 1 y)=1-F_X(\frac 1 y)\\
    F_X(x)=\int_0^x4x^3dx=x^4\\
    f_Y(y)=\frac{dF_Y(y)}{dy}=\frac 4{y^5}
    $$

* Exp2: RV $X$ with PDF $f_X(x)=\frac 1{\sqrt{2\pi}}e^{-\frac{x^2}2}$

  Let $Y=g(X)=x^2$, $g'(x)=2x$, $R_Y=[0,+\infin)$

  $x_1=\sqrt y,~ x_2=-\sqrt y$

  * A1: Apply Theorem 2:

    $$
    f_Y(y)=\frac{f_X(x_1)}{|g'(x_1)|}+\frac{f_X(x_2)}{|g'(x_2)|}=\frac{f_X(\sqrt y)}{|2\sqrt y|}+\frac{f_X(\sqrt y)}{|2\sqrt y|}\\
    f_Y(y)=
    \left\{
    \begin{array}{rcl}
    &\frac{1}{\sqrt{2\pi y}}e^{-\frac y 2} ~~~&for~~y\geq0\\
    &0&\text{otherwise}
    \end{array}
    \right.
    $$
  * A2: CDF approach
    $$
    F_Y(y)=P(Y\leq y)=P(X^2\leq y)=P(-\sqrt y\leq x\leq \sqrt y)~~~~~for ~~y\geq 0\\
    F_Y(y)=F_X(\sqrt y)-F_X(-\sqrt y)\\
    f_Y(y)=\frac 1{2\sqrt y}f_X(\sqrt y)+\frac 1{2\sqrt y}f_X(-\sqrt y)
    $$

### 3.5 Special Continuous Distributions

#### a. Uniform distribution

* PDF:
  $$
  f_X(x) = \left\{
  \begin{array}{rcl}
  &\frac 1{b-a} &for ~~a\leq x<b\\
  &0&otherwise
  \end{array}
  \right.
  $$
* CDF:
  $$
  F_X(x) = \left\{
  \begin{array}{rcl}
  &0& for ~~x<a\\
  &\frac {x-a}{b-a} &for ~~a\leq x<b\\
  &1&for ~~x\geq b
  \end{array}
  \right.
  $$
* $E(X)=\frac{a+b}2$, $Var(X)=\frac {(b-a)^2}{12}$

#### b. Exponential Distribution

* $X\sim Exponential(\lambda)$ if

$$
f_X(x) = \left\{
\begin{array}{rcl}
&\lambda e^{-\lambda x} &for~~ x\geq 0\\
&0&otherwise
\end{array}
\right.
$$

* CDF of $X$

$$
F_X(x) = \left\{
\begin{array}{rcl}
&1- e^{-\lambda x} &for~~ x\geq 0\\
&0&otherwise
\end{array}
\right.
$$

* $E(X)=\frac 1\lambda$, $Var(X)=\frac 1{\lambda^2}$

* Properties of Exponential RV

  * P1: Relation to Geometric RV

    The exponential distribution can be viewed as the continuous version of the geometric RV

    Suppose that you toss a coin until you observe the first head and  the RV $X$ be the time you observe the first head. So it we let $\Delta$ be the time between two tosses and the proba of heads, let $p=\Delta \cdot \lambda \text { then, as }$ $\Delta \rightarrow 0, x \sim\operatorname{Exp}(\lambda)$

  * P2: Memoryless Property of Exponential RV
    Theorem:

    Consider $X\sim Exp(\lambda)$ with $\lambda>0$, then
    $$
    P(X>x+\delta|x>\delta)=P(X>x)~~~~~\text{for all }\delta \text{ and }x\geq0
    $$

#### c. Gaussian (Normal) Distribution $X\sim N(\mu,\sigma^2)$

$$
f_X(x)=\frac 1 {\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}~~~~~for~~ -\infin<x<+\infin
$$

* Standard Gaussian $N(0,1)$, $f_X(x)=\frac 1 {\sqrt{2\pi}}e^{-\frac{x^2}{2}}$

* CDF of $N(0,1)$: $F_X(x)=\int_{-\infin}^x\frac 1{\sqrt{2\pi}}e^{-\frac{t^2}2}dt = \phi(x)$

* For $X\sim N(\mu,\sigma^2)$, $F_X(x)=\phi(\frac{x-\mu}\sigma)$

  * Properties of $\phi(x)$:

    * $\lim_{x\rightarrow -\infin}\phi(x)=0$

    * $\lim_{x\rightarrow +\infin}\phi(x)=1$

    * $\phi(0)=\frac 1 2$

    * $\phi(-x)=1-\phi(x)$

    * Useful bound:
      $$
      \frac 1 {\sqrt{2\pi}}\frac {x}{x^2+1}e^{-\frac{x^2}{2}}\leq 1-\phi (x)\leq\frac 1 {\sqrt{2\pi}} \frac 1 x e^{-\frac{x^2}{2}}
      $$

    * If $X\sim N(\mu_X,\sigma_X^2)$ and $Y=aX+b$, then $Y\sim N(a\mu_X+b,~~a^2\sigma_X^2)$
  
### 3.7 Mixed RVs

* Def: A Mixed RV has a discrete part and a continuous part.

* Example:

  Consider a mixed RV $Y$ with CDF $F_Y(y)$ given by:
  $$
  F_X(x) = \left\{
  \begin{array}{rcl}
  &1&for ~~y\geq \frac 12\\
  &y^2 &for ~~0\leq y<\frac 12\\
  &0& otherwise\\
  \end{array}
  \right.
  $$

* Note that the CDF of $Y$ is not continuous as there is a jump at $y=\frac 12$

* Note also that we do not have the staircase form, so $Y$ is not a discrete RV

* More generally, the CDF of $Y$ has continuous part and discrete part, so we can write
  $$
  F_Y(y)=C(y)+D(y)
  $$
  with

$$
C(y)=\left\{
\begin{array}{rcl}
&1/4&for ~~y\geq \frac 12\\
&y^2 &for ~~0\leq y<\frac 12\\
&0& otherwise\\
\end{array}
\right.\\
D(y)=\left\{
\begin{array}{rcl}
&3/4&for ~~y\geq \frac 12\\

&0& otherwise\\
\end{array}
\right.\\
$$

* Using the delta function in the PDF expressions of mixed RVs (and discrete RV)
  $$
  f_X(x)=\sum_ka_k\delta(x-x_k)+g(x)
  $$
  where $a_k=P(X=x_k)$ and $g(x)\geq 0$ that does not contain any delta functions. So we have
  $$
  \int_{-\infin}^{+\infin}f_X(x)dx=\sum_ka_k+\int_{-\infin}^{+\infin}g(x)dx=1
  $$
  
* As a special case, if $X$ is a discrete RV with range $R_X=\{x_1,x_2,\dots\}$ and PMF $P_X(x)$, we can define its PDF as
  $$
   f_X(x)=\sum_{x\in R_X}P_X(x_k)\delta(x-x_k)
  $$

## Chapter 4: Simulations of RVs

### 4.1 Method of Inverse Transform

#### a.Method

* Suppose we want to generate a RV $X$ with a prescribed CDF $F_X(x)$

* Note that the RV $Y=F_X(x)$ is $U(0,1)$, because
  $$
  f_Y(y)=\frac{f_X(x)}{|F_X'(x)|} = 1
  $$

* Thus given $U(0,1)$ random number generator $Y$, the inverse transform $X=F_X^{-1}(y)$ will gave the desired CDF $F_X(x)$

* The algorithmic steps for the inverse transform methods are as follows:

  1. Generate a random number from $Y\sim U(0,1)$, call it $y$.

  2. Computer the value $x$ such that $F_X(x)=y$ (i.e. $x=F_X^{-1}(y)$)
  3. Take $x$ to be the random number generated.

#### b.Examples

* Example 1:

$$
F_X(x) = \left\{
\begin{array}{rcl}
&0& for~~x<0\\
&\frac{y^2}9 &for ~~0\leq x<3\\
&1&for ~~x\geq 3\\
\end{array}
\right.\\
F_X(x)=y \Rightarrow \frac 19x^2=y \Rightarrow x=\sqrt{9y}\\
y\sim U(0,1)\Rightarrow x=\sqrt{9y}\sim F_X(x)
$$

* Example 2:

  Suppose we want to generate a RV with an exponential distribution given by:
  $$
  f_X(x)=\lambda e^{-\lambda x}u(x)~~~~\text{ with } \lambda>0 \text{ and u(x) is the unit step function}\\
  F_X(x)=1-e^{-\lambda x}
  $$
  Therefore given $y$, we can get $x$ by the mapping $1-e^{-\lambda x}=y$, i.e. $x=-\frac{\ln(1-y)}\lambda$

  Since $1-y$ is also uniformly distributed over $[0,1]$, the above expression can also be re-written as:
  $$
  x=-\frac {\ln y}\lambda
  $$

* Example 3: Generation of discrete RV

  Since $P(X=x_k)=P_X(x_k)=F_X(x_k)-F_X(x_{k-1})$, so the inverse mapping is:
  $$
  F_X(x_{k-1})<y<F_X(x_k) \Rightarrow x_k=F_X^{-1}(y)
  $$
  So the algorithm steps for the generation of a discrete RV is:

  1. Generate a random number $Y\sim U(0,1)$. Call it $y$.
  2. Compute the value $x_k$ such that $F_X(x_{k-1})\leq y<F_X(x_k)$
  3. take $x_k$ to be the random number generated.

* For instance the generation of a Bernoulli RV $X\sim Bernoulli(p)$

  Generate $y$ from $U(0,1)$ and then:
  $$
  x= \left\{
  \begin{array}{rcl}
  &0& for~~y\leq 1-p\\
  &1&otherwise\\
  \end{array}
  \right.\\
  $$

### 4.2 Method of Acceptance-Rejection

* Inversing the CDF of a desired RV $X$ to be simulated can not always be done in closed form. For many samples inversing makes it computationally costly.

* Instead we can rely on Acceptance-Rejection Approach.

* Suppose that we want to generate RV $Y$ with PDF $f_Y(y)$

  To use the acceptance-rejection method, we have to find another RV $X$ with PDF $f_X(x)$ and a constant $c\geq 0$, such that
  $$
  \frac {f_X(x)}{f_Y(y)}\geq c>0~~~~~for ~~\forall x\in R_X
  $$
  Given that the steps of this method are as follows:

  1. Generate number $x$ with the PDF $f_X(x)$
  2. Generate a random number $u$ (independent of $x$) from $u\sim U(0,1)$
  3. if $u\leq \frac{cf_Y(x)}{f_X(x)}$ then the output $y=x$, else go to step 1.

* Remark: For this algorithm to be efficient, $c$ should be as close as possible to $1$.

### 4.3 Histogram and Empirical CDF

Assume that we have $\boldsymbol{n}$ i.i.d. observations $\left\{\boldsymbol{x}_{k}\right\}_{k=1}^{n}$ and we want to estimate the underlying PDF.

One simple method for doing this is to divide the range of observations into $k$ intervals at points $c_{0}, c_{1}, c_{2}, \ldots, c_{k}$.

Defining $\Delta_{j}=c_{j}-c_{j-1}, j=1,2, \ldots, k$ and $n_{j}$ as the number of observations that fall in the interval $\left(c_{j-1}, c_{j}\right]$, the estimated PDF $\hat{f}(x)=\frac{n_{j}}{n \Delta_{j}}, x \in\left(c_{j-1}, c_{j}\right]$. (Function $h(x)=n_{j}$ is called histogram.)

Note that $\boldsymbol{n}_{j}=\sum_{k=1}^{n} \mathbb{I}\left\{x_{k} \in\left(\boldsymbol{c}_{j-1}, c_{j}\right]\right\}$ and $\mathbb{E}\{\widehat{\boldsymbol{f}}(\boldsymbol{x})\}=\frac{\mathbb{E}\left\{\boldsymbol{n}_{j}\right\}}{n \Delta_{j}}=\frac{n \mathbb{P}\left(x_{k} \in\left(c_{j-1}, c_{j}\right]\right)}{n \Delta_{j}}=\frac{F_{X}\left(c_{j}\right)-F_{X}\left(c_{j-1}\right)}{\Delta_{j}}$
$$
\begin{aligned}
\operatorname{Var}\{\hat{f}(x)\}=& \frac{\operatorname{Var}\left\{n_{j}\right\}}{n^{2} \Delta_{j}^{2}}=\frac{n \mathbb{P}\left(x_{k} \in\left(c_{j-1}, c_{j}\right]\right)\left[1-\mathbb{P}\left(x_{k} \in\left(c_{j-1}, c_{j}\right]\right)\right]}{n^{2} \Delta_{j}^{2}} \\
&=\frac{\left[F_{X}\left(c_{j}\right)-F_{X}\left(c_{j-1}\right)\right]\left[1-\left[F_{X}\left(c_{j}\right)-F_{X}\left(c_{j-1}\right)\right]\right]}{n \Delta_{j}^{2}}
\end{aligned}
$$
For sufficiently small $\Delta_{j}, F_{X}\left(c_{j}\right)-F_{X}\left(c_{j-1}\right) \approx f_{X}\left(c_{j}\right) \Delta_{j}$

The empirical CDF (or cumulative histogram) is $\widehat{\boldsymbol{F}}(\boldsymbol{x})=\frac{\mathbb{1}}{n} \sum_{k=1}^{n} \mathbb{I}\left\{\boldsymbol{x}_{k} \leq x\right\}$, The sum $\sum_{k=1}^{n} \mathbb{I}\left\{\boldsymbol{x}_{k} \leq \boldsymbol{x}\right\}$ is equal to the number of observations less than or equal to $x$.
$$
\begin{aligned}
&\mathbb{E}\{\widehat{F}(x)\}=\frac{1}{n} \sum_{k=1}^{n} \mathbb{E}\left\{\mathbb{I}\left\{x_{k} \leq x\right\}\right\}=\frac{1}{n} \sum_{k=1}^{n} \mathbb{P}\left(x_{k} \leq x\right)=\frac{1}{n} \sum_{k=1}^{n} F_{X}(x)=F_{X}(x) \\
&\operatorname{Var}\{\widehat{F}(x)\}= \frac{1}{n^{2}} \sum_{k=1}^{n}
\operatorname{Var}\left\{\mathbb{I}\left\{x_{k} \leq x\right\}\right\}=\frac{1}{n^{2}} \sum_{k=1}^{n}\left[\mathbb{P}\left(x_{k} \leq x\right)-\left(\mathbb{P}\left(x_{k} \leq x\right)\right)^{2}\right] \\
&=\frac{F_{X}(x)-\left[F_{X}(x)\right]^{2}}{n} \leq \frac{1}{4 n} \\

\end{aligned}
$$

## Chapter 5: Probability Bounds

### 5.1 The Union Bound and its Extensions

#### a. Union Bound

For any events $A_1, A_2, \dots, A_n$, we have
$$
P(A_1\cup A_2\cup\dots\cup A_n)\leq P(A_1)+P(A_2)+\dots+P(A_n)
$$
It is widely use in the area of random graph

* Example: Consider an Erdos-Rany Graph model $G(n,p)$,

  where $n$ is the number of nodes in the graph  and each pair of nodes are connected by an edge with probability $p$.

  note that the occurrence of edges are independent from each other.

  Q: what is the probability that there exists an **isolated** node in the graph?

  A: Consider $G(n,p)$ model, let $B_n$ denote the event that $G(n,p)$ has at least one isolated node.

  ​Let $A_i$ be the event that the $i$-th node is isolated. Then $B_n=\bigcup_{i=1}^nA_i$
  $$
  P(B_n)=P(\bigcup_{i=1}^nA_i)\leq \sum_{i=1}^nP(A_i)=nP(A_1)
  $$
  Given that the connections are independent, thus $P(A_1)=(1-p)^{n-1}$

  Thus $P(B_n)\leq n(1-p)^{n-1}$

#### b. Extensions

* Generation of Union Bound: Bonferroni Inequality

* For any events $A_1, A_2, \dots, A_n$, we have:
  $$
  P(\bigcup_{i=1}^nA_i)\leq \sum_{i=1}^nP(A_i)\\
  P(\bigcup_{i=1}^nA_i)\geq \sum_{i=1}^nP(A_i)-\sum_{i< j}P(A_i\cap A_j)\\
  P(\bigcup_{i=1}^nA_i)\leq \sum_{i=1}^nP(A_i)-\sum_{i< j}P(A_i\cap A_j)+\sum_{i<j<k}P(A_i\cap A_j\cap A_k)
  $$
  In general, if you write an odd number of terms, then you get an upper bound and if you write an even number of terms you get a lower bound.

#### c. Expected Value of the number of Events

* The union bound formula is also equal to the expected value of the number of occurred events.

* Let $A_1, A_2, \dots, A_n$ be any events. Define the indicator random variables $X_1, X_2, \dots, X_n$ as $X_i = 1$ if $A_i$ occurs, $X_i=0$ otherwise.

  If we define $X=X_1+X_2+\dots+X_n$, then $X$ shows the number of events that actually occurs.
  $$
  E(X)=E(X_1+X_2+\dots+X_n)=E(X_1)+E(X_2)+\dots+E(X_n)=P(A_1)+P(A_2)+\dots+P(A_n)
  $$
  which is indeed the right-hand-side of the union-bound

* So with reference to previous Example, we can conclude that the expected number of isolated nodes in a graph randomly generated occurs to $G(n,p)$ is also equal to $E(X)=n(1-p)^{n-1}$

### 5.2 Markov, Chebyshev and Chernoff Inequalities

#### a. Markov Bound

Theorem: If $X$ is a non-negative RV, then
$$
P(X\leq a)\leq \frac{E(X)}a~~~~~\forall a>0
$$
Remark: This inequality is useful only when $a>E(x)$

#### b. Chebyshev Inequality

Theorem: For any arbitrary RV $Y$ and a constant $d$, we have:
$$
P(|y-E(Y)|\geq d)\leq \frac{Var(Y)}{d^2}
$$

#### c. Chernoff Inequality

Theorem: For an arbitrary RV $X$ and a constant $c$
$$
P(X\geq c)\leq \min_{s\geq0}\{e^{-s c}M_X(s)\}
$$
where $M_X(s)=E(e^{sX})$ is the MGF of RV $X$

In particular, it holds for $s^*$ for which $e^{-s^*c}M_X(s^*)$ is the minimum.

### 5.3 Jensen's Inequality

Theorem: If $g(x)$ is a convex function on $R_X$ and $E(g(X))$ and $g(E(X))$ are finite, then
$$
E(g(X))\geq g(E(X))
$$
Remark: If $g(x)$ is concave:
$$
E(g(X))\leq g(E(X))
$$

* Example: Let $X$ be a positive RV. Compare $E(X^a)$ with $(E(X))^a$ for $a\in\mathbb R$

  Note, for $a=0$, $E(X^0)=1=(E(X))^0$ and for $a=1$, $E(X^1)=E(X)=(E(X))^1$

  Let us assume $a\neq 0$ and $a\neq 1$

  If $g(x)=x^a, ~g'(x)=ax^{a-1}, ~g''(x)=a(a-1)x^{a-2}$

  If $a<0 ~~or~~a>1 $ then $g''(x)\geq 0~~ \Rightarrow~~g(x)$ is convex

  If $0<a<1$, then $g''(x)\leq 0~~\Rightarrow ~~ g(x)$ is concave. Then we can apply Jensen's Inequality

### 5.4 Holder, Cauchy Schwarz, Minkowski and Lyapunov Inequality

#### a. Holder Inequality

Theorem: If $p,q>1$ and $p^{-1}+q^{-1}=1$, then
$$
E(|XY|)\leq (E(|X|^p))^\frac1p(E(|Y|^q))^\frac1q
$$

#### b. Cauchy-Schwarz Inequality ($p=q=2$ in Holder Inequality)

$$
E(|XY|)\leq (E(X^2))^\frac12(E(Y^2))^\frac12\\
E^2(XY)\leq E(X^2)E(Y^2)
$$

#### c. Minkowski Inequality

Theorem:
$$
(E(|X+Y|^p))^\frac1p\leq (E(|X|^p))^\frac1p+(E(|Y|^p))^\frac1p
$$

#### d. Lyapunov Inequality

$$
(E(|Z^r|))^\frac1r\geq (E(|Z^s|))^\frac1s ~~~~~for ~~r\geq s\geq 0
$$

Implication: If RV $Z$ has a finite $r^{th}$ moment, then all $s^{th}$ moments are finite also for positive $0\leq s\leq r$

## Chapter 6: Two Random Variables

### 6.1 Joint Probability Mass Function (JPMF)

* Def: the JPMF of two discrete RVs $X$ and $Y$ is defined as:
  $$
  P_{X,Y}(x,y)=P(X=x ~~and ~~Y=y)
  $$

* Range: we can define the joint Range of $X$ and $Y$ as
  $$
  R_{XY}=\{(x,y)|P(x,y)>0\}
  $$
  If $R_X={x_1,x_2,\dots}$ and $R_Y={y_1, y_2,\dots}$, then for simplicity we can write:
  $$
  R_{XY}=R_X\times R_Y
  $$
  with the understanding that in this case for some pairs $(x_i,y_j)$ in $R_X\times R_Y$, $P_{XY}(x_i,y_j)$ might be equal to zero.

* Properties

  * For two discrete RVs $X$ and $Y$, we have
    $$
    \sum_{(x_i,y_j)\in R_{XY}}P_{X,Y}(x_i,y_j)=1
    $$

  * To find $P\left((x,y)\in A\right)$ for any set $A\sub \mathbb R^2$, we have
    $$
    P\left((x,y)\in A\right)=\sum_{(x_i,y_j)\in (A\cap R_{XY})}P_{X,Y}(x_i,y_j)
    $$

* Marginals PMFs of $X$ and $Y$
  $$
  P_X(x_i)=\sum_{y_j\in R_Y}P(x_i,y_j) ~~~~~\forall x_i\in R_X\\
  P_Y(y_j)=\sum_{x_i\in R_X}P(x_i,y_j) ~~~~~\forall y_j\in R_Y\\
  $$

### 6.2 Joint Cumulative Distribution Function (JCDF)

* Def: The JCDF of two RVs $X$ and $Y$ is defined as:
  $$
  F_{X,Y}(x,y)=P(X\leq x ~~and ~~Y\leq y)
  $$

* Properties

  1. $0\leq F_{X,Y}(x,y)\leq 1$

  2. $F_{X,Y}(+\infin,+\infin)=1$

      $F_{X,Y}(x,-\infin)=0$

      $F_{X,Y}(-\infin,y)=0$

  3. $$P(x_1<X\leq x_2,~~ y_1<Y\leq y_2)=F_{X,Y}(x_2,y_2)-F_{X,Y}(x_1,y_2)-F_{X,Y}(x_2,y_1)+F_{X,Y}(x_1,y_1)$$

* Marginal CDFs of $X$ and $Y$
  $$
  F_X(x)=F_{XY}(x,+\infin)~~~~~\forall x\\
  F_Y(y)=F_{XY}(+\infin, ~y)~~~~~\forall y\\
  $$

### 6.3 Conditioning and Independence

* Def1:

  * Conditional PMF on an Event
    $$
    P_{X|A}=P(X=x_i|A)=\frac{P(X=x_i ~~and ~~A)}{P(A)}~~~~~for ~~x_i\in R_X
    $$

  * Correspondingly, we can define a conditional CDF on an Event.
    $$
    F_{X|A}(x)=P(X\leq x|A)
    $$

* Def2: Conditional PMF of $X$ given $Y$
  $$
  P_{X|Y}(x_i|y_i)=\frac{P_{X,Y}(x_i,y_j)}{P_Y(y_j)}
  $$
  for any $x_i\in R_X$ and $y_j\in R_Y$

* Independence: Two discrete RVs $X$ and $Y$ are independent if
  $$
  P_{X,Y}(x,y)=P_X(x)\cdot P_Y(y) ~~~~~for ~all~~x~~and~~y
  $$

  * Equivalently, $X$ and $Y$ are independent if
    $$
    F_{X,Y}(x,y)=F_X(x)\cdot F_Y(y)~~~~~for ~all~~x~~and~~y
    $$

  * As a Result for independent RVs, the conditional PMF is equal to the marginal PMF
    $$
    P_{X|Y}(x_i|y_j)=P(X=x_i|Y=y_j)=\frac{P(X=x_i~~and~~Y=y_j)}{P(Y=y_j)}=P_X(x)
    $$

  * In other words, in this independent special case, knowing the value of $Y$ does not provide any information about $X$

### 6.4 Conditional Expectation

* Def1: Conditioning on an event
  $$
  E(X|A)=\sum_{x_i\in R_X}x_iP_X(x|A)
  $$

* Def2: Conditioning on another RV:
  $$
  E(X|Y=y_j)=\sum_{x_i\in R_X}x_iP_{X|Y}(x_i|y_j)
  $$

* Law of total Expectation

  1. If $B_1, B_2, \dots$ form a partition of sample space $S$, then
  $$
  E(X)=\sum_iE(X|B_i)\cdot P(B_i)
  $$
  2. For a RV $X$ and another discrete RV $Y$,
  $$
  E(X)=\sum_{y_j\in R_Y}E(X|Y=y_j)\cdot P_Y(y_j)
  $$

* Properties

  * Let $X=aY+b$ with $a$ and $b$ constants.
    $$
    E(X|Y)=aY+b
    $$

  * More generally, if we have two RVs and two function $g(\cdot )$ and $h(\cdot)$
    $$
    E(g(X)\cdot h(Y)|X)=g(X)\cdot E(h(Y)|X)
    $$

* Law of Iterated Expectations
  $$
  E(X)=E\left(E(X|Y)\right)
  $$

* If $X$ and $Y$ are independent
  * $E(X|Y)=E(X)$
  * $E(g(X)|Y)=E(g(X))$
  * $E(XY)=E(X)\cdot E(Y)$
  * $E(g(X)\cdot h(Y))=E(g(X))\cdot E(h(Y))$
  * The converse of the third and fourth formulas are not true.

### 6.5 Conditional Variance

Let $\mu_{X|Y}(y)=E(X|Y=y)$, then
$$
Var(X|Y=y)=E\left(\left(X-\mu_{X|Y}\left(y\right)\right)^2|Y=y\right)=\sum_{x_i\in R_X}\left(x_i-\mu_{X|Y}\left(y\right)\right)^2\cdot P_{X|Y(x_i)}=E(X^2|Y=y)-\left(\mu_{X|Y}\left(y\right)\right)^2
$$

* Law of Total Variance
  $$
  Var(X)= E\left(Var\left(X|Y\right)\right)+Var\left(E\left(X|Y\right)\right)
  $$

### 6.6 Functions of two RVs

* Consider $Z=g(X,Y)$ where $X$ and $Y$ are discrete RV and $g:\mathbb R\rightarrow \mathbb R$

* The PMF of $Z$ is given by:
  $$
  A_z=\{(x_i,y_j)\in R_{XY}:g(x_i,y_j)=z\}\\
  P_Z(z)=P(g(X,Y)=z)=\sum_{(x_i,y_j)\in A_z}P_{X,Y}(x_i,y_j)
  $$

* As a result we have
  $$
  E\left(g\left(X,Y\right)\right)=\sum_{(x_j,y_j)\in R_z}g(x_i, y_j)P_{X,Y}(x_i,y_j)
  $$

### 6.7 Joint Probability Density Function

* Def: Two continuous RVs $X$ and $Y$ are jointly continuous if there exists a non-negative $f_{X,Y}:\mathbb R^2\rightarrow \mathbb R$ such that for any set $A\subset \mathbb R^2$
  $$
  P\left(\left(X,Y\right)\in A\right)=\iint_Af_{X,Y}(x,y)dxdy
  $$
  The function $f_{X,Y}(x,y)$ is called the joint probability density function (PDF) of $X$ and $Y$

* Properties of $f_{X,Y}(x,y)$

  * The domain of $f_{X,Y}(x,y)$ is $\mathbb {R}^2$, but we can also define the range of $(X,Y)$ as
    $$
    R_{XY}=\{(x,y)|f_{X,Y}(x,y)>0\}
    $$

  *
    $$
    \int_{-\infin}^{+\infin}\int_{-\infin}^{+\infin}f_{X,Y}(x,y)dxdy=1
    $$

  * For small positive $\delta_x$ and $\delta_y$, we can write
    $$
    P(x<X\leq x+\delta x, ~~~y<Y<y+\delta y)\approx f_{X,Y}(x,y)\delta x\delta y
    $$

* Marginals

  * Similar to the discrete case, we can obtain marginal PDFs of $X$ and $Y$ from their joint PDF
    $$
    f_X(x)=\int_{-\infin}^{+\infin}f_{X,Y}(x,y)dy~~~~~for ~all ~~x\\
    f_Y(y)=\int_{-\infin}^{+\infin}f_{X,Y}(x,y)dx~~~~~for ~all ~~y
    $$

### 6.8 Joint CDF

* Def: The joint CDF of two RVs $X$ and $Y$ is defined as:
  $$
  F_{X,Y}(x,y)=P(X\leq x ~~and ~~Y\leq y)
  $$

* Properties

  * $F_{X,Y}(+\infin,+\infin)=1$

  * $F_{X,Y}(x,-\infin)=0$

  * $F_{X,Y}(-\infin,y)=0$

  * $F_{XY}(x,+\infin)=F_X(x)\leftarrow$ Marginal CDF of $X$

  * $F_{XY}(+\infin, ~y)=F_Y(y)\leftarrow$ Marginal CDF of $Y$

  * $P(x_1<X\leq x_2,~~ y_1<Y\leq y_2)=F_{X,Y}(x_2,y_2)-F_{X,Y}(x_1,y_2)-F_{X,Y}(x_2,y_1)+F_{X,Y}(x_1,y_1)$

  * If $X$ and $Y$ are independent
    $$
    f_{X,Y}(x,y)=f_X(x)\cdot f_Y(y)\\
    F_{X,Y}(x,y)=F_X(x)\cdot F_Y(y)
    $$

  *
    $$
    F_{X,Y}(x,y)=\int_{-\infin}^{x}\int_{-\infin}^{y}f_{X,Y}(u,v)dudv
    $$

  *
    $$
    f_{X,Y}(x,y)=\frac{\partial^2}{\partial x\partial y}F_{X,Y}(x,y)
    $$
  
*

### 6.9 Conditioning and Independence

For two RVs $X$ and $Y$, we can write
$$
P(X\in C|Y\in D)=\frac{P(X\in C, ~~Y\in D)}{P(Y\in D)}
$$
where $C, D\sub \mathbb R$

#### a. Conditioning on an Event

* Conditional CDF

  If $X$ is a continuous RV and $A$ is the event that $a\leq X< b$ (with the possibility of having $b=+\infin$ and $a=-\infin$), then
  $$
  F_{X|A}(x) = \left\{
  \begin{array}{rcl}
  &1&for ~~x\geq b\\
  &\frac{F_X(x)-F_X(a)}{F_X(b)-F_X(a)} &for ~~a\leq x<b\\
  &0& for~~x<a\\
  \end{array}
  \right.\\
  $$

* Conditional PDF
  $$
  f_{X|A}(x) = \left\{
  \begin{array}{rcl}
  
  &\frac{f_X(x)}{P(A)} &for ~~a\leq x<b\\
  &0& otherwise\\
  \end{array}
  \right.\\
  $$
  with $P(A)=F_X(b)-F_X(a)=\int_a^bf_X(x)dx$

* Conditional Moments
  $$
  E(X|A)=\int_{-\infin}^{+\infin}xf_{X|A}(x)dx\\
  E(X^n|A)=\int_{-\infin}^{+\infin}x^nf_{X|A}(x)dx\\
  E(g(X)|A)=\int_{-\infin}^{+\infin}g(x)f_{X|A}(x)dx\\
  $$
  in particular:
  $$
  Var(X|A)=E(X^2|A)-(E(X|A))^2
  $$

#### b. Conditioning on another RV

* Defs: For two joint continuous RVs $X$ and $Y$, we can define the following concepts

  * The conditional PDF of $X$ given $Y=y$
    $$
    f_{X|Y}(x|y)=\frac{f_{X,Y}(x,y)}{f_Y(y)}
    $$

  * The conditional probability that $X\in A$ given $Y=y$:
    $$
    P(X\in A|Y=y)=\int_Af_{X|Y}(x|y)dx
    $$

  * The conditional CDF of $X$ given $Y=y$
    $$
    F_{X|Y}(x|y)=P(X\leq x|Y=y)=\int_{-\infin}^xf_{X|Y}(x|y)dx
    $$

  * Conditional Expected value of $X$ given $Y=y$
    $$
    E(X|Y=y)=\int_{-\infin}^{+\infin}xf_{X|Y}(x|y)dx
    $$

  * More generally, we can have
    $$
    E(g(X)|Y=y)=\int_{-\infin}^{+\infin}g(x)f_{X|Y}(x|y)dx
    $$
    For instance we can define the conditional variance as
    $$
    Var(X|Y=y)=E(X^2|Y=y)-(E(X|Y=y))^2
    $$

#### c. Independent RVs

* $f_{X|Y}(x|y)=f_X(x)$

* $E(XY)=E(X)\cdot E(Y)$

* More generally, we have

  $E(g(X)\cdot h(Y))=E(g(X))\cdot E(h(Y))$

#### d. Functions of Two Continuous RVs

* $$
  E(g(X,Y))=\int_{-\infin}^{+\infin}\int_{-\infin}^{+\infin}g(x,y)f_{X,Y}(x,y)dxdy
  $$
  Consider $Z=g(X,Y)$

* CDF of $Z$:
  $$
  F_Z(z)=P(Z\leq z)=P(g(X,Y)\leq z)=\iint_Df_{X,Y}(x,y)dxdy
  $$
  where $D=\{(x,y)|g(x,y)\leq z\}$. We can get $f_Z(z)$ by differentiate $F_Z(z)$ with respect to $z$

* Direct PDF approach

  Theorem: Let $X$ and $Y$ be two jointly continuous RVs. Let $(Z,W)=g(X,Y)=(g_1(X,Y), g_2(X,Y))$ and $h=g^{-1}$, i.e. $(X,Y)=h(Z,W)=(h_1(Z,W), h_2(Z,W))$

  Then $Z$ and $W$ are jointly continuous RVs with joint PDF
  $$
  f_{ZW}(z,w)=f_{XY}(h_1(z,w), h_2(z,w))|J|
  $$
  with $J$ is the Jacobian of $h$
  $$
  J=\left | \begin{matrix}
  \frac{\partial h_1}{\partial z} &\frac{\partial h_1}{\partial w}   \\
  \frac{\partial h_2}{\partial z} &\frac{\partial h_2}{\partial w}   \\
  \end{matrix} \right |=\frac{\partial h_1}{\partial z}\cdot \frac{\partial h_2}{\partial w}-\frac{\partial h_1}{\partial w}\cdot \frac{\partial h_2}{\partial z}
  $$
  Finally $f_Z(z)=\int_{-\infin}^{+\infin}f_{Z,W}(z,w)dw$

* Applications:

  1. $Z=X+Y$
     $$
     f_{Z}(z)=\int_{-\infin}^{+\infin}f_{XY}(w, z-w)dw
     $$
     and if $X$ and $Y$ are independent, then
     $$
     f_{Z}(z)=\int_{-\infin}^{+\infin}f_{X}(w)f_Y(z-w)dw
     $$

  2. If $X\sim N(\mu_X,\sigma_X^2), ~~Y\sim N(\mu_Y,\sigma_Y^2)$ are independent, then $X+Y\sim N(\mu_X+\mu_Y,\sigma_X^2+\sigma_Y^2)$

#### e. Covariance and Correlation

* The covariance between $X$ and $Y$ gives information about how $X$ and $Y$ are statistically related

* Def1:
  $$
  Cov(X,Y)\triangleq E\left(\left(X-E\left(X\right)\right)\left(Y-E\left(Y\right)\right)\right)=E(XY)-E(X)\cdot E(Y)
  $$

* Properties 1:

  * $Cov(X,X) = Var(X)$

  * If $X$ and $Y$ are independent, then $Cov(X,Y)=0$

  * $Cov(X, Y)=Cov(Y,X)$

  * $Cov(aX, Y) = aCov(X, Y)$

  * $Cov(X+c, Y)=Cov(X, Y)$

  * $Cov(X+Y, Z)=Cov(X, Z)+Cov(Y, Z)$

  * More generally
    $$
    Cov(\sum_{i=1}^ma_iX_i, \sum_{j=1}^mb_iY_i)=\sum_{i=1}^m\sum_{j=1}^na_ib_jCov(X_i,Y_j)
    $$

  * If $Z=X+Y$,
    $$
    Var(Z)=E(Z^2)-E^2(Z)=E((X+Y)^2)-E^2(X+Y)
    =E(X^2+Y^2+2XY)-E^2(X)-E^2(Y)-2E(X)E(Y)\\
    =E(X^2)-E^2(X)+E(Y^2)-E^2(Y)+2E(XY)-2E(X)E(Y)
    =Var(X)+Var(Y)+2Cov(X,Y)
    $$
    Thus
    $$
    Var(X+Y)=Var(X)+Var(Y)+2Cov(X,Y)
    $$

  * More generally, for $a,b\in \mathbb R$, we can write:
    $$
    Var(aX+bY)=a^2Var(X)+b^2Var(Y)+2ab~Cov(X,Y)
    $$

* Def2: The correlation coefficient denoted by $\rho_{XY}$ is obtained by normalizing the covariance:
  $$
  \rho_{XY}=\rho(X,Y)=\frac{Cov(X,Y)}{\sqrt{Var(X)}\sqrt{Var(Y)}}=\frac{Cov(X,Y)}{\sigma_X\sigma_Y}
  $$

* Properties

  * $-1\leq \rho_{XY}\leq 1$
  * If $\rho_{XY}=1$, then $Y=aX+b$ with $a>0$
  * If $\rho_{XY}=-1$, then $Y=aX+b$ with $a<0$
  * $\rho(aX+b,cY+d)=\rho(X,Y)$

## Chapter 7: Multiple RVs

### 7.1 Joint Distributions and Independence

* Definitions

  * The joint PMF of $n$ discrete $X_1, X_2, \dots, X_n$ is
    $$
    P_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)\triangleq P(X_1=x_1, X_2=x_2, \dots, X_n=x_n)
    $$

  * The joint PDF of $n$ continuous RVs is denoted by $f_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)$ such that the probability of $A\sub \mathbb R^n$ is given by:
    $$
    P(({X_1, X_2, \dots, X_n})\in A)=\int_Af_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)dx_1dx_2\dots dx_n
    $$

* Marginals: Marginal of $X_1$ can be obtained from the joint PDF by
  $$
  f_{X_1}(x_1)=\int_{-\infin}^{+\infin}\dots \int_{-\infin}^{+\infin}f_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)dx_2dx_3\dots dx_n
  $$

* Joint CDF

  The joint CDF of $n$ RVs $X_{1}, X_{2}, \ldots, X_{n}$ is given by
  $$
  F_{X_1, X_2, \dots, X_n}\left(x_{1}, x_{2}, \ldots, x_{n}\right)=\operatorname{P}\left(X_{1} \leq x_{1}, X_{2} \leq x_{2}, \ldots, X_{n} \leqslant x_{n}\right)
  $$

* Independence

* Random variables $X_{1}, X_{2}, \ldots, X_{n}$ are independent, if for all $\left(x_{1}, x_{2}, \ldots, x_{n}\right) \in \mathbb{R}^{n}$, we hove
  $$
  F_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)=F_{X_1}(x_1)\cdot F_{X_2}(x_2)\cdot \ldots \cdot F_{X_n}(x_n)\\
  P_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)=P_{X_1}(x_1)\cdot P_{X_2}(x_2)\cdot \ldots \cdot P_{X_n}(x_n)~~~~~\text{for discrete case}\\
  f_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)=f_{X_1}(x_1)\cdot f_{X_2}(x_2)\cdot \ldots \cdot f_{X_n}(x_n)~~~~~\text{for continuous case}\\
  $$

* Implication of independence

  If $X_{1}, X_{2}, \ldots, X_{n}$ are independent, then $E(X_{1}, X_{2}, \ldots, X_{n})=E(X_1)\cdot E(X_2)\dots E(X_n)$

  More generally, $E(h_1(X_{1}), h_2(X_{2}), \ldots, h_n(X_{n}))=E(h_1(X_1))\cdot E(h_2(X_2))\dots E(h_n(X_n))$

* i.i.d (independent identically distributed) RVs are RVs that are independent and have exactly the same marginals i.e.
  $$
  F_{X_1}(x_1)= F_{X_2}(x_2)= \ldots = F_{X_n}(x_n)~~~~~for ~all ~~x\in\mathbb R
  $$

### 7.2 Random Vectors

#### a. Notations

* When we have $n$ RVs $X_{1}, X_{2}, \ldots, X_{n}$, we can put them in a (column) vector.
  $$
  \underline X=\left[\begin{matrix}
  X_1   \\
  X_2  \\
  \vdots\\
  X_n
  \end{matrix} \right]
  $$
  where $X$ is a $n$-dimensional column vector.

* The CDF of a random vector $X$
  $$F_{\underline X}(\underline x)=F_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)={P}\left(X_{1} \leq x_{1}, X_{2} \leq x_{2}, \ldots, X_{n} \leqslant x_{n}\right)$$

* The joint PDF can also be written as
  $$
  f_{\underline X}(\underline x)=f_{X_1, X_2, \dots, X_n}(x_1, x_2,\dots, x_n)
  $$

#### b. Expectations

* Expected Value Vector or Mean Vector
  $$
  E(\underline X)=\left[\begin{matrix}
  E(X_1)   \\
  E(X_2)  \\
  \vdots\\
  E(X_n)
  \end{matrix} \right]
  $$

* If we have a random matrix
  $$
  \begin{aligned}
  & {[M]=\left[\begin{array}{llll}
  X_{11} & X_{12} & \cdots & X_{1 n} \\
  X_{21} & X_{22} & \cdots & X_{2 n} \\
  X_{11} & X_{n 2} & \cdots & X_{n n}
  \end{array}\right]_{n \times n} \quad[M]=\left[X_{i j}\right]_{n \times n} } \\
  \rightarrow & \text { The mean Matrix } \\
  & E[(M)]=\left[\begin{array}{lll}
  E\left(X_{11}\right) & E\left(X_{12}\right) &\cdots E\left(X_{1n}\right) \\
  E\left(X_{21}\right) & E\left(X_{12}\right) & ~~~~~~ \vdots \\
  \vdots&\vdots&\ddots\vdots\\
  E\left(X_{n1}\right) & E\left(X_{n2}\right)&\cdots  E\left(X_{nn}\right)
  \end{array}\right]_{n \times n}
  \end{aligned}
  $$

* The linearity of Expectation is also valid for random vectors and random matrices

* So for example

  * $\underline Y=[A]\underline X+b$

    with $[A]$ is $m\times n$ fixed matrix and $b$ is a fixed $m$-dimensional vector

    $E(\underline Y)=[A]E(\underline X)+b$

  * If  $X_{1}, X_{2}, \ldots, X_{n}$ are $n$-dimensional vectors, then we have:
    $$
    E(a_1X_1+a_2X_2+\dots+a_nX_n)=a_1E(X_1)+a_2E(X_2)+\dots+a_nE(X_n)
    $$

#### c. Correlation and Covariance Matrix

* Def: For a random vector $\underline X$, we define the

  1. Correlation Matrix of $\underline X$ as
     $$
     [R]_{\underline X}=E(\underline X\underline X^\top)=\left[\begin{array}{lll}
     E\left(X_{1}^2\right) & E\left(X_{1}X_2\right) &\cdots E\left(X_1X_{n}\right) \\
     E\left(X_{2}X_1\right) & E\left(X_{2}^2\right) & ~~~~~~ \vdots \\
     \vdots&\vdots&\ddots\vdots\\
     E\left(X_{n}X_1\right) & E\left(X_{n}X_2\right)&\cdots  E\left(X_{n}^2\right)
     \end{array}\right]_{n \times n}
     $$

  2. Covariance Matrix of $X$ as
     $$
     [C]_{\underline X}=E\left(\left(\underline X-E\left(\underline X\right)\right)\left(\underline X-E\left(\underline X\right)\right)^\top\right)=[R]_{\underline X}-E(\underline X)\cdot E(\underline X^\top)\\
     =\left[\begin{array}{lll}
     Var\left(X_{1}\right) & Cov\left(X_{1}X_2\right) &\cdots Cov\left(X_1X_{n}\right) \\
     Cov\left(X_{2}X_1\right) & Var\left(X_{2}\right) & ~~~~~~ \vdots \\
     \vdots&\vdots&\ddots\vdots\\
     Cov\left(X_{n}X_1\right) & Cov\left(X_{n}X_2\right)&\cdots  Var\left(X_{n}\right)
     \end{array}\right]_{n \times n}
     $$

* Properties

  1. The covariance matrix $[C]_{\underline X}$ is a symmetric matrix
     $$
     C_{ij}=Cov(X_i,Y_j)=Cov(X_j,Y_i)=C_{ji}
     $$

  2. $[C]_{\underline X}$ can be diagonalized and all eigenvalues of $[C]_{\underline X}$ are real
  3. $[C]_{\underline X}$ is a positive semi-definite matrix (i.e.  $b^\top[C]_{\underline X}b\geq 0$ for all vector $b$)

* As an extension, we can also introduce for random vectors $X$ and $Y$

  * $[R]_{\underline X\underline Y}=E(\underline X\underline Y^\top)$, which is the cross-correlation matrix
  * $[C]_{\underline X\underline Y}=E\left(\left(\underline X-E\left(\underline X\right)\right)\left(\underline Y-E\left(\underline Y\right)\right)^\top\right)$, which is the cross-covariance matrix

### 7.3 Functions of Random Vectors

#### a. set-up

* Let $\underline X$ be an $n$-dimensional random vector with joint PDF $f_{\underline X}(\underline x)$.

* Let $G: \mathbb R^n\rightarrow\mathbb R^n$ be a continuous and invertible function with continuous partial derivatives and let us denote $H=G^{-1}$

* Let the random vector $\underline Y$ be given by $\underline Y=G\underline X$ (i.e. $\underline X=G^{-1}(\underline Y)=H(\underline Y))$)
  $$
  \underline{X}=\left[\begin{array}{c}
  x_{1} \\
  x_{2} \\
  \vdots \\
  x_{n}
  \end{array}\right]=\left[\begin{array}{c}
  H_{1}\left(Y_{1}, Y_{2}, \ldots, Y_{n}\right) \\
  H_{2}\left(Y_{1}, Y_{2}, \ldots, Y_{n}\right) \\
  \vdots \\
  H_{n}\left(Y_{1}, Y_{2}, \ldots, Y_{n}\right)
  \end{array}\right]_{n \times 1}
  $$

#### b. Main Result: Method of Transformation

The PDF of the mapped vector $\underline Y$,
$$
f_{\underline Y}(\underline y)=f_{Y_1, Y_2, \dots, Y_n}(y_1, y_2,\dots, y_n)
$$
is given by
$$
f_{\underline Y}(\underline y)=f_{\underline X}(H(\underline Y))\cdot |J|
$$
where $J$ is the Jacobian of $H$ defined by
$$
J=\operatorname{det}\left[\begin{array}{llll}
\frac{\partial H_{1}}{\partial y_{1}} & \frac{\partial H_{1}}{\partial y_{2}} & \cdots & \frac{\partial H_{1}}{\partial y_{n}} \\
\frac{\partial H_{2}}{\partial y_{1}} & \frac{\partial H_{2}}{\partial y_{2}} &\cdots & \frac{\partial H_{2}}{\partial y_{n}} \\
\vdots & \vdots& \ddots&\vdots\\
\frac{\partial H_{2}}{\partial y_{1}} & \frac{\partial H_{2}}{\partial y_{2}}&\cdots& \frac{\partial H_{n}}{\partial y_n}
\end{array}\right]_{n \times n}
$$
and evaluated at $(y_1,y_2,\dots,y_n)$

### 7.4 Normal (Gaussian) Random Vectors

#### a. General Case

* Def: A random vector $\underline X=\left[\begin{matrix}
  X_1   \\
  X_2  \\
  \vdots\\
  X_n
  \end{matrix} \right]$ is said to be Normal or Gaussian if the RVs $X_{1}, X_{2}, \ldots, X_{n}$ are jointly Gaussian, i.e. the joint PDF of $\{X_i\}_{i=1}^n$ is given by:
  $$
  \begin{aligned}
  &f_{\underline{X}}(\underline{x})=\frac{1}{(2 \pi)^{n / 2} \sqrt{\operatorname{det}[C]}} \exp \left[-\frac{1}{2}(\underline{X}-m)^{\top}[C]^{-1}(\underline{X}-\underline{m})\right]\\
  \\
  \\
  &\text { where } \quad m=\left[\begin{array}{c}
  m_{1} \\
  m_{2} \\
  \vdots \\
  m_{n}
  \end{array}\right] ~~~~~~~\text { with } m_{i}=E\left[X_{i}\right]\\
  \\
  \\
  &[C]=\left[\begin{array}{cccc}
  \operatorname{Cov}\left(X_{1}, X_{1}\right) & \operatorname{Cov}\left(X_{1}, X_{2}\right) & \ldots & \operatorname{Cov}\left(X_{1}, X_{n}\right) \\
  \vdots & \vdots & \ddots & \\
  \operatorname{Cov}\left(X_{1}, X_{n}\right) & \cdots & \cdots & \operatorname{Cov}\left(X_{1}, X_{n}\right)
  \end{array}\right]
  \end{aligned}
  $$
  
* Properties

  * Uncorrelation  $\iff$ Independece (Independence always means uncorrelation but uncorrelation means independence when it is Gaussian)

  * Linear Transformation Preserves "Gaussianity"
     Theorem: If $\underline X=[X_1, X_2, \dots, X_n]^\top$ is a Normal vector $\underline X\sim N(\underline m, [C])$, given $[A]$ is an $m\times n$ fixed matrix and $\underline b$ is an $m$-dimensional fixed vector, then
    $$
    {\underline Y}=[A]{\underline X}+{\underline b}\sim N([A]\underline m+\underline b, [A][C][A]^\top)
    $$
     Application: If $X_{1}, X_{2}, \ldots, X_{n}$ are correlated multi-variate Gaussian RVs (i.e. $[C]_{\underline X}$ is not diagnal), one can choose $[A]$ such that
    $$
    [C]_Y=[A][C]_X[A]^\top~~~~\text{is diagonal}
    $$
     Then $Y_{1}, Y_{2}, \ldots, Y_{n}$ are uncorrelated and because they are jointly Gaussian RVs, then they are independent.

  * Joint CF
    $$
    \Phi_{\underline X}(\underline \omega) \triangleq E(e^{j\underline \omega^\top\underline X})=E(e^{j\omega_1X_1+j\omega_2X_2+\dots+j\omega_nX_n})
    $$
    Since $\underline X$ is a jointly Gaussian RVs, we have
    $$
    \begin{aligned}

    \Phi_{\underline X}(\underline \omega)&=\exp \left[-\frac{1}{2} \omega^{\top}[C] \underline{\omega}+j m^{\top} \omega\right] \\
    &=\exp \left[-\frac{1}{2} \sum_{j=1}^{n} \sum_{k=1}^{n} \operatorname{Cov}\left[x_{j} x_{k}\right] \omega_{j} \omega_{k}+\right.\left.j \sum_{k=1}^{n} m_{k} \omega_{k}\right]
    \end{aligned}
    $$

  * Joint Moments

    Theorem: Let $X_{1}, X_{2}, \ldots, X_{n}$ be $n$-zero mean jointly Gaussian RVs then
    $$
    E\left[X_{1} X_{2} \ldots X_{n}\right]= \begin{cases}0 & \text {when n is odd } \\
    \sum \prod_{j \neq k}^{n} E\left[x_{j} x_{k}\right] &\text {when n is  even }\end{cases}
    $$
    where the sum is taken over all distinct pairs
    Illustration for $n=4$
    $$
    E\left(X_{1} X_{2} X_{3} X_{4}\right)=E\left(X_{1} X_{2}\right) E\left(X_{3} X_{4}\right)+E\left(X_{1} X_{3}\right) E\left(X_{2} X_{4}\right)+E\left(X_{1} X_{4}\right) E\left(X_{2} X_{3}\right)
    $$
    as a special case we can Let $X_1=X_2=X, Y_1=Y_2=Y$, then we have
    $$
    E(X^2Y^2)=E(X^2)E(Y^2)+2E(XY)
    $$

#### b. Special Case: $n=2$

* Definition: Two RVs $X$ and $Y$ are said to have bivariate normal distribution with parameters $\mu_X, \sigma_X^2,\mu_Y, \sigma_Y^2$, and $\rho$ then their joint PDF is given by:
  $$
  \begin{aligned}
  f_{X,Y}(x, y)=\frac{1}{2 \pi \sigma_{X} \sigma_{Y} \sqrt{1-\rho^{2}}} . \exp \left[-\frac{1}{2\left(1-\rho^{2}\right)}\left(\left(\frac{x-\mu_{X}}{\sigma_{X}}\right)^{2}+\left(\frac{y-\mu_{Y}}{\sigma_{Y}}\right)^{2}-2 \rho \frac{\left(x-\mu_{X}\right)(y-\mu_ Y)}{\sigma_{X} \sigma_{Y}}\right)\right]
  \end{aligned}
  $$

* Properties

  1. If $X$ and $Y$ are bivariate Normal and uncorrelated then they are independent

  2. If $X$ and $Y$ are bivariate Normal, then
    $$
    X\sim N(E(X),Var(X))\\
    Y\sim N(E(Y), Var(Y))
    $$

  3. Let $X$ and $Y$ be two bivariate normal RVs. Then there exist **independent standard** normal random variables $Z_1$ and $Z_2$ such that:
    $$
    X=\sigma_XZ_1+\mu_X\\
    Y=\sigma_Y(\rho Z_1+\sqrt{1-\rho^2}Z_2)+\mu_Y
    $$
    with $Z_1\sim N(0,1)$ and $Z_2\sim N(0,1)$ and they are independent.

  4. Theorem: Suppose  $X$ and $Y$ are jointly Normal RVs with parameters $\mu_X, \sigma_X^2,\mu_Y, \sigma_Y^2$, and $\rho$, then Given $X=x$, $Y$ is normally distributed with
    $$
    E(Y|X=x)=\mu_Y+\rho\sigma_Y\frac{x-\mu_X}{\sigma_X}\\
    Var(Y|X=x)=(1-\rho^2)\sigma_Y^2
    $$

  5. For $n=2$, the joint characteristic Function is
     $$
     \begin{aligned}
     &\Phi_{X_{1} X_{2}}\left(\omega_{1}, \omega_{2}\right)=E\left(e^{j \omega_{1} x_{1}+j \omega_{2} x_{2}}\right) \\
     &=\exp \left[-\frac{1}{2}\left(\sigma_{1}^{2} \omega_{1}^{2}+2 \omega_{1} \omega_{2} \rho_{12} \sigma_{1} \sigma_{2}+\sigma_{2}^{2} \omega_{2}^{2}\right)+{j m_{1} \omega_{1}+j m_{2} \omega_{2}}\right]
     \end{aligned}
    $$

## Chapter 8: Sum of RVs

### 8.1: General Set-up

Let $X_1, X_2, ..., X_n$ be a set of RVs and define
$S_n = \sum_{i=1}^{n}X_i$,
what are the statistics of $S_n$?

### 8.2 Mean and Variance

#### Case 1: n is constant

* $E[S_n] = E[\sum_{i=1}^{n}X_i] = \sum_{i=1}^{n}E[X_i]$

#### Case 2: n is random (N is a RV)


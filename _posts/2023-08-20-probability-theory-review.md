---
layout: post
title: "probability theory review"
---

__1__ Player $M$ has 1 dollar and player $N$ has 2 dollars. Each game gives the winner 1 from the other. As a better player, $M$ wins $2/3$ of the games. They play until one of them is bankrupt. What is the probability that $M$ wins?

__solution:__ This is a Markov chain problem. We consider the following state space: $\{(0,3),(1,2),(2,1),(3,0)\}$ where the first number in the ordered pair stand for the amount of money $M$ has and the second stand for the amound of money $N$ has. Note the $(0,3)$ and $(3,0)$ are absorbing states. With the above setup, the transition matrix looks like:

$$
\begin{pmatrix}
1 & 1/3 & 0 & 0\\
0 & 0 & 1/3 & 0\\
0 & 2/3 & 0 & 0\\
0 & 0 & 2/3 & 1\\
\end{pmatrix}
$$

By the equation for absorption probability, let $a_i$ be the probability of reaching from state $i$ to state $1$. Then $a_1=0$, $a_4=1$, $a_2=\sum_{i=1}^4 p_{2i}a_i=\frac{1}{3}a_1+\frac{2}{3}a_3=\frac{2}{3}a_3$, $a_3=\sum_{i=1}^4 p_{3i}a_i=\frac{1}{3}a_2+\frac{2}{3}a_4=\frac{1}{3}a_2+\frac{2}{3}$. So, $a_2=\frac{4}{7}$.

__extension:__ Let the transition matrix be $T$ and the vector of probability of reaching state $1$ be $A$, then $TA=A$. We also want a solution with first entry of $A$ being $1$ and the last entry being $0$. Such a vector exists because the probabilistic meaning of the vector (the probability of reaching an absorption state starting from a given state). The existence could also be seen by acting on $I=(0,...,0,1,0,...,0)$ (the $i_1$th entry is $1$ and all other entries are $0$) with $T$. Suppose the Markov process described by transition matrix $T$ has absorbing states $i_1, ,...i_k$, then $T^nI$s are $0$ on the $i_2,...,i_k$th entries. The sequence $T^nI$ also converges due to Brower's fixed point theorem, thereby proving our theorem. I suspect there must be an algebraic proof that such a vector (a vector that's $1$ on the $i_1$th entry, $0$ on $i_2,...i_k$th entry, and satisfies $Tv=v$ for a Markov transition matrix) exists but couldn't find it. （I assumed that the vector $A$ of absorption probabilities would be unique, which is wrong. Refer to theorem 1.3.2 of Norris' Markov Chains.)


__2__ Two players bet on rolls of the total of two standard six-face dice. Player A bets that a sum of 12 will occur first. Player B bets that two consecutive 7s will occur first. The players keep rolling the dice and record the sums until one player wins. What is the probability that A will win?

__solution:__ Consider the following state space $(7,7),7,12,s$ with $(7,7)$ standing for B winning, $7$ standing for a single 7 occuring before any $12$ or consecutive $7$s occur, $12$ standing for A winning, and $s$ standing for the starting state. $s$ has $1/6$ probability going to $7$, $1/36$ to $12$, and $29/36$ to itself. $7$ has $1/6$ probability going to $(7,7)$, $29/36$ to $s$, and $1/36$ to $12$. $12$ has probability $1$ going to itself. And $(7,7)$ has probability $1$ going to itself. Assume $a_s, a_{(7,7)}, a_7, a_{12}$ are the probabilities of ending up at $12$, then $a_s=\frac{1}{6}a_7+\frac{1}{36}a_{12}+\frac{29}{36}a_s=\frac{1}{6}a_7+\frac{1}{36}+\frac{29}{36}a_s$, $a_7=\frac{1}{6}a_{(7,7)}+\frac{29}{36}a_s+\frac{1}{36}a_{12}=\frac{29}{36}a_s+\frac{1}{36}$. These equations give that $a_s=7/13$. 

**extension:** The result could be generalized to 2 players betting on whether $c+s$ or $c+t$ appear first with $c$ being the maximum common initial substring of $c+s$ and $c+t$. Let $s_i$ denote the string formed by the first $i$ characteers of $s$. Then it suffices to consider a Markov process with state space consisting of $o, c_1,...,c,c+s_1,...,c+s,c+t_1,...,c+t$ and transition matrix $T$. Here $o$ denotes the original state. Note that $c+s$ and $c+t$ are absorption states and it suffices to consider the absorption probability of starting from $o$ and going to $c+s$ to determine the probability of winning of the 2 players. 


**3a** If you keep on tossing a fair coin, what is the expected number of tosses such that you can have HHH (heads heads heads) in a row?

**solution:** We consider a Markov chain with states $O,H,HH,HHH$ meaning encountering $0$ to $3$ consecutive heads. $O$ has probability $1/2$ going to $O$, $1/2$ going to $H$; $H$ has probability $1/2$ going to $O$ and $1/2$ to $HH$; $HH$ has probability $1/2$ going to $O$ and $1/2$ going to $HHH$; $HHH$ is an absorbing state. Suppose $s_a$ is an absorbing state and let $t_s$ denote the expected time it takes to go from state $s$ to state $s_a$, then $t_s=\sum_{s'}1+p_{ss'}t_{s'}$, or $MT+(1,...,1)=T$. We have $t_O=1+\frac{1}{2}t_O+\frac{1}{2}t_H$, $t_H=1+\frac{1}{2}t_O+\frac{1}{2}T_{HH}$, $t_{HH}=1+\frac{1}{2}t_O$, and $t_{HHH}=0$. This gives $t_O=14$. So, the expected number of tosses such that you can have $HHH$ in a row is $14$. 

**extension** (Refer to theorem 1.3.5 of Norris' Markov Chains for a characterization of the expected hitting times of the absorption state.)

**Definition** Variance is defined as $s^2=\sum_{i=1}^n(x_i-\overline{x})^2/(n-1) and standard deviation is defined as $s=\sqrt{s^2}$. 

**Definition** The sample 100p percentile is that data value such that at least 100p percent of the data are less than or equal to it and at least 100(1 − p) percent are greater than or equal to it. If two data values satisfy this condition, then the sample 100p percentile is the arithmetic average of these two values.

**Calculating 100p percentail**Then, note that if np is not an integer, then the only data value that satisfies the preceding conditions is the one whose position when the data are ordered from smallest to largest is the smallest integer exceeding np. For instance, if n = 22, p = .8, then we require a data value such that at least 17.6 of the values are less than or equal to it, and at least 4.4 of them are greater than or equal to it. Clearly, only the 18th smallest value satisfies both conditions and this is the sample 80 percentile. On the other hand, if np is an integer, then it is easy to check that both the values in positions np and np + 1 satisfy the preceding conditions, and so the sample 100p percentile is the average of these values. For instance, if we wanted the 90 percentile of a data set of size 20, then both the (18)th and (19)th smallest values would be such that at least 90 percent of the data values are less than or equal to them, and at least 10 percent of the data values are greater than or equal to them.

**Definition** The sample 25 percentile is called the first quartile; the sample 50 percentile is called the sample median or the second quartile; the sample 75 percentile is called the third quartile. A box plot is often used to plot some of the summarizing statistics of a data set. A straight line segment stretching from the smallest to the largest data value is drawn on a horizontal axis; imposed on the line is a “box,” which starts at the first and continues to the third quartile, with the value of the second quartile indicated by a vertical line. The length of the line segment on the box plot, equal to the largest minus the smallest data value, is called the range of the data. Also, the length of the box itself, equal to the third quartile minus the first quartile, is called the interquartile range. 

**Chebyshev's inequality** We have $P(|X-\overline{X}|\geq k\sigma)\leq \frac{1}{k^2}$. 

**Theorem** For a normal distribution $\mathcal{N}$, $P(|X-\overline{X}|\leq s)\geq 0.68$, $P(|X-\overline{X}|\leq 2s)\geq 0.95$, and $P(|X-\overline{X}|\leq 3s)\geq 0.997$. 

**Definition** $r=\frac{\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})}{(n-1)s_xs_y}$. When $r \>\ 0$, we say the sample data pairs are positively correlated and we say the sample data pairs are negatively correlated when $r<0$. 

**Theorem** We have $-1\leq r\leq 1$ and $|r|=1$ iff $(x_i,y_i)$ lie on a straight line, with $r=1$ iff the line has positive slope and $r=-1$ iff the line has negative slope. Suppose $x_i$ and $y_i$ have correlation coefficient $r$, then $a+bx_i$ and $c+dy_i$ have correlation coefficient $r$ if $bd \>\ 0$ and $-r$ if $bd \<\ 0$. 

**Definition** $A_1,...,A_n$ are independent if for $I\subset\{1,...,n\}$, we have $P(\cap_{i\in I} A_i)=\prod_{i\in I} P(A_i)$. 

**Theorem** We have $A_1,...,A_n$ are independent iff $1_{A_1},...,1_{A_n}$ are independent iff $A_1^c,A_2,...,A_n$ are independent. Here $X_1,...,X_n$ are independent iff $\sigma(X_1),...,\sigma(X_n)$ are independent iff for $A_i\in\sigma(X_i)$, $P(\cap A_i)=\prod_i P(A_i)$.

**Theorem** If $X_1,...,X_n$ are independent and $X_i$ has distribution $\mu_i$, then $(X_1,...,X_n)$ has distribution $\mu_1\times ...\times \mu_n$. 

**Definition** The joint cumulative probability distribution function of $X$ and $Y$ is $F(x,y)=P(\{X\leq x, Y\leq y\}$.

**Definition** $X$ and $Y$ are jointly continuous if there is $f(x,y)$ so that $P((X,Y)\in C)=\int_C f(x,y)dxdy$. 

**Theorem** If $X$ and $Y$ have joint probability density function $f(x,y)$, then $f(a,b)=\frac{\partial^2 F(a,b)}{\partial a\partial b}$ and $f_X(x)=\int_\mathbb{R}f(x,y)dy$. If in addition $X$ and $Y$ are independent, then $f(x,y)=f_X(x)f_Y(y)$. (I wonder if the discusion of jointly continuity could begin by defining $f(a,b)=\frac{\partial^2 F(a,b)}{\partial a\partial b}$?)

**Definition** Suppose $X$ and $Y$ have joint probability density function $f(x,y)$, then the conditional probability density function of $X$ given $Y=y$ (when $f_Y(y) \>\ 0$) is $f_{X|Y}(x|y)=\frac{f(x,y)}{f_Y(y)}$. (I wonder what's a measure theoretic interpretation of this expression. I couldn't find one because it seems the event $Y=y$ has measure $0$.)

**Theorem** $P(X\in A|Y=y)=\int_Af_{X|Y}(x|y)dx$. 

**Problem** Suppose that $X$ and $Y$ are independent and have the common density function of $e^{-x}$ for $x \>\ 0$ and $0$ otherwise. What's the density function of $X/Y$? 
**Solution** We first work out the CDF of $X/Y$: $X/Y \<\ a$ iff $X \<\ Ya$. Since $X$ and $Y$ are independent, $F(a)=P(X \<\ Ya)=\int_0^\infty\int_0^{ya} e^{-x}dxe^{-y}dy=\int_0^\infty(1-e^{-ya})e^{-y}dy=1-\int_0^\inftye^{-y(a+1)}dy=1-\frac{1}{a+1}=\frac{a}{a+1}$. So, the PDF of $X/Y$ is $\frac{dF){da}=\frac{1}{(a+1)^2}$. 

**Theorem** If $X$ and $Y$ have joint density $f$, then $E[g(x,y)]=\int_{\mathbb{R}^2}fgdxdy$. 






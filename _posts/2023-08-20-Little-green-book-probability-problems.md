---
layout: post
title: "Little green book probability problems"
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

__extension:__ Let the transition matrix be $T$ and the vector of probability of reaching state $1$ be $A$, then $TA=A$. We also want a solution with first entry of $A$ being $1$ and the last entry being $0$. Such a vector exists because the probabilistic meaning of the vector (the probability of reaching an absorption state starting from a given state). The existence could also be seen by acting on $I=(0,...,0,1,0,...,0)$ (the $i_1$th entry is $1$ and all other entries are $0$) with $T$. Suppose the Markov process described by transition matrix $T$ has absorbing states $i_1, ,...i_k$, then $(T)^nI$s are $0$ on the $i_2,...,i_k$th entries. The sequence $(T)^nI$ also converges due to Brower's fixed point theorem, thereby proving our theorem. I suspect there must be an algebraic proof that such a vector (a vector that's $1$ on the $i_1$th entry, $0$ on $i_2,...i_k$th entry, and satisfies $Tv=v$ for a Markov transition matrix) exists but couldn't find it. 


__2__ Two players bet on rolls of the total of two standard six-face dice. Player A bets that a sum of 12 will occur first. Player B bets that two consecutive 7s will occur first. The players keep rolling the dice and record the sums until one player wins. What is the probability that A will win?

__solution:__ Consider the following state space $(7,7),7,12,s$ with $(7,7)$ standing for B winning, $7$ standing for a single 7 occuring before any $12$ or consecutive $7$s occur, $12$ standing for A winning, and $s$ standing for the starting state. $s$ has $1/6$ probability going to $7$, $1/36$ to $12$, and $29/36$ to itself. $7$ has $1/6$ probability going to $(7,7)$, $29/36$ to $s$, and $1/36$ to $12$. $12$ has probability $1$ going to itself. And $(7,7)$ has probability $1$ going to itself. Assume $a_s, a_{(7,7)}, a_7, a_{12}$ are the probabilities of ending up at $12$, then $a_s=\frac{1}{6}a_7+\frac{1}{36}a_{12}+\frac{29}{36}a_s=\frac{1}{6}a_7+\frac{1}{36}+\frac{29}{36}a_s$, $a_7=\frac{1}{6}a_{(7,7)}+\frac{29}{36}a_s+\frac{1}{36}a_{12}=\frac{29}{36}a_s+\frac{1}{36}$. These equations give that $a_s=7/13$. 

**extension:** The result could be generalized to 2 players betting on whether $c+s$ or $c+t$ appear first with $c$ being the maximum common initial substring of $c+s$ and $c+t$. Let $s_i$ denote the string formed by the first $i$ characteers of $s$. Then it suffices to consider a Markov process with state space consisting of $o, c_1,...,c,c+s_1,...,c+s,c+t_1,...,c+t$ and transition matrix $T$. Here $o$ denotes the original state. Note that $c+s$ and $c+t$ are absorption states and it suffices to consider the absorption probability of starting from $o$ and going to $c+s$ to determine the probability of winning of the 2 players. 


**3** If you keep on tossing a fair coin, what is the expected number of tosses such that you can have HHH (heads heads heads) in a row? What is the expected number of tosses to have THH (tails heads heads) in a row?

**solution:** We consider a Markov chain with states $O,H,HH,HHH$. 



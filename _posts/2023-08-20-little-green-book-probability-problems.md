---
layout: post
title: "little green book probability problems"
---

1 Player $M$ has 1 dollar and player $N$ has 2 dollars. Each game gives the winner 1 from the other. As a better player, $M$ wins $2/3$ of the games. They play until one of them is bankrupt. What is the probability that $M$ wins?

This is a Markov chain problem. We consider the following state space: $\{(0,3),(1,2),(2,1),(3,0)\}$ where the first number in the ordered pair stand for the amount of money $M$ has and the second stand for the amound of money $N$ has. Note the $(0,3)$ and $(3,0)$ are absorbing states. With the above setup, the transition matrix looks like:

$$
\begin{pmatrix}
1 & 1/3 & 0 & 0\\
0 & 0 & 1/3 & 0\\
0 & 2/3 & 0 & 0\\
0 & 0 & 2/3 & 1\\
\end{pmatrix}
$$

By the equation for absorption probability, let $a_i$ be the probability of reaching from state $i$ to state $1$. Then $a_1=0$, $a_4=1$, $a_2=\sum_{i=1}^4 p_{2i}a_i=\frac{1}{3}a_1+\frac{2}{3}a_3=\frac{2}{3}a_3$, $a_3=\sum_{i=1}^4 p_{3i}a_i=\frac{1}{3}a_2+\frac{2}{3}a_4=\frac{1}{3}a_2+\frac{2}{3}$. So, $a_2=\frac{4}{7}$.

Consider a probability $p$ instead of $1/3$, we have the equations $a_2=(1-p)a_3$ and $a_3=pa_2+(1-p)$. So, $a_3=\frac{1-p}{1-p(1-p)}$ and $a_2=\frac{(1-p)^2}{1-p(1-p)}$.

Let the transition matrix be $T$ and the vector of probability of reaching state $1$ be $A$, then $T^tA=A$. We also have that the first entry of $A$ is $1$ and the last entry is $0$. 

2 





---
layout: post
title: "little green book probability problems"
---

Player $M$ has 1 dollar and player $N$ has 2 dollars. Each game gives the winner 1 from the other. As a better player, $M$ wins $2/3$ of the games. They play until one of them is bankrupt. What is the probability that $M$ wins?

This is a Markov chain problem. We consider the following state space: $(m,n)$ with $m$ the amount of dollar player $M$ currently have and $n$ the amount of dollar player $N$ currently have. The initial state of the state space is $(1,2)$ and the transition matrix is 

$$\begin{pmatrix} 

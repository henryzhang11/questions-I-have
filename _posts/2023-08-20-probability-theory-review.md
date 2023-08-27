---
layout: post
title: "probability theory review"
---

**Definition** Variance is defined as $s^2=\sum_{i=1}^n(x_i-\overline{x})^2/(n-1) and standard deviation is defined as $s=\sqrt{s^2}$. 

**Definition** The sample 100p percentile is that data value such that at least 100p percent of the data are less than or equal to it and at least 100(1 − p) percent are greater than or equal to it. If two data values satisfy this condition, then the sample 100p percentile is the arithmetic average of these two values.

**Calculating 100p percentail**Then, note that if np is not an integer, then the only data value that satisfies the preceding conditions is the one whose position when the data are ordered from smallest to largest is the smallest integer exceeding np. For instance, if n = 22, p = .8, then we require a data value such that at least 17.6 of the values are less than or equal to it, and at least 4.4 of them are greater than or equal to it. Clearly, only the 18th smallest value satisfies both conditions and this is the sample 80 percentile. On the other hand, if np is an integer, then it is easy to check that both the values in positions np and np + 1 satisfy the preceding conditions, and so the sample 100p percentile is the average of these values. For instance, if we wanted the 90 percentile of a data set of size 20, then both the (18)th and (19)th smallest values would be such that at least 90 percent of the data values are less than or equal to them, and at least 10 percent of the data values are greater than or equal to them.

**Definition** The sample 25 percentile is called the first quartile; the sample 50 percentile is called the sample median or the second quartile; the sample 75 percentile is called the third quartile. A box plot is often used to plot some of the summarizing statistics of a data set. A straight line segment stretching from the smallest to the largest data value is drawn on a horizontal axis; imposed on the line is a “box,” which starts at the first and continues to the third quartile, with the value of the second quartile indicated by a vertical line. The length of the line segment on the box plot, equal to the largest minus the smallest data value, is called the range of the data. Also, the length of the box itself, equal to the third quartile minus the first quartile, is called the interquartile range. 

**Chebyshev's inequality** We have $P(|X-\overline{X}|\geq k\sigma)\leq \frac{1}{k^2}$. 

**Theorem** For a normal distribution $\mathcal{N}$, $P(|X-\overline{X}|\leq s)\geq 0.68$, $P(|X-\overline{X}|\leq 2s)\geq 0.95$, and $P(|X-\overline{X}|\leq 3s)\geq 0.997$. 

**Definition** $r=\frac{\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})}{(n-1)s_xs_y}$. When $r \>\ 0$, we say the sample data pairs are positively correlated and we say the sample data pairs are negatively correlated when $r \<\ 0$. 

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
**Solution** We first work out the CDF of $X/Y$: $X/Y \<\ a$ iff $X \<\ Ya$. Since $X$ and $Y$ are independent, $F(a)=P(X \<\ Ya)=\int_0^\infty\int_0^{ya} e^{-x}dxe^{-y}dy=\int_0^\infty(1-e^{-ya})e^{-y}dy=1-\int_0^\infty e^{-y(a+1)}dy=1-\frac{1}{a+1}=\frac{a}{a+1}$. So, the PDF of $X/Y$ is $\frac{dF}{da}=\frac{1}{(a+1)^2}$. 

**Theorem** If $X$ and $Y$ have joint density $f$, then $E[g(x,y)]=\int_{\mathbb{R}^2}fgdxdy$. 

**Theorem** Properties of covariance: 1. $cov(X,Y)=E(XY)-(EX)(EY)$; 2. $cov(Y,X)=cov(X,Y)$; 3. $cov(X,X)=Var(X)$; 4. $cov(aX,Y)=acov(X,Y)$; 5. $cov(\sum_iX_i,\sum_j Y_j)=\sum_{i,j}cov(X_i,Y_j)$.

**Definition** $Corr(X,Y)=\frac{cov(X,Y)}{s_xs_y}$. 

**Definition** The moment generating function of $X$ is $\phi(t)=E[e^{tX}]$.

**Theorem** We have the following properties of moment generating functions: 1. $\phi^{(n)}(t)=E[X^ne^{tX}]$, so $\phi^{(n)}(0)=E[X^n]$; 2. the moment generating function of independent random variables are the product of the individual moment generating functions;

**Theorem** (Markov’s inequality) We have $P(X \>\ a)\leq \frac{E[X]}{a}$.

**Problem** Suppose that it is known that the number of items produced in a factory during a week is a random variable with mean 50. (a)  What can be said about the probability that this week’s production will exceed 75? (b)  If the variance of a week’s production is known to equal 25, then what can be said about the probability that this week’s production will be between 40 and 60?  
**Solution** (a) By Markov’s inequality, $P(X \>\ 75)\leq \frac{E[X]}{75}=2/3$. (b) By Chebyshev’s inequality, $P(X\in[40,60])=1-P(X\notin[40,60])\geq 1-\frac{\sigma^2}{k^2}=1-\frac{25}{10^2}=\frac{3}{4}$. 

**Theorem** Let $X_i$ be iid random variables with mean $\mu$, then $E[|\frac{S_n}{n}-\mu |>\epsilon]\to 0$ as $n\to\infty$. 

**Binomial distribution** $P(X=i)=\(\binom{i}{n}\) p^i(1-p)^{n-i}$. 

**Poisson distribution** $P(X=i)=e^{-\lambda}\frac{\lambda^2}{i!}$ approximates the number of successful binomial trials given that $n$ is large and $p$ is small. For instance, $Poisson_np$ approximates the number of misprinted alphabets on a page of a book with $n$ (which is large) characters and $p$ probability of having a wrong character. $\phi(t)=exp\{\lambda(e^t-1)\}$, which gives $E[X]=\lambda$ and $Var[X]=\lambda$. The sum of independent $Poisson(\lambda_1)$ and $Poisson(\lambda_2)$ is a new Poisson random variable $Poisson(\lambda_1+\lambda_2)$. If each of a Poisson number of events having mean $\lambda$ is independently classified as being of one of the types $1,…,r$ with respective probabilities $p_1,…,p_r$, $r_i=1$, $\sum_{i=1}^rp_i =1$ , then the numbers of type $1, . . . ,r$ events are independent Poisson random variables with respective means $λp_1,…,λp_r$. If $X$ is Poisson with mean $\lambda$, then $\frac{P(X=i+1)}{P(X=i)}=\frac{\lambda}{i+1}$. ($P(X=1)=\lambda P(X=0)$, $P(X=2)=\frac{\lambda}{2}P(X=1)$, $P(X=3)=\frac{\lambda}{3}P(X=2)$, ….

**Problem** Suppose that the average number of accidents occurring weekly on a particular stretch of a highway equals 3. Calculate the probability that there is at least one accident this week. 
**Solution** We model this as a Poisson distribution with $\lambda=3$ and we have $P(X\geq 1)=1-P(X=0)=1-e^{-\lambda}\frac{\lambda^i}{i!}=1-e^{-3}\frac{3^0}{0!}=1-e^{-3}$. 

**Hypergeometric distribution** We have an urn filled with $N$ good and $M$ bad samples and hypergeometric distribution calculates probability of getting $i$ good samples during a random draw of $n$ samples from the urn: $P(X=i)=\frac{\binom{n}{i}\binom{m}{n-i}}{\binom{N+M}{n}}$. Let $p=\frac{N}{N+M}$, then $E[X]=np$ and $Var[X]=np(1-p)[1-\frac{n-1}{N+M-1}]$.

**Normal distribution** We write $X\sim \mathcal{N}(\mu,\sigma^2)$ if its density is $f(x)=\frac{1}{\sqrt{2\pi\sigma}}e^{-(x-\mu)^2/2\sigma^2}$ for $-\infty \<\ x \<\ \infty$. We write $Z=\mathcal{N}(0,1)$ and $\Phi(x)=P(Z \<\ x)$ (we have $\frac{\mathcal{N}(\mu,\sigma^2)-\mu}{\sigma}=Z$. If $X\sim\mathcal{N}(\mu,\sigma^2)$, then $E[X]=\mu$, $var(X)=\sigma^2$, $Y=aX+b\sim \mathcal{N}(a\mu +b, a^2\sigma^2)$, independent $X_i\sim\mathcal{N}(\mu_i,\sigma_i^2)$ sums to $\mathcal{N}(\sum_{i}\mu_i,\sum_i\sigma_i^2)$.

**Exponential distribution** Let $f(x)=\lambda e^{-\lambda x}$ for $x\geq 0$ and $0$ otherwise, then $F(x)=1-e^{-\lambda x}$ for $x\geq 0$, $\phi(t)=\frac{\lambda}{\lambda-t}$ for $t \<\ \lambda$, $EX=\frac{1}{\lambda}$, $Var(X)=\frac{1}{\lambda^2}$, $P(X \>\ s+t|X \>\ t)=P(X \>\ s)$. If $X_1,...,X_n$ are independent exponential random variables, then $min(X_1,...,X_n)$ is exponential with $\lambda=sum_{i=1}^n \lambda_i$. 

**Problem** What is the probability of a man's car breaking down after 5000 miles if the time until the car breaks down follows exponential distribution with average $10000$?
**Solution** That would be $P(X \>\ 5000)=1-F(5000)=1-(1-e^{-\lambda 5000})=e^{-\frac{1}{10000}5000}=e^{-1/2}$.

**$\chi_n^2$-distribution** Given iid $X_i\sim Z$, $Z=\sum_{i=1}^n X_i^2$ is a $\chi_n^2$-distribution. The sum of independent $\chi_n^2$ and $\chi_m^2$ is $\chi_{n+m}^2$. 

**t-distribution** Let $Z$ and $\chi_n^2$ be independent, $T_n=\frac{Z}{\sqrt{\chi_n^2/n}}$ is a t-distribution with $n$ degrees of freedom. $T_n$ approximates $Z$ as $n\to\infty$ because $\chi_n^2/n\to 1$ by the weak law of large numbers. $E[T_n]=0$, $var(T_n)=\frac{n}{n-2}$ (for $n>2$), 

**F-distribution** Let $\chi_n^2$ and $\chi_m^2$ be independent, then $F_{n,m}=\frac{\chi_n^2/n}{\chi_m^2/m}$ is a $F$-distribution with $n$ and $m$ degrees of freedom. For $\alpha\in(0,1)$, let $F_{\alpha,n,m}$ be such that $P(F_{n,m}>F_{\alpha,n,m})=\alpha$, then $\frac{1}{F_{\alpha,n,m}}=F_{1-\alpha,m,n}$ 

**Theorem (Central Limit Theorem)** It follows from the central limit theorem that $X_1+...+X_n$ is approximately $\mathcal{N}(n\mu, n\sigma^2)$. In other words, the sample mean $\overline{X}\sim\mathcal{N}(\mu,\sigma/\sqrt{n})$.

**Problem** W, the weight (in 1,000 pounds uits) that a bridge can withstand without damage, is $\mathcal{N}(400,1600)$. Suppose the weight (in 1,000 pounds units) of a car is a random variable with mean 3 and standard deviation .3. How many cars would have to be on the bridge span for the probability of structural damage to exceed .1? 
**Solution** Let $X_i$ be the weight of car $i$ and $R_n=W-\sum_{i=1}^n X_i$, then we want the minimum $n$ so that $P(R_n<0)>0.1$. We approximate $\sum_{i=1}^n X_i$ by $\mathcal{N}(3n, 0.09n)$ by central limit theorem, then $R_n=\mathcal{N}(400-3n, 0.09n+1600)$. The minimum $n$ so that $P(\mathcal{N}(400-3n,0.09n+1600)<0)=P(Z<\frac{-400+3n}{\sqrt{0.09n}+1600})<0.1$ is $117$. 

**Problem** An astronomer wants to measure the distance to a distant star. The astronomer believes the values of the successive measurements are iid with a mean of d light years and a standard deviation of 2 light years, how many measurements need she make to be at least 95 percent certain that her estimate is accurate to within ± .5 light years? 
**Solution** When there are $n$ measurements $\overline{X}\sim\mathcal{N}(d, 2/\sqrt{n})$. $P(|\overline{X}-d|<0.5)=P(|Z|<0.5\sqrt{n}/2)>0.95$ is equivalent to $\Phi(0.5\sqrt{n}/2)>0.975$, which gives $n\geq 62$. 

**Definition** $S^2=\frac{\sum_{i=1}^n(X_i-\overline{X})^2}{n-1}$ is called the sample variance and $S=\sqrt{S^2}$ is the sample standard deviation. We have $E[S^2]=\sigma^2$, the population variance.

**Theorem** If $X_1,...,X_n$ is a sample from a normal population with mean $\mu$ and variance $\sigma^2$, then $X$ and $S^2$ are independent random variables, with $X$ being normal with mean $\mu$ and variance $\sigma^2/n$ and $(n − 1)S^2/\sigma^2$ being chi-square with $n − 1$ degrees of freedom.

**Problem** The time it takes a CPU to process job A is normally distributed with mean 20 seconds and standard deviation 3 seconds. If a sample of 15 such jobs is observed, what is the probability that the sample variance will exceed 12? 
**Solution** The sample variance $S^2\sim \frac{9\chi_{14}^2}{14}$. So, $P(S^2>12)=P(\frac{9\chi_{14}^2}{14}>12)=P(\chi_{14}^2>\frac{14\cdot 12}{9})$.

**Theorem** Let $X_1,...,X_n$ be a sample from a normal population with mean $\mu$. Let $\overline{X}$ be the sample mean and $S$ be the sample standard deviation, then $\sqrt{n}\frac{\overline{X}-\mu}{S}\sim t_{n-1}$.
**Proof** We have $\overline{X}\sim \frac{Z}{\sqrt{n}}+\mu$ and $S\sim\sqrt{\frac{\sigma^2 \chi_{n-1}^2}{n-1}}$ are independent. So, $\frac{\sqrt{n}(\overline{X}-\mu)}{S}\sim \frac{nZ}{}$ (didn't succeed deriving it).

**Problem** Suppose 45 percent of the population favors a certain candidate in an upcoming election. If a random sample of size 200 is chosen, find (a) the expected value and standard deviation of the number of members of the sample that favor the candidate; (b) the probability that more than half the members of the sample favor the candidate.
**Solution** (a) Since the entire population is large, we approximate the hypergeometric distribution (of number of candidates supporting a certain candidate) with binomial distribution. So, $E[\overlin{X}]=np=200\cdot .45=90$ and $\sigma(\overline{X})=\sqrt{np(1-p)}=\sqrt{200\cdot 0.45\cdot 0.55}$. (b) We approximate the binomial distribution $binom(p,n)$ with a normal distribution $\mathcal{N}(n\mu, n\sigma^2)=\mathcal{N}(np,np(1-p))$. The probability is then approximately $P(S_n\geq 101)\approx P(S_n\geq 100.5)=P(\mathcal{N}(90,200\cdot 0.45\cdot 0.55) \>\ 100.5)=P(Z \>\ \frac{10.5}{\sqrt{200\cdot 0.45\cdot 0.55}})$.

**Problem** The country with the greatest per capita consumption of pork is Denmark. In 2013, the amount of pork consumed by a person residing in Denmark had a mean value of 147 pounds with a standard deviation of 62 pounds. If a random sample of 25 Danes is chosen, approximate the probability that the average amount of pork consumed by the members of this group in 2013 exceeded 150 pounds.
**Solution** We have $\sqrt{n}(\overline{X}-\mu)/\sigma\sim Z$, so $\overline{X}\sim\mathcal{N}(\mu,\frac{\sigma^2}{n})=\mathcal{N}(147,\frac{62^2}{25})$ when $n$ is large. So, $P(\overline{X} \>\ 147)\approx P(\mathcal{N}(147,\frac{62^2}{25})>150)=P(Z>\frac{3}{\sqrt{62^2/25}})$.

































---
layout: post
title: "probability theory review"
---

**Definition** Variance is defined as $s^2=\sum_{i=1}^n(x_i-\overline{x})^2/(n-1)$ and standard deviation is defined as $s=\sqrt{s^2}$. 

**Definition** The sample 100p percentile is that data value such that at least 100p percent of the data are less than or equal to it and at least 100(1-p) percent are greater than or equal to it. If two data values satisfy this condition, then the sample 100p percentile is the arithmetic average of these two values.

**Calculating 100p percentile** Then, note that if np is not an integer, then the only data value that satisfies the preceding conditions is the one whose position when the data are ordered from smallest to largest is the smallest integer exceeding np. For instance, if n = 22, p = .8, then we require a data value such that at least 17.6 of the values are less than or equal to it, and at least 4.4 of them are greater than or equal to it. Clearly, only the 18th smallest value satisfies both conditions and this is the sample 80 percentile. On the other hand, if np is an integer, then it is easy to check that both the values in positions np and np + 1 satisfy the preceding conditions, and so the sample 100p percentile is the average of these values. For instance, if we wanted the 90 percentile of a data set of size 20, then both the (18)th and (19)th smallest values would be such that at least 90 percent of the data values are less than or equal to them, and at least 10 percent of the data values are greater than or equal to them.

**Definition** The sample 25 percentile is called the first quartile; the sample 50 percentile is called the sample median or the second quartile; the sample 75 percentile is called the third quartile. A box plot is often used to plot some of the summarizing statistics of a data set. A straight line segment stretching from the smallest to the largest data value is drawn on a horizontal axis; imposed on the line is a “box,” which starts at the first and continues to the third quartile, with the value of the second quartile indicated by a vertical line. The length of the line segment on the box plot, equal to the largest minus the smallest data value, is called the range of the data. Also, the length of the box itself, equal to the third quartile minus the first quartile, is called the interquartile range. 

**Chebyshev's inequality** We have $P(|X-\overline{X}|\geq k\sigma)\leq \frac{1}{k^2}$. 

**Theorem** For a normal distribution $\mathcal{N}$, $P(|X-\overline{X}|\leq s)\geq 0.68$, $P(|X-\overline{X}|\leq 2s)\geq 0.95$, and $P(|X-\overline{X}|\leq 3s)\geq 0.997$. 

**Definition** $r=\frac{\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})}{(n-1)s_xs_y}$. When $r > 0$, we say the sample data pairs are positively correlated and we say the sample data pairs are negatively correlated when $r < 0$. 

**Theorem** We have $-1\leq r\leq 1$ and $|r|=1$ iff $(x_i,y_i)$ lie on a straight line, with $r=1$ iff the line has positive slope and $r=-1$ iff the line has negative slope. Suppose $x_i$ and $y_i$ have correlation coefficient $r$, then $a+bx_i$ and $c+dy_i$ have correlation coefficient $r$ if $bd > 0$ and $-r$ if $bd < 0$. 

**Definition** $A_1,...,A_n$ are independent if for $I\subset\{1,...,n\}$, we have $P(\cap_{i\in I} A_i)=\prod_{i\in I} P(A_i)$. 

**Theorem** We have $A_1,...,A_n$ are independent iff $1_{A_1},...,1_{A_n}$ are independent iff $A_1^c,A_2,...,A_n$ are independent. Here $X_1,...,X_n$ are independent iff $\sigma(X_1),...,\sigma(X_n)$ are independent iff for $A_i\in\sigma(X_i)$, $P(\cap A_i)=\prod_i P(A_i)$.

**Theorem** If $X_1,...,X_n$ are independent and $X_i$ has distribution $\mu_i$, then $(X_1,...,X_n)$ has distribution $\mu_1\times ...\times \mu_n$. 

**Definition** The joint cumulative probability distribution function of $X$ and $Y$ is $F(x,y)=P(\{X\leq x, Y\leq y\}$.

**Definition** $X$ and $Y$ are jointly continuous if there is $f(x,y)$ so that $P((X,Y)\in C)=\int_C f(x,y)dxdy$. 

**Theorem** If $X$ and $Y$ have joint probability density function $f(x,y)$, then $f(a,b)=\frac{\partial^2 F(a,b)}{\partial a\partial b}$ and $f_X(x)=\int_\mathbb{R}f(x,y)dy$. If in addition $X$ and $Y$ are independent, then $f(x,y)=f_X(x)f_Y(y)$. (I wonder if the discusion of jointly continuity could begin by defining $f(a,b)=\frac{\partial^2 F(a,b)}{\partial a\partial b}$?)

**Definition** Suppose $X$ and $Y$ have joint probability density function $f(x,y)$, then the conditional probability density function of $X$ given $Y=y$ (when $f_Y(y) \>\ 0$) is $f_{X|Y}(x|y)=\frac{f(x,y)}{f_Y(y)}$. (I wonder what's a measure theoretic interpretation of this expression. I couldn't find one because it seems the event $Y=y$ has measure $0$.)

**Theorem** $P(X\in A|Y=y)=\int_Af_{X|Y}(x|y)dx$. 

**Problem** Suppose that $X$ and $Y$ are independent and have the common density function of $e^{-x}$ for $x \>\ 0$ and $0$ otherwise. What's the density function of $X/Y$? 
**Solution** We first work out the CDF of $X/Y$: $X/Y < a$ iff $X < Ya$. Since $X$ and $Y$ are independent, $F(a)=P(X < Ya)=\int_0^\infty\int_0^{ya} e^{-x}dxe^{-y}dy=\int_0^\infty(1-e^{-ya})e^{-y}dy=1-\int_0^\infty e^{-y(a+1)}dy=1-\frac{1}{a+1}=\frac{a}{a+1}$. So, the PDF of $X/Y$ is $\frac{dF}{da}=\frac{1}{(a+1)^2}$. 

**Theorem** If $X$ and $Y$ have joint density $f$, then $E[g(x,y)]=\int_{\mathbb{R}^2}fgdxdy$. 

**Theorem** Properties of covariance: 1. $cov(X,Y)=E(XY)-(EX)(EY)$; 2. $cov(Y,X)=cov(X,Y)$; 3. $cov(X,X)=Var(X)$; 4. $cov(aX,Y)=acov(X,Y)$; 5. $cov(\sum_iX_i,\sum_j Y_j)=\sum_{i,j}cov(X_i,Y_j)$.

**Definition** $Corr(X,Y)=\frac{cov(X,Y)}{s_xs_y}$. 

**Definition** The moment generating function of $X$ is $\phi(t)=E[e^{tX}]$.

**Theorem** We have the following properties of moment generating functions: 1. $\phi^{(n)}(t)=E[X^ne^{tX}]$, so $\phi^{(n)}(0)=E[X^n]$; 2. the moment generating function of independent random variables are the product of the individual moment generating functions;

**Theorem** (Markov’s inequality) We have $P(X \>\ a)\leq \frac{E[X]}{a}$.

**Problem** Suppose that it is known that the number of items produced in a factory during a week is a random variable with mean 50. (a) What can be said about the probability that this week’s production will exceed 75? (b) If the variance of a week’s production is known to equal 25, then what can be said about the probability that this week’s production will be between 40 and 60?
**Solution** (a) By Markov’s inequality, $P(X \>\ 75)\leq \frac{E[X]}{75}=2/3$. (b) By Chebyshev’s inequality, $P(X\in[40,60])=1-P(X\notin[40,60])\geq 1-\frac{\sigma^2}{k^2}=1-\frac{25}{10^2}=\frac{3}{4}$. 

**Theorem** Let $X_i$ be iid random variables with mean $\mu$, then $E[|\frac{S_n}{n}-\mu |>\epsilon]\to 0$ as $n\to\infty$. 

**Binomial distribution** $P(X=i)=\binom{i}{n} p^i(1-p)^{n-i}$. 

**Poisson distribution** $P(X=i)=e^{-\lambda}\frac{\lambda^i}{i!}$ approximates the number of successful binomial trials given that $n$ is large and $p$ is small. For instance, $Poisson_np$ approximates the number of misprinted alphabets on a page of a book with $n$ (which is large) characters and $p$ probability of having a wrong character. $\phi(t)=exp\{\lambda(e^t-1)\}$, which gives $E[X]=\lambda$ and $Var[X]=\lambda$. The sum of independent $Poisson(\lambda_1)$ and $Poisson(\lambda_2)$ is a new Poisson random variable $Poisson(\lambda_1+\lambda_2)$. If each of a Poisson number of events having mean $\lambda$ is independently classified as being of one of the types $1,…,r$ with respective probabilities $p_1,…,p_r$, $r_i=1$, $\sum_{i=1}^rp_i =1$ , then the numbers of type $1, . . . ,r$ events are independent Poisson random variables with respective means $λp_1,…,λp_r$. If $X$ is Poisson with mean $\lambda$, then $\frac{P(X=i+1)}{P(X=i)}=\frac{\lambda}{i+1}$. ($P(X=1)=\lambda P(X=0)$, $P(X=2)=\frac{\lambda}{2}P(X=1)$, $P(X=3)=\frac{\lambda}{3}P(X=2)$, ….

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

**Theorem (Central Limit Theorem)** It follows from the central limit theorem that $X_1+...+X_n$ is approximately $\mathcal{N}(n\mu, n\sigma^2)$. In other words, the sample mean $\overline{X}\sim\mathcal{N}(\mu,\sigma^2/n)$.

**Problem** W, the weight (in 1,000 pounds uits) that a bridge can withstand without damage, is $\mathcal{N}(400,1600)$. Suppose the weight (in 1,000 pounds units) of a car is a random variable with mean 3 and standard deviation .3. How many cars would have to be on the bridge span for the probability of structural damage to exceed .1? 
**Solution** Let $X_i$ be the weight of car $i$ and $R_n=W-\sum_{i=1}^n X_i$, then we want the minimum $n$ so that $P(R_n<0)>0.1$. We approximate $\sum_{i=1}^n X_i$ by $\mathcal{N}(3n, 0.09n)$ by central limit theorem, then $R_n=\mathcal{N}(400-3n, 0.09n+1600)$. The minimum $n$ so that $P(\mathcal{N}(400-3n,0.09n+1600)<0)=P(Z<\frac{-400+3n}{\sqrt{0.09n}+1600})<0.1$ is $117$. 

**Problem** An astronomer wants to measure the distance to a distant star. The astronomer believes the values of the successive measurements are iid with a mean of d light years and a standard deviation of 2 light years, how many measurements need she make to be at least 95 percent certain that her estimate is accurate to within ± .5 light years? 
**Solution** When there are $n$ measurements $\overline{X}\sim\mathcal{N}(d, 2/\sqrt{n})$. $P(|\overline{X}-d|<0.5)=P(|Z|<0.5\sqrt{n}/2)>0.95$ is equivalent to $\Phi(0.5\sqrt{n}/2)>0.975$, which gives $n\geq 62$. 

**Definition** $S^2=\frac{\sum_{i=1}^n(X_i-\overline{X})^2}{n-1}$ is called the sample variance and $S=\sqrt{S^2}$ is the sample standard deviation. We have $E[S^2]=\sigma^2$, the population variance.

**Theorem** If $X_1,...,X_n$ is a sample from a normal population with mean $\mu$ and variance $\sigma^2$, then $X$ and $S^2$ are independent random variables, with $X$ being normal with mean $\mu$ and variance $\sigma^2/n$ and $(n − 1)S^2/\sigma^2$ being chi-square with $n − 1$ degrees of freedom.

**Problem** The time it takes a CPU to process job A is normally distributed with mean 20 seconds and standard deviation 3 seconds. If a sample of 15 such jobs is observed, what is the probability that the sample variance will exceed 12? 
**Solution** The sample variance $S^2\sim \frac{9\chi_{14}^2}{14}$. So, $P(S^2>12)=P(\frac{9\chi_{14}^2}{14}>12)=P(\chi_{14}^2>\frac{14\cdot 12}{9})$.

**Theorem** Let $X_1,...,X_n$ be a sample from a normal population with mean $\mu$. Let $\overline{X}$ be the sample mean and $S$ be the sample standard deviation, then $\sqrt{n}\frac{\overline{X}-\mu}{S}\sim T_{n-1}$.
**Proof** $\frac{\overline{X}-\mu}{\sigma/\sqrt{n}}\sim\mathcal{N}(0,1)$ and $S^2/\sigma^2\sim\chi_{n-1}^2/(n-1)$ are independent. So, $\frac{\sqrt{n}(\overline{X}-\mu)}{S}\sim T_{n-1}$. 

**Problem** Suppose 45 percent of the population favors a certain candidate in an upcoming election. If a random sample of size 200 is chosen, find (a) the expected value and standard deviation of the number of members of the sample that favor the candidate; (b) the probability that more than half the members of the sample favor the candidate.
**Solution** (a) Since the entire population is large, we approximate the hypergeometric distribution (of number of candidates supporting a certain candidate) with binomial distribution. So, $E[\overline{X}]=np=200\cdot .45=90$ and $\sigma(\overline{X})=\sqrt{np(1-p)}=\sqrt{200\cdot 0.45\cdot 0.55}$. (b) We approximate the binomial distribution $binom(p,n)$ with a normal distribution $\mathcal{N}(n\mu, n\sigma^2)=\mathcal{N}(np,np(1-p))$. The probability is then approximately $P(S_n\geq 101)\approx P(S_n\geq 100.5)=P(\mathcal{N}(90,200\cdot 0.45\cdot 0.55) \>\ 100.5)=P(Z \>\ \frac{10.5}{\sqrt{200\cdot 0.45\cdot 0.55}})$.

**Problem** The country with the greatest per capita consumption of pork is Denmark. In 2013, the amount of pork consumed by a person residing in Denmark had a mean value of 147 pounds with a standard deviation of 62 pounds. If a random sample of 25 Danes is chosen, approximate the probability that the average amount of pork consumed by the members of this group in 2013 exceeded 150 pounds.
**Solution** We have $\sqrt{n}(\overline{X}-\mu)/\sigma\sim Z$, so $\overline{X}\sim\mathcal{N}(\mu,\frac{\sigma^2}{n})=\mathcal{N}(147,\frac{62^2}{25})$ when $n$ is large. So, $P(\overline{X} \>\ 147)\approx P(\mathcal{N}(147,\frac{62^2}{25})>150)=P(Z \>\ \frac{3}{62/5})$.

**Definition** Define the likelihood function $f(x_1,...,x_n|\theta)$ as the probability mass of $(x_1,...,x_n)$ for discrete independent $X_1,...,X_n$ and the joint probability density function of continnuous independent population. We maximize $f(x_1,...,x_n|\theta)$ (which is equivalent to maximizing $\log(f(x_1,...,x_n|\theta))$) w.r.t. $\theta$ to obtain the maximum likelihood estimate of $\theta$.

**Theorem** Based on independent trials $X_1,...,X_n$, maximum likelihood estimator (MLE) of $p$ for binary $X_i$ is $\frac{\sum_i X_i}{n}$, MLE of $\lambda$ for Poisson $X_i$ is $\frac{\sum_i X_i}{n}$, MLE of $\mu$ and $\sigma$ for normal $X_i$ is $\frac{\sum_i X_i}{n}$ and $\sqrt{\frac{\sum_i (X_i-\overline{X})^2}{n}}$ (notice MLE $\sigma$ is different from sample standard deviation), the MLE of $\theta$ for uniform $X_i$ is $max(X_1,...,X_n)$. 

**Problem** The number of traffic accidents in Berkeley in 10 randomly chosen days is as follows: 4,0,6,5,2,1,2,0,4,3. Use these data to estimate the proportion of days that had 2 or fewer accidents.
**Solution** Since the total number of drivers is large and the probability of accident is small, we approximate the number of accidents with a Poisson random variable. With the above trials, the MLE of $\lambda$ is $2.7$. So, we have $P(X\leq 2)\approx e^{-2.7}(1+2.7+\frac{2.7^2}{2})$.

**Theorem** Let $X_1,...,X_n$ be a sample from a normal population and let $z_\alpha$ be $P(Z>z_\alpha)=\alpha$. 

1. If $\mu$ is unknown and $\sigma$ is known, then the $\alpha$% confidence intervals are $(\overline{x}\pm z_{\alpha/2}\frac{\sigma}{\sqrt{n}})$, $(-\infty,\overline{x}+z_\alpha\frac{\sigma}{\sqrt{n}})$, and $(\overline{x}-z_\alpha\frac{\sigma}{\sqrt{n}},\infty)$. 

2. If $\mu$ and $\sigma$ are unknown, then $\frac{\overline{x}-\mu}{S/\sqrt{n}}\sim T_{n-1}$ and the $1-\alpha$ confidence intervals of $\mu$ are $(\overline{x}\pm t_{n-1,\alpha/2}\frac{S}{\sqrt{n}})$, $(-\infty,\overline{x}+t_{n-1,\alpha}\frac{S}{\sqrt{n}})$, or $(\overline{x}-t_{n-1,\alpha}\frac{S}{\sqrt{n}})$ with $S$ the sample variance. 

3. If $\mu$ and $\sigma$ are unknown, then the $1-\alpha$ confidence interval of $X_{n+1}$ is $(\overline{X_n}-t_{n-1,\alpha/2}S_n\sqrt{1+1/n},\overline{X_n}+t_{n-1,\alpha/2}S_n\sqrt{1+1/n})$.

4. If $\mu$ and $\sigma$ are unknown, then the $1-\alpha$ confidence interval of $\sigma^2$ is $(\frac{(n-1)S_n^2}{\chi_{n-1,\alpha/2}^2},\frac{(n-1)S_n^2}{\chi_{n-1,1-\alpha/2}^2})$.

5. If in addition $Y_1,...,Y_m$ is a sample from a normal population, $X_i$ has unknown $\mu_1$ and known $\sigma_1^2$, $Y_i$ has unknown $\mu_2$ and known $\sigma_2^2$, then $\frac{\overline{X}-\overline{Y}-(\mu_x-\mu_y)}{\sqrt{\sigma_x^2/n+\sigma_y^2/m}}\sim Z$ and the $1-\alpha$ confidence interval of $\mu_1-\mu_2$ is $(\overline{X_n}-\overline{Y_n}\pm z_{\alpha/2}\sqrt{\frac{\sigma_1^2}{n}+\frac{\sigma_2^2}{m}})$.

6. If in addition $Y_1,...,Y_m$ is a sample from a normal population, $X_i$ has unknown $\mu_x$ and $\sigma^2$, $Y_i$ has unknown $\mu_y$ and $\sigma^2$, then the $1-\alpha$ confidence interval of $\mu_1-\mu_2$ is $(\overline{X_n}-\overline{Y_m}\pm t_{n+m-2,\alpha/2}\sqrt{(\frac{1}{n}+\frac{1}{m})\frac{(n-1)S_1^2+(m-1)S_2^2}{n+m-2}})$.


**Proof of 3** $\overline{X_n}\sim\mathcal{N}(\mu,\sigma^2/n)$ and $X_{n+1}\sim\mathcal{N}(\mu,\sigma^2)$, so $\overline{X_n}-X_{n+1}\sim\mathcal{N}(0,\sigma^2(1+1/n))$ and $\frac{\overline{X_n}-X_{n+1}}{\sigma\sqrt{1+1/n}}\sim\mathcal{N}(0,1)$. Since $\frac{(n-1)S_n^2}{\sigma^2}\sim \chi_{n-1}^2$ and is independent of $\frac{\overline{X_n}-X_{n+1}}{\sigma\sqrt{1+1/n}}$, we have $\frac{\overline{X_n}-X_{n+1}}{S_n\sqrt{(1+1/n)}}\sim T_{n-1}$. So, $X_{n+1}\in (\overline{X_n}\pm t_{n-1,\alpha/2}S_n\sqrt{1+1/n})$ with confidence $1-\alpha$.

**Proof of 4** $(n-1)S_n^2/\sigma^2\sim T_{n-1}$.

**Proof of 5** $\overline{X_n}\sim\mathcal{N}(\mu_1,\sigma_1^2/n)$, $\overline{Y_n}\sim\mathcal{N}(\mu_2,\sigma_2^2/m)$, so $\overline{X_n}-\overline{Y_n}\sim \mathcal{N}(\mu_1-\mu_2,\sigma_1^2/n+\sigma_2^2/m)$.

**Proof of 6** $\frac{\overline{X}-\overline{Y}-(\mu_x-\mu_y)}{\sqrt{\sigma^2(1/n+1/m)}}\sim Z$ and $\frac{(n-1)S_x^2+(m-1)S_y^2}{\sigma^2}\sim \chi_{n+m-2}^2$. So, $\frac{\overline{X}-\overline{Y}-(\mu_x-\mu_y)}{\sqrt{(1/n+1/m)\frac{(n-1)S_x^2+(m-1)S_y^2}{n+m-2}}}\sim T_{n+m-2}$.

**Problem** The weights of salmon are normal with a mean that varies from season to season but with a standard deviation that remains fixed at 0.3 pounds. If we want to be 95 percent certain that our estimate of the present season’s mean weight of a salmon is correct to within ±0.1 pounds, how large a sample is needed?
**Solution** We want $2z_{0.025}\frac{0.3}{\sqrt{n}}=2z_{\alpha}\frac{\sigma}{\sqrt{n}}\leq 0.2$, then $n\geq (3z_{0.025})^2=34.57$.

**Theorem** Let $X_1,...,X_n$ be a sample drawn from a Bernoulli random variable population, then the $1-\alpha$ confidence interval for $p$ is approximately $(\hat{p}\pm z_{\alpha/2}\sqrt{\frac{\hat{p}(1-\hat{p})}{n}})$ with $\hat{p}=\frac{X}{n}$.
**Proof** By CLT, $\frac{X-np}{\sqrt{p(1-p)n}}\sim\mathcal{N}(0,1)$. So, $p\in (\hat{p}\pm z_{\alpha/2}\sqrt{p(1-p)/n})$, which is approximately $(\hat{p}\pm z_{\alpha/2}\sqrt{\hat{p}(1-\hat{p})/n})$. 

**Definition** A null hypothesis is a statement about parameters $\theta$ of a population distribution. If the null hypothesis, along with existing information on $\theta$, completely determines the distribution, then its a simple hypothesis. Otherwise, its a composite hypothesis. A test for a null hypothesis could be specified by defining a "critical region" $C\subset \mathbb{R}^n$ so that one rejects the null hypothesis if $(X_1,...,X_n)\in C$ and one accepts the null hypothesis if $(X_1,...,X_n)\notin C$. Type I error, is said to result if the test incorrectly calls for rejecting $H_0$ when it is indeed correct. Type II error, results if the test calls for accepting $H_0$ when it is false. One way to measure type II errors is the operating characteristic (OC) curve, the probability that null hypothesis is accepted when its false. $p$-value of a test sample is the probability of getting results at least as extreme as the test sample under the null hypothesis. If the $p$-value is less than the significance level $\alpha$, then the null hypothesis is rejected. A common approach to developing a test of $H_0$ at level of significance $\alpha$, is to start by determining a point estimator of $\theta$ such as $d(X)$. To determine how “far away” it need be to justify rejection of $H_0$, we determine the probability distribution of $d(X)$ when $H_0$ is true and then the critical region with significance level $\alpha$.

**Theorem** Given a sample $X_1,...,X_n$ from a normal population. If $\mu$ is unknown and $\sigma$ is known, the probability of accepting $\mu=\mu_0$ when $\mu\neq \mu_0$ equals $\beta(\mu)=\Phi(\frac{(\mu_0+z_{\alpha/2}\sigma/\sqrt{n}-\mu)}{\sigma/\sqrt{n}})-\Phi(\frac{(\mu_0-z_{\alpha/2}\sigma/\sqrt{n}-\mu)}{\sigma/\sqrt{n}})=\Phi(\frac{\mu_0-\mu}{\sigma/\sqrt{n}}+z_{\alpha/2})-\Phi(\frac{\mu_0-\mu}{\sigma/\sqrt{n}}-z_{\alpha/2})$. (The first step could be seen as calculating the probability that $\overline{X_n}\sim\mathcal{N}(\mu,\sigma/\sqrt{n})$ falls in the interval $(\mu_0\pm z_{\alpha/2}\sigma/\sqrt{n})$.); the probability of accepting $\mu=\mu_0$ when $\mu \>\ \mu_0$ equals $\beta(\mu)=\Phi(\frac{\mu_0-\mu+z_\alpha\sigma/sqrt{n}}{\sigma/\sqrt{n}})=\Phi(\frac{\sqrt{n}(\mu_0-\mu)}{\sigma}+z_\alpha)$.

**Theorem** Given a sample $X_1,...,X_n$ from a normal population. 
1. If $\mu$ is unknown and $\sigma$ is known, let $S=\frac{\overline{X}-\mu_0}{\sigma/\sqrt{n}}\sim Z$ be the statistics. Reject $\mu=\mu_0$ with confidence level $\alpha$ if $P(Z\geq S)\leq\alpha/2$ or $P(Z\leq S)\leq\alpha/2$; reject $\mu\leq\mu_0$ if $P(Z\geq S)\leq\alpha$; reject $\mu\geq\mu_0$ if $P(Z\leq S)\leq\alpha$.

2. If $\mu$ and $\sigma$ are unknown, let $S=\frac{\overline{X}-\mu_0}{S/\sqrt{n}}\sim T_{n-1}$ be the statistics. Reject $\mu=\mu_0$ with significant level $\alpha$ if $P(T_{n-1}\geq S)\leq\alpha/2$ or $P(T_{n-1}\leq S)\leq\alpha/2$; reject $\mu\leq\mu_0$ with significant level $\alpha$ if $P(T_{n-1}\geq S)\leq\alpha$ $\mu_0\notin(\overline{X}-t_{n-1,\alpha}\frac{S}{\sqrt{n}},\infty)$.

3. Given sample $Y_1,...,Y_m$ from another normal population, if $\mu_x$ and $\mu_y$ are unknown and $\sigma_x$ and $\sigma_y$ are known, then reject $\mu_x=\mu_y$ if $P(\mathcal{N}(0,\sqrt{\sigma_x^2/n+\sigma_y^2/m})>\overline{X}-\overline{Y})\leq \alpha/2$ or $P(\mathcal{N}(0,\sqrt{\sigma_x^2/n+\sigma_y^2/m})\leq\overline{X}-\overline{Y})\leq\alpha/2$.

4. Given sample $Y_1,...,Y_m$ from another normal population, if $\mu_x$, $\mu_y$, and $\sigma_x^2=\sigma^2=\sigma_y^2$ are unknown, then reject $\mu_x=\mu_y$ if $\frac{(\overline{X}-\overline{Y})}{\sqrt{(\frac{1}{n}+\frac{1}{m})\frac{S_x^2(n-1)+S_y^2(m-1)}{(m+n-2)}}}\notin(\pm t_{n+m-2,\alpha/2})$.

5. Given sample $Y_1,...,Y_m$ from another normal population, if $\mu_x$, $\mu_y$, $\sigma_x^2$, $\sigma_y^2$ are unknown and $m$ and $n$ are large, then reject $\mu_x=\mu_y$ if $\frac{\overline{X}-\overline{Y}}{\sqrt{\frac{S_x^2}{n}+\frac{S_y^2}{m}}}\notin(\pm Z_{\alpha/2})$.

6. If $\mu$ and $\sigma$ are both unknown, then reject $\sigma^2=\sigma_0^2$ if $\frac{(n-1)S^2}{\sigma_0^2}\notin(\chi_{n-1,1-\alpha/2}^2,\chi_{n-1,\alpha/2}^2)$.

7. Given sample $Y_1,...,Y_m$ from another normal population, if $\mu_x$, $\mu_y$, $\sigma_x^2$, $\sigma_y^2$ are unknown, then reject $\sigma_x^2=\sigma_y^2$ if $\frac{S_x^2}{S_y^2}\notin(F_{1-\alpha/2,n-1,m-1},F_{\alpha/2,n-1,m-1})$. (because $\frac{S_x^2}{\sigma_x^2}\sim\chi_{n-1}^2/(n-1)$.)

**Theorem** Given a sample $X_1,...,X_n$ from a Bernoulli population with $p$ unknown:

1. Reject the hypothesis $p\neq p_0$ with $\alpha$ significance if $p$-value $P(binom(n,p_0)\geq x)\leq \alpha/2$ or $P(binom(n,p_0)\leq x)\leq \alpha/2$; reject the hypothesis $p\leq p_0$ with $\alpha$ significance if $p$-value $P(binom(n,p_0)\geq X)\leq \alpha$; reject the hypothesis $p\geq p_0$ with $\alpha$ significance if $p$-value $P(binom(n,p_0)\leq  X)\leq \alpha$; (reject the null hypothesis that $p\geq p_0$ if the probability of $binom(x,p)\geq binom(x,p_0)$ is $\leq \alpha$)

2. If $n$ is large, an approximate significance level $\alpha$ test would reject $p\leq p_0$ if $\frac{\overline{X}-np_0}{\sqrt{np_0(1-p_0)}}\geq z_\alpha$.

3. Given a sample $Y_1,...,Y_m$ from another Bernoulli sample with $p'$ unknown, reject the hypothesis that $p=p'$ if $P(hypergeometric(n,m,x+y)\geq x)\leq \alpha/2$ or $P(hypergeometric(n,m,x+y)\leq x)\leq\alpha/2$ with $x=\sum X_i$ and $y=\sum Y_i$.

**Theorem** Given a sample $X_1,...,X_n$ from a Poisson population (their sum is Poisson) with $\lambda$ unknown:

1. Reject the hypothesis $\lambda=\lambda_0$ if $P_{\lambda_0}(X\geq x)\leq\alpha/2$ or $P_{\lambda_0}(X\leq x)\leq\alpha/2$. 

2. Given a sample $Y_1,...,Y_n$ from another Poisson population (their sum is Poisson) with $\lambda_2$ unknown, reject the hypothesis $\lambda_2=c\lambda$ if $P(Bin(n,1/(1+c))\geq x_1)\leq \alpha/2$ or if $P(Bin(n,1/(1+c))\leq x_1)\leq\alpha/2$ with $x_1=\sum X_i$ (because the distribution of $X_1$ given $X_1+X_2=n$ (with $X_1\sim Poisson(\lambda_1)$ and $X_2\sim Poisson(\lambda_2)$) is biomial with $p=1/(1+c)$.)

**Theorem** Let $S_{xY}=\sum_i(x_i-\overline{x})(Y_i-\overline{Y})$, $S_{xx}=\sum_i(x_i-\overline{x})^2$, and $S_{YY}=\sum_i(Y_i-\overline{Y})^2$. Suppose $Y_i=\mathcal{N}(A+Bx_i,\sigma^2)$. The least square estimate of $Y_i=A+Bx_i$ is $B=\frac{S_{xY}}{S_{xx}}$, $A=\overline{Y}-B\overline{x}$ with $A\sim \mathcal{N}(\alpha,\frac{\sigma^2\sum_ix_i^2}{nS_{xx}})$, $B\sim\mathcal{N}(\beta,\sigma^2/S_{xx})$. Let $SS_R=\sum_i(Y_i-A-Bx_i)^2=\frac{S_{xx}S_{YY}-S_{xY}^2}{S_{xx}}$, then $\frac{SS_R}{\sigma^2}\sim \chi_{n-2}^2$

**Theorem** Reject $\beta=0$ if $\sqrt{\frac{(n-2)S_{xx}}{SS_R}}|B|>t_{n-2,\alpha/2}$. A $1-\alpha$ confidence interval for $\beta$ is $(B\pm \sqrt{\frac{SS_R}{(n-2)S_{xx}}}t_{n-2,\alpha/2})$. The $1-\alpha$ confidence interval for $\alpha$ is $A\pm t_{n-2,\alpha/2}\sqrt{\frac{SS_R\sum_i x_i^2}{n(n-2)S_{xx}}}$. The $1-\alpha$ confidence interval for $\alpha+\beta x_0$ is $(A+Bx_0\pm \sqrt{\frac{1}{n}+\frac{(x_0-\overline{x})^2}{S_{xx}}}\sqrt{\frac{SS_R}{n-2}}t_{n-2,\alpha/2})$. The $1-\alpha$ confidence interval for $Y$ is $A+Bx\pm t_{n-2,\alpha/2}\sqrt{(\frac{n+1}{n}+\frac{(x_0-\overline{x})^2}{S_{xx}})\frac{SS_R}{n-2}}$

**Definition** $R^2=\frac{S_{YY}-SS_R}{S_{YY}}=1-\frac{SS_R}{S_{YY}}$ measures the amount of variation in the response explained by different inputs. We have $R^2=r^2$ with $r=\frac{S_{xY}}{S_{xx}S_{YY}}$

test hypothesis that \beta_i=0

estimate variance

estimate 95% confidence interval of Y given x










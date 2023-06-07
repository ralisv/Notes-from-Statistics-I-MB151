# Notes-from-Statistics-I-MB151


## Bayes' Theorem

### Theorem
$$
\mathcal{P}(\theta \mid \mathcal{Data}) =
\frac{\mathcal{P}(\mathcal{Data} \mid \theta) \cdot \mathcal{P}(\theta)}
{\mathcal{P}(\mathcal{Data})}
$$

The prior probability of the outcome theta is $\mathcal{P}(\theta)$, this probability is assumed and not deduced from the $\mathcal{Data}$, it is often based on an educated guess or prior knowledge. $\mathcal{P}(\theta)$ can for instance represent the probability of having a disease.

$\mathcal{Data}$ represents the new information we've found about something. It can for instance refer to some new testing.

$\mathcal{P}(\theta \mid \mathcal{Data})$ represents the true probability of theta given the new Data.

### Example
Let's illustrate how Bayes' theorem can help us to answer important question using the example of COVID-19 testing.

We know that the one out of 50 people has COVID-19. The test is guaranteed to detect the virus in someone if he has it and it has a 99.9% chance of correctly identifying that someone does not have the virus, therefore it's got a 0.1% chance of a false positive.

Given I was tested positive, what is the true probability that I actually am infected?

In this case, the prior knowledge theta is that $\frac{1}{50}$ of population suffer from COVID-19,thus how likely am I to have the infection regardless of some test.
The $\mathcal{Data}$ is what we know about test.

So what we're truly interested in is $\mathcal{P}(\mathcal{covid} \mid \mathcal{+test})$.

$$
\mathcal{P}(\mathcal{covid} \mid \mathcal{+test}) =
\frac{\mathcal{P}(\mathcal{+test} \mid \mathcal{covid}) \cdot \mathcal{P}(\mathcal{covid})}
{\mathcal{P}(\mathcal{+test})} =
\frac{\mathcal{1} \cdot \frac{1}{50}}{\frac{1}{50} + \frac{49}{50} \cdot 0.001} = 0.9532888
$$

So one should really believe the test.


## Random variable

### What's a random variable
Formally, random variable is a mathematical formalization of of quantity or object which depends on random events.

From now on, we'll refer to random variable as to $\mathcal{X}$.

We describe the behaviour of random variable with cumulative distribution functions which tell us the likelihoods of $\mathcal{X}$ taking on certain value or values.

It helps us simplify mathematical expressions as follows:  
$\mathcal{P}(\mathcal{X} < 5) = \mathcal{P}(\{e \mid e \in \mathcal{E} \land e < 5\})$, where $\mathcal{E}$ is the set of all events that can occur. Such expression would result in probability that $\mathcal{X}$ will take on value smaller than 5.

There are discrete random variables, which can take on at most enumerable number of values, and there are continous random variables, which can take on any value in an interval for instance.

### Example
Random variable $\mathcal{X}$ could represent many things, for instance:
- a coin toss, in which case it could take on two separate values being tail and head,

- a count of heads when we toss 10 coins at a time,

- the time one has to wait in a queue,

- the amount of organisms living in a unit of space.

### Probability distribution functions
They are tightly connected to random variables and are used to formally describe its behavioral patterns.

Let's say that random variable $\mathcal{X}$ is defined by probability distribution function $\mathcal{F}$, then $\mathcal{F}(x) = \mathcal{P}(\mathcal{X} \leq x)$  

Probability distribution functions must follow certain rules, for instance:

$$
\lim_{x \to \infty} \mathcal{F}(x) = 1 
$$

This must hold true, otherwise it would mean that the probability of anything occuring at all is lower than 100%.

#### Probability distribution function for discrete variable

Let's have a discrete random variable representing the number of coin tosses before having our first head. So the range of values $\mathcal{R}_{\mathcal{X}} = \{1, 2, 3, ...\}$

$$
\mathcal{F}(x) = 2^{-x}
$$

And the graph would of such cummulative distribution function would look like this:

![cummulative-discrete](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/59169278-87f0-4c9a-ad75-e65ccf760440)


The graph would go into infinity in reality, however, the likelihoods of $\mathcal{X}$ becoming higher lowers exponentially, so those chances become negligible.

#### Probability distribution function for continuous variable

Let's have a continuous random variable representing the amout of time we need to spend in queue in shop, the range of values $\mathcal{R}_{\mathcal{X}} = [0, 5]$ (in minuts)

If the waiting time were completely random, the cummulative distribution function would look like this:

![cummulative-continuous](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/736fb683-be3b-44fb-823b-5c2c6a15a3c2)

## Discrete probability distributions

Discrete probability distributions are probability distributions that can take on only a countable number of values.

Each probability distribution is associated with a probability mass function (PMF),
which is a function that gives the probability that a discrete random variable is exactly equal to some value.

Mean of a discrete probability distribution is the expected value of the random variable, therefore the average value that we would receive after selecting $\infty$ number of samples.

Variance of a discrete probability distribution is the expected value of the squared deviation of a random variable from its mean.

### Bernoulli distribution

Bernulli distribution is a discrete probability distribution is linked to a random trial with the $\theta$
probability of success and $1 - \theta$ probability of failure. Therefore the set of value the $\mathcal{X}$ can take on has two elements.

#### Example graph

![bernoulli-distribution-0 6](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/d9c3a548-b809-4602-8f1f-ff2932770831)


### Binomial distribution

Binomial distribution is a discrete probability distribution which models the number of successes in a fixed number $n$ of independent Bernoulli trials.

It is defined by two parameters being:
- $n$, the number of trials,
- $\theta$, the probability for success in each Bernoulli trial,

#### PMF = $\mathcal{P}(x) = \(\binom{n}{x}\) \theta^x\(1 - \theta\)^{n - x}$

#### Mean = $n \cdot \theta$

#### Variance = $n \cdot \theta \cdot (1 - \theta)$

#### Example graph

![binomial-distribution-10-0 3](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/2a9054ab-a748-4974-ac20-31f0c9cc4a85)


![binomial-distribution-20-0 5](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/ec35b664-dd76-4928-b3e9-18eb655d9035)


#### Practical example

A sniper has got a 0.8 probability of hitting a target and 15 bullets. There are 15 different targets. What is the probability that he will hit at least 14 of them?

$$
\mathcal{P}(x \geq 14) = \mathcal{P}(x = 14) + \mathcal{P}(x = 15) = \(\binom{15}{14}\) 0.8^{14} 0.2^{1} + \(\binom{15}{15}\) 0.8^{15} 0.2^{0} = 0.1319 + 0.0352 = 0.1671
$$

### Poisson distribution

Poisson distribution is a discrete probability distribution which models the number of events occuring
in a fixed interval of time or space, if these events occur with a known constant rate and independently of the time since the last event.

It is defined by one parameter:
- $\lambda$, which represents the expected number of events in the interval.

#### PMF = $\mathcal{P}(x) = \frac{\lambda^x e^{-\lambda}}{x!}$

#### Mean = $\lambda$

#### Variance = $\lambda$

#### Example graph

![poisson-distribution-2](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/b8f8e269-44ca-4d55-986d-3581f26a5d0b)

![poisson-distribution-10](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/478672ad-6ec4-49c7-a35d-b4d259c1820a)

#### Practical example

An OPC-UA server receives 50 read requests per second on average.
What is the probability that it will receive 42 read requests in a second?

$$
\mathcal{P}(x = 42) = \frac{50^{42} e^{-50}}{42!} = 0.0312
$$

### Geometric distribution

Geometric distribution is a discrete probability distribution which models the number of independent Bernoulli trials
needed to get the first success.

It is defined by one parameter:
- $\theta$, the probability for success in each Bernoulli trial.

#### PMF = $\mathcal{P}(x) = \theta (1 - \theta)^{x - 1}$

#### Mean = $\frac{1}{\theta}$

#### Variance = $\frac{1 - \theta}{\theta^2}$

#### Example graph

![geometric-distribution-0 8](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/14ede7d4-5f20-4622-8f30-c657ac6297c2)

![geometric-distribution-0 5](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/77f908c3-4ae8-44de-8efc-ec61275c5130)

#### Practical example

A sniper has got a 0.8 probability of hitting a target but he only has 3 bullets.
What is the probability that he won't hit the target?

$$
\mathcal{P}(x > 3) = 1 - \mathcal{P}(x \leq 3) = 1 - \mathcal{P}(x = 1) - \mathcal{P}(x = 2) - \mathcal{P}(x = 3) = 1 - 0.8 - 0.16 - 0.032 = 0.008
$$


## Continuous probability distributions

Continuous probability distributions are probability distributions that represent a behaviour of a continuous random variable.

They are associated with a probability density function (PDF) which is a function that describes the relative likelihood for this random variable to take on a given value.

If we want to find the probability of a random variable being in a certain interval, we need to integrate the PDF over that interval.

The chance of a random variable following any continuous probability distribution taking on one particular value is always $\frac{1}{\infty} = 0$.

Doing that, we'll get the cumulative distribution function (CDF) which is a function that describes the probability that the random variable will be less than or equal to a certain value.

Mean of a continuous probability distribution is defined as $\int_{-\infty}^{\infty} x \cdot f(x) dx$, where $f(x)$ is the PDF.

Variance of a continuous probability distribution is defined as $\int_{-\infty}^{\infty} (x - \mu)^2 \cdot f(x) dx$, where $f(x)$ is the PDF and $\mu$ is the mean.

### Normal distribution

Normal distribution is a continuous probability distribution which models a random variable whose PDF has a bell-shaped curve.

It is the most important distribution in statistics because of the Central Limit Theorem.

It is defined by two parameters:
- $\mu$, the mean,
- $\sigma$, the standard deviation.

#### PDF = $f(x) = \frac{1}{\sigma \sqrt{2 \pi}} e^{-\frac{(x - \mu)^2}{2 \sigma^2}}$

#### Mean = $\mu$

#### Variance = $\sigma^2$

#### Example graph

![normal-distribution-0-1](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/1a33edd5-6abd-4f1c-9171-70bb95265a6e)

![normal-distribution-175-6](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/45e43d6f-e8a1-44cc-8df7-758bab7ffcdf)


#### Practical example

An average man is 175 cm tall with a standard deviation of 6 cm, how many percent of men are taller than 180 cm?

$$
\mathcal{P}(x > 180) = 1 - \mathcal{P}(x \leq 180) = 1 - \int_{-\infty}^{180} \frac{1}{6 \sqrt{2 \pi}} e^{-\frac{(x - 175)^2}{2 \cdot 6^2}} dx
$$

However, such integral is pretty hard to solve, so we can transform it to a standard normal distribution N(mean=0, sd=1).

$$
\mathcal{P}(x > 180) = 1 - \mathcal{P}(x \leq 180) = 1 - \mathcal{P_N}(x \leq \frac{180 - 175}{6}) = 1 - \mathcal{P_N}(x \leq 0.833) = 1 - 0.7977 = 0.2023
$$

Where $\mathcal{P_N}$ is the CDF of the standard normal distribution, the value of CDF for 0.833 can be found in the table of values of the standard normal distribution.

### Exponential distribution

Exponential distribution is a continuous probability distribution which models the time between events in a Poisson process.

It is the continuous analogue of the geometric distribution and a particular case of the gamma distribution.

It is defined by one parameter:
- $\lambda$, which represents the rate of events.

#### PDF = $f(x) = \lambda e^{-\lambda x}$

#### CDF = $F(x) = 1 - e^{-\lambda x}$

#### Mean = $\frac{1}{\lambda}$

#### Variance = $\frac{1}{\lambda^2}$

#### Example graph

![exponential-distribution-50](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/a999bc7d-8df5-4424-bb89-0d3e58ba3764)

#### Practical example

An OPC-UA server receives 50 read requests per second on average. What is the probability that it will receive more than 5 request in 20 ms?

We're going to need to convert the time to milliseconds. 50 requests per second means 1 request per 20 ms.

$$
\mathcal{P}(x > 5) = 1 - \mathcal{P}(x \leq 5) = e^{-1 \cdot 5} = 0.0.0067
$$

### Uniform distribution

Uniform distribution is a continuous probability distribution which models a random variable that is equally likely to take on any value within an interval.

It is defined by two parameters:
- $a$, the lower bound of the interval,
- $b$, the upper bound of the interval.

#### PDF = $f(x) = \frac{1}{b - a}$

#### CDF = $F(x) = \frac{x - a}{b - a}$

#### Mean = $\frac{a + b}{2}$

#### Variance = $\frac{(b - a)^2}{12}$

#### Example graph

![uniform-distribution-0-1](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/7290e48f-f4ba-47fb-8197-101857ed6dc9)

![uniform-distribution-0-1](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/02c67963-ac90-47ab-8792-fbcb8d28c789)

#### Practical example

A random number generator generates a random number between 0 and 1. What is the probability that the number will be between 0.2 and 0.5?

$$
\mathcal{P}(0.2 \leq x \leq 0.5) = \mathcal{P}(x \leq 0.5) - \mathcal{P}(x \leq 0.2) = 0.5 - 0.2 = 0.3
$$


## Central Limit Theorem

### Theorem

Under certain conditions, the average or sum of many samples of a random variable with finite mean $\mu$ and standard deviation $\sigma$ is approximately normally distributed.

According to the CLT, as n (sample length) approaches infinity, the distribution of the sample mean tends to a normal distribution with mean $\mu$ and standard deviation $\frac{\sigma}{\sqrt{n}}$.

In case we need a distribution for sample sum, mean would be $\mu n$ and standard deviation $\frac{\sigma}{\sqrt{n}}$.

Let $\mathcal{X}_1, \mathcal{X}_2, \dots, \mathcal{X}_n$ be a sequence of independent and identically distributed random variables with finite mean $\mu$ and variance $\sigma^2$.
Then the random variable $\mathcal{S}_n$ representing the sample sum is defined as:

$$
\mathcal{S}_n = \frac{\mathcal{X}_1 + \mathcal{X}_2 + \dots + \mathcal{X}_n - n \cdot \mu}{\sigma \sqrt{n}}
$$

The random variable $\mathcal{S}_n$ converges in distribution to a normal $\mathcal{N}(0, 1)$ as $n \to \infty$.

### Example

Let's have a look at the example of rolling a dice. We know that the mean of the dice is 3.5 and the variance is 2.92.
What is the chance that the average of 10000 dice rolls will be greater than 3.6?

$$
\mathcal{P}(\mathcal{M} > 3.6) = 1 - pnorm(\frac{3.6 * 10000 - 3.5 * 10000}{2.92 * sqrt(10000)}, mean=0, sd=1) = 0.0003
$$

And if we increase the number of dice rolls to 100000?

$$
\mathcal{P}(\mathcal{M} > 3.6) = 1 - pnorm(\frac{3.6 * 100000 - 3.5 * 100000}{2.92 * sqrt(100000)}, mean=0, sd=1) = \text{almost zero}
$$

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

There are continous random variables, which can take on at most enumerable number of values, and there are continous random variables, which can take on any value in an interval for instance.

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

## Central Limit Theorem

### Theorem

Under certain conditions, the average or sum of many samples of a random variable with finite mean and variance is approximately normally distributed.

According to the CLT, as n approaches infinity, the distribution of the sample mean M tends to a normal distribution with mean $\mu$ and standard deviation $\frac{\sigma}{\sqrt{n}}$.

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

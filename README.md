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

## Probability distributions

### Bernoulli distribution

Bernulli distribution is a discrete probability distribution is linked to a random trial with the $\theta$
probability of success and $1 - \theta$ probability of failure. Therefore the set of value the $\mathcal{X}$ can take on has two elements.

#### Example graph
![cumulative-alternative](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/4790aca9-4155-4795-874b-7751d3353de5)

### Binomial distribution

Binomial distribution is a discrete probability distribution which models the number of successes in a fixed number $n$ of independent Bernoulli trials.

It is defined by two parameters being:
- $n$, the number of trials,
- $\theta$, the probability for success in each Bernoulli trial,
as follows: $\mathcal{P}(x) = \(\binom{n}{x}\) \theta^x\(1 - \theta\)^{n - x}$

#### Example graph

Binomial distribution with $n = 10$ and $\theta = 0.3$,

![binomial-distribution-10-0 3](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/30b173b8-cb9d-4959-9dce-4f2e54a073c3)


with $n = 20$ and $\theta = 0.5$,

![binomial-distribution-20-0 5](https://github.com/ralisv/Notes-from-Statistics-I-MB151/assets/90596867/baf35ca9-f6f0-4abb-b2e0-041de2745ad6)


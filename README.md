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

Random variable $\mathcal{X}$ could represent many things, for instance a coin toss, in which case it could take on two separate values being tail and head. Or it could represent a count of heads when we toss 10 coins at a time. Or the time one has to wait in a queue or the amount of organisms living in a unit of space.

We describe the behaviour of random variable with cumulative distribution functions which tell us the likelihoods of $\mathcal{X}$ taking on certain value or values.

It helps us simplify mathematical expressions as follows:  
$\mathcal{P}(\mathcal{X} < 5) = \mathcal{P}(\{e \mid e \in \mathcal{E} \land e < 5\})$, where $\mathcal{E}$ is the set of all events that can occur. Such expression would result in probability that $\mathcal{X}$ will take on value smaller than 5.

### Probability distribution functions
They are tightly connected to random variables and are used to formally describe its behavioral patterns.

Let's say that random variable $\mathcal{X}$ is defined by probability distribution function $\mathcal{F}$, then $\mathcal{F}(x) = \mathcal{P}(\mathcal{X} \leq x)$  

Probability distribution functions must follow certain rules, for instance:

$$
\lim_{x \to \infty} \mathcal{F}(x) = 1 
$$

This must hold true, otherwise it would mean that the probability of anything occuring at all is lower than 100%.

Probability distribution functions can describe continuous variables or discrete variables.
**Probability** is a measure of the likelihood of an event occurring. Probability is usually represented as a number between 0 and 1, where 0 means that the event is impossible and 1 means that the event is certain to occur.

**Random Variables** are variables whose values depend on the outcome of a random process. Random variables can be either discrete or continuous.

- Discrete random variables take on a countable number of distinct values (e.g., the number of heads in three coin flips).
- Continuous random variables can take on an uncountable number of values (e.g., the height of a person).

**Probability Distribution** is a function that describes the likelihood of each possible outcome of a random variable. There are two types of probability distributions:

- Discrete probability distributions, which are used to model discrete random variables. Examples include the Bernoulli distribution and the Poisson distribution.
- Continuous probability distributions, which are used to model continuous random variables. Examples include the Normal distribution and the Exponential distribution.

**Joint Probability** is the probability of two or more events occurring together. It is denoted as P(A and B), where A and B are events.

**Conditional Probability** is the probability of an event occurring given that another event has occurred. It is denoted as P(A|B), where A is the event of interest and B is the condition.

**Bayes' Theorem** is a formula that describes how to update our beliefs about the probability of an event occurring based on new evidence. It is expressed as:

**P(A|B) = P(B|A) * P(A) / P(B)**

where P(A|B) is the probability of A given that B has occurred, P(B|A) is the probability of B given that A has occurred, P(A) is the prior probability of A, and P(B) is the prior probability of B.

In the context of Naive Bayes, Bayes' Theorem is used to compute the posterior probability of a class label given the observed features of a data point. The prior probability of each class is estimated from the training data, and the likelihood of the features given each class is computed using the probability density function of each feature.
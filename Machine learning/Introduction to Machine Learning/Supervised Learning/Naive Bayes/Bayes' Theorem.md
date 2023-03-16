## Bayes' Theorem
Bayes' Theorem is a fundamental theorem in probability theory that describes the probability of an event based on prior knowledge of conditions that might be related to the event. It is named after the Reverend Thomas Bayes, who first formulated the theorem in the 18th century.

The theorem is often used in machine learning algorithms, including Naive Bayes, to calculate the probability of a certain class given a set of features.

## The formula
Bayes' Theorem can be expressed mathematically as:

P(A|B) = P(B|A) * P(A) / P(B)

where:

- P(A|B) is the probability of A given B (i.e., the probability of the hypothesis given the observed evidence).
- P(B|A) is the probability of B given A (i.e., the probability of the evidence given the hypothesis).
- P(A) is the prior probability of A (i.e., the probability of the hypothesis before observing the evidence).
- P(B) is the prior probability of B (i.e., the probability of the evidence before considering the hypothesis).

## Example
To illustrate Bayes' Theorem, let's consider a simple example. Suppose we want to determine the probability that a person has a certain disease, given that they have tested positive for the disease.

Let's define:

- A: the event that the person has the disease.
- B: the event that the person tests positive for the disease.

We can use Bayes' Theorem to calculate P(A|B), the probability of A given B:

P(A|B) = P(B|A) * P(A) / P(B)

P(B|A) is the sensitivity of the test, or the probability that a person with the disease tests positive. P(A) is the prevalence of the disease in the population. P(B) is the probability of a positive test result, which can be calculated as:

P(B) = P(B|A) * P(A) + P(B|~A) * P(~A)

where:

- P(B|~A) is the specificity of the test, or the probability that a person without the disease tests negative.
- P(~A) is the complement of P(A), or the probability that the person does not have the disease.
By plugging in the appropriate values, we can calculate P(A|B) and determine the probability of the person having the disease given a positive test result.

## Conclusion
Bayes' Theorem is a powerful tool for calculating conditional probabilities and is widely used in machine learning algorithms such as Naive Bayes. Understanding the basics of Bayes' Theorem is essential for understanding how Naive Bayes classification works.
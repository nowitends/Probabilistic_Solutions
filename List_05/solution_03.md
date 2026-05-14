# Binomial Distribution Presentation

## Slide 1 — Title
In this presentation, I will explain what the binomial distribution is, how it works, and where we use it in real life.

---

## Slide 2 — What is Binomial Distribution?
The binomial distribution is a discrete probability distribution.

It shows the number of successes in repeated experiments.

Each experiment has only two possible results:

- Success
- Failure

For example, when we flip a coin, we can get heads or tails.

---

## Slide 3 — Random Experiment
A binomial experiment repeats the same action many times.

For example, we flip a coin 5 times.

Each flip is independent.

This means one result does not change the next result.

---

## Slide 4 — Sample Space Ω
The sample space contains all possible outcomes.

For 5 coin flips, some outcomes are:

- HHHHH
- HHTTT
- THTHT

Each possible result is called an elementary outcome.

---

## Slide 5 — Random Variable X
The random variable X counts the number of successes.

For example:

If success means getting heads, then:

`X(HHTHT) = 3`

because there are 3 heads.

---

## Slide 6 — Support of X
The support of X is all possible values of the random variable.

For 5 coin flips, X can be:

`0, 1, 2, 3, 4, or 5`

This is different from the sample space.

The sample space contains outcomes, but the support contains values of X.

---

## Slide 7 — PMF Formula
The probability mass function (PMF) gives the probability of getting exactly k successes.

\[
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
\]

Where:

- `n` is the number of trials
- `p` is the probability of success
- `k` is the number of successes

---

## Slide 8 — Example Probability
Now let’s see an example.

Suppose we flip a coin 5 times.

The probability of heads is `0.5`.

We want to find the probability of getting exactly 3 heads.

This is written as:

\[
P(X = 3)
\]

---

## Slide 9 — PMF Graph
The PMF graph shows the probability for each value of X.

The graph changes when `p` changes.

- Small `p` moves the graph to the left
- Large `p` moves the graph to the right

---

## Slide 10 — CDF
The cumulative distribution function (CDF) shows cumulative probability.

\[
F(x)=P(X\le x)
\]

It adds probabilities from left to right.

The CDF always increases from 0 to 1.

---

## Slide 11 — PMF and CDF Comparison
The PMF gives the probability at one value.

Example:

\[
P(X = 3)
\]

The CDF gives probability up to a value.

Example:

\[
P(X \le 3)
\]

Both functions help us understand probability distributions.

---

## Slide 12 — Real Applications
Binomial distribution is used in many areas:

- Exams
- Medical tests
- Quality control
- Surveys
- Coin flips

It is useful when there are only two outcomes.

---

## Slide 13 — Parameter Effects
Changing `p` changes the shape of the graph.

Changing `n` changes the spread of the graph.

A larger `n` makes the graph wider.

---

## Slide 14 — Conclusion
In conclusion, the binomial distribution is useful for repeated experiments with two outcomes.

It helps us calculate probabilities and understand random events.

It is an important distribution in probability and statistics.
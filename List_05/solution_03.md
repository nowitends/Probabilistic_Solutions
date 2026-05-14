# Binomial Distribution Presentation

## Probability and Statistics

---



# Slide 1 — Random Experiment

First, we define the random experiment.

Our experiment is:

- flipping a coin 5 times.

Each flip has two outcomes:

- Heads
- Tails

The flips are independent.

This means one result does not affect another result.

This is important for the binomial distribution.

---

# Slide 2 — Sample Space Ω

Now we define the sample space Ω.

The sample space contains all elementary outcomes.

An elementary outcome is one complete sequence.

Examples:

- HHHHH
- HHTTT
- HTHTH
- TTTTT

The sample space contains all possible sequences of 5 coin flips.

---

# Slide 3 — Random Variable X

Next, we define the random variable X.

The random variable counts the number of successes.

In this presentation:

- success means getting Heads.

Example:

For the outcome:

`HHTHT`

we have:

\[
X(HHTHT)=3
\]

because there are 3 heads.

---

# Slide 4 — Support of X

Now we identify the support of X.

The support is the set of values taken by the random variable.

For 5 coin flips:

\[
X \in \{0,1,2,3,4,5\}
\]

Important:

- the sample space contains outcomes,
- the support contains numerical values.

These are different concepts.

---

# Slide 5 — Definition of Binomial Distribution

The binomial distribution is a discrete probability distribution.

It gives probabilities for repeated independent experiments.

Conditions:

- fixed number of trials,
- two outcomes,
- independent trials,
- same probability of success.

The distribution has two parameters:

- `n` = number of trials,
- `p` = probability of success.

---

# Slide 6 — Parameters

For this example:

\[
n=5
\]

and

\[
p=0.5
\]

This means:

- 5 coin flips,
- probability of heads is 0.5.

Changing parameters changes the graph of the distribution.

---

# Slide 7 — Probability Mass Function (PMF)

The PMF gives the probability of exactly k successes.

\[
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
\]

Where:

- `n` = number of trials,
- `k` = number of successes,
- `p` = probability of success.

The PMF gives probability at one exact value.

---

# Slide 8 — PMF Example

Now we calculate a probability.

We want:

\[
P(X=3)
\]

This means:

- probability of getting exactly 3 heads.

We use:

- `n = 5`
- `k = 3`
- `p = 0.5`

Result:

\[
P(X=3)=0.3125
\]

So the probability is 31.25%.

---

# Slide 9 — PMF Graph

The PMF graph shows probability values for every possible value of X.

Parameter effects:

- small `p` moves the graph left,
- large `p` moves the graph right,
- larger `n` makes the graph wider.

Graphs help us understand probability visually.

---

# Slide 10 — Cumulative Distribution Function (CDF)

Now we study the CDF.

\[
F(x)=P(X\le x)
\]

The CDF adds probabilities from left to right.

Example:

\[
P(X\le3)
\]

This means:

- probability of at most 3 successes.

The CDF always increases from 0 to 1.

---

# Slide 11 — PMF and CDF Comparison

PMF and CDF are different.

PMF:

\[
P(X=3)
\]

- exact probability.

CDF:

\[
P(X\le3)
\]

- cumulative probability.

Both functions are important in probability theory.

---

# Slide 12 — Graphical Understanding

We compare graphs for different values of:

- `n`
- `p`

We study:

- center,
- spread,
- symmetry,
- concentration of probability.

Some properties remain invariant:

- probabilities stay between 0 and 1,
- total probability is always 1.

---

# Slide 13 — Real Applications

The binomial distribution has many practical applications.

Examples:

- exams,
- surveys,
- medical testing,
- quality control,
- reliability analysis.

It is useful when there are only two outcomes:

- success or failure.

---

# Slide 14 — Computational Tools

Computational tools help students visualize distributions.

Examples:

- Python,
- HTML and JavaScript,
- statistical software.

An application can allow users to:

- choose a distribution,
- change parameters,
- display PMF and CDF,
- compare probabilities.

This improves technical understanding.


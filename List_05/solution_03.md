# Binomial Distribution Presentation

## Probability and Statistics

---

# Slide 1 — Random Experiment

First, we define the random experiment.

Our experiment is:
- Flipping a coin 5 times.

Each flip has two outcomes:
- Heads
- Tails

The flips are independent. This means one result does not affect another result. This is important for the binomial distribution.

---

# Slide 2 — Sample Space $\Omega$

Now we define the sample space $\Omega$.

The sample space contains all elementary outcomes. An elementary outcome is one complete sequence.

Examples:
- HHHHH
- HHTTT
- HHTHT
- TTTTT

The sample space contains all possible sequences of 5 coin flips.

---

# Slide 3 — Random Variable $X$

Next, we define the random variable $X$.

The random variable counts the number of successes.

In this presentation:
- Success means getting Heads.

Example: For the outcome `HHTHT`, we have:

$$X(\text{HHTHT}) = 3$$

because there are 3 heads.

---

# Slide 4 — Support of $X$

Now we identify the support of $X$.

The support is the set of values taken by the random variable. For 5 coin flips:

$$X \in \{0, 1, 2, 3, 4, 5\}$$

Important:
- The sample space contains outcomes.
- The support contains numerical values.

These are different concepts.

---

# Slide 5 — Definition of Binomial Distribution

The binomial distribution is a discrete probability distribution. It gives probabilities for repeated independent experiments.

Conditions:
- Fixed number of trials
- Two outcomes (success or failure)
- Independent trials
- Same probability of success for each trial

The distribution has two parameters:
- $n$ = number of trials
- $p$ = probability of success

---

# Slide 6 — Parameters

For this example:

$$n = 5$$
$$p = 0.5$$

This means:
- 5 coin flips.
- Probability of heads is $0.5$.

Changing parameters changes the graph of the distribution.

---

# Slide 7 — Probability Mass Function (PMF)

The PMF gives the probability of exactly $k$ successes.

$$P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}$$

Where:
- $n$ = number of trials
- $k$ = number of successes
- $p$ = probability of success
- $\binom{n}{k}$ = number of combinations ($C(n,k)$)

The PMF gives the probability at one exact value.

---

# Slide 8 — PMF Example

Now we calculate a probability. We want to find:

$$P(X = 3)$$

This means the probability of getting exactly 3 heads.

We use:
- $n = 5$
- $k = 3$
- $p = 0.5$

Calculation:

$$P(X = 3) = \binom{5}{3} \times 0.5^3 \times 0.5^{5-3}$$
$$P(X = 3) = 10 \times 0.125 \times 0.25 = 0.3125$$

So the probability is $31.25\%$.

---

# Slide 9 — PMF Graph

The PMF graph shows probability values for every possible value of $X$.

Parameter effects:
- Small $p$ moves the graph to the left.
- Large $p$ moves the graph to the right.
- Larger $n$ makes the graph wider.

Graphs help us understand probability visually.

---

# Slide 10 — Cumulative Distribution Function (CDF)

Now we study the CDF.

$$F(x) = P(X \le x) = \sum_{k=0}^{\lfloor x \rfloor} \binom{n}{k} p^k (1-p)^{n-k}$$

The CDF adds probabilities from left to right.

Example:

$$P(X \le 3)$$

This means the probability of getting at most 3 successes (3 or fewer). The CDF always increases from $0$ to $1$.

---

# Slide 11 — PMF and CDF Comparison

PMF and CDF are different.

* **PMF:** $P(X = 3) \rightarrow$ exactly 3 successes.
* **CDF:** $P(X \le 3) \rightarrow$ 3 successes or fewer (cumulative probability).

Both functions are important in probability theory.

---

# Slide 12 — Graphical Understanding

We compare graphs for different values of $n$ and $p$.

We study:
- Center (mean)
- Spread (variance)
- Symmetry
- Concentration of probability

Some properties remain invariant:
- Probabilities always stay between $0$ and $1$.
- Total probability is always equal to $1$.

---

# Slide 13 — Real Applications

The binomial distribution has many practical applications.

Examples:
- Exams (passing/failing multiple-choice questions)
- Surveys (yes/no responses)
- Medical testing (positive/negative results)
- Quality control (defective/non-defective items)
- Reliability analysis

It is useful whenever there are only two outcomes: success or failure.

---

# Slide 14 — Computational Tools

Computational tools help students visualize distributions.

Examples:
- Python (with SciPy and Matplotlib)
- HTML and JavaScript
- Statistical software (R, SPSS)

An application can allow users to:
- Choose a distribution.
- Change parameters interacting with sliders.
- Display PMF and CDF simultaneously.
- Compare probabilities visually.

This improves technical and intuitive understanding.
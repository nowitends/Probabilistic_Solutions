# Task 3 — Binomial Distribution Bin(n,p)

## Presentation Script | B1 English | 7–10 Minutes

---

# PART 1 — The Experiment (1 min)

First, I need to describe the random experiment.

The experiment is:
- We repeat a simple test **n times**.
- Each test has only **two possible outcomes**: success or failure.
- Each test is **independent**.

This single test is called a **Bernoulli trial**.

The Binomial Distribution is simply **n Bernoulli trials together**.

A special case:

If `n = 1`, we get the **Bernoulli Distribution**:

\[
\text{Bin}(1,p)
\]

---

# PART 2 — Sample Space and Random Variable (1.5 min)

Now I define the **sample space Ω**.

The experiment is:
- We flip a coin **n times**.

The sample space contains all possible **sequences** of results.

One sequence is called an **elementary outcome** `ω`.

For example, if `n = 5`, one elementary outcome looks like this:

```text
ω = (H, T, H, H, T)
```

Here:
- `H` = Heads
- `T` = Tails

Other examples:

```text
ω = (H, H, H, H, H)   ← all Heads
ω = (T, T, T, T, T)   ← all Tails
ω = (H, T, H, T, H)   ← mixed
```

Important:

The sample space contains **sequences**.

But we do not want sequences — we want **numbers**.

So I define the **random variable X**.

`X` counts the number of Heads in the sequence.

```text
X(H, T, H, H, T) = 3
```

`X = 3` because there are 3 Heads.

The **support** of `X` is:

```text
X ∈ {0,1,2,3,...,n}
```

The support is **not** the sample space.

- Sample space → sequences
- Support → numbers

---

# PART 3 — The PMF (2 min)

Now I write the **Probability Mass Function (PMF)**.

The PMF gives the probability of **exactly k successes**.

\[
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
\]

Where:

```text
n = number of trials
k = number of successes
p = probability of success
```

Let me explain the formula:

- `C(n,k)` counts the number of arrangements
- `p^k` gives the probability of successes
- `(1-p)^(n-k)` gives the probability of failures

Example:

`n = 5`, `p = 0.5`, `k = 3`

\[
P(X=3)=\binom{5}{3}(0.5)^3(0.5)^2
\]

\[
=10 \times 0.125 \times 0.25
\]

\[
=0.3125
\]

So the probability is:

```text
31.25%
```

---

# PART 4 — PMF Graph: What Changes? (1.5 min)

Now I look at the **shape of the PMF graph**.

## Case 1 — Fixed n, Different p

```text
n = 10, p = 0.2  → graph moves LEFT
n = 10, p = 0.5  → graph is symmetric
n = 10, p = 0.8  → graph moves RIGHT
```

When `p` increases, the graph moves to the **right**.

## Case 2 — Fixed p, Different n

```text
p = 0.5, n = 5   → narrow graph
p = 0.5, n = 20  → wider graph
```

When `n` increases:
- the graph becomes **wider**
- and more **spread out**

What does NOT change?
- All probabilities stay between 0 and 1
- Total probability is always 1

---

# PART 5 — The CDF (1.5 min)

Now the **Cumulative Distribution Function (CDF)**.

\[
F(x)=P(X \le x)
\]

The CDF adds probabilities from the left.

It:
- starts at 0
- ends at 1
- never decreases

The PMF and CDF answer different questions:

```text
PMF → P(X = 3)   → exactly 3
CDF → P(X ≤ 3)   → 3 or less
```

We can also calculate other probabilities:

\[
P(X \ge k)=1-P(X \le k-1)
\]

\[
P(a \le X \le b)=P(X \le b)-P(X \le a-1)
\]

Example:

\[
P(X \ge 3)=1-P(X \le 2)
\]

\[
=1-0.5
\]

\[
=0.5
\]

---

# PART 6 — Real Applications (1 min)

The Binomial Distribution is very useful in real life.

## Examples

### Exams

A student guesses on 10 questions.

```text
Bin(10,0.25)
```

### Medicine

A treatment works for 70% of patients.

We test 20 patients.

```text
Bin(20,0.7)
```

### Quality Control

A factory checks 100 products.

Each product has a 2% defect probability.

```text
Bin(100,0.02)
```

### Surveys

40% of people support a new law.

We ask 50 people.

```text
Bin(50,0.4)
```

In all examples:
- two outcomes
- independent trials
- fixed n

---

# PART 7 — Conclusion (30 sec)

Let me summarize the key points.

The Binomial Distribution:

\[
\text{Bin}(n,p)
\]

models:
- `n` independent trials
- two outcomes
- same probability `p`

The PMF gives probability at **one exact value**.

The CDF gives probability for **k or less**.

When:
- `p` increases → graph moves right
- `n` increases → graph becomes wider

Thank you.

---

# Quick Reference Card

| Symbol | Meaning | Example |
|---|---|---|
| n | number of trials | 5 coin flips |
| p | probability of success | 0.5 |
| ω | elementary outcome | (H,T,H,H,T) |
| X(ω) | number of Heads | X = 3 |
| Support | possible values | {0,1,2,3,4,5} |
| PMF | P(X=k) | P(X=3)=0.3125 |
| CDF | P(X≤k) | P(X≤3)=0.8125 |
| P(X≥k) | 1−P(X≤k−1) | P(X≥3)=0.5 |
| P(a≤X≤b) | P(X≤b)-P(X≤a−1) | P(2≤X≤4) |
# Problem 4 — Inclusion–Exclusion and Double Counting

## Given Data

A company surveyed **200 employees** about two software tools.

| | Count |
|---|---|
| Use Tool A | 130 |
| Use Tool B | 90 |
| Use **both** tools | 60 |
| Total employees | 200 |

**Definitions:**
- A = the employee uses Tool A
- B = the employee uses Tool B

---

## Part 1 — Basic Probabilities: P(A), P(B), P(A∩B)

$$P(A) = \frac{130}{200} = 0.65$$

$$P(B) = \frac{90}{200} = 0.45$$

$$P(A \cap B) = \frac{60}{200} = 0.30$$

**Interpretation:**
- 65% of employees use Tool A
- 45% use Tool B
- 30% use **both** tools at the same time

---

## Part 2 — Inclusion–Exclusion Formula: P(A∪B)

**The formula:**

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Why do we subtract P(A∩B)?**

If we just add P(A) + P(B):

$$0.65 + 0.45 = 1.10$$

This is **wrong** — a probability cannot be greater than 1.

The problem is **double counting**: the 60 employees who use *both* tools are included in the 130 (Tool A group) **and** in the 90 (Tool B group). So they are counted **twice**.

To fix this, we subtract their probability once:

$$P(A \cup B) = 0.65 + 0.45 - 0.30 = \boxed{0.80}$$

**Interpretation:** 80% of employees use at least one of the two tools.

---

## Part 3 — Four Disjoint Regions

The sample space can be divided into four non-overlapping regions:

### Region 1: A only (A \ B) — uses Tool A but NOT Tool B

$$P(A \setminus B) = P(A) - P(A \cap B) = 0.65 - 0.30 = \boxed{0.35}$$

→ 70 employees (35%)

### Region 2: B only (B \ A) — uses Tool B but NOT Tool A

$$P(B \setminus A) = P(B) - P(A \cap B) = 0.45 - 0.30 = \boxed{0.15}$$

→ 30 employees (15%)

### Region 3: Both (A∩B) — uses both tools

$$P(A \cap B) = \boxed{0.30}$$

→ 60 employees (30%)

### Region 4: Neither (A^c ∩ B^c) — uses neither tool

$$P(A^c \cap B^c) = 1 - P(A \cup B) = 1 - 0.80 = \boxed{0.20}$$

→ 40 employees (20%)

### Verification — the four regions must sum to 1:

$$0.35 + 0.15 + 0.30 + 0.20 = 1.00 \checkmark$$

### Venn Diagram (count view):

```
┌─────────────────────────────────────────────────────────────┐
│  Sample space — 200 employees                               │
│                                                             │
│   ╔═══════════════════╗                                     │
│   ║    Tool A         ║                                     │
│   ║    (130 total)    ║                                     │
│   ║                   ║                                     │
│   ║   A only      ╔═══╬══════════════╗                      │
│   ║   70 people   ║   ║  A ∩ B       ║  Tool B              │
│   ║   P = 0.35    ║   ║  60 people   ║  (90 total)          │
│   ║               ║   ║  P = 0.30    ║                      │
│   ║               ║   ║              ║  B only              │
│   ║               ╚═══╬══════════════╣  30 people           │
│   ╚═══════════════════╝              ║  P = 0.15            │
│                                      ╚══════════════╗        │
│                                                     │        │
│   Neither (Aᶜ ∩ Bᶜ): 40 people  —  P = 0.20        │        │
│                                                     │        │
└─────────────────────────────────────────────────────────────┘

  Check:  0.35 + 0.30 + 0.15 + 0.20 = 1.00  ✓
```

---

## Part 4 — Conditional Probabilities: P(A|B) and P(B|A)

### P(A|B) — probability of using Tool A, **given** the employee uses Tool B

$$P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{0.30}{0.45} = \boxed{0.667}$$

**In words:** Among employees who use Tool B, about **66.7%** also use Tool A.

### P(B|A) — probability of using Tool B, **given** the employee uses Tool A

$$P(B \mid A) = \frac{P(A \cap B)}{P(A)} = \frac{0.30}{0.65} = \boxed{0.462}$$

**In words:** Among employees who use Tool A, about **46.2%** also use Tool B.

### Why are they different?

P(A|B) and P(B|A) ask **different questions**:
- P(A|B): *"If I know someone uses B, what is the chance they also use A?"* → We look only at the 90 Tool B users.
- P(B|A): *"If I know someone uses A, what is the chance they also use B?"* → We look only at the 130 Tool A users.

The same 60 overlap is divided by **different group sizes** (90 vs 130), so the results differ.

---

## Part 5 — Why P(A∪B) ≠ P(A) + P(B)

**The core problem — double counting:**

When we compute P(A) + P(B), the 60 employees who use **both** tools are counted in:
- P(A): they are part of the 130 Tool A users ✓
- P(B): they are also part of the 90 Tool B users ✓

So they are added **twice**, even though they are the **same people**.

**The fix — inclusion–exclusion:**

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

By subtracting P(A∩B) once, we remove the extra count and get the correct answer.

**Numerical check:**

| Step | Value |
|---|---|
| P(A) + P(B) | 1.10 (incorrect — > 1) |
| − P(A∩B) | − 0.30 |
| **P(A∪B)** | **0.80** ✓ |

---

## Summary Table

| Probability | Formula | Value | Meaning |
|---|---|---|---|
| P(A) | 130/200 | 0.65 | Uses Tool A |
| P(B) | 90/200 | 0.45 | Uses Tool B |
| P(A∩B) | 60/200 | 0.30 | Uses both |
| P(A∪B) | 0.65+0.45−0.30 | 0.80 | Uses at least one |
| P(A\B) | 0.65−0.30 | 0.35 | Uses A only |
| P(B\A) | 0.45−0.30 | 0.15 | Uses B only |
| P(A^c∩B^c) | 1−0.80 | 0.20 | Uses neither |
| P(A\|B) | 0.30/0.45 | 0.667 | Uses A, given uses B |
| P(B\|A) | 0.30/0.65 | 0.462 | Uses B, given uses A |

---

## Key Takeaways

1. **Inclusion–exclusion** fixes the double-counting problem: always subtract the intersection when computing the union of two events.
2. **The four regions** (A only, B only, both, neither) are disjoint and always sum to 1.
3. **Conditional probabilities** P(A|B) and P(B|A) are **not equal** — they answer different questions with different reference groups.
4. **Double counting** happens when the same people belong to two groups at the same time.
# Bernoulli Distribution
## The Foundation of Probability — A Complete Guide 🎯

---

## The Simplest Question in Probability

Every day, we face yes/no questions:

- Will it rain today? ☔
- Will I pass the exam? 📝
- Will the customer buy? 💰
- Will the coin land heads? 🪙

These simple binary outcomes are the building blocks of probability theory, and they follow the **Bernoulli Distribution**.

---

## 📖 Story: Fatima's Job Interview

Meet Fatima, a software developer in Dhaka. She has a job interview tomorrow at a top tech company.

Based on her preparation, skills, and the competition, she estimates:
- **70% chance** of getting the job offer ✅
- **30% chance** of not getting it ❌

This single trial with two possible outcomes is a perfect example of a **Bernoulli trial**.

---

## What is a Bernoulli Distribution?

The Bernoulli distribution models a **single experiment** (trial) with exactly **two possible outcomes**:

| Outcome | Label | Probability |
|---------|-------|-------------|
| Success | 1 | p |
| Failure | 0 | 1 - p = q |

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   BERNOULLI DISTRIBUTION                                │
│                                                         │
│   • Single trial (one experiment)                       │
│   • Two outcomes only (success or failure)              │
│   • Probability of success = p                          │
│   • Probability of failure = 1 - p                      │
│                                                         │
│   Named after Jacob Bernoulli (1654-1705)               │
│   Swiss mathematician                                   │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## The Mathematics

### Random Variable Definition

Let X be a Bernoulli random variable:

```
X = { 1  with probability p     (Success)
    { 0  with probability 1-p   (Failure)
```

### Probability Mass Function (PMF)

```
P(X = x) = p^x × (1-p)^(1-x)    for x ∈ {0, 1}
```

**Let's verify this formula:**

| x | Calculation | Result |
|---|-------------|--------|
| x = 1 (Success) | p¹ × (1-p)⁰ = p × 1 | p ✓ |
| x = 0 (Failure) | p⁰ × (1-p)¹ = 1 × (1-p) | 1-p ✓ |

### Alternative PMF Notation

```
P(X = x) = { p      if x = 1
           { 1-p    if x = 0
           { 0      otherwise
```

---

## Visualization

### Fatima's Interview (p = 0.70)

```
Probability
     │
 0.7 ┤                              ●───────────────
     │                              │███████████████│
 0.6 ┤                              │███████████████│
     │                              │███████████████│
 0.5 ┤                              │███████████████│
     │                              │███████████████│
 0.4 ┤                              │███████████████│
     │         ●───────────────     │███████████████│
 0.3 ┤         │███████████████│    │███████████████│
     │         │███████████████│    │███████████████│
 0.2 ┤         │███████████████│    │███████████████│
     │         │███████████████│    │███████████████│
 0.1 ┤         │███████████████│    │███████████████│
     │         │███████████████│    │███████████████│
   0 ┼─────────┴───────────────┴────┴───────────────┴───
               X = 0                    X = 1
             (Failure)                (Success)
              P = 0.30                 P = 0.70
```

### Different Values of p

```
p = 0.2                    p = 0.5                    p = 0.8
(Low success)              (Fair coin)                (High success)

   │                          │                          │
0.8├●                         │                          │         ●
   ││                       0.5├●         ●            0.8├         │
   ││                          ││         │              ││         │
0.2├│         ●             0.5├│         │            0.2├●        │
   ││         │                ││         │              ││         │
 0 ┴┴─────────┴──            0 ┴┴─────────┴──          0 ┴┴─────────┴──
    0         1                 0         1               0         1
```

---

## Key Properties

### 1. Mean (Expected Value)

The average outcome you'd expect over many trials:

```
E[X] = μ = p
```

**Derivation:**
```
E[X] = Σ x × P(X = x)
E[X] = 0 × P(X=0) + 1 × P(X=1)
E[X] = 0 × (1-p) + 1 × p
E[X] = p
```

**For Fatima:** E[X] = 0.70

*Interpretation: If Fatima could repeat this interview infinitely, her average "success rate" would be 0.70*

### 2. Variance

How spread out the outcomes are from the mean:

```
Var(X) = σ² = p(1-p) = pq
```

**Derivation:**
```
Var(X) = E[X²] - (E[X])²

First, find E[X²]:
E[X²] = 0² × (1-p) + 1² × p = p

Therefore:
Var(X) = p - p²
Var(X) = p(1-p)
```

**For Fatima:** Var(X) = 0.70 × 0.30 = 0.21

### 3. Standard Deviation

```
σ = √(p(1-p)) = √(pq)
```

**For Fatima:** σ = √0.21 ≈ 0.458

### 4. Variance is Maximum at p = 0.5

```
     Variance
        │
   0.25 ┤           ●
        │         ╱   ╲
    0.2 ┤       ╱       ╲
        │     ╱           ╲
   0.15 ┤   ╱               ╲
        │ ╱                   ╲
    0.1 ┤╱                     ╲
        │                       ╲
   0.05 ┤                         ╲
        │                           ╲
      0 ●───────────────────────────●
        0    0.25   0.5   0.75     1
                    p
                    
Maximum variance = 0.25 when p = 0.5 (most uncertainty)
Variance = 0 when p = 0 or p = 1 (no uncertainty)
```

---

## Complete Properties Summary

| Property | Formula | Fatima's Example (p=0.7) |
|----------|---------|--------------------------|
| **Parameter** | p ∈ [0,1] | p = 0.70 |
| **Support** | x ∈ {0, 1} | {0, 1} |
| **PMF** | P(X=x) = p^x(1-p)^(1-x) | P(1)=0.7, P(0)=0.3 |
| **Mean** | μ = p | 0.70 |
| **Variance** | σ² = p(1-p) | 0.21 |
| **Std Dev** | σ = √(p(1-p)) | 0.458 |
| **Skewness** | (1-2p)/√(p(1-p)) | -0.873 |
| **Mode** | 1 if p>0.5, 0 if p<0.5 | 1 |

---

## Cumulative Distribution Function (CDF)

The CDF gives P(X ≤ x):

```
F(x) = P(X ≤ x) = { 0      if x < 0
                  { 1-p    if 0 ≤ x < 1
                  { 1      if x ≥ 1
```

### Visualization of CDF

```
F(x)
  │
1 ┤                    ●────────────────
  │                    │
  │                    │
1-p├────────●──────────┘
  │        │
  │        │
0 ●────────┘
  └────┬───┬───┬───┬───┬───┬───
      -1   0   1   2   3   4

Step function with jumps at x=0 and x=1
```

---

## Real-Life Bernoulli Examples

### 📖 Story 2: The Quality Inspector

Rahim is a quality inspector at a phone factory. Each phone has a **2% chance of being defective**.

For a single phone:
- X = 1 if defective (Success in this context)
- X = 0 if not defective
- p = 0.02

```
Properties:
Mean = 0.02 (on average, 2% are defective)
Variance = 0.02 × 0.98 = 0.0196
```

### 📖 Story 3: The Free Throw

Basketball player Messi takes a single free throw. His success rate is **85%**.

- X = 1 if he scores
- X = 0 if he misses
- p = 0.85

```
Properties:
Mean = 0.85
Variance = 0.85 × 0.15 = 0.1275
```

### 📖 Story 4: The Email Campaign

A marketing team sends an email. Based on history, **12% of recipients click the link**.

For a single recipient:
- X = 1 if clicks
- X = 0 if doesn't click
- p = 0.12

```
Properties:
Mean = 0.12
Variance = 0.12 × 0.88 = 0.1056
```

---

## Bernoulli in Different Fields

| Field | Bernoulli Event | p (typical) |
|-------|-----------------|-------------|
| **Medicine** | Patient responds to treatment | 0.75 |
| **Finance** | Stock goes up today | 0.52 |
| **Marketing** | Customer makes purchase | 0.03 |
| **Manufacturing** | Product is defective | 0.01 |
| **Sports** | Team wins the match | 0.60 |
| **Technology** | Server request succeeds | 0.999 |
| **Education** | Student passes exam | 0.85 |
| **Weather** | It rains tomorrow | 0.30 |

---

## Bernoulli: The Building Block

The Bernoulli distribution is the **foundation** for many other distributions:

```
                    ┌─────────────────┐
                    │    BERNOULLI    │
                    │  Single Trial   │
                    │    p, 1-p       │
                    └────────┬────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ↓                  ↓                  ↓
   ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
   │  BINOMIAL   │    │  GEOMETRIC  │    │   NEGATIVE  │
   │             │    │             │    │   BINOMIAL  │
   │ n Bernoulli │    │ Trials until│    │ Trials until│
   │   trials    │    │ 1st success │    │ k successes │
   └─────────────┘    └─────────────┘    └─────────────┘
          │
          │ n→∞, p→0, np=λ
          ↓
   ┌─────────────┐
   │   POISSON   │
   │             │
   │ Rare events │
   └─────────────┘
```

### Key Relationships

| Distribution | Relationship to Bernoulli |
|--------------|--------------------------|
| **Binomial(n, p)** | Sum of n independent Bernoulli(p) trials |
| **Geometric(p)** | Number of Bernoulli trials until first success |
| **Negative Binomial(k, p)** | Number of trials until k successes |

---

## Mathematical Properties

### 1. Moment Generating Function (MGF)

```
M_X(t) = E[e^(tX)]
M_X(t) = e^(t×0) × (1-p) + e^(t×1) × p
M_X(t) = (1-p) + p×e^t
M_X(t) = 1 - p + p×e^t
```

### 2. Characteristic Function

```
φ_X(t) = (1-p) + p×e^(it)
```

### 3. Entropy

```
H(X) = -p×log(p) - (1-p)×log(1-p)
```

Maximum entropy at p = 0.5 (most uncertainty)

```
Entropy
   │
   │        ●
0.69├      ╱ ╲
   │    ╱     ╲
0.5├  ╱         ╲
   │╱             ╲
 0 ●───────────────●
   0     0.5      1
         p
```

### 4. Odds Ratio

```
Odds = p / (1-p)

If p = 0.70:
Odds = 0.70 / 0.30 = 2.33

"The odds of success are 2.33 to 1"
(or "7 to 3")
```

---

## Bernoulli in Code

### Python Implementation

```python
import numpy as np
from scipy import stats

# Define Bernoulli distribution with p = 0.7
p = 0.7
bernoulli = stats.bernoulli(p)

# PMF
print(f"P(X=0) = {bernoulli.pmf(0)}")  # 0.3
print(f"P(X=1) = {bernoulli.pmf(1)}")  # 0.7

# Mean and Variance
print(f"Mean = {bernoulli.mean()}")      # 0.7
print(f"Variance = {bernoulli.var()}")   # 0.21

# Generate random samples
samples = bernoulli.rvs(size=1000)
print(f"Sample mean = {samples.mean()}")  # ≈ 0.7

# Simulate Fatima's interview
result = bernoulli.rvs()
print("Got the job!" if result == 1 else "Keep trying!")
```

### Simple Simulation

```python
import random

def bernoulli_trial(p):
    """Single Bernoulli trial"""
    return 1 if random.random() < p else 0

# Fatima's interview simulation (1000 times)
p = 0.70
results = [bernoulli_trial(p) for _ in range(1000)]

successes = sum(results)
print(f"Successes: {successes}/1000 = {successes/1000:.1%}")
# Should be approximately 70%
```

---

## Indicator Random Variables

Bernoulli random variables are also called **indicator variables** because they "indicate" whether an event occurred:

```
I_A = { 1  if event A occurs
      { 0  if event A does not occur

Then: P(I_A = 1) = P(A)
```

### Useful Property

For any event A:
```
E[I_A] = P(A)
```

This makes calculating probabilities elegant!

### Example: Counting with Indicators

**Problem:** 5 coins are flipped. What's the expected number of heads?

**Solution using indicators:**
```
Let I₁, I₂, I₃, I₄, I₅ be indicators for each coin

X = I₁ + I₂ + I₃ + I₄ + I₅  (total heads)

E[X] = E[I₁] + E[I₂] + E[I₃] + E[I₄] + E[I₅]
E[X] = 0.5 + 0.5 + 0.5 + 0.5 + 0.5
E[X] = 2.5 heads
```

---

## Bernoulli Process

When you repeat independent Bernoulli trials over time, you get a **Bernoulli Process**:

```
Trial:    1    2    3    4    5    6    7    8    9   10
Result:   1    0    1    1    0    0    1    0    1    1
          ↑         ↑    ↑              ↑         ↑    ↑
        Success   Success           Success    Successes

Each trial is independent with same probability p
```

### Properties of Bernoulli Process

1. Each trial has same probability p
2. Trials are independent
3. Only two outcomes per trial
4. Leads to Binomial distribution (count in n trials)
5. Leads to Geometric distribution (time to first success)

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Assuming Independence

❌ **Wrong:** "If I failed the last 5 interviews, I'm 'due' for success"

✅ **Correct:** Each Bernoulli trial is independent — past failures don't change future probability

### Mistake 2: Confusing p with Outcome

❌ **Wrong:** "p = 0.7 means I'll definitely succeed"

✅ **Correct:** p = 0.7 means 70% chance — failure (30%) is still very possible!

### Mistake 3: Multiple Trials = Bernoulli

❌ **Wrong:** Using Bernoulli for "number of heads in 10 flips"

✅ **Correct:** Use Binomial for multiple trials; Bernoulli is for a SINGLE trial

---

## Practice Problems 📝

### Problem 1: Basic PMF
A light bulb has a 5% chance of being defective. What is P(X = 0) and P(X = 1)?

<details>
<summary>Click for Answer</summary>

```
p = 0.05 (probability of defective)

P(X = 1) = p = 0.05 (defective)
P(X = 0) = 1 - p = 0.95 (not defective)
```

</details>

### Problem 2: Calculate Mean and Variance
A coin is biased with P(Heads) = 0.6. Find the mean and variance.

<details>
<summary>Click for Answer</summary>

```
p = 0.6

Mean = p = 0.6

Variance = p(1-p) = 0.6 × 0.4 = 0.24

Standard Deviation = √0.24 ≈ 0.49
```

</details>

### Problem 3: Which p gives Maximum Variance?
For what value of p is the variance of a Bernoulli distribution maximized?

<details>
<summary>Click for Answer</summary>

```
Variance = p(1-p)

To find maximum, take derivative and set to 0:
d/dp [p(1-p)] = 1 - 2p = 0
p = 0.5

Maximum variance = 0.5 × 0.5 = 0.25

This makes sense: most uncertainty when success 
and failure are equally likely!
```

</details>

### Problem 4: Odds Calculation
A weather forecast says 80% chance of rain. What are the odds of rain?

<details>
<summary>Click for Answer</summary>

```
p = 0.80

Odds = p / (1-p) = 0.80 / 0.20 = 4

"The odds of rain are 4 to 1"
(or equivalently, "4:1 in favor of rain")
```

</details>

### Problem 5: Multiple Independent Events
Two independent machines each have 95% reliability (working). What's the probability both work?

<details>
<summary>Click for Answer</summary>

```
Machine 1: X₁ ~ Bernoulli(0.95)
Machine 2: X₂ ~ Bernoulli(0.95)

Since independent:
P(Both work) = P(X₁=1) × P(X₂=1)
P(Both work) = 0.95 × 0.95
P(Both work) = 0.9025 or 90.25%
```

</details>

---

## When to Use Bernoulli Distribution

### ✅ Use Bernoulli When:

- There is only **ONE trial**
- There are exactly **TWO outcomes** (success/failure)
- You need to model a **single binary event**
- You're building up to more complex distributions

### ❌ Don't Use Bernoulli When:

- You have **multiple trials** → Use Binomial
- You're counting **events over time** → Use Poisson
- Outcomes are **not binary** → Use Categorical/Multinomial
- You need **time until success** → Use Geometric

---

## Bernoulli in Machine Learning

The Bernoulli distribution appears everywhere in ML:

| Application | How Bernoulli is Used |
|-------------|----------------------|
| **Logistic Regression** | Models binary outcomes with Bernoulli |
| **Neural Networks** | Dropout uses Bernoulli to randomly disable neurons |
| **Naive Bayes** | Bernoulli NB for binary features |
| **A/B Testing** | Each user's conversion is Bernoulli |
| **Recommender Systems** | Click/no-click is Bernoulli |

---

## Summary: The Essence of Bernoulli

```
┌─────────────────────────────────────────────────────────────┐
│                    BERNOULLI DISTRIBUTION                    │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  "The simplest probability distribution"                     │
│                                                              │
│  • ONE trial, TWO outcomes                                   │
│  • Success (1) with probability p                            │
│  • Failure (0) with probability 1-p                          │
│                                                              │
│  ┌─────────────────────────────────────┐                    │
│  │  Mean     = p                       │                    │
│  │  Variance = p(1-p)                  │                    │
│  │  Max variance when p = 0.5          │                    │
│  └─────────────────────────────────────┘                    │
│                                                              │
│  Foundation for: Binomial, Geometric, Negative Binomial     │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## The Beautiful Simplicity

> **The Bernoulli distribution captures the most fundamental uncertainty: "Will it happen or not?"**

From this simple question, an entire world of probability theory emerges. Every complex distribution, every machine learning model dealing with binary outcomes, every statistical test — they all trace back to this elegant, simple distribution.

Master Bernoulli, and you've taken the first step into the vast world of probability! 🚀

---

*Simple? Yes. Fundamental? Absolutely. Powerful? Beyond measure.* ✨
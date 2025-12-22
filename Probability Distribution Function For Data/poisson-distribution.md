# Poisson Distribution
## Counting Random Events — A Complete Guide 🎯

---

## The Big Question

Some events happen randomly over time or space:

- How many customers will arrive at a shop in the next hour?
- How many emails will you receive today?
- How many typos are on this page?
- How many cars will pass this intersection in 10 minutes?

These questions are answered by the **Poisson Distribution** — named after French mathematician Siméon Denis Poisson (1781-1840).

---

## 📖 Story: Rashida's Call Center

Meet Rashida, who manages a call center in Dhaka. Based on historical data, the center receives an average of **5 calls per minute**.

**The Questions:**
- What's the probability of receiving exactly 3 calls in the next minute?
- What's the probability of receiving no calls?
- What's the probability of receiving more than 7 calls?

This is a perfect **Poisson** scenario!

---

## What is the Poisson Distribution?

The Poisson distribution models the **number of events** occurring in a **fixed interval** of time or space, when events happen:

- **Independently** of each other
- At a **constant average rate**
- **Randomly** (not in clusters)

```
┌─────────────────────────────────────────────────────────────┐
│                    POISSON DISTRIBUTION                      │
│                                                              │
│   "How many events in a fixed interval?"                     │
│                                                              │
│   Requirements:                                              │
│   ✓ Events occur independently                               │
│   ✓ Events occur at a constant average rate (λ)              │
│   ✓ Two events cannot occur at exactly the same instant      │
│   ✓ The probability of an event is proportional to           │
│     the length of the interval                               │
│                                                              │
│   Named after Siméon Denis Poisson (1781-1840)               │
│   French mathematician                                       │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## The Single Parameter: λ (Lambda)

The Poisson distribution has just **one parameter**:

| Parameter | Symbol | Meaning | Example |
|-----------|--------|---------|---------|
| Rate | λ (lambda) | Average number of events per interval | 5 calls/minute |

**Notation:** X ~ Poisson(λ) or X ~ Pois(λ)

For Rashida: X ~ Poisson(5)

---

## The Poisson Formula

### Probability Mass Function (PMF)

```
P(X = k) = (λ^k × e^(-λ)) / k!
```

Where:
- **k** = number of events (0, 1, 2, 3, ...)
- **λ** = average rate (expected number of events)
- **e** ≈ 2.71828 (Euler's number)
- **k!** = k factorial (k × (k-1) × ... × 2 × 1)

---

## Solving Rashida's Problems Step by Step

**Given:** λ = 5 calls per minute

### Problem 1: P(exactly 3 calls)

```
P(X = 3) = (5³ × e^(-5)) / 3!
         = (125 × 0.00674) / 6
         = 0.8425 / 6
         = 0.1404 or about 14%
```

### Problem 2: P(no calls)

```
P(X = 0) = (5⁰ × e^(-5)) / 0!
         = (1 × 0.00674) / 1
         = 0.00674 or about 0.67%
```

*Very unlikely to have a minute with no calls!*

### Problem 3: P(more than 7 calls)

```
P(X > 7) = 1 - P(X ≤ 7)
         = 1 - [P(X=0) + P(X=1) + ... + P(X=7)]
         = 1 - 0.8666
         = 0.1334 or about 13.3%
```

---

## Why Does the Formula Work?

The Poisson distribution arises from the **Binomial distribution** when:
- n (number of trials) → ∞
- p (probability per trial) → 0
- np = λ (stays constant)

### Intuition

Divide 1 minute into 1000 tiny intervals:
- Each interval: very small chance of a call
- n = 1000 intervals
- p = 5/1000 = 0.005 chance per interval
- λ = np = 5

As we make intervals smaller and smaller, Binomial → Poisson!

```
Binomial(n, p) ──────────────────→ Poisson(λ)
               n→∞, p→0, np=λ
```

---

## Visualization

### Rashida's Call Center (λ = 5)

```
P(X=k)
   │
   │        ●
0.18├       ●●
   │      ●  ●
0.14├     ●    ●
   │    ●      ●
0.10├   ●        ●
   │  ●          ●
0.06├ ●            ●
   │●              ●
0.02├                ●  ●
   │                    ●  ●  ●
   0┼─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─
     0 1 2 3 4 5 6 7 8 9 10 11 12 13
              Number of Calls (k)
              
Peak is at k = 4 or 5 (near λ)
```

### Probability Table for λ = 5

| k (calls) | P(X = k) | Cumulative P(X ≤ k) |
|-----------|----------|---------------------|
| 0 | 0.0067 | 0.0067 |
| 1 | 0.0337 | 0.0404 |
| 2 | 0.0842 | 0.1247 |
| 3 | 0.1404 | 0.2650 |
| 4 | 0.1755 | 0.4405 |
| 5 | **0.1755** | 0.6160 |
| 6 | 0.1462 | 0.7622 |
| 7 | 0.1044 | 0.8666 |
| 8 | 0.0653 | 0.9319 |
| 9 | 0.0363 | 0.9682 |
| 10 | 0.0181 | 0.9863 |

---

## How Shape Changes with λ

```
λ = 1 (Low)                λ = 5 (Medium)             λ = 10 (High)

   │                          │                          │
   │●                         │      ●●                  │         ●●
   │ ●                        │     ●  ●                 │       ●●  ●●
   │  ●                       │    ●    ●                │      ●      ●
   │   ●                      │   ●      ●               │     ●        ●
   │    ●                     │  ●        ●              │    ●          ●
   │     ●●                   │ ●          ●             │  ●            ●
   │       ●●●                │●            ●●           │ ●              ●●
   └──────────────            └──────────────            └──────────────────
   0 1 2 3 4 5 6              0 2 4 6 8 10               0 4 8 12 16 20

   Highly skewed right       Slightly skewed            Nearly symmetric
   (most values are small)   (moderate spread)          (looks like Normal)
```

**Key Insight:** As λ increases, Poisson approaches Normal distribution!

---

## Key Properties

### 1. Mean (Expected Value)

```
E[X] = μ = λ
```

**For Rashida:** E[X] = 5 calls per minute

*The mean equals the rate parameter — beautiful simplicity!*

### 2. Variance

```
Var(X) = σ² = λ
```

**For Rashida:** Var(X) = 5

### 3. Standard Deviation

```
σ = √λ
```

**For Rashida:** σ = √5 ≈ 2.24 calls

### ⭐ Special Property: Mean = Variance!

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   In Poisson distribution:  E[X] = Var(X) = λ          │
│                                                         │
│   This is a unique "fingerprint" of Poisson!            │
│   If your data has Mean ≈ Variance, consider Poisson.   │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### 4. Mode (Most Likely Value)

```
Mode = ⌊λ⌋  (floor of λ)

If λ is an integer, both λ and λ-1 are modes.
```

**For Rashida:** Mode = 4 and 5 (λ = 5 is integer, so bimodal)

---

## Properties Summary Table

| Property | Formula | Rashida (λ = 5) |
|----------|---------|-----------------|
| **Parameter** | λ > 0 | 5 |
| **Support** | k ∈ {0, 1, 2, ...} | {0, 1, 2, ...} |
| **Mean** | λ | 5 |
| **Variance** | λ | 5 |
| **Std Dev** | √λ | 2.24 |
| **Skewness** | 1/√λ | 0.447 |
| **Mode** | ⌊λ⌋ | 4 and 5 |

---

## Scaling the Interval

One powerful property: You can **scale λ** for different intervals!

### Example: Rashida's Call Center

If λ = 5 calls per **minute**, then:

| Interval | New λ | Calculation |
|----------|-------|-------------|
| 30 seconds | 2.5 | 5 × 0.5 |
| 2 minutes | 10 | 5 × 2 |
| 5 minutes | 25 | 5 × 5 |
| 1 hour | 300 | 5 × 60 |

### Problem: P(exactly 15 calls in 3 minutes)?

```
λ for 3 minutes = 5 × 3 = 15

P(X = 15) = (15^15 × e^(-15)) / 15!
          ≈ 0.1024 or about 10.2%
```

---

## Real-Life Poisson Examples

### 📖 Story 2: The Typo Counter

A publisher knows that a typical book has an average of **2 typos per page**.

**Question:** What's the probability a page has no typos?

```
λ = 2 typos per page

P(X = 0) = (2⁰ × e^(-2)) / 0!
         = e^(-2)
         = 0.1353 or about 13.5%
```

*About 1 in 7 pages will be typo-free!*

---

### 📖 Story 3: The Hospital Emergency Room

An ER receives an average of **8 patients per hour** during night shift.

**Question:** What's the probability of receiving 10 or more patients in an hour?

```
λ = 8 patients/hour

P(X ≥ 10) = 1 - P(X ≤ 9)
          = 1 - 0.7166
          = 0.2834 or about 28.3%
```

---

### 📖 Story 4: The Website Traffic

A website gets an average of **100 visitors per hour**.

**Question:** What's the probability of getting exactly 90 visitors in the next hour?

```
λ = 100 visitors/hour

P(X = 90) = (100^90 × e^(-100)) / 90!
          ≈ 0.0250 or about 2.5%
```

---

### 📖 Story 5: Radioactive Decay

A radioactive sample emits an average of **4 particles per second**.

**Question:** What's the probability of exactly 6 emissions in one second?

```
λ = 4 particles/second

P(X = 6) = (4^6 × e^(-4)) / 6!
         = (4096 × 0.0183) / 720
         = 0.1042 or about 10.4%
```

---

## Poisson in Different Fields

| Field | Event | λ (typical) |
|-------|-------|-------------|
| **Telecommunications** | Calls per minute | 5-50 |
| **Healthcare** | ER admissions per hour | 3-15 |
| **Transportation** | Accidents per day | 2-10 |
| **Nature** | Earthquakes per year | 10-20 |
| **Technology** | Server requests per second | 100-10000 |
| **Biology** | Mutations per DNA strand | 0.5-5 |
| **Finance** | Market crashes per decade | 1-3 |
| **Quality Control** | Defects per unit | 0.1-5 |
| **Astronomy** | Meteor strikes per hour | 1-10 |
| **Customer Service** | Complaints per day | 5-20 |

---

## Poisson vs Binomial: When to Use Which?

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   BINOMIAL                          POISSON                     │
│   ─────────                         ───────                     │
│   • Fixed number of trials (n)      • Events in continuous      │
│   • Success/failure per trial         time or space             │
│   • Counting successes              • Counting occurrences      │
│   • p is known and moderate         • Only λ (rate) is known    │
│                                                                 │
│   "Out of n trials, how many        "How many events in this    │
│    successes?"                       time/space interval?"      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Quick Decision Guide

| Question Type | Distribution |
|---------------|--------------|
| "How many heads in 10 flips?" | Binomial |
| "How many customers this hour?" | Poisson |
| "How many defectives in 100 items?" | Binomial |
| "How many typos on this page?" | Poisson |
| "How many correct in 20 questions?" | Binomial |
| "How many emails today?" | Poisson |

---

## The Poisson-Binomial Connection

Poisson is the **limit of Binomial** when n → ∞ and p → 0:

```
Binomial(n, p)  ────────────────→  Poisson(λ = np)
                n→∞, p→0, np=λ
```

### Rule of Thumb for Approximation

Use Poisson to approximate Binomial when:
```
n ≥ 20  AND  p ≤ 0.05  AND  np ≤ 10
```

### Example: Rare Disease

In a city of 100,000 people, a rare disease affects 0.001% of the population.

```
Binomial: n = 100,000, p = 0.00001
Poisson approximation: λ = np = 1

P(X = 0) using Poisson = e^(-1) = 0.368
P(X = 0) using Binomial = (0.99999)^100000 ≈ 0.368

Both give the same answer!
```

---

## Normal Approximation to Poisson

When λ is large (λ ≥ 20), Poisson approaches Normal!

```
Poisson(λ)  ────────────→  Normal(μ = λ, σ² = λ)
            λ → large
```

### Example: Website Traffic

λ = 100 visitors per hour

```
Approximate: X ~ Normal(μ = 100, σ = 10)

P(X > 115) ≈ P(Z > (115-100)/10) = P(Z > 1.5) = 0.0668
```

### Visual Comparison

```
           Poisson (λ=25)                 Normal Approximation
           
P(X)              │                              │
                  │       ▄▄▄▄                   │       ╭──╮
                  │     ▄██████▄                 │     ╭─╯  ╰─╮
                  │   ▄██████████▄               │   ╭─╯      ╰─╮
                  │ ▄██████████████▄             │ ╭─╯          ╰─╮
                  └────────────────────          └────────────────────
                          25                              25
                          
Almost identical for large λ!
```

---

## Relationship to Other Distributions

```
                    ┌─────────────────┐
                    │    BINOMIAL     │
                    │   n large,      │
                    │   p small       │
                    └────────┬────────┘
                             │ np = λ
                             ↓
                    ┌─────────────────┐
                    │     POISSON     │◄─── YOU ARE HERE
                    │    Pois(λ)      │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ↓                   ↓                   ↓
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│     NORMAL      │ │   EXPONENTIAL   │ │      GAMMA      │
│   (large λ)     │ │  (time between  │ │   (time until   │
│                 │ │   events)       │ │   k events)     │
└─────────────────┘ └─────────────────┘ └─────────────────┘
```

### Poisson ↔ Exponential Connection

| Poisson | Exponential |
|---------|-------------|
| **Counts** events in interval | **Time** between events |
| Discrete (0, 1, 2, ...) | Continuous (0 to ∞) |
| λ = rate per interval | Same λ parameter |
| "How many in 1 hour?" | "How long until next one?" |

If arrivals follow Poisson(λ), then time between arrivals follows Exponential(λ)!

---

## Sum of Poisson Random Variables

If X ~ Poisson(λ₁) and Y ~ Poisson(λ₂) are independent:

```
X + Y ~ Poisson(λ₁ + λ₂)
```

### Example

- Store A: 3 customers per hour
- Store B: 7 customers per hour

Combined: 3 + 7 = **10 customers per hour** (still Poisson!)

---

## Compound Poisson Process

Sometimes events come with different "sizes":

```
Total = Σ (Size of event i)  for i = 1 to N

Where N ~ Poisson(λ)
```

### Example: Insurance Claims

- Claims arrive at rate λ = 5 per day
- Each claim has random size

Total claims in a day = Sum of N random sizes, where N ~ Poisson(5)

---

## Mathematical Properties

### Moment Generating Function (MGF)

```
M_X(t) = E[e^(tX)] = e^(λ(e^t - 1))
```

### Probability Generating Function (PGF)

```
G_X(s) = E[s^X] = e^(λ(s - 1))
```

### Characteristic Function

```
φ_X(t) = e^(λ(e^(it) - 1))
```

### Moments

```
E[X] = λ
E[X²] = λ + λ²
E[X³] = λ + 3λ² + λ³
```

---

## Python Implementation

### Using SciPy

```python
from scipy import stats
import numpy as np

# Define Poisson distribution: λ = 5
lam = 5
poisson = stats.poisson(lam)

# Probability of exactly 3 events
print(f"P(X = 3) = {poisson.pmf(3):.4f}")  # 0.1404

# Probability of at most 4 events
print(f"P(X ≤ 4) = {poisson.cdf(4):.4f}")  # 0.4405

# Probability of more than 7 events
print(f"P(X > 7) = {1 - poisson.cdf(7):.4f}")  # 0.1334

# Mean and variance
print(f"Mean = {poisson.mean()}")      # 5.0
print(f"Variance = {poisson.var()}")   # 5.0

# Generate random samples
samples = poisson.rvs(size=1000)
print(f"Sample mean = {samples.mean():.2f}")  # ≈ 5.0
```

### Manual Calculation

```python
import math

def poisson_pmf(lam, k):
    """Calculate P(X = k) for Poisson(λ)"""
    return (lam ** k) * math.exp(-lam) / math.factorial(k)

# Rashida's call center
lam = 5
for k in range(15):
    prob = poisson_pmf(lam, k)
    print(f"P(X = {k:2d}) = {prob:.4f}")
```

### Simulation

```python
import random
import math

def simulate_poisson(lam, n_simulations=10000):
    """Simulate Poisson using inverse transform"""
    results = []
    for _ in range(n_simulations):
        # Count events until cumulative prob exceeds random uniform
        L = math.exp(-lam)
        k = 0
        p = 1.0
        while p > L:
            k += 1
            p *= random.random()
        results.append(k - 1)
    return results

# Simulate
results = simulate_poisson(5, 10000)
print(f"Simulated mean: {sum(results)/len(results):.2f}")  # ≈ 5.0
print(f"Simulated variance: {np.var(results):.2f}")        # ≈ 5.0
```

---

## Visualizing Poisson

```python
import matplotlib.pyplot as plt
from scipy import stats
import numpy as np

# Different λ values
lambdas = [1, 5, 10, 20]
fig, axes = plt.subplots(2, 2, figsize=(12, 10))

for ax, lam in zip(axes.flatten(), lambdas):
    x = np.arange(0, lam + 4*np.sqrt(lam))
    poisson = stats.poisson(lam)
    probs = poisson.pmf(x)
    
    ax.bar(x, probs, color='steelblue', edgecolor='black')
    ax.axvline(x=lam, color='red', linestyle='--', label=f'λ = {lam}')
    ax.set_xlabel('k')
    ax.set_ylabel('P(X = k)')
    ax.set_title(f'Poisson(λ = {lam})')
    ax.legend()

plt.tight_layout()
plt.show()
```

---

## Testing for Poisson Distribution

### Dispersion Test

Check if Mean ≈ Variance:

```
Dispersion Index = Variance / Mean

If ≈ 1 → Likely Poisson
If > 1 → Overdispersed (try Negative Binomial)
If < 1 → Underdispersed (try Binomial)
```

### Chi-Square Goodness of Fit

```python
from scipy import stats

# Observed data
observed = [10, 25, 30, 20, 10, 5]  # frequencies for k=0,1,2,3,4,5+
n = sum(observed)
mean = sum(k * f for k, f in enumerate(observed)) / n

# Expected under Poisson(mean)
poisson = stats.poisson(mean)
expected = [n * poisson.pmf(k) for k in range(5)]
expected.append(n * (1 - poisson.cdf(4)))  # P(X ≥ 5)

# Chi-square test
chi2, p_value = stats.chisquare(observed, expected)
print(f"Chi-square: {chi2:.2f}, p-value: {p_value:.4f}")
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Events Not Independent

❌ **Wrong:** "Number of accidents on icy vs normal days"
→ Rate changes with conditions, not constant!

✅ **Correct:** Same rate λ throughout the interval

---

### Mistake 2: Events Can Cluster

❌ **Wrong:** "Earthquake aftershocks" 
→ Aftershocks cluster after main quake

✅ **Correct:** Events occur randomly, not in bursts

---

### Mistake 3: Using Wrong λ for Different Intervals

❌ **Wrong:** λ = 5 per hour, asking P(X = 3) in 30 minutes using λ = 5

✅ **Correct:** Scale λ = 5 × 0.5 = 2.5 for 30 minutes

---

### Mistake 4: Bounded Counts

❌ **Wrong:** "Number of heads in 10 flips" (max is 10)
→ Poisson has no upper bound!

✅ **Correct:** Use Binomial when there's a maximum

---

## When to Use vs. Not Use Poisson

### ✅ Use Poisson When:

- Counting events in continuous time/space
- Events are independent
- Constant average rate
- No theoretical upper bound
- Rare events over many opportunities

### ❌ Don't Use Poisson When:

| Situation | Use Instead |
|-----------|-------------|
| Fixed number of trials | Binomial |
| Rate varies with conditions | Mixed models |
| Events cluster | Negative Binomial |
| Time between events | Exponential |
| Overdispersed data | Negative Binomial |

---

## Practice Problems 📝

### Problem 1: Basic Probability
A bakery sells an average of 4 cakes per hour. What's the probability of selling exactly 6 cakes in an hour?

<details>
<summary>Click for Answer</summary>

```
λ = 4 cakes/hour, k = 6

P(X = 6) = (4^6 × e^(-4)) / 6!
         = (4096 × 0.0183) / 720
         = 0.1042 or about 10.4%
```

</details>

---

### Problem 2: Scaling the Interval
Using the same bakery (4 cakes/hour), what's the probability of selling no cakes in 30 minutes?

<details>
<summary>Click for Answer</summary>

```
For 30 minutes: λ = 4 × 0.5 = 2

P(X = 0) = (2^0 × e^(-2)) / 0!
         = e^(-2)
         = 0.1353 or about 13.5%
```

</details>

---

### Problem 3: At Least Probability
A website receives 3 errors per day on average. What's the probability of at least 1 error tomorrow?

<details>
<summary>Click for Answer</summary>

```
λ = 3 errors/day

P(X ≥ 1) = 1 - P(X = 0)
         = 1 - e^(-3)
         = 1 - 0.0498
         = 0.9502 or about 95%
```

*Almost certain to have at least one error!*

</details>

---

### Problem 4: Mean = Variance Check
Data shows: Mean = 7.2, Variance = 7.5. Is Poisson appropriate?

<details>
<summary>Click for Answer</summary>

```
Dispersion Index = Variance / Mean = 7.5 / 7.2 = 1.04

Since this is very close to 1, Poisson is appropriate!

(If it were much greater than 1, we'd consider 
Negative Binomial instead)
```

</details>

---

### Problem 5: Combining Rates
Store A gets 2 customers/hour, Store B gets 5 customers/hour. What's the probability the combined stores get exactly 10 customers in an hour?

<details>
<summary>Click for Answer</summary>

```
Combined λ = 2 + 5 = 7 customers/hour

P(X = 10) = (7^10 × e^(-7)) / 10!
          = (282475249 × 0.000912) / 3628800
          = 0.0710 or about 7.1%
```

</details>

---

## Applications in Data Science

### 1. A/B Testing

Modeling rare conversion events:
```
Clicks ~ Poisson(λ)
```

### 2. Anomaly Detection

If normal traffic is Poisson(λ), flag when observed count is extremely high:
```
Flag if X > λ + 3√λ  (beyond 3 standard deviations)
```

### 3. Queueing Theory

Customer arrivals often modeled as Poisson:
```
Arrivals ~ Poisson(λ)
Service times ~ Exponential(μ)
```

### 4. Text Analysis

Word frequencies in documents:
```
Rare word occurrences ~ Poisson
```

### 5. Insurance

Claim counts per policy:
```
Claims ~ Poisson(λ)
```

---

## Summary: The Essence of Poisson

```
┌─────────────────────────────────────────────────────────────────┐
│                      POISSON DISTRIBUTION                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "Count random events in a fixed interval"                     │
│                                                                  │
│   Requirements:                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │ • Events occur independently                             │   │
│   │ • Constant average rate (λ)                              │   │
│   │ • Events can't occur simultaneously                      │   │
│   │ • No upper bound on count                                │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Formula:  P(X = k) = (λ^k × e^(-λ)) / k!                      │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  Mean     = λ                                            │   │
│   │  Variance = λ           ← SAME! Unique property         │   │
│   │  Std Dev  = √λ                                           │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Key Relationships:                                             │
│   • Limit of Binomial (n→∞, p→0, np=λ)                          │
│   • Approximates Normal for large λ                              │
│   • Connected to Exponential (time between events)               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Poisson Matters

The Poisson distribution models **rare, random events** — which happen everywhere:

| Domain | Poisson Models... |
|--------|-------------------|
| **Business** | Customer arrivals, sales, complaints |
| **Technology** | Server requests, system failures, bugs |
| **Healthcare** | Disease cases, ER arrivals, mutations |
| **Transportation** | Accidents, vehicle arrivals |
| **Nature** | Earthquakes, meteor strikes, species counts |
| **Finance** | Market events, insurance claims |

> **The Poisson distribution answers: "How many random events will occur in this interval?"**

Named after a French mathematician over 200 years ago, it remains one of the most practical and widely-used distributions in modern data science! 🚀

---

*When events are random, independent, and constant in rate — Poisson is your friend!* ✨
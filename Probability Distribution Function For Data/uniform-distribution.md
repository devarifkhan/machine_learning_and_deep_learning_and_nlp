# Uniform Distribution
## When Every Outcome is Equally Likely 🎲

---

## The Essence of Fairness

What do these have in common?

- Rolling a fair die 🎲
- Spinning a wheel of fortune 🎡
- Random number generators 💻
- Waiting for a bus that arrives "sometime in the next 10 minutes" 🚌

They all follow the **Uniform Distribution** — where every outcome has an **equal chance** of occurring!

---

## 📖 Story: The Fair Lottery

The Bangladesh government runs a lottery. Numbers 1 through 100 are in a drum, and one is drawn randomly.

**Question:** What's the probability of drawing number 42?

Since every number has an **equal chance**:

```
P(X = 42) = 1/100 = 0.01 = 1%
```

This is the **Discrete Uniform Distribution** in action!

---

## Two Types of Uniform Distribution

```
┌─────────────────────────────────────────────────────────────┐
│                   UNIFORM DISTRIBUTION                       │
│                                                              │
│         "Every outcome is equally likely"                    │
│                                                              │
├─────────────────────────┬───────────────────────────────────┤
│                         │                                    │
│   DISCRETE UNIFORM      │      CONTINUOUS UNIFORM            │
│                         │                                    │
│   • Countable outcomes  │   • Infinite outcomes in range     │
│   • Rolling dice        │   • Random decimals                │
│   • Lottery numbers     │   • Arrival times                  │
│   • Card draws          │   • Measurement errors             │
│                         │                                    │
│   X ∈ {1, 2, 3, ..., n} │   X ∈ [a, b]                       │
│                         │                                    │
└─────────────────────────┴───────────────────────────────────┘
```

---

# Part 1: Discrete Uniform Distribution
## *Countable, Equal Probabilities*

---

## Definition

A discrete random variable X follows a **Discrete Uniform Distribution** if it takes values from a finite set {a, a+1, a+2, ..., b} with **equal probability**.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              DISCRETE UNIFORM DISTRIBUTION                   │
│                                                             │
│   Parameters:                                               │
│   • a = minimum value                                       │
│   • b = maximum value                                       │
│   • n = b - a + 1 (number of possible values)               │
│                                                             │
│   Notation: X ~ DU(a, b) or X ~ DiscreteUniform(a, b)       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The PMF (Probability Mass Function)

```
P(X = k) = 1/n = 1/(b - a + 1)    for k ∈ {a, a+1, ..., b}
```

Every value has the **same probability**: 1/n

### Example: Rolling a Fair Die

```
a = 1, b = 6, n = 6

P(X = k) = 1/6 ≈ 0.1667    for k ∈ {1, 2, 3, 4, 5, 6}
```

---

## Visualization: Discrete Uniform

### Fair Die (n = 6)

```
P(X = k)
    │
1/6 ├───●─────●─────●─────●─────●─────●───
    │   │     │     │     │     │     │
    │   │     │     │     │     │     │
    │   │     │     │     │     │     │
    │   │     │     │     │     │     │
  0 ┼───┴─────┴─────┴─────┴─────┴─────┴───
        1     2     3     4     5     6
                    Outcome
                    
All bars have EQUAL height = 1/6
```

### Lottery (n = 100)

```
P(X = k)
    │
1/100├──●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●──
    │  ││││││││││││││││││││││││││││││││││││││││││││││││││││
    │  ││││││││││││││││││││││││││││││││││││││││││││││││││││
  0 ┼──┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴──
       1  10  20  30  40  50  60  70  80  90  100
                      Lottery Number
                      
Each number has probability 1/100 = 1%
```

---

## Key Properties: Discrete Uniform

### 1. Mean (Expected Value)

```
E[X] = (a + b) / 2
```

The mean is simply the **midpoint** of the range!

**For a die:** E[X] = (1 + 6) / 2 = 3.5

### 2. Variance

```
Var(X) = ((b - a + 1)² - 1) / 12 = (n² - 1) / 12
```

**For a die:** Var(X) = (6² - 1) / 12 = 35/12 ≈ 2.917

### 3. Standard Deviation

```
σ = √(Var(X)) = √((n² - 1) / 12)
```

**For a die:** σ = √2.917 ≈ 1.708

---

## Properties Summary: Discrete Uniform

| Property | Formula | Die Example (1 to 6) |
|----------|---------|---------------------|
| **Parameters** | a, b | 1, 6 |
| **Number of values** | n = b - a + 1 | 6 |
| **PMF** | P(X=k) = 1/n | 1/6 |
| **Mean** | (a + b) / 2 | 3.5 |
| **Variance** | (n² - 1) / 12 | 2.917 |
| **Std Dev** | √((n² - 1) / 12) | 1.708 |
| **Median** | (a + b) / 2 | 3.5 |
| **Mode** | All values | All (1-6) |

---

## CDF: Discrete Uniform

The Cumulative Distribution Function:

```
F(x) = P(X ≤ x) = (⌊x⌋ - a + 1) / n    for a ≤ x ≤ b
```

### For a Die:

| x | F(x) = P(X ≤ x) |
|---|-----------------|
| 1 | 1/6 = 0.167 |
| 2 | 2/6 = 0.333 |
| 3 | 3/6 = 0.500 |
| 4 | 4/6 = 0.667 |
| 5 | 5/6 = 0.833 |
| 6 | 6/6 = 1.000 |

### Visualization: CDF

```
F(x)
  │
1 ┤                              ●────
  │                         ●────╯
5/6├                    ●────╯
  │               ●────╯
4/6├          ●────╯
  │     ●────╯
2/6├────╯
  │
0 ┼────┬────┬────┬────┬────┬────┬────
       1    2    3    4    5    6
              Outcome
              
Step function with equal steps of 1/n
```

---

## 📖 Real-Life Examples: Discrete Uniform

### Example 1: Drawing a Card (Rank Only)

From a standard deck, what's the probability of drawing a Jack?

```
Ranks: {A, 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K} → n = 13

P(Jack) = 1/13 ≈ 0.0769 or 7.69%
```

### Example 2: Random Selection

A teacher randomly selects 1 student from a class of 40 to answer a question.

```
n = 40 students

P(any specific student) = 1/40 = 0.025 = 2.5%
```

### Example 3: Random Number Generator

A program generates a random integer from 1 to 1000.

```
n = 1000

P(X = 777) = 1/1000 = 0.001 = 0.1%
P(X ≤ 500) = 500/1000 = 0.5 = 50%
```

---

# Part 2: Continuous Uniform Distribution
## *Any Value in the Range is Equally Likely*

---

## 📖 Story: Waiting for the Bus

Anika is waiting for a bus that arrives randomly sometime between **2:00 PM and 2:30 PM**. She arrives at the stop at 2:00 PM.

**Questions:**
- What's the probability she waits less than 10 minutes?
- What's the expected waiting time?
- What's the probability she waits between 5 and 15 minutes?

This is the **Continuous Uniform Distribution**!

---

## Definition

A continuous random variable X follows a **Continuous Uniform Distribution** if it can take any value in the interval [a, b] with **equal probability density**.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│             CONTINUOUS UNIFORM DISTRIBUTION                  │
│                                                             │
│   Parameters:                                               │
│   • a = minimum value (left endpoint)                       │
│   • b = maximum value (right endpoint)                      │
│                                                             │
│   Notation: X ~ U(a, b) or X ~ Uniform(a, b)                │
│                                                             │
│   Key: Any value in [a, b] is equally likely!               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The PDF (Probability Density Function)

```
         ┌  1/(b-a)    if a ≤ x ≤ b
f(x) =   │
         └  0          otherwise
```

The PDF is a **constant** (flat/rectangular) over the interval!

### For Anika's Bus (a = 0, b = 30 minutes):

```
f(x) = 1/(30 - 0) = 1/30 ≈ 0.0333    for 0 ≤ x ≤ 30
```

---

## Visualization: Continuous Uniform

### The "Rectangular" Distribution

```
f(x)
    │
1/(b-a)├────┬─────────────────────────────────┬────
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
  0 ┼────┴─────────────────────────────────┴────
         a                                 b
         
Total shaded area = base × height = (b-a) × 1/(b-a) = 1 ✓
```

### Anika's Bus Wait (a = 0, b = 30)

```
f(x)
    │
1/30├────┬─────────────────────────────────┬────
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
    │    │█████████████████████████████████│
  0 ┼────┴─────────────────────────────────┴────
         0     5    10    15    20    25   30
                  Wait time (minutes)
                  
Height = 1/30, Width = 30, Area = 1
```

---

## Key Properties: Continuous Uniform

### 1. Mean (Expected Value)

```
E[X] = (a + b) / 2
```

The mean is the **midpoint** of the interval!

**For Anika:** E[X] = (0 + 30) / 2 = **15 minutes**

### 2. Variance

```
Var(X) = (b - a)² / 12
```

**For Anika:** Var(X) = (30 - 0)² / 12 = 900/12 = **75**

### 3. Standard Deviation

```
σ = (b - a) / √12 ≈ (b - a) / 3.464
```

**For Anika:** σ = 30 / √12 ≈ **8.66 minutes**

### 4. Median

```
Median = (a + b) / 2
```

Same as mean (due to symmetry)!

---

## Properties Summary: Continuous Uniform

| Property | Formula | Anika's Bus (0 to 30) |
|----------|---------|----------------------|
| **Parameters** | a, b | 0, 30 |
| **PDF** | f(x) = 1/(b-a) | 1/30 |
| **Mean** | (a + b) / 2 | 15 min |
| **Variance** | (b - a)² / 12 | 75 |
| **Std Dev** | (b - a) / √12 | 8.66 min |
| **Median** | (a + b) / 2 | 15 min |
| **Mode** | Any value in [a,b] | Any |
| **Skewness** | 0 | 0 (symmetric) |
| **Kurtosis** | -6/5 = -1.2 | -1.2 |

---

## Calculating Probabilities: Continuous Uniform

### The Simple Formula

For continuous uniform, probability = **proportion of interval**:

```
P(c < X < d) = (d - c) / (b - a)
```

It's just the **length of the subinterval** divided by the **total length**!

### Visual Intuition

```
f(x)
    │
1/(b-a)├────┬──────███████████────────────────┬────
    │    │      ███████████                │
    │    │      ███████████                │
    │    │      ███████████                │
  0 ┼────┴──────███████████────────────────┴────
         a      c          d               b
         
P(c < X < d) = Shaded Area = (d-c) × 1/(b-a) = (d-c)/(b-a)
```

---

## 📖 Solving Anika's Problems

**Given:** X ~ U(0, 30) minutes

### Problem 1: P(X < 10) — Waits less than 10 minutes

```
P(X < 10) = (10 - 0) / (30 - 0) = 10/30 = 1/3 ≈ 33.3%
```

### Problem 2: E[X] — Expected waiting time

```
E[X] = (0 + 30) / 2 = 15 minutes
```

### Problem 3: P(5 < X < 15) — Waits between 5 and 15 minutes

```
P(5 < X < 15) = (15 - 5) / (30 - 0) = 10/30 = 1/3 ≈ 33.3%
```

### Visualization of Anika's Problems

```
f(x)
    │
1/30├────┬─────────────────────────────────┬────
    │    │████████████                     │    P(X < 10)
    │    │████████████                     │    = 10/30
    │    │████████████                     │    = 33.3%
  0 ┼────┴────────────┴────────────────────┴────
         0    5    10    15    20    25   30

    │
1/30├────┬─────────────────────────────────┬────
    │    │     ██████████                  │    P(5 < X < 15)
    │    │     ██████████                  │    = 10/30
    │    │     ██████████                  │    = 33.3%
  0 ┼────┴─────┴─────────┴─────────────────┴────
         0    5    10    15    20    25   30
```

---

## The CDF: Continuous Uniform

```
         ┌  0              if x < a
F(x) =   │  (x - a)/(b-a)  if a ≤ x ≤ b
         └  1              if x > b
```

### Visualization: CDF (Linear Function)

```
F(x)
  │
1 ┤                              ●──────────
  │                            ╱
  │                          ╱
  │                        ╱
0.5├──────────────────────●
  │                     ╱
  │                   ╱
  │                 ╱
0 ●───────────────●
  └────┬──────────┬──────────┬──────────
       a      (a+b)/2        b
       
Straight line from (a, 0) to (b, 1)
```

### For Anika (a = 0, b = 30):

```
F(x) = x/30    for 0 ≤ x ≤ 30

F(10) = 10/30 = 0.333  (33.3% chance of waiting ≤ 10 min)
F(15) = 15/30 = 0.500  (50% chance of waiting ≤ 15 min)
F(20) = 20/30 = 0.667  (66.7% chance of waiting ≤ 20 min)
```

---

## The Standard Uniform Distribution

A special case when **a = 0** and **b = 1**:

```
X ~ U(0, 1)

PDF: f(x) = 1    for 0 ≤ x ≤ 1
CDF: F(x) = x    for 0 ≤ x ≤ 1

Mean = 0.5
Variance = 1/12 ≈ 0.0833
Std Dev ≈ 0.289
```

### Why U(0, 1) is Special

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   The Standard Uniform U(0, 1) is fundamental because:      │
│                                                             │
│   1. All random number generators start with U(0, 1)        │
│   2. Can transform U(0, 1) to ANY other distribution        │
│   3. F(X) ~ U(0, 1) for any continuous X (probability       │
│      integral transform)                                    │
│   4. Used in Monte Carlo simulations                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Transforming U(0, 1) to U(a, b)

If U ~ U(0, 1), then:

```
X = a + (b - a) × U ~ U(a, b)
```

---

## 📖 More Real-Life Examples

### Example 1: Random Number Generator

A computer generates a random decimal between 0 and 1.

```
X ~ U(0, 1)

P(X < 0.3) = 0.3 - 0 = 0.3 = 30%
P(0.25 < X < 0.75) = 0.75 - 0.25 = 0.5 = 50%
```

---

### Example 2: Arrival Time

A flight is scheduled to land between 3:00 PM and 3:30 PM, uniformly distributed.

```
X ~ U(0, 30) minutes after 3:00 PM

P(arrives before 3:10) = 10/30 = 33.3%
P(arrives after 3:20) = (30-20)/30 = 10/30 = 33.3%
E[Arrival] = 15 min after 3:00 = 3:15 PM
```

---

### Example 3: Rounding Error

When measuring to the nearest centimeter, the rounding error is uniform between -0.5 and +0.5 cm.

```
X ~ U(-0.5, 0.5)

E[X] = 0 (no systematic bias)
Var(X) = (0.5 - (-0.5))² / 12 = 1/12 ≈ 0.0833
σ ≈ 0.289 cm
```

---

### Example 4: Spinning a Wheel

A prize wheel is divided into 360 degrees. The stopping point is uniformly distributed.

```
X ~ U(0, 360) degrees

P(stops in first quarter) = 90/360 = 25%
P(stops between 100° and 200°) = 100/360 = 27.8%
```

---

### Example 5: Manufacturing Tolerance

A machine cuts rods with length uniformly distributed between 99.5 and 100.5 mm.

```
X ~ U(99.5, 100.5)

E[X] = (99.5 + 100.5) / 2 = 100 mm (target!)
σ = (100.5 - 99.5) / √12 = 1/√12 ≈ 0.289 mm

P(99.8 < X < 100.2) = (100.2 - 99.8) / 1 = 0.4 = 40%
```

---

## Comparing Discrete vs Continuous Uniform

| Aspect | Discrete Uniform | Continuous Uniform |
|--------|------------------|-------------------|
| **Values** | Finite, countable | Infinite in [a, b] |
| **Function** | PMF: P(X = k) = 1/n | PDF: f(x) = 1/(b-a) |
| **P(X = specific value)** | 1/n > 0 | 0 (continuous!) |
| **Visualization** | Bar chart | Rectangle |
| **Mean** | (a + b) / 2 | (a + b) / 2 |
| **Variance** | (n² - 1) / 12 | (b - a)² / 12 |
| **Example** | Die roll | Random time |

---

## Mathematical Properties

### Moment Generating Function (MGF)

**Discrete Uniform:**
```
M_X(t) = (e^(at) × (1 - e^(nt))) / (n × (1 - e^t))
```

**Continuous Uniform:**
```
M_X(t) = (e^(bt) - e^(at)) / (t(b - a))    for t ≠ 0
M_X(0) = 1
```

### Characteristic Function

**Continuous Uniform:**
```
φ_X(t) = (e^(ibt) - e^(iat)) / (it(b - a))
```

### Entropy (Continuous)

```
H(X) = ln(b - a)
```

Maximum entropy among all distributions on [a, b]!

---

## Uniform Distribution and Other Distributions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              UNIFORM AS A BUILDING BLOCK                     │
│                                                             │
│   U(0,1) can generate ANY distribution via:                 │
│                                                             │
│   1. Inverse Transform Method:                              │
│      If U ~ U(0,1), then X = F⁻¹(U) has CDF F               │
│                                                             │
│   2. Box-Muller Transform:                                  │
│      Two U(0,1) variables → Two Normal variables            │
│                                                             │
│   3. Acceptance-Rejection:                                  │
│      Use uniform to sample from complex distributions       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Generating Exponential from Uniform

If U ~ U(0, 1), then:

```
X = -ln(U) / λ ~ Exponential(λ)
```

### Example: Sum of Uniforms → Approaches Normal

```
U₁ + U₂ + ... + U₁₂ - 6 ≈ N(0, 1)

(By Central Limit Theorem, sum of 12 U(0,1) minus 6 
approximates standard normal!)
```

---

## Special Cases and Related Distributions

### Beta(1, 1) = Uniform(0, 1)

```
If X ~ Beta(α=1, β=1), then X ~ U(0, 1)
```

### Uniform as Limit

```
As n → ∞: Binomial(n, 0.5)/n → U(0, 1) in distribution
```

### Order Statistics

If X₁, X₂, ..., Xₙ are i.i.d. U(0, 1):
- The k-th smallest value X₍ₖ₎ follows Beta(k, n-k+1)
- Spacing between consecutive order statistics → Exponential

---

## Python Implementation

### Using NumPy and SciPy

```python
import numpy as np
from scipy import stats

# Continuous Uniform U(0, 30)
a, b = 0, 30
uniform = stats.uniform(loc=a, scale=b-a)

# PDF at x = 15
print(f"f(15) = {uniform.pdf(15):.4f}")  # 0.0333

# CDF: P(X ≤ 10)
print(f"P(X ≤ 10) = {uniform.cdf(10):.4f}")  # 0.3333

# P(5 < X < 20)
prob = uniform.cdf(20) - uniform.cdf(5)
print(f"P(5 < X < 20) = {prob:.4f}")  # 0.5000

# Mean and Variance
print(f"Mean = {uniform.mean():.2f}")  # 15.0
print(f"Variance = {uniform.var():.2f}")  # 75.0

# Generate random samples
samples = uniform.rvs(size=1000)
print(f"Sample mean = {samples.mean():.2f}")
```

### Discrete Uniform (Die Roll)

```python
from scipy import stats

# Discrete Uniform: Die roll (1 to 6)
discrete_uniform = stats.randint(low=1, high=7)  # high is exclusive

# PMF
for k in range(1, 7):
    print(f"P(X = {k}) = {discrete_uniform.pmf(k):.4f}")

# Mean and Variance
print(f"Mean = {discrete_uniform.mean():.2f}")  # 3.5
print(f"Variance = {discrete_uniform.var():.2f}")  # 2.917

# Generate samples
samples = discrete_uniform.rvs(size=1000)
print(f"Sample mean = {samples.mean():.2f}")
```

### Manual Implementation

```python
import random

# Continuous Uniform
def uniform_continuous(a, b):
    """Generate U(a, b) random variable"""
    return a + (b - a) * random.random()

# Discrete Uniform
def uniform_discrete(a, b):
    """Generate discrete uniform on {a, a+1, ..., b}"""
    return random.randint(a, b)

# Simulations
continuous_samples = [uniform_continuous(0, 30) for _ in range(10000)]
discrete_samples = [uniform_discrete(1, 6) for _ in range(10000)]

print(f"Continuous mean: {sum(continuous_samples)/len(continuous_samples):.2f}")
print(f"Discrete mean: {sum(discrete_samples)/len(discrete_samples):.2f}")
```

### Visualization

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

fig, axes = plt.subplots(1, 2, figsize=(14, 5))

# Continuous Uniform
ax1 = axes[0]
a, b = 0, 30
x = np.linspace(-5, 35, 1000)
y = stats.uniform.pdf(x, loc=a, scale=b-a)
ax1.plot(x, y, 'b-', linewidth=2)
ax1.fill_between(x, y, where=(x >= a) & (x <= b), alpha=0.3)
ax1.axvline((a+b)/2, color='red', linestyle='--', label=f'Mean = {(a+b)/2}')
ax1.set_xlabel('x')
ax1.set_ylabel('f(x)')
ax1.set_title(f'Continuous Uniform U({a}, {b})')
ax1.legend()
ax1.set_ylim(0, 0.05)

# Discrete Uniform (Die)
ax2 = axes[1]
x = np.arange(1, 7)
y = [1/6] * 6
ax2.bar(x, y, color='steelblue', edgecolor='black')
ax2.axhline(y=1/6, color='red', linestyle='--', label='P = 1/6')
ax2.set_xlabel('Outcome')
ax2.set_ylabel('P(X = k)')
ax2.set_title('Discrete Uniform (Fair Die)')
ax2.set_xticks(x)
ax2.legend()

plt.tight_layout()
plt.show()
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: P(X = exact value) for Continuous

❌ **Wrong:** P(X = 15) = 1/30 for U(0, 30)

✅ **Correct:** P(X = 15) = 0 for any continuous distribution!
Use P(14.9 < X < 15.1) instead.

---

### Mistake 2: Forgetting Scale in SciPy

❌ **Wrong:** `stats.uniform(0, 30)` doesn't give U(0, 30)!

✅ **Correct:** `stats.uniform(loc=0, scale=30)` gives U(0, 30)
(SciPy uses loc and scale, not a and b directly)

---

### Mistake 3: Confusing Discrete and Continuous

❌ **Wrong:** Using PMF formula for continuous data

✅ **Correct:** 
- Discrete: P(X = k) = 1/n
- Continuous: P(c < X < d) = (d-c)/(b-a)

---

### Mistake 4: Variance Formula Mix-up

❌ **Wrong:** Using (b-a)²/12 for discrete uniform

✅ **Correct:** 
- Discrete: (n² - 1) / 12 where n = b - a + 1
- Continuous: (b - a)² / 12

---

## Practice Problems 📝

### Problem 1: Die Roll
What's the probability of rolling a 4 or higher on a fair die?

<details>
<summary>Click for Answer</summary>

```
X ~ Discrete Uniform(1, 6)

P(X ≥ 4) = P(X = 4) + P(X = 5) + P(X = 6)
         = 1/6 + 1/6 + 1/6
         = 3/6 = 0.5 = 50%

Or simply: 3 favorable outcomes out of 6
```

</details>

---

### Problem 2: Bus Arrival
A bus arrives uniformly between 8:00 and 8:20 AM. What's the probability it arrives between 8:05 and 8:12?

<details>
<summary>Click for Answer</summary>

```
X ~ U(0, 20) minutes after 8:00

P(5 < X < 12) = (12 - 5) / (20 - 0)
              = 7/20
              = 0.35 = 35%
```

</details>

---

### Problem 3: Expected Value
A random number is generated uniformly between 50 and 100. What's the expected value and standard deviation?

<details>
<summary>Click for Answer</summary>

```
X ~ U(50, 100)

E[X] = (50 + 100) / 2 = 75

Var(X) = (100 - 50)² / 12 = 2500/12 ≈ 208.33

σ = √208.33 ≈ 14.43
```

</details>

---

### Problem 4: Finding Percentile
For X ~ U(10, 50), find the 75th percentile.

<details>
<summary>Click for Answer</summary>

```
The 75th percentile means P(X ≤ x) = 0.75

For uniform: x = a + 0.75 × (b - a)
           x = 10 + 0.75 × (50 - 10)
           x = 10 + 0.75 × 40
           x = 10 + 30
           x = 40

The 75th percentile is 40.
```

</details>

---

### Problem 5: Quality Control
Parts are manufactured with length uniformly distributed between 9.8 and 10.2 cm. What percentage are between 9.9 and 10.1 cm?

<details>
<summary>Click for Answer</summary>

```
X ~ U(9.8, 10.2)

P(9.9 < X < 10.1) = (10.1 - 9.9) / (10.2 - 9.8)
                  = 0.2 / 0.4
                  = 0.5 = 50%

Half the parts are in the tighter tolerance range.
```

</details>

---

## Applications in Real World

### 1. Monte Carlo Simulation

```
Generate U(0,1) → Transform to any distribution → Run simulations
```

### 2. Random Sampling

```
Selecting random items from a list uses discrete uniform.
```

### 3. Cryptography

```
Random key generation starts with uniform random bits.
```

### 4. Game Development

```
Random events, loot drops, procedural generation.
```

### 5. Queueing Theory

```
Inter-arrival times sometimes modeled as uniform.
```

### 6. Numerical Integration

```
Monte Carlo integration uses uniform random points.
```

---

## Summary: The Essence of Uniform Distribution

```
┌─────────────────────────────────────────────────────────────────┐
│                    UNIFORM DISTRIBUTION                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "Every outcome is equally likely"                              │
│                                                                  │
│   DISCRETE UNIFORM                   CONTINUOUS UNIFORM          │
│   ─────────────────                  ──────────────────          │
│   X ∈ {a, a+1, ..., b}               X ∈ [a, b]                  │
│   P(X = k) = 1/n                     f(x) = 1/(b-a)              │
│   n = b - a + 1                      P(c<X<d) = (d-c)/(b-a)      │
│                                                                  │
│   BOTH HAVE:                                                     │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  Mean = (a + b) / 2                                      │   │
│   │  Variance involves (range)² / 12                         │   │
│   │  Symmetric around the mean                               │   │
│   │  Flat probability (no values preferred)                  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY APPLICATIONS:                                              │
│   • Random number generation                                     │
│   • Simulations                                                  │
│   • Fair games and lotteries                                     │
│   • Modeling uncertainty when no preference exists               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Uniform Distribution Matters

| Reason | Explanation |
|--------|-------------|
| **Foundation of Randomness** | All random number generators start with uniform |
| **Maximum Ignorance** | When you know nothing, assume uniform |
| **Fairness** | Models truly fair games and selections |
| **Transformation Base** | Can create ANY distribution from U(0,1) |
| **Simplicity** | Easy to calculate, easy to understand |

> **"The Uniform distribution represents pure randomness — when nature (or a computer) shows no preference, every outcome gets an equal chance."**

Master the Uniform distribution, and you've mastered the foundation of all random number generation! 🎲

---

*Equal chances, simple math, endless applications — that's the beauty of uniform!* ✨
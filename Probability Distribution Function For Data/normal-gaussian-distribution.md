# Normal (Gaussian) Distribution
## The Bell Curve — The Most Important Distribution in Statistics 🔔

---

## The King of All Distributions

If there's one distribution you must understand, it's the **Normal Distribution**. It appears everywhere in nature, science, and everyday life:

- Heights of people
- Test scores
- Measurement errors
- Blood pressure readings
- Stock returns
- IQ scores

This ubiquitous "bell curve" is the foundation of modern statistics!

---

## 📖 Story: The National Exam

The Bangladesh SSC examination results are in. The education board has data on **millions of students**:

- **Average score:** 65%
- **Standard deviation:** 12%

The scores follow a beautiful bell-shaped curve — the **Normal Distribution**.

**Questions we can answer:**
- What percentage of students scored above 80%?
- What score puts a student in the top 10%?
- What percentage scored between 50% and 75%?

---

## What is the Normal Distribution?

The Normal (or Gaussian) distribution is a **continuous probability distribution** characterized by its symmetric, bell-shaped curve.

```
┌─────────────────────────────────────────────────────────────┐
│                    NORMAL DISTRIBUTION                       │
│                                                              │
│   "The bell curve of nature"                                 │
│                                                              │
│   Key Characteristics:                                       │
│   ✓ Symmetric around the mean (μ)                            │
│   ✓ Bell-shaped curve                                        │
│   ✓ Mean = Median = Mode                                     │
│   ✓ Tails extend to infinity (but probability diminishes)    │
│   ✓ Total area under curve = 1                               │
│                                                              │
│   Named after Carl Friedrich Gauss (1777-1855)               │
│   German mathematician — "Prince of Mathematics"             │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## The Two Parameters

The Normal distribution is completely defined by **two parameters**:

| Parameter | Symbol | Meaning | Effect on Curve |
|-----------|--------|---------|-----------------|
| Mean | μ (mu) | Center/average | Shifts curve left or right |
| Standard Deviation | σ (sigma) | Spread/variability | Makes curve wider or narrower |

**Notation:** X ~ N(μ, σ²) or X ~ Normal(μ, σ²)

For SSC scores: X ~ N(65, 12²) or N(65, 144)

---

## The Normal PDF (Probability Density Function)

### The Formula

```
f(x) = (1 / (σ√(2π))) × e^(-(x-μ)²/(2σ²))
```

Where:
- **μ** = mean (center)
- **σ** = standard deviation (spread)
- **e** ≈ 2.71828 (Euler's number)
- **π** ≈ 3.14159

### Simplified View

```
f(x) = (1 / (σ√(2π))) × exp(-(x-μ)²/(2σ²))
       \_____________/   \________________/
        Scaling factor    Exponential decay
        (ensures area=1)  (creates bell shape)
```

---

## The Beautiful Bell Curve

### Visualization

```
                              f(x)
                               │
                               │           ╭───╮
                               │         ╭─╯   ╰─╮
                               │        ╭╯       ╰╮
                               │       ╭╯         ╰╮
                               │      ╭╯           ╰╮
                               │     ╭╯             ╰╮
                               │    ╭╯               ╰╮
                               │  ╭─╯                 ╰─╮
                               │╭─╯                     ╰─╮
                            ───┴───────────────────────────────
                                         μ
                                      (center)
```

### Anatomy of the Bell Curve

```
                                    │
                                   ╭┴╮         ← Peak at x = μ
                                  ╭╯ ╰╮
                                 ╭╯   ╰╮
                    Inflection →╭╯     ╰╮← Inflection
                    Points     ╭╯       ╰╮   Points
                              ╭╯         ╰╮
                             ╭╯           ╰╮
                          ╭──╯             ╰──╮
                     ╭────╯                   ╰────╮
                ─────╯                             ╰─────
                     │     │     │     │     │     │
                   μ-3σ  μ-2σ  μ-1σ    μ   μ+1σ  μ+2σ  μ+3σ
                   
Inflection points occur at μ ± σ (where curve changes from 
concave to convex)
```

---

## The Empirical Rule (68-95-99.7 Rule)

This is the **most important rule** for the Normal distribution!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    THE EMPIRICAL RULE                        │
│                                                             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │  68.27%  of data falls within  μ ± 1σ               │   │
│   │  95.45%  of data falls within  μ ± 2σ               │   │
│   │  99.73%  of data falls within  μ ± 3σ               │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                             │
│   Only 0.27% of data lies beyond 3 standard deviations!     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual Representation

```
                         68.27%
                    ┌───────┴───────┐
                    │               │
                   ╭┴╮             ╭┴╮
                  ╭╯ ╰╮           ╭╯ ╰╮
                 ╭╯███╰╮         ╭╯███╰╮
                ╭╯█████╰╮       ╭╯█████╰╮
               ╭╯███████╰╮     ╭╯███████╰╮
              ╭╯█████████╰╮   ╭╯█████████╰╮
           ╭──╯███████████╰───╯███████████╰──╮
      ╭────╯█████████████████████████████████╰────╮
  ────╯███████████████████████████████████████████╰────
      │        │        │        │        │        │
    μ-3σ    μ-2σ     μ-1σ       μ      μ+1σ    μ+2σ    μ+3σ
    
    ←─────────────── 95.45% ───────────────→
    ←──────────────────── 99.73% ────────────────────→
```

### For SSC Scores (μ = 65, σ = 12)

| Range | Interval | % of Students |
|-------|----------|---------------|
| μ ± 1σ | 53% to 77% | 68.27% |
| μ ± 2σ | 41% to 89% | 95.45% |
| μ ± 3σ | 29% to 101%* | 99.73% |

*Capped at 100% for scores

---

## The Standard Normal Distribution (Z-Distribution)

### What is Z?

The **Standard Normal** is a special Normal with:
- **Mean μ = 0**
- **Standard deviation σ = 1**

**Notation:** Z ~ N(0, 1)

### The Z-Score (Standardization)

Any Normal variable X can be converted to Z:

```
Z = (X - μ) / σ
```

This **standardization** tells us "how many standard deviations away from the mean" a value is.

### Why Z-Scores Matter

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Z-Score Interpretation:                                    │
│                                                             │
│   Z = 0   → Exactly at the mean                             │
│   Z = 1   → 1 standard deviation above the mean             │
│   Z = -1  → 1 standard deviation below the mean             │
│   Z = 2   → 2 standard deviations above (top ~2.5%)         │
│   Z = -2  → 2 standard deviations below (bottom ~2.5%)      │
│   Z = 3   → 3 standard deviations above (very rare!)        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Converting SSC Score to Z-Score

A student scored 89%. What's their Z-score?

```
μ = 65, σ = 12, X = 89

Z = (89 - 65) / 12 = 24 / 12 = 2.0

This student is 2 standard deviations above average!
```

---

## Using the Z-Table (Standard Normal Table)

The Z-table gives P(Z ≤ z) — the area to the LEFT of z.

### Common Z-Values to Remember

| Z | P(Z ≤ z) | Meaning |
|---|----------|---------|
| -3.0 | 0.0013 | Bottom 0.13% |
| -2.0 | 0.0228 | Bottom 2.28% |
| -1.0 | 0.1587 | Bottom 15.87% |
| 0.0 | 0.5000 | Exactly at median |
| 1.0 | 0.8413 | Top 15.87% |
| 2.0 | 0.9772 | Top 2.28% |
| 3.0 | 0.9987 | Top 0.13% |

### Critical Z-Values (Used in Hypothesis Testing)

| Confidence Level | α | Z-critical (two-tailed) |
|------------------|---|------------------------|
| 90% | 0.10 | ±1.645 |
| 95% | 0.05 | ±1.960 |
| 99% | 0.01 | ±2.576 |

---

## Solving Normal Distribution Problems

### Step-by-Step Method

```
1. Identify μ and σ
2. Define the probability you want
3. Convert X to Z using: Z = (X - μ) / σ
4. Use Z-table or calculator
5. Interpret the result
```

---

## 📖 Solving SSC Score Problems

### Problem 1: P(X > 80) — "What percentage scored above 80%?"

```
Step 1: μ = 65, σ = 12, X = 80

Step 2: Want P(X > 80)

Step 3: Z = (80 - 65) / 12 = 15 / 12 = 1.25

Step 4: P(Z > 1.25) = 1 - P(Z ≤ 1.25)
                    = 1 - 0.8944
                    = 0.1056

Answer: About 10.56% of students scored above 80%
```

### Problem 2: P(50 < X < 75) — "What percentage scored between 50% and 75%?"

```
Step 1: μ = 65, σ = 12

Step 2: Want P(50 < X < 75)

Step 3: Z₁ = (50 - 65) / 12 = -1.25
        Z₂ = (75 - 65) / 12 = 0.833

Step 4: P(-1.25 < Z < 0.833) = P(Z < 0.833) - P(Z < -1.25)
                              = 0.7977 - 0.1056
                              = 0.6921

Answer: About 69.21% of students scored between 50% and 75%
```

### Problem 3: "What score is needed for the top 10%?"

```
Step 1: μ = 65, σ = 12

Step 2: Want X such that P(X > x) = 0.10
        This means P(X ≤ x) = 0.90

Step 3: Find Z where P(Z ≤ z) = 0.90
        Z = 1.28 (from table)

Step 4: Convert back to X:
        X = μ + Z × σ
        X = 65 + 1.28 × 12
        X = 65 + 15.36
        X = 80.36

Answer: A student needs about 80.4% to be in the top 10%
```

---

## Visual Problem-Solving Guide

### Type 1: P(X < a) — Left Tail

```
         ╭───╮
       ╭─╯   ╰─╮
      ╭╯       ╰╮
     ╭╯█████████╰╮
    ╭╯███████████╰╮
  ──╯█████████████╰─────────
              a
              
Shaded area = P(X < a) = P(Z < z_a)
```

### Type 2: P(X > a) — Right Tail

```
         ╭───╮
       ╭─╯   ╰─╮
      ╭╯       ╰╮
     ╭╯         ╰█████╮
    ╭╯           █████╰╮
  ──╯            █████████──
              a
              
Shaded area = P(X > a) = 1 - P(Z < z_a)
```

### Type 3: P(a < X < b) — Between Two Values

```
         ╭───╮
       ╭─╯███╰─╮
      ╭╯██████╰╮
     ╭╯████████╰╮
    ╭╯██████████╰╮
  ──╯████████████╰─────────
        a     b
              
Shaded area = P(a < X < b) = P(Z < z_b) - P(Z < z_a)
```

### Type 4: Finding X from Probability (Inverse)

```
Given: P(X < ?) = 0.90

1. Find Z where P(Z < z) = 0.90 → Z = 1.28
2. Convert: X = μ + Z × σ
```

---

## Key Properties

### 1. Mean, Median, Mode

```
Mean = Median = Mode = μ
```

All three measures of central tendency are **equal** due to symmetry!

### 2. Symmetry

```
P(X < μ - a) = P(X > μ + a)

The curve is perfectly symmetric around μ
```

### 3. Variance and Standard Deviation

```
Variance: Var(X) = σ²
Standard Deviation: SD(X) = σ
```

### 4. Linear Transformations

If X ~ N(μ, σ²), then:

```
aX + b ~ N(aμ + b, a²σ²)
```

### 5. Sum of Normal Variables

If X ~ N(μ₁, σ₁²) and Y ~ N(μ₂, σ₂²) are independent:

```
X + Y ~ N(μ₁ + μ₂, σ₁² + σ₂²)
```

---

## Properties Summary Table

| Property | Formula/Value |
|----------|---------------|
| **Parameters** | μ ∈ ℝ, σ > 0 |
| **Support** | x ∈ (-∞, +∞) |
| **PDF** | (1/(σ√(2π))) × e^(-(x-μ)²/(2σ²)) |
| **Mean** | μ |
| **Median** | μ |
| **Mode** | μ |
| **Variance** | σ² |
| **Std Dev** | σ |
| **Skewness** | 0 (symmetric) |
| **Kurtosis** | 3 (or 0 excess) |
| **Entropy** | ½ ln(2πeσ²) |

---

## How Parameters Affect the Curve

### Effect of μ (Mean) — Horizontal Shift

```
       μ = 0              μ = 3              μ = -2
         │                  │                  │
        ╭┴╮                ╭┴╮                ╭┴╮
       ╭╯ ╰╮              ╭╯ ╰╮              ╭╯ ╰╮
      ╭╯   ╰╮            ╭╯   ╰╮            ╭╯   ╰╮
     ╭╯     ╰╮          ╭╯     ╰╮          ╭╯     ╰╮
  ───╯───────╰───    ───╯───────╰───    ───╯───────╰───
         0                  3                 -2
         
Same shape, different center
```

### Effect of σ (Standard Deviation) — Spread

```
       σ = 0.5            σ = 1              σ = 2
         │                  │                  │
        ╭┴╮                                   
       ╭╯ ╰╮              ╭┴╮               ╭──┴──╮
      ╭╯   ╰╮            ╭╯ ╰╮            ╭─╯     ╰─╮
     ╭╯     ╰╮          ╭╯   ╰╮          ╭╯         ╰╮
  ───╯───────╰───    ──╯─────╰──     ──╯─────────────╰──
         0                 0                  0
         
    Tall & narrow      Standard         Short & wide
```

### Combined Effects

```
N(0, 1)     N(2, 1)     N(0, 4)     N(2, 4)
   │           │           │           │
  ╭┴╮         ╭┴╮        ╭─┴─╮       ╭─┴─╮
 ╭╯ ╰╮       ╭╯ ╰╮      ╭╯   ╰╮     ╭╯   ╰╮
 ╯   ╰       ╯   ╰      ╯     ╰     ╯     ╰
───────    ───────    ───────    ───────
   0          2          0          2

Standard   Shifted     Wider      Shifted
           right                  & wider
```

---

## The Central Limit Theorem (CLT)

### The Most Important Theorem in Statistics!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              THE CENTRAL LIMIT THEOREM                       │
│                                                             │
│   If you take sufficiently large random samples from        │
│   ANY population (regardless of its distribution),           │
│   the distribution of sample means will be approximately     │
│   NORMAL.                                                   │
│                                                             │
│   Sample Mean X̄ ~ N(μ, σ²/n)  as n → large                  │
│                                                             │
│   Rule of Thumb: n ≥ 30 is usually "large enough"           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Why CLT is Revolutionary

Even if the original population is:
- Skewed
- Uniform
- Bimodal
- Any shape!

The **sample means** will still be approximately Normal!

### Visual: CLT in Action

```
Original Population          Distribution of Sample Means
(could be anything)          (always approaches Normal)

    █                              ╭───╮
    █ █                          ╭─╯   ╰─╮
  █ █ █                         ╭╯       ╰╮
  █ █ █ █                      ╭╯         ╰╮
█ █ █ █ █ █        n→∞       ╭╯           ╰╮
█ █ █ █ █ █ █      ────→    ╭╯             ╰╮
█ █ █ █ █ █ █ █            ╭╯               ╰╮
                        ───╯─────────────────╰───
                                  μ
```

### Standard Error

The standard deviation of sample means:

```
Standard Error (SE) = σ / √n
```

As sample size **n increases**, standard error **decreases** → estimates become more precise!

---

## Real-Life Normal Distribution Examples

### 📖 Story 2: Human Heights

Adult male heights in Bangladesh follow approximately:

```
X ~ N(μ = 165 cm, σ = 7 cm)
```

**Question:** What percentage of men are taller than 180 cm?

```
Z = (180 - 165) / 7 = 15/7 = 2.14

P(X > 180) = P(Z > 2.14) = 1 - 0.9838 = 0.0162

Answer: Only about 1.6% of men are taller than 180 cm!
```

---

### 📖 Story 3: Manufacturing Quality

A factory produces bolts with target diameter 10 mm:

```
X ~ N(μ = 10 mm, σ = 0.05 mm)
```

**Question:** What percentage of bolts are within specification (9.9 to 10.1 mm)?

```
Z₁ = (9.9 - 10) / 0.05 = -2.0
Z₂ = (10.1 - 10) / 0.05 = 2.0

P(9.9 < X < 10.1) = P(-2 < Z < 2) = 0.9772 - 0.0228 = 0.9544

Answer: About 95.44% of bolts meet specifications!
```

---

### 📖 Story 4: IQ Scores

IQ scores are designed to follow:

```
X ~ N(μ = 100, σ = 15)
```

**Question:** What IQ score is needed to join Mensa (top 2%)?

```
P(X > x) = 0.02 → P(X ≤ x) = 0.98

Z = 2.05 (from table)

X = 100 + 2.05 × 15 = 100 + 30.75 = 130.75

Answer: IQ of about 131 is needed for Mensa!
```

---

### 📖 Story 5: Stock Returns

Daily returns of a stock follow approximately:

```
X ~ N(μ = 0.05%, σ = 1.5%)
```

**Question:** What's the probability of losing more than 3% in a day?

```
Z = (-3 - 0.05) / 1.5 = -3.05 / 1.5 = -2.03

P(X < -3) = P(Z < -2.03) = 0.0212

Answer: About 2.1% chance of losing more than 3% in a day
```

---

## Normal Distribution in Different Fields

| Field | Variable | Typical μ | Typical σ |
|-------|----------|-----------|-----------|
| **Psychology** | IQ Score | 100 | 15 |
| **Education** | Test Scores | 500 | 100 |
| **Biology** | Human Height | 170 cm | 10 cm |
| **Manufacturing** | Part Dimensions | Target | Tolerance |
| **Finance** | Returns | 0.05% | 1-2% |
| **Physics** | Measurement Error | 0 | Varies |
| **Medicine** | Blood Pressure | 120 mmHg | 15 mmHg |
| **Agriculture** | Crop Yield | Regional avg | Varies |

---

## Relationship to Other Distributions

```
                         ┌─────────────────┐
                         │     NORMAL      │◄─── YOU ARE HERE
                         │    N(μ, σ²)     │
                         └────────┬────────┘
                                  │
       ┌──────────────────────────┼──────────────────────────┐
       │                          │                          │
       ↓                          ↓                          ↓
┌─────────────┐          ┌─────────────┐          ┌─────────────┐
│  LOGNORMAL  │          │ CHI-SQUARED │          │  STUDENT'S  │
│             │          │             │          │      t      │
│ eˣ where    │          │ Sum of      │          │ Small sample│
│ X~Normal    │          │ squared Z's │          │ means       │
└─────────────┘          └─────────────┘          └─────────────┘
                                  │
                                  ↓
                         ┌─────────────────┐
                         │ F-DISTRIBUTION  │
                         │ Ratio of        │
                         │ Chi-squared     │
                         └─────────────────┘

                    APPROXIMATIONS TO NORMAL
                    ────────────────────────
                    
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│  BINOMIAL   │    │   POISSON   │    │    ANY      │
│  (large n)  │    │  (large λ)  │    │ Distribution│
│             │    │             │    │   (via CLT) │
└──────┬──────┘    └──────┬──────┘    └──────┬──────┘
       │                  │                  │
       └──────────────────┴──────────────────┘
                          │
                          ↓
                   ┌─────────────┐
                   │   NORMAL    │
                   └─────────────┘
```

### Key Relationships

| From | To Normal | Condition |
|------|-----------|-----------|
| Binomial(n, p) | N(np, np(1-p)) | np ≥ 5, n(1-p) ≥ 5 |
| Poisson(λ) | N(λ, λ) | λ ≥ 20 |
| Sample Means | N(μ, σ²/n) | n ≥ 30 (CLT) |
| Sum of Normals | Normal | Always! |

---

## The Normal CDF (Φ Function)

The CDF of the standard normal is denoted **Φ(z)**:

```
Φ(z) = P(Z ≤ z) = ∫ from -∞ to z of (1/√(2π)) × e^(-t²/2) dt
```

### Properties of Φ

```
Φ(-z) = 1 - Φ(z)        (symmetry)
Φ(0) = 0.5              (median at 0)
Φ(∞) = 1                (total probability)
Φ(-∞) = 0
```

### Visual CDF

```
Φ(z)
  │
1 ┤                              ────────────
  │                         ╭────╯
  │                    ╭────╯
0.5├───────────────────●
  │              ╭────╯
  │         ╭────╯
0 ├─────────╯
  └────┬────┬────┬────┬────┬────┬────
      -3   -2   -1    0    1    2    3
                     z
                     
S-shaped curve (sigmoid)
```

---

## Mathematical Properties

### Moment Generating Function (MGF)

```
M_X(t) = E[e^(tX)] = e^(μt + σ²t²/2)
```

### Characteristic Function

```
φ_X(t) = e^(iμt - σ²t²/2)
```

### Moments

```
E[X] = μ
E[X²] = μ² + σ²
E[(X-μ)³] = 0           (skewness = 0)
E[(X-μ)⁴] = 3σ⁴         (kurtosis = 3)
```

### Entropy

```
H(X) = ½ ln(2πeσ²) ≈ 0.5 ln(σ²) + 1.42
```

---

## Python Implementation

### Using SciPy

```python
from scipy import stats
import numpy as np

# Define Normal distribution: μ = 65, σ = 12
mu, sigma = 65, 12
normal = stats.norm(mu, sigma)

# PDF at x = 70
print(f"f(70) = {normal.pdf(70):.4f}")

# CDF: P(X ≤ 80)
print(f"P(X ≤ 80) = {normal.cdf(80):.4f}")  # 0.8944

# P(X > 80)
print(f"P(X > 80) = {1 - normal.cdf(80):.4f}")  # 0.1056

# P(50 < X < 75)
print(f"P(50 < X < 75) = {normal.cdf(75) - normal.cdf(50):.4f}")

# Inverse CDF: What score for top 10%?
print(f"Top 10% threshold = {normal.ppf(0.90):.2f}")  # 80.38

# Generate random samples
samples = normal.rvs(size=1000)
print(f"Sample mean = {samples.mean():.2f}")
print(f"Sample std = {samples.std():.2f}")
```

### Z-Score Calculations

```python
def z_score(x, mu, sigma):
    """Calculate Z-score"""
    return (x - mu) / sigma

def from_z_score(z, mu, sigma):
    """Convert Z-score back to X"""
    return mu + z * sigma

# Examples
mu, sigma = 65, 12

# Student scored 89
z = z_score(89, mu, sigma)
print(f"Z-score for 89: {z:.2f}")  # 2.0

# What score corresponds to Z = 1.5?
x = from_z_score(1.5, mu, sigma)
print(f"Score at Z=1.5: {x:.2f}")  # 83.0
```

### Visualization

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

# Parameters
mu, sigma = 65, 12

# Create x values
x = np.linspace(mu - 4*sigma, mu + 4*sigma, 1000)

# PDF
y = stats.norm.pdf(x, mu, sigma)

# Plot
plt.figure(figsize=(12, 6))
plt.plot(x, y, 'b-', linewidth=2, label='Normal PDF')

# Fill areas for empirical rule
x_fill_1 = np.linspace(mu - sigma, mu + sigma, 100)
x_fill_2 = np.linspace(mu - 2*sigma, mu + 2*sigma, 100)
x_fill_3 = np.linspace(mu - 3*sigma, mu + 3*sigma, 100)

plt.fill_between(x_fill_1, stats.norm.pdf(x_fill_1, mu, sigma), 
                  alpha=0.3, color='green', label='68.27%')
plt.fill_between(x_fill_2, stats.norm.pdf(x_fill_2, mu, sigma), 
                  alpha=0.2, color='blue', label='95.45%')
plt.fill_between(x_fill_3, stats.norm.pdf(x_fill_3, mu, sigma), 
                  alpha=0.1, color='red', label='99.73%')

plt.axvline(mu, color='black', linestyle='--', label=f'μ = {mu}')
plt.xlabel('Score')
plt.ylabel('Density')
plt.title(f'Normal Distribution N({mu}, {sigma}²)')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()
```

---

## Checking for Normality

### 1. Visual Methods

**Histogram:**
```python
plt.hist(data, bins=30, density=True, alpha=0.7)
# Should look bell-shaped
```

**Q-Q Plot (Quantile-Quantile):**
```python
from scipy import stats
stats.probplot(data, dist="norm", plot=plt)
# Points should fall on diagonal line
```

### 2. Statistical Tests

| Test | Function | Null Hypothesis |
|------|----------|-----------------|
| Shapiro-Wilk | `stats.shapiro()` | Data is normal |
| D'Agostino-Pearson | `stats.normaltest()` | Data is normal |
| Kolmogorov-Smirnov | `stats.kstest()` | Data follows specified distribution |

```python
# Shapiro-Wilk test
stat, p_value = stats.shapiro(data)
if p_value > 0.05:
    print("Data appears to be normal")
else:
    print("Data is not normal")
```

### 3. Descriptive Statistics

For normal data:
- **Skewness ≈ 0** (symmetric)
- **Kurtosis ≈ 3** (or excess kurtosis ≈ 0)

```python
print(f"Skewness: {stats.skew(data):.2f}")
print(f"Kurtosis: {stats.kurtosis(data):.2f}")
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Assuming Everything is Normal

❌ **Wrong:** "This data must be normal"
→ Many real-world distributions are skewed!

✅ **Correct:** Always check normality before assuming

---

### Mistake 2: Confusing σ and σ²

❌ **Wrong:** N(65, 144) means σ = 144
→ 144 is the **variance** (σ²), not σ!

✅ **Correct:** σ = √144 = 12

---

### Mistake 3: Forgetting to Standardize

❌ **Wrong:** Using Z-table directly with X values

✅ **Correct:** Always convert X to Z first: Z = (X - μ) / σ

---

### Mistake 4: P(X = specific value) for Continuous

❌ **Wrong:** P(X = 65) = some positive value

✅ **Correct:** P(X = 65) = 0 for continuous distributions
→ Use P(64.5 < X < 65.5) instead

---

## Practice Problems 📝

### Problem 1: Basic Z-Score
Heights of women follow N(160, 36). What's the Z-score for a woman who is 172 cm tall?

<details>
<summary>Click for Answer</summary>

```
μ = 160, σ² = 36, so σ = 6
X = 172

Z = (172 - 160) / 6 = 12 / 6 = 2.0

She is 2 standard deviations above average.
```

</details>

---

### Problem 2: Finding Probability
Test scores follow N(75, 100). What percentage score above 90?

<details>
<summary>Click for Answer</summary>

```
μ = 75, σ = 10, X = 90

Z = (90 - 75) / 10 = 1.5

P(X > 90) = P(Z > 1.5) = 1 - 0.9332 = 0.0668

About 6.68% score above 90.
```

</details>

---

### Problem 3: Finding Percentile
IQ follows N(100, 225). What IQ is at the 90th percentile?

<details>
<summary>Click for Answer</summary>

```
μ = 100, σ = 15

90th percentile → P(X ≤ x) = 0.90
Z = 1.28 (from table)

X = μ + Z × σ = 100 + 1.28 × 15 = 119.2

IQ of about 119 is at the 90th percentile.
```

</details>

---

### Problem 4: Between Two Values
A machine fills bottles with μ = 500 ml, σ = 5 ml. What percentage of bottles have between 492 and 508 ml?

<details>
<summary>Click for Answer</summary>

```
Z₁ = (492 - 500) / 5 = -1.6
Z₂ = (508 - 500) / 5 = 1.6

P(-1.6 < Z < 1.6) = Φ(1.6) - Φ(-1.6)
                  = 0.9452 - 0.0548
                  = 0.8904

About 89% of bottles are within specification.
```

</details>

---

### Problem 5: Central Limit Theorem
Population has μ = 50, σ = 10. For samples of n = 100, what's P(X̄ > 52)?

<details>
<summary>Click for Answer</summary>

```
By CLT: X̄ ~ N(μ = 50, σ²/n = 100/100 = 1)
Standard Error = σ/√n = 10/10 = 1

Z = (52 - 50) / 1 = 2.0

P(X̄ > 52) = P(Z > 2) = 1 - 0.9772 = 0.0228

Only 2.28% chance of sample mean exceeding 52.
```

</details>

---

## Applications in Data Science

### 1. Confidence Intervals

```
95% CI for mean: X̄ ± 1.96 × (σ/√n)
```

### 2. Hypothesis Testing

```
Z-test: Z = (X̄ - μ₀) / (σ/√n)
```

### 3. Linear Regression

Residuals should be normally distributed.

### 4. Machine Learning

- Gaussian Naive Bayes
- Gaussian Mixture Models
- Feature normalization
- Weight initialization in neural networks

### 5. Anomaly Detection

Flag data points beyond 3σ from the mean.

---

## Summary: The Essence of Normal Distribution

```
┌─────────────────────────────────────────────────────────────────┐
│                    NORMAL (GAUSSIAN) DISTRIBUTION                │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "The Bell Curve — Nature's Favorite Distribution"             │
│                                                                  │
│   Key Features:                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │ • Symmetric bell-shaped curve                            │   │
│   │ • Mean = Median = Mode = μ                               │   │
│   │ • Fully defined by μ (center) and σ (spread)            │   │
│   │ • Tails extend to ±∞                                     │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   The Empirical Rule (68-95-99.7):                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  68.27% within μ ± 1σ                                    │   │
│   │  95.45% within μ ± 2σ                                    │   │
│   │  99.73% within μ ± 3σ                                    │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Z-Score: Z = (X - μ) / σ                                       │
│                                                                  │
│   Central Limit Theorem: Sample means → Normal as n → ∞         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Normal Distribution is So Important

1. **Ubiquity:** Appears naturally in countless phenomena
2. **Central Limit Theorem:** Sample means always approach normal
3. **Mathematical Tractability:** Many useful properties
4. **Foundation of Statistics:** Most statistical tests assume normality
5. **Approximation Power:** Can approximate other distributions

> **"The Normal distribution is not just a mathematical convenience — it's a deep truth about how randomness behaves when many small, independent factors combine."**

Master the Normal distribution, and you've mastered the heart of statistics! 🚀

---

*The bell curve rings true across all of nature — from human heights to measurement errors, from test scores to stock returns. It truly is the queen of all distributions!* 👑
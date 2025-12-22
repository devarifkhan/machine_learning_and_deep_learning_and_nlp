# Standard Normal Distribution & Z-Score
## The Universal Language of Statistics 🎯

---

## The Problem: Different Scales, How to Compare?

Imagine these three students:

| Student | Subject | Score | Class Average | Std Dev |
|---------|---------|-------|---------------|---------|
| Rina | Math | 85 | 70 | 10 |
| Kamal | Physics | 78 | 65 | 8 |
| Fatima | Chemistry | 92 | 80 | 15 |

**The Question:** Who performed best *relative to their class*?

We can't compare raw scores directly — the scales are different! This is where the **Z-Score** comes in as a universal translator.

---

## 📖 Story: The Universal Translator

Think of the Z-score as a **universal translator** that converts any normal distribution into a common language — the **Standard Normal Distribution**.

Just like how different currencies can be converted to a single reference (like USD), different normal distributions can be converted to one standard reference: **N(0, 1)**.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Math Scores       Physics Scores      Chemistry Scores    │
│   N(70, 100)        N(65, 64)           N(80, 225)          │
│       │                 │                    │              │
│       │                 │                    │              │
│       └────────────────┼────────────────────┘              │
│                        │                                    │
│                        ▼                                    │
│              ┌─────────────────┐                            │
│              │ STANDARD NORMAL │                            │
│              │    N(0, 1)      │                            │
│              │  (Z-Scores)     │                            │
│              └─────────────────┘                            │
│                                                             │
│   Now all scores speak the same language!                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## What is the Standard Normal Distribution?

The **Standard Normal Distribution** is a special normal distribution with:

| Parameter | Value |
|-----------|-------|
| Mean (μ) | 0 |
| Standard Deviation (σ) | 1 |
| Variance (σ²) | 1 |

**Notation:** Z ~ N(0, 1)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              STANDARD NORMAL DISTRIBUTION                    │
│                                                             │
│   • Mean (μ) = 0  → Center is at zero                       │
│   • Std Dev (σ) = 1 → Spread is standardized                │
│   • Total area under curve = 1                              │
│   • Symmetric around 0                                      │
│                                                             │
│   Every normal distribution can be converted to this!       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Visualizing the Standard Normal

```
                              φ(z)
                               │
                        0.4    │    ╭───╮
                               │   ╭╯   ╰╮
                        0.3    │  ╭╯     ╰╮
                               │ ╭╯       ╰╮
                        0.2    │╭╯         ╰╮
                               ╭╯           ╰╮
                        0.1   ╭╯             ╰╮
                             ╭╯               ╰╮
                        0  ──╯─────────────────╰──────────────
                            -3   -2   -1   0   1   2   3
                                       z
                                       
                            ◄── 68.27% ──►
                       ◄────── 95.45% ──────►
                    ◄────────── 99.73% ──────────►
```

### The Standard Normal PDF

```
φ(z) = (1/√(2π)) × e^(-z²/2)
```

Since μ = 0 and σ = 1, the formula simplifies beautifully!

---

## What is a Z-Score?

The **Z-Score** (also called **standard score**) tells you **how many standard deviations** a value is **away from the mean**.

### The Z-Score Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    Z = (X - μ) / σ                          │
│                                                             │
│   Where:                                                    │
│   • X = the original value                                  │
│   • μ = mean of the distribution                            │
│   • σ = standard deviation of the distribution              │
│   • Z = the standardized value (Z-score)                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Intuitive Understanding

```
Z = (X - μ) / σ
    ═══════   ═══
       │       │
       │       └── Divided by "one unit" of spread
       │
       └── Distance from the mean
       
Z-Score = "How many standard deviations from the mean?"
```

---

## Z-Score Interpretation Guide

| Z-Score | Interpretation | Percentile (approx) |
|---------|----------------|---------------------|
| Z = -3 | 3 SD below mean (very rare, bottom) | 0.13% |
| Z = -2 | 2 SD below mean (unusual, low) | 2.28% |
| Z = -1 | 1 SD below mean (below average) | 15.87% |
| Z = 0 | Exactly at the mean (average) | 50% |
| Z = +1 | 1 SD above mean (above average) | 84.13% |
| Z = +2 | 2 SD above mean (unusual, high) | 97.72% |
| Z = +3 | 3 SD above mean (very rare, top) | 99.87% |

### Visual Interpretation

```
      Very    Below   Below  Average  Above   Above    Very
      Low     Avg     Avg             Avg     Avg      High
       │        │       │       │       │       │        │
       ▼        ▼       ▼       ▼       ▼       ▼        ▼
                           ╭───╮
                          ╭╯   ╰╮
                         ╭╯     ╰╮
                        ╭╯       ╰╮
                       ╭╯         ╰╮
                      ╭╯           ╰╮
                   ╭──╯             ╰──╮
              ╭────╯                   ╰────╮
         ─────╯                             ╰─────
              │     │     │     │     │     │     │
            -3σ   -2σ   -1σ    0    +1σ   +2σ   +3σ
            
         Z=-3   Z=-2   Z=-1   Z=0   Z=+1   Z=+2   Z=+3
```

---

## 📖 Solving the Student Comparison Problem

Let's find out who performed best relative to their class!

### Step 1: Calculate Each Z-Score

**Rina (Math):**
```
X = 85, μ = 70, σ = 10
Z = (85 - 70) / 10 = 15 / 10 = 1.5
```

**Kamal (Physics):**
```
X = 78, μ = 65, σ = 8
Z = (78 - 65) / 8 = 13 / 8 = 1.625
```

**Fatima (Chemistry):**
```
X = 92, μ = 80, σ = 15
Z = (92 - 80) / 15 = 12 / 15 = 0.8
```

### Step 2: Compare Z-Scores

| Student | Raw Score | Z-Score | Interpretation |
|---------|-----------|---------|----------------|
| Rina | 85 | **1.50** | 1.5 SD above class average |
| Kamal | 78 | **1.625** | 1.625 SD above class average |
| Fatima | 92 | **0.80** | 0.8 SD above class average |

### Winner: Kamal! 🏆

Even though Fatima had the highest raw score (92), **Kamal performed best relative to his class** because his Z-score (1.625) is highest!

---

## The Standardization Process

### From Any Normal to Standard Normal

```
Original Distribution              Standard Normal
    X ~ N(μ, σ²)                      Z ~ N(0, 1)
         │                               │
         │      Z = (X - μ)/σ            │
         │  ─────────────────────►       │
         │                               │
        ╭┴╮                             ╭┴╮
       ╭╯ ╰╮                           ╭╯ ╰╮
      ╭╯   ╰╮                         ╭╯   ╰╮
     ╭╯     ╰╮                       ╭╯     ╰╮
  ───╯───────╰───                 ───╯───────╰───
         μ                               0
         
Shift center to 0, scale spread to 1
```

### The Reverse: From Z to X

```
X = μ + Z × σ
```

This lets you convert Z-scores back to original units!

---

## The Standard Normal Table (Z-Table)

The Z-table gives **Φ(z) = P(Z ≤ z)** — the cumulative probability (area to the LEFT).

### How to Read the Z-Table

```
┌─────┬───────┬───────┬───────┬───────┬───────┐
│  z  │  .00  │  .01  │  .02  │  .03  │  .04  │
├─────┼───────┼───────┼───────┼───────┼───────┤
│ 0.0 │ .5000 │ .5040 │ .5080 │ .5120 │ .5160 │
│ 0.1 │ .5398 │ .5438 │ .5478 │ .5517 │ .5557 │
│ 0.2 │ .5793 │ .5832 │ .5871 │ .5910 │ .5948 │
│ ... │  ...  │  ...  │  ...  │  ...  │  ...  │
│ 1.0 │ .8413 │ .8438 │ .8461 │ .8485 │ .8508 │
│ 1.5 │ .9332 │ .9345 │ .9357 │ .9370 │ .9382 │
│ 2.0 │ .9772 │ .9778 │ .9783 │ .9788 │ .9793 │
└─────┴───────┴───────┴───────┴───────┴───────┘

To find P(Z ≤ 1.53):
• Row: 1.5
• Column: .03
• Answer: 0.9370
```

### Essential Z-Values to Memorize

| Z | P(Z ≤ z) | P(Z > z) | Meaning |
|---|----------|----------|---------|
| -3.00 | 0.0013 | 0.9987 | Bottom 0.13% |
| -2.58 | 0.0049 | 0.9951 | 99% CI bound |
| -2.33 | 0.0099 | 0.9901 | Bottom 1% |
| -2.00 | 0.0228 | 0.9772 | Bottom 2.28% |
| -1.96 | 0.0250 | 0.9750 | 95% CI bound |
| -1.645 | 0.0500 | 0.9500 | 90% CI bound |
| -1.00 | 0.1587 | 0.8413 | Bottom 15.87% |
| 0.00 | 0.5000 | 0.5000 | Median (50%) |
| 1.00 | 0.8413 | 0.1587 | Top 15.87% |
| 1.645 | 0.9500 | 0.0500 | Top 5% |
| 1.96 | 0.9750 | 0.0250 | Top 2.5% |
| 2.00 | 0.9772 | 0.0228 | Top 2.28% |
| 2.33 | 0.9901 | 0.0099 | Top 1% |
| 2.58 | 0.9951 | 0.0049 | Top 0.5% |
| 3.00 | 0.9987 | 0.0013 | Top 0.13% |

---

## Types of Z-Table Problems

### Type 1: Find P(Z < z) — Left Tail

```
Find P(Z < 1.25)

         ╭───╮
       ╭─╯███╰─╮
      ╭╯██████╰╮
     ╭╯████████╰╮
    ╭╯██████████╰╮
  ──╯████████████╰─────────
                1.25
                
Shaded = P(Z < 1.25) = 0.8944 (read directly from table)
```

---

### Type 2: Find P(Z > z) — Right Tail

```
Find P(Z > 1.25)

         ╭───╮
       ╭─╯   ╰█╮
      ╭╯      █╰╮
     ╭╯       ██╰╮
    ╭╯        ███╰╮
  ──╯         █████────────
                1.25
                
Shaded = P(Z > 1.25) = 1 - P(Z < 1.25) = 1 - 0.8944 = 0.1056
```

**Formula:** P(Z > z) = 1 - P(Z < z)

---

### Type 3: Find P(Z < -z) — Left Tail (Negative Z)

```
Find P(Z < -1.25)

         ╭───╮
       █╭╯   ╰─╮
      █╰╮      ╰╮
     ██╰╮       ╰╮
    ███╰╮        ╰╮
  ─████╯          ╰────────
    -1.25
                
Shaded = P(Z < -1.25) = 0.1056

By symmetry: P(Z < -z) = P(Z > z) = 1 - P(Z < z)
```

**Formula:** P(Z < -z) = 1 - P(Z < z)

---

### Type 4: Find P(a < Z < b) — Between Two Values

```
Find P(-1.5 < Z < 2.0)

         ╭───╮
       ╭█╯███╰█╮
      ╭█████████╮
     ╭███████████╰╮
    ╭█████████████╰╮
  ──╯██████████████╰───────
    -1.5          2.0
                
Shaded = P(Z < 2.0) - P(Z < -1.5)
       = 0.9772 - 0.0668
       = 0.9104
```

**Formula:** P(a < Z < b) = P(Z < b) - P(Z < a)

---

### Type 5: Find P(|Z| > z) — Both Tails

```
Find P(|Z| > 1.96) = P(Z < -1.96 OR Z > 1.96)

       ██╭───╮██
       █╭╯   ╰╮█
      █╭╯     ╰╮█
     █╭╯       ╰╮█
    █╭╯         ╰╮█
  ──█╯           ╰█────────
   -1.96         1.96
                
Shaded = P(Z < -1.96) + P(Z > 1.96)
       = 0.0250 + 0.0250
       = 0.05 (5%)
```

**Formula:** P(|Z| > z) = 2 × P(Z > z) = 2 × (1 - P(Z < z))

---

### Type 6: Find z Given Probability (Inverse)

```
Find z such that P(Z < z) = 0.90

         ╭───╮
       ╭─╯███╰─╮
      ╭╯██████╰╮
     ╭╯████████╰╮    90% of area
    ╭╯██████████╰╮   to the left
  ──╯████████████╰─────────
                 ?
                
From table: z = 1.28

P(Z < 1.28) ≈ 0.90
```

**Method:** Look up 0.90 in the body of the table, find corresponding z.

---

## Complete Problem-Solving Framework

### Converting X Problems to Z Problems

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   STEP 1: Identify μ and σ                                  │
│                                                             │
│   STEP 2: Determine what probability you need              │
│           • P(X < a) → P(Z < z_a)                          │
│           • P(X > a) → P(Z > z_a)                          │
│           • P(a < X < b) → P(z_a < Z < z_b)                │
│                                                             │
│   STEP 3: Convert X to Z                                    │
│           z = (X - μ) / σ                                   │
│                                                             │
│   STEP 4: Use Z-table to find probability                  │
│                                                             │
│   STEP 5: Interpret the result                             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Real-Life Examples

### Example 1: Test Scores

**Problem:** SAT scores follow N(1050, 200²). What percentage of students score above 1250?

```
Step 1: μ = 1050, σ = 200, X = 1250

Step 2: Want P(X > 1250)

Step 3: Z = (1250 - 1050) / 200 = 200 / 200 = 1.0

Step 4: P(Z > 1.0) = 1 - P(Z < 1.0) = 1 - 0.8413 = 0.1587

Answer: About 15.87% of students score above 1250
```

---

### Example 2: Manufacturing Quality

**Problem:** Bolts have diameter N(10 mm, 0.1² mm²). What percentage are between 9.8 and 10.2 mm?

```
Step 1: μ = 10, σ = 0.1

Step 2: Want P(9.8 < X < 10.2)

Step 3: Z₁ = (9.8 - 10) / 0.1 = -2.0
        Z₂ = (10.2 - 10) / 0.1 = 2.0

Step 4: P(-2 < Z < 2) = P(Z < 2) - P(Z < -2)
                      = 0.9772 - 0.0228
                      = 0.9544

Answer: About 95.44% of bolts are within specification
```

---

### Example 3: Finding a Percentile

**Problem:** IQ scores follow N(100, 15²). What IQ is needed to be in the top 5%?

```
Step 1: μ = 100, σ = 15

Step 2: Want X such that P(X > x) = 0.05
        This means P(X < x) = 0.95

Step 3: Find Z where P(Z < z) = 0.95
        Z = 1.645 (from table)

Step 4: Convert back: X = μ + Z × σ
        X = 100 + 1.645 × 15
        X = 100 + 24.675
        X = 124.68

Answer: IQ of about 125 is needed for the top 5%
```

---

### Example 4: Finding Probability Range

**Problem:** Heights of men follow N(175 cm, 8² cm²). A door is designed for men between 160 cm and 190 cm. What percentage can use it comfortably?

```
Step 1: μ = 175, σ = 8

Step 2: Want P(160 < X < 190)

Step 3: Z₁ = (160 - 175) / 8 = -1.875
        Z₂ = (190 - 175) / 8 = 1.875

Step 4: P(-1.875 < Z < 1.875) = P(Z < 1.875) - P(Z < -1.875)
                               = 0.9696 - 0.0304
                               = 0.9392

Answer: About 93.92% of men can use the door comfortably
```

---

### Example 5: Working Backwards

**Problem:** A teacher grades on a curve. The top 10% get A's. If scores are N(72, 9² ), what score is needed for an A?

```
Step 1: μ = 72, σ = 9

Step 2: Want X such that P(X > x) = 0.10
        This means P(X < x) = 0.90

Step 3: Z for 90th percentile = 1.28

Step 4: X = μ + Z × σ
        X = 72 + 1.28 × 9
        X = 72 + 11.52
        X = 83.52

Answer: A score of at least 84 is needed for an A
```

---

## Properties of Z-Scores

### 1. Mean of Z-Scores is 0

```
If X ~ N(μ, σ²), then Z = (X - μ)/σ has mean 0

E[Z] = E[(X - μ)/σ] = (E[X] - μ)/σ = (μ - μ)/σ = 0
```

### 2. Standard Deviation of Z-Scores is 1

```
Var[Z] = Var[(X - μ)/σ] = Var[X]/σ² = σ²/σ² = 1

Therefore, SD[Z] = √1 = 1
```

### 3. Z-Scores are Unitless

```
Z = (X - μ) / σ = (units - units) / units = no units!

This allows comparison across different scales.
```

### 4. Symmetry Property

```
P(Z < -z) = P(Z > z)
P(Z > -z) = P(Z < z)

Because the standard normal is symmetric around 0.
```

### 5. Linear Transformation Preserves Z-Scores

If you transform X with Y = aX + b, the Z-scores of corresponding values remain the same!

---

## Z-Scores in Different Contexts

### Academic Grading

| Z-Score Range | Grade | Description |
|---------------|-------|-------------|
| Z ≥ 2.0 | A+ | Exceptional |
| 1.5 ≤ Z < 2.0 | A | Excellent |
| 1.0 ≤ Z < 1.5 | B+ | Very Good |
| 0.5 ≤ Z < 1.0 | B | Good |
| 0 ≤ Z < 0.5 | C+ | Above Average |
| -0.5 ≤ Z < 0 | C | Average |
| -1.0 ≤ Z < -0.5 | D | Below Average |
| Z < -1.0 | F | Poor |

### Quality Control (Six Sigma)

| Sigma Level | Defects per Million | Z-Score |
|-------------|---------------------|---------|
| 1σ | 690,000 | ±1 |
| 2σ | 308,000 | ±2 |
| 3σ | 66,800 | ±3 |
| 4σ | 6,210 | ±4 |
| 5σ | 230 | ±5 |
| 6σ | 3.4 | ±6 |

### Outlier Detection

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   OUTLIER DETECTION RULES:                                   │
│                                                             │
│   • |Z| > 2: Unusual (outside 95%)                          │
│   • |Z| > 2.5: Very unusual                                 │
│   • |Z| > 3: Potential outlier (outside 99.7%)              │
│   • |Z| > 4: Almost certainly an outlier                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Comparing Z-Scores Across Distributions

### 📖 Story: The Job Applicants

Three candidates took different aptitude tests:

| Candidate | Test | Score | Mean | Std Dev | Z-Score |
|-----------|------|-------|------|---------|---------|
| Ahmed | Verbal | 580 | 500 | 50 | (580-500)/50 = **1.6** |
| Bella | Quantitative | 720 | 650 | 80 | (720-650)/80 = **0.875** |
| Chen | Logical | 45 | 38 | 4 | (45-38)/4 = **1.75** |

**Ranking by Z-Score:**
1. **Chen** (Z = 1.75) — Best relative performance
2. **Ahmed** (Z = 1.6)
3. **Bella** (Z = 0.875)

Even though Bella had the highest raw score (720), Chen performed best relative to the test-taking population!

---

## The Empirical Rule Revisited

With Z-scores, the Empirical Rule becomes crystal clear:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   P(-1 < Z < 1) = 68.27%   →  Middle 68% of data           │
│   P(-2 < Z < 2) = 95.45%   →  Middle 95% of data           │
│   P(-3 < Z < 3) = 99.73%   →  Middle 99.7% of data         │
│                                                             │
│   These percentages are EXACT for the standard normal!      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual Representation with Z-Scores

```
                         68.27%
                    ┌───────┴───────┐
                    │               │
                   ╭┴╮             ╭┴╮
                  ╭╯ ╰╮           ╭╯ ╰╮
                 ╭╯   ╰╮         ╭╯   ╰╮
                ╭╯     ╰╮       ╭╯     ╰╮
               ╭╯       ╰╮     ╭╯       ╰╮
              ╭╯         ╰╮   ╭╯         ╰╮
           ╭──╯           ╰───╯           ╰──╮
      ╭────╯                                 ╰────╮
  ────╯                                           ╰────
      │     │     │     │     │     │     │
    Z=-3  Z=-2  Z=-1   Z=0  Z=+1  Z=+2  Z=+3
    
   0.13%  2.15%  13.59% │ 13.59%  2.15%  0.13%
                 34.13% │ 34.13%
```

---

## Confidence Intervals Using Z-Scores

### Critical Z-Values for Confidence Intervals

| Confidence Level | α | α/2 | Z_(α/2) |
|------------------|---|-----|---------|
| 90% | 0.10 | 0.05 | 1.645 |
| 95% | 0.05 | 0.025 | 1.960 |
| 99% | 0.01 | 0.005 | 2.576 |

### Confidence Interval Formula

```
CI = X̄ ± Z_(α/2) × (σ/√n)

Where:
• X̄ = sample mean
• Z_(α/2) = critical Z-value
• σ = population standard deviation
• n = sample size
• σ/√n = standard error
```

### Example: Confidence Interval

**Problem:** A sample of n=100 has X̄=75, and σ=10. Find 95% CI for μ.

```
Z_(0.025) = 1.96
Standard Error = 10/√100 = 1

CI = 75 ± 1.96 × 1
CI = 75 ± 1.96
CI = (73.04, 76.96)

We are 95% confident μ is between 73.04 and 76.96
```

---

## Hypothesis Testing with Z-Scores

### The Z-Test Statistic

```
Z = (X̄ - μ₀) / (σ/√n)

Where:
• X̄ = sample mean
• μ₀ = hypothesized population mean
• σ = population standard deviation
• n = sample size
```

### Decision Rules

**Two-tailed test (H₁: μ ≠ μ₀):**
```
Reject H₀ if |Z| > Z_(α/2)
At α = 0.05: Reject if |Z| > 1.96
```

**Right-tailed test (H₁: μ > μ₀):**
```
Reject H₀ if Z > Z_α
At α = 0.05: Reject if Z > 1.645
```

**Left-tailed test (H₁: μ < μ₀):**
```
Reject H₀ if Z < -Z_α
At α = 0.05: Reject if Z < -1.645
```

---

## Python Implementation

### Basic Z-Score Calculations

```python
import numpy as np
from scipy import stats

# Calculate Z-score
def z_score(x, mu, sigma):
    """Calculate Z-score for value x"""
    return (x - mu) / sigma

# Convert Z-score back to X
def from_z_score(z, mu, sigma):
    """Convert Z-score to original value"""
    return mu + z * sigma

# Example: SSC scores
mu, sigma = 65, 12

# Student scored 89
x = 89
z = z_score(x, mu, sigma)
print(f"Score {x} has Z-score: {z:.2f}")  # 2.0

# What score corresponds to Z = 1.5?
z = 1.5
x = from_z_score(z, mu, sigma)
print(f"Z-score {z} corresponds to score: {x:.2f}")  # 83.0
```

### Using SciPy for Probabilities

```python
from scipy import stats

# Standard Normal Distribution
standard_normal = stats.norm(0, 1)

# P(Z < 1.96)
print(f"P(Z < 1.96) = {standard_normal.cdf(1.96):.4f}")  # 0.9750

# P(Z > 1.96)
print(f"P(Z > 1.96) = {1 - standard_normal.cdf(1.96):.4f}")  # 0.0250

# P(-1.96 < Z < 1.96)
prob = standard_normal.cdf(1.96) - standard_normal.cdf(-1.96)
print(f"P(-1.96 < Z < 1.96) = {prob:.4f}")  # 0.9500

# Find Z for given probability (inverse CDF)
print(f"Z for 95th percentile = {standard_normal.ppf(0.95):.4f}")  # 1.6449
print(f"Z for 97.5th percentile = {standard_normal.ppf(0.975):.4f}")  # 1.9600
```

### Standardizing a Dataset

```python
import numpy as np

# Original data
data = np.array([85, 90, 78, 92, 88, 76, 95, 82, 89, 91])

# Calculate mean and std
mu = np.mean(data)
sigma = np.std(data, ddof=0)  # population std

print(f"Original - Mean: {mu:.2f}, Std: {sigma:.2f}")

# Standardize (convert to Z-scores)
z_scores = (data - mu) / sigma

print(f"Z-scores: {z_scores.round(2)}")
print(f"Z-scores - Mean: {np.mean(z_scores):.2f}, Std: {np.std(z_scores):.2f}")
# Mean ≈ 0, Std ≈ 1
```

### Visualization

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

# Create standard normal
x = np.linspace(-4, 4, 1000)
y = stats.norm.pdf(x, 0, 1)

plt.figure(figsize=(12, 6))
plt.plot(x, y, 'b-', linewidth=2, label='Standard Normal N(0,1)')

# Shade areas
x_fill = np.linspace(-1, 1, 100)
plt.fill_between(x_fill, stats.norm.pdf(x_fill), alpha=0.3, 
                  color='green', label='68.27% (±1σ)')

x_fill = np.linspace(-2, 2, 100)
plt.fill_between(x_fill, stats.norm.pdf(x_fill), alpha=0.2, 
                  color='blue', label='95.45% (±2σ)')

# Mark key Z-values
for z in [-3, -2, -1, 0, 1, 2, 3]:
    plt.axvline(z, color='gray', linestyle='--', alpha=0.5)
    plt.text(z, -0.02, f'Z={z}', ha='center')

plt.xlabel('Z-Score')
plt.ylabel('Probability Density')
plt.title('Standard Normal Distribution')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()
```

---

## Complete Z-Table Reference

### Positive Z-Values: P(Z ≤ z)

```
┌──────┬────────┬────────┬────────┬────────┬────────┬────────┐
│   z  │   .00  │   .01  │   .02  │   .03  │   .04  │   .05  │
├──────┼────────┼────────┼────────┼────────┼────────┼────────┤
│  0.0 │ 0.5000 │ 0.5040 │ 0.5080 │ 0.5120 │ 0.5160 │ 0.5199 │
│  0.1 │ 0.5398 │ 0.5438 │ 0.5478 │ 0.5517 │ 0.5557 │ 0.5596 │
│  0.2 │ 0.5793 │ 0.5832 │ 0.5871 │ 0.5910 │ 0.5948 │ 0.5987 │
│  0.3 │ 0.6179 │ 0.6217 │ 0.6255 │ 0.6293 │ 0.6331 │ 0.6368 │
│  0.4 │ 0.6554 │ 0.6591 │ 0.6628 │ 0.6664 │ 0.6700 │ 0.6736 │
│  0.5 │ 0.6915 │ 0.6950 │ 0.6985 │ 0.7019 │ 0.7054 │ 0.7088 │
│  0.6 │ 0.7257 │ 0.7291 │ 0.7324 │ 0.7357 │ 0.7389 │ 0.7422 │
│  0.7 │ 0.7580 │ 0.7611 │ 0.7642 │ 0.7673 │ 0.7704 │ 0.7734 │
│  0.8 │ 0.7881 │ 0.7910 │ 0.7939 │ 0.7967 │ 0.7995 │ 0.8023 │
│  0.9 │ 0.8159 │ 0.8186 │ 0.8212 │ 0.8238 │ 0.8264 │ 0.8289 │
│  1.0 │ 0.8413 │ 0.8438 │ 0.8461 │ 0.8485 │ 0.8508 │ 0.8531 │
│  1.1 │ 0.8643 │ 0.8665 │ 0.8686 │ 0.8708 │ 0.8729 │ 0.8749 │
│  1.2 │ 0.8849 │ 0.8869 │ 0.8888 │ 0.8907 │ 0.8925 │ 0.8944 │
│  1.3 │ 0.9032 │ 0.9049 │ 0.9066 │ 0.9082 │ 0.9099 │ 0.9115 │
│  1.4 │ 0.9192 │ 0.9207 │ 0.9222 │ 0.9236 │ 0.9251 │ 0.9265 │
│  1.5 │ 0.9332 │ 0.9345 │ 0.9357 │ 0.9370 │ 0.9382 │ 0.9394 │
│  1.6 │ 0.9452 │ 0.9463 │ 0.9474 │ 0.9484 │ 0.9495 │ 0.9505 │
│  1.7 │ 0.9554 │ 0.9564 │ 0.9573 │ 0.9582 │ 0.9591 │ 0.9599 │
│  1.8 │ 0.9641 │ 0.9649 │ 0.9656 │ 0.9664 │ 0.9671 │ 0.9678 │
│  1.9 │ 0.9713 │ 0.9719 │ 0.9726 │ 0.9732 │ 0.9738 │ 0.9744 │
│  2.0 │ 0.9772 │ 0.9778 │ 0.9783 │ 0.9788 │ 0.9793 │ 0.9798 │
│  2.5 │ 0.9938 │ 0.9940 │ 0.9941 │ 0.9943 │ 0.9945 │ 0.9946 │
│  3.0 │ 0.9987 │ 0.9987 │ 0.9987 │ 0.9988 │ 0.9988 │ 0.9989 │
└──────┴────────┴────────┴────────┴────────┴────────┴────────┘

For negative Z: P(Z ≤ -z) = 1 - P(Z ≤ z)
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Forgetting to Standardize

❌ **Wrong:** Looking up X = 75 directly in Z-table

✅ **Correct:** First convert: Z = (75 - μ) / σ, then use Z-table

---

### Mistake 2: Wrong Tail Direction

❌ **Wrong:** P(Z > 1.5) = 0.9332 (reading table directly)

✅ **Correct:** P(Z > 1.5) = 1 - P(Z < 1.5) = 1 - 0.9332 = 0.0668

---

### Mistake 3: Confusing σ and σ²

❌ **Wrong:** Z = (X - μ) / σ² (using variance)

✅ **Correct:** Z = (X - μ) / σ (using standard deviation)

---

### Mistake 4: Negative Z-Score Confusion

❌ **Wrong:** Z = -1.5 means something is wrong

✅ **Correct:** Negative Z simply means below the mean — perfectly normal!

---

### Mistake 5: Assuming Z-Tables Give Right Tail

❌ **Wrong:** Looking up Z = 2 and getting 0.0228 for P(Z < 2)

✅ **Correct:** Standard Z-tables give LEFT tail (cumulative from left)
   P(Z < 2) = 0.9772, P(Z > 2) = 0.0228

---

## Practice Problems 📝

### Problem 1: Basic Z-Score
A student scores 82 on a test with mean 75 and standard deviation 5. What is their Z-score?

<details>
<summary>Click for Answer</summary>

```
Z = (X - μ) / σ
Z = (82 - 75) / 5
Z = 7 / 5
Z = 1.4

The student is 1.4 standard deviations above the mean.
```

</details>

---

### Problem 2: Finding Probability
For Z ~ N(0, 1), find P(Z > 1.65).

<details>
<summary>Click for Answer</summary>

```
P(Z > 1.65) = 1 - P(Z < 1.65)
            = 1 - 0.9505
            = 0.0495

About 4.95% probability.
```

</details>

---

### Problem 3: Between Two Values
Find P(-1.25 < Z < 0.75).

<details>
<summary>Click for Answer</summary>

```
P(-1.25 < Z < 0.75) = P(Z < 0.75) - P(Z < -1.25)
                    = 0.7734 - 0.1056
                    = 0.6678

About 66.78% probability.
```

</details>

---

### Problem 4: Inverse Z
What Z-score corresponds to the 80th percentile?

<details>
<summary>Click for Answer</summary>

```
P(Z < z) = 0.80

Looking up 0.80 in the table body:
z ≈ 0.84

The 80th percentile corresponds to Z = 0.84
```

</details>

---

### Problem 5: Full Application
Heights of adults follow N(170, 64). What percentage are taller than 180 cm?

<details>
<summary>Click for Answer</summary>

```
μ = 170, σ² = 64, so σ = 8
X = 180

Z = (180 - 170) / 8 = 10 / 8 = 1.25

P(X > 180) = P(Z > 1.25)
           = 1 - P(Z < 1.25)
           = 1 - 0.8944
           = 0.1056

About 10.56% are taller than 180 cm.
```

</details>

---

## Summary: The Essence of Z-Scores

```
┌─────────────────────────────────────────────────────────────────┐
│           STANDARD NORMAL DISTRIBUTION & Z-SCORES                │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   STANDARD NORMAL: Z ~ N(0, 1)                                   │
│   • Mean = 0, Standard Deviation = 1                             │
│   • The "universal reference" for all normal distributions       │
│                                                                  │
│   Z-SCORE FORMULA:                                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                          │   │
│   │              Z = (X - μ) / σ                             │   │
│   │                                                          │   │
│   │   "How many standard deviations from the mean?"          │   │
│   │                                                          │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY PROPERTIES:                                                │
│   • Z-scores have mean 0 and std dev 1                           │
│   • Z-scores are unitless (allow cross-comparison)              │
│   • Negative Z = below mean, Positive Z = above mean            │
│                                                                  │
│   COMMON Z-VALUES:                                               │
│   • Z = ±1.645 → 90% CI                                          │
│   • Z = ±1.96  → 95% CI                                          │
│   • Z = ±2.576 → 99% CI                                          │
│                                                                  │
│   REVERSE FORMULA:                                               │
│   X = μ + Z × σ                                                  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Z-Scores Matter

| Application | How Z-Scores Help |
|-------------|-------------------|
| **Comparing Different Scales** | Convert to common scale |
| **Finding Percentiles** | Use Z-table to find percentages |
| **Outlier Detection** | Flag values with |Z| > 3 |
| **Confidence Intervals** | Use critical Z-values |
| **Hypothesis Testing** | Calculate test statistics |
| **Quality Control** | Six Sigma methodology |
| **Standardized Testing** | SAT, GRE, IQ scores |

> **"The Z-score is statistics' universal translator — turning any normal distribution into a language we can all understand."**

Master Z-scores, and you've mastered the key to unlocking the power of the normal distribution! 🚀

---

*From raw scores to universal comparisons — that's the magic of standardization!* ✨
# Z-Test: Hypothesis Testing
## Testing Hypotheses When You Know the Population Standard Deviation 📊

---

## What is a Z-Test?

The **Z-Test** is a statistical hypothesis test that uses the **standard normal distribution (Z-distribution)** to determine whether there is a significant difference between:

- A sample mean and a population mean
- A sample proportion and a population proportion
- Two sample means or proportions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                      Z-TEST                                  │
│                                                             │
│   Use When:                                                 │
│   • Population standard deviation (σ) is KNOWN              │
│   • Sample size is LARGE (n ≥ 30)                          │
│   • Data is approximately normally distributed              │
│     (or n is large enough for CLT to apply)                │
│                                                             │
│   The test statistic follows: Z ~ N(0, 1)                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: The Mystery of the Light Bulbs

Fatima works as a quality inspector at a light bulb factory in Chittagong. The factory claims their bulbs last **μ = 1000 hours** on average, with a known standard deviation of **σ = 50 hours** (from years of production data).

Recently, Fatima noticed some customer complaints. She suspects the new batch might be different. She tests **n = 50 bulbs** and finds:

- Sample mean: X̄ = 985 hours

**Question:** Is there enough evidence to conclude this batch is different from the standard?

This is exactly where the Z-test comes in!

---

## Z-Test vs t-Test: When to Use Which?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   USE Z-TEST WHEN:              USE t-TEST WHEN:            │
│   ─────────────────             ─────────────────           │
│   • σ is KNOWN                  • σ is UNKNOWN              │
│   • Large sample (n ≥ 30)       • Small sample (n < 30)     │
│   • Testing proportions         • Estimating σ from sample  │
│                                                             │
│   In practice:                                              │
│   • t-test is more common (σ rarely known)                 │
│   • Z-test used mainly for proportions                     │
│   • With large n, Z and t give similar results             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Z vs t Distribution

```
                    Z-distribution (standard normal)
                    t-distribution (heavier tails)
                    
                         ╭───╮  ← Z (taller, thinner)
                       ╭─╯ t ╰─╮
                      ╭╯  ╭─╮  ╰╮  ← t (shorter, fatter tails)
                     ╭╯  ╭╯ ╰╮  ╰╮
                    ╭╯  ╭╯   ╰╮  ╰╮
                   ╭╯  ╭╯     ╰╮  ╰╮
                  ╭╯ ╭─╯       ╰─╮ ╰╮
               ──╯──╯─────────────╰──╰──
                          0
                          
As sample size increases, t → Z (they converge)
```

---

## Types of Z-Tests

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    TYPES OF Z-TESTS                          │
│                                                             │
│   1. ONE-SAMPLE Z-TEST (for means)                          │
│      Compare sample mean to known population mean           │
│                                                             │
│   2. ONE-SAMPLE Z-TEST (for proportions)                    │
│      Compare sample proportion to known population          │
│      proportion                                             │
│                                                             │
│   3. TWO-SAMPLE Z-TEST (for means)                          │
│      Compare means of two independent groups                │
│                                                             │
│   4. TWO-SAMPLE Z-TEST (for proportions)                    │
│      Compare proportions of two independent groups          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

# Part 1: One-Sample Z-Test for Means
## *Is the sample mean different from the population mean?*

---

## The Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ONE-SAMPLE Z-TEST FOR MEANS                                │
│                                                             │
│   Hypotheses:                                               │
│   H₀: μ = μ₀  (population mean equals claimed value)       │
│   H₁: μ ≠ μ₀  (two-tailed)                                 │
│       μ > μ₀  (right-tailed)                               │
│       μ < μ₀  (left-tailed)                                │
│                                                             │
│   Test Statistic:                                           │
│                                                             │
│              X̄ - μ₀                                         │
│        Z = ──────────                                       │
│              σ / √n                                         │
│                                                             │
│   Where:                                                    │
│   • X̄ = sample mean                                        │
│   • μ₀ = hypothesized population mean                      │
│   • σ = population standard deviation (KNOWN)              │
│   • n = sample size                                         │
│                                                             │
│   Standard Error: SE = σ / √n                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Step-by-Step: Light Bulb Example

### Step 1: State the Hypotheses

```
H₀: μ = 1000 hours (bulbs meet specification)
H₁: μ ≠ 1000 hours (bulbs are different)

This is a TWO-TAILED test (we care about any difference)
α = 0.05
```

### Step 2: Identify the Given Information

```
Sample mean:       X̄ = 985 hours
Population mean:   μ₀ = 1000 hours
Population σ:      σ = 50 hours
Sample size:       n = 50
Significance:      α = 0.05
```

### Step 3: Calculate the Standard Error

```
       σ        50
SE = ───── = ─────── = 7.07 hours
      √n      √50
```

### Step 4: Calculate the Test Statistic

```
       X̄ - μ₀     985 - 1000     -15
Z = ────────── = ──────────── = ────── = -2.12
        SE          7.07        7.07
```

### Step 5: Find the Critical Values and p-value

```
For two-tailed test at α = 0.05:
Critical values: Z_crit = ±1.96

Our Z = -2.12

Since |-2.12| > 1.96, Z is in the rejection region!

p-value = 2 × P(Z < -2.12)
        = 2 × 0.0170
        = 0.034
```

### Step 6: Visualize the Test

```
                    Standard Normal Distribution
                    
                           ╭───╮
                         ╭─╯   ╰─╮
                        ╭╯       ╰╮
                       ╭╯         ╰╮
                      ╭╯           ╰╮
              ████████╯             ╰████████
             █████████│             │█████████
           ──┼────────┼──────┬──────┼────────┼──
           -2.12   -1.96    0     1.96     2.12
             ▲        │             │
             │        │  α/2=0.025  │
        Our Z│        └─────────────┘
             │         Fail to Reject
             │
        In Rejection Region!
        
p-value = 0.034 (shaded areas beyond ±2.12)
```

### Step 7: Make a Decision

```
METHOD 1: Using p-value
p-value = 0.034 < α = 0.05
→ REJECT H₀

METHOD 2: Using critical values
|Z| = 2.12 > Z_crit = 1.96
→ REJECT H₀

Both methods give the same conclusion!
```

### Step 8: State the Conclusion

```
STATISTICAL CONCLUSION:
"At the α = 0.05 significance level, we reject H₀."

PRACTICAL CONCLUSION:
"There is sufficient evidence to conclude that the mean 
lifetime of bulbs in this batch (985 hours) is significantly 
different from the claimed 1000 hours (Z = -2.12, p = 0.034).

The batch appears to have shorter-lasting bulbs than 
specified. Quality control should investigate."
```

---

## Effect Size: Cohen's d

```
Beyond just "significant," how big is the effect?

        X̄ - μ₀     985 - 1000
d = ──────────── = ────────── = -0.30
          σ            50

|d| = 0.30 → Small to medium effect

Interpretation:
• |d| < 0.2: Negligible
• |d| ≈ 0.2: Small
• |d| ≈ 0.5: Medium
• |d| ≈ 0.8: Large

The bulbs are about 0.3 standard deviations below target.
```

---

# Part 2: One-Sample Z-Test for Proportions
## *Is the sample proportion different from the claimed proportion?*

---

## 📖 Story: The Election Poll

A political analyst claims that **60% of voters** in Dhaka support Candidate A. A news organization conducts a poll of **n = 500 voters** and finds that **280 support Candidate A** (p̂ = 0.56).

**Question:** Is this significantly different from the claimed 60%?

---

## The Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ONE-SAMPLE Z-TEST FOR PROPORTIONS                          │
│                                                             │
│   Hypotheses:                                               │
│   H₀: p = p₀  (proportion equals claimed value)            │
│   H₁: p ≠ p₀  (two-tailed)                                 │
│       p > p₀  (right-tailed)                               │
│       p < p₀  (left-tailed)                                │
│                                                             │
│   Test Statistic:                                           │
│                                                             │
│              p̂ - p₀                                         │
│        Z = ─────────────────                                │
│            √(p₀(1-p₀)/n)                                    │
│                                                             │
│   Where:                                                    │
│   • p̂ = sample proportion = X/n                            │
│   • p₀ = hypothesized population proportion                │
│   • n = sample size                                         │
│                                                             │
│   CONDITIONS (for normal approximation):                    │
│   • np₀ ≥ 10                                               │
│   • n(1-p₀) ≥ 10                                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Step-by-Step: Election Poll Example

### Step 1: State the Hypotheses

```
H₀: p = 0.60 (60% support as claimed)
H₁: p ≠ 0.60 (support is different)

α = 0.05, two-tailed test
```

### Step 2: Check Conditions

```
np₀ = 500 × 0.60 = 300 ≥ 10 ✓
n(1-p₀) = 500 × 0.40 = 200 ≥ 10 ✓

Normal approximation is valid!
```

### Step 3: Calculate Sample Proportion and Standard Error

```
       X      280
p̂ = ───── = ───── = 0.56
       n      500

            _______________
           /  p₀(1-p₀)         /  0.60 × 0.40
SE = \    / ────────────  = \  / ──────────────
      \  /       n             \/      500

SE = √(0.24/500) = √0.00048 = 0.0219
```

### Step 4: Calculate the Test Statistic

```
       p̂ - p₀       0.56 - 0.60     -0.04
Z = ────────────── = ──────────── = ─────── = -1.83
         SE           0.0219        0.0219
```

### Step 5: Find the p-value

```
For Z = -1.83 (two-tailed):

p-value = 2 × P(Z < -1.83)
        = 2 × 0.0336
        = 0.0672 ≈ 0.067
```

### Step 6: Make a Decision

```
p-value = 0.067 > α = 0.05

DECISION: FAIL TO REJECT H₀

(Also: |Z| = 1.83 < 1.96 = Z_crit)
```

### Step 7: State the Conclusion

```
"At the α = 0.05 significance level, there is insufficient 
evidence to conclude that voter support differs from 60% 
(Z = -1.83, p = 0.067).

The poll result of 56% is consistent with the claimed 60% 
support — the 4 percentage point difference could be due 
to sampling variability."

NOTE: At α = 0.10, we WOULD reject H₀ (since 0.067 < 0.10)
```

---

# Part 3: Two-Sample Z-Test for Means
## *Are the means of two populations different?*

---

## 📖 Story: Comparing Two Factories

A company has two factories producing batteries:

**Factory A:** n₁ = 40 batteries, X̄₁ = 85 hours, σ₁ = 10 hours
**Factory B:** n₂ = 50 batteries, X̄₂ = 82 hours, σ₂ = 12 hours

**Question:** Is there a significant difference in mean battery life?

---

## The Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TWO-SAMPLE Z-TEST FOR MEANS                                │
│                                                             │
│   Hypotheses:                                               │
│   H₀: μ₁ = μ₂  (or μ₁ - μ₂ = 0)                            │
│   H₁: μ₁ ≠ μ₂  (two-tailed)                                │
│       μ₁ > μ₂  (right-tailed)                              │
│       μ₁ < μ₂  (left-tailed)                               │
│                                                             │
│   Test Statistic:                                           │
│                                                             │
│              (X̄₁ - X̄₂) - (μ₁ - μ₂)₀                        │
│        Z = ───────────────────────────                      │
│              √(σ₁²/n₁ + σ₂²/n₂)                             │
│                                                             │
│   Usually (μ₁ - μ₂)₀ = 0, so:                              │
│                                                             │
│                   X̄₁ - X̄₂                                   │
│        Z = ─────────────────────                            │
│            √(σ₁²/n₁ + σ₂²/n₂)                               │
│                                                             │
│   Requirements:                                              │
│   • Both σ₁ and σ₂ are KNOWN                               │
│   • Independent samples                                      │
│   • Large samples or normal populations                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Step-by-Step: Factory Comparison Example

### Step 1: State the Hypotheses

```
H₀: μ₁ = μ₂ (no difference between factories)
H₁: μ₁ ≠ μ₂ (factories are different)

α = 0.05, two-tailed test
```

### Step 2: Calculate the Standard Error

```
            _______________
           /  σ₁²     σ₂²
SE = \    / ────── + ──────
      \  /    n₁       n₂

SE = √(10²/40 + 12²/50)
   = √(100/40 + 144/50)
   = √(2.5 + 2.88)
   = √5.38
   = 2.32
```

### Step 3: Calculate the Test Statistic

```
       X̄₁ - X̄₂      85 - 82       3
Z = ──────────── = ────────── = ────── = 1.29
         SE          2.32       2.32
```

### Step 4: Find the p-value

```
For Z = 1.29 (two-tailed):

p-value = 2 × P(Z > 1.29)
        = 2 × (1 - 0.9015)
        = 2 × 0.0985
        = 0.197
```

### Step 5: Make a Decision

```
p-value = 0.197 > α = 0.05

DECISION: FAIL TO REJECT H₀

The 3-hour difference is not statistically significant.
```

### Step 6: State the Conclusion

```
"At the α = 0.05 significance level, there is insufficient 
evidence to conclude that the mean battery life differs 
between Factory A (85 hours) and Factory B (82 hours) 
(Z = 1.29, p = 0.197).

The observed 3-hour difference could reasonably be due 
to random sampling variation."
```

---

# Part 4: Two-Sample Z-Test for Proportions
## *Are two population proportions different?*

---

## 📖 Story: Comparing Treatment Success Rates

A hospital compares two treatment methods for a condition:

**Treatment A:** 120 successes out of 200 patients (p̂₁ = 0.60)
**Treatment B:** 90 successes out of 180 patients (p̂₂ = 0.50)

**Question:** Is Treatment A significantly more effective?

---

## The Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TWO-SAMPLE Z-TEST FOR PROPORTIONS                          │
│                                                             │
│   Hypotheses:                                               │
│   H₀: p₁ = p₂  (proportions are equal)                     │
│   H₁: p₁ ≠ p₂  (two-tailed)                                │
│       p₁ > p₂  (right-tailed)                              │
│       p₁ < p₂  (left-tailed)                               │
│                                                             │
│   Pooled Proportion (under H₀: p₁ = p₂):                   │
│                                                             │
│            X₁ + X₂                                          │
│        p̂ = ──────────                                       │
│            n₁ + n₂                                          │
│                                                             │
│   Test Statistic:                                           │
│                                                             │
│                  p̂₁ - p̂₂                                    │
│        Z = ─────────────────────────                        │
│            √(p̂(1-p̂)(1/n₁ + 1/n₂))                          │
│                                                             │
│   CONDITIONS:                                               │
│   • n₁p̂ ≥ 5, n₁(1-p̂) ≥ 5                                  │
│   • n₂p̂ ≥ 5, n₂(1-p̂) ≥ 5                                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Step-by-Step: Treatment Comparison Example

### Step 1: State the Hypotheses

```
H₀: p₁ = p₂ (treatments equally effective)
H₁: p₁ > p₂ (Treatment A is more effective)

α = 0.05, RIGHT-TAILED test
```

### Step 2: Calculate Sample Proportions

```
       X₁      120
p̂₁ = ───── = ───── = 0.60
       n₁      200

       X₂       90
p̂₂ = ───── = ───── = 0.50
       n₂      180
```

### Step 3: Calculate Pooled Proportion

```
       X₁ + X₂       120 + 90      210
p̂ = ────────────── = ────────── = ───── = 0.553
       n₁ + n₂       200 + 180     380
```

### Step 4: Check Conditions

```
n₁p̂ = 200 × 0.553 = 110.6 ≥ 5 ✓
n₁(1-p̂) = 200 × 0.447 = 89.4 ≥ 5 ✓
n₂p̂ = 180 × 0.553 = 99.5 ≥ 5 ✓
n₂(1-p̂) = 180 × 0.447 = 80.5 ≥ 5 ✓

All conditions met!
```

### Step 5: Calculate the Standard Error

```
SE = √(p̂(1-p̂)(1/n₁ + 1/n₂))
   = √(0.553 × 0.447 × (1/200 + 1/180))
   = √(0.247 × (0.005 + 0.00556))
   = √(0.247 × 0.01056)
   = √0.00261
   = 0.0511
```

### Step 6: Calculate the Test Statistic

```
       p̂₁ - p̂₂      0.60 - 0.50      0.10
Z = ──────────── = ────────────── = ────── = 1.96
         SE           0.0511        0.0511
```

### Step 7: Find the p-value

```
For Z = 1.96 (right-tailed):

p-value = P(Z > 1.96) = 1 - 0.9750 = 0.025
```

### Step 8: Make a Decision

```
p-value = 0.025 < α = 0.05

DECISION: REJECT H₀

(Also: Z = 1.96 > 1.645 = Z_crit for one-tailed)
```

### Step 9: State the Conclusion

```
"At the α = 0.05 significance level, there is sufficient 
evidence to conclude that Treatment A (60% success rate) 
is more effective than Treatment B (50% success rate) 
(Z = 1.96, p = 0.025).

The 10 percentage point difference in success rates is 
statistically significant."
```

---

## Critical Values: Quick Reference

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   CRITICAL VALUES FOR Z-TEST                                     │
│                                                                  │
│   Significance     Two-Tailed         One-Tailed                │
│   Level (α)        (|Z| > z)          (Z > z or Z < -z)         │
│   ────────────     ──────────         ─────────────────         │
│   0.10             ±1.645             ±1.28                     │
│   0.05             ±1.96              ±1.645                    │
│   0.01             ±2.576             ±2.33                     │
│   0.001            ±3.29              ±3.09                     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Visual: Rejection Regions

```
TWO-TAILED (α = 0.05)             ONE-TAILED RIGHT (α = 0.05)

     α/2=0.025    α/2=0.025                           α=0.05
         │            │                                  │
         ▼            ▼                                  ▼
     ╭────────────────────╮               ╭────────────────────╮
   ╭─╯                    ╰─╮           ╭─╯                    ╰█
  ╭╯                        ╰╮         ╭╯                      ╰██
 ╭╯                          ╰╮       ╭╯                        ╰███
█╯                            ╰█     ╭╯                          ╰████
────┬───────────┬───────────┬────   ─────────────────────┬──────────
  -1.96         0         1.96                         1.645
    │                       │                            │
 REJECT      FAIL TO     REJECT            FAIL TO    REJECT
            REJECT                         REJECT
```

---

## Z-Test Summary Table

```
┌─────────────────────────────────────────────────────────────────┐
│                    Z-TEST FORMULA SUMMARY                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   TEST                    FORMULA                                │
│   ────                    ───────                                │
│                                                                  │
│   One-Sample              Z = (X̄ - μ₀) / (σ/√n)                 │
│   (Mean)                                                         │
│                                                                  │
│   One-Sample              Z = (p̂ - p₀) / √(p₀(1-p₀)/n)          │
│   (Proportion)                                                   │
│                                                                  │
│   Two-Sample              Z = (X̄₁ - X̄₂) / √(σ₁²/n₁ + σ₂²/n₂)   │
│   (Means)                                                        │
│                                                                  │
│   Two-Sample              Z = (p̂₁ - p̂₂) / √(p̂(1-p̂)(1/n₁+1/n₂)) │
│   (Proportions)           where p̂ = (X₁+X₂)/(n₁+n₂)             │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Python Implementation

### Complete Z-Test Functions

```python
import numpy as np
from scipy import stats

# ============================================
# ONE-SAMPLE Z-TEST FOR MEAN
# ============================================
def z_test_one_sample_mean(x_bar, mu0, sigma, n, alternative='two-sided'):
    """
    One-sample Z-test for population mean
    
    Parameters:
    - x_bar: sample mean
    - mu0: hypothesized population mean
    - sigma: known population standard deviation
    - n: sample size
    - alternative: 'two-sided', 'greater', 'less'
    """
    se = sigma / np.sqrt(n)
    z = (x_bar - mu0) / se
    
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.norm.cdf(abs(z)))
    elif alternative == 'greater':
        p_value = 1 - stats.norm.cdf(z)
    else:  # less
        p_value = stats.norm.cdf(z)
    
    return {'z_statistic': z, 'p_value': p_value, 'se': se}

# Example: Light bulb test
result = z_test_one_sample_mean(x_bar=985, mu0=1000, sigma=50, n=50, alternative='two-sided')
print("=== One-Sample Z-Test for Mean ===")
print(f"Z-statistic: {result['z_statistic']:.4f}")
print(f"p-value: {result['p_value']:.4f}")
print(f"Standard Error: {result['se']:.4f}")


# ============================================
# ONE-SAMPLE Z-TEST FOR PROPORTION
# ============================================
def z_test_one_sample_proportion(x, n, p0, alternative='two-sided'):
    """
    One-sample Z-test for population proportion
    
    Parameters:
    - x: number of successes
    - n: sample size
    - p0: hypothesized proportion
    - alternative: 'two-sided', 'greater', 'less'
    """
    p_hat = x / n
    se = np.sqrt(p0 * (1 - p0) / n)
    z = (p_hat - p0) / se
    
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.norm.cdf(abs(z)))
    elif alternative == 'greater':
        p_value = 1 - stats.norm.cdf(z)
    else:
        p_value = stats.norm.cdf(z)
    
    return {'z_statistic': z, 'p_value': p_value, 'p_hat': p_hat, 'se': se}

# Example: Election poll
result = z_test_one_sample_proportion(x=280, n=500, p0=0.60, alternative='two-sided')
print("\n=== One-Sample Z-Test for Proportion ===")
print(f"Sample proportion: {result['p_hat']:.4f}")
print(f"Z-statistic: {result['z_statistic']:.4f}")
print(f"p-value: {result['p_value']:.4f}")


# ============================================
# TWO-SAMPLE Z-TEST FOR MEANS
# ============================================
def z_test_two_sample_means(x1_bar, x2_bar, sigma1, sigma2, n1, n2, alternative='two-sided'):
    """
    Two-sample Z-test for comparing population means
    """
    se = np.sqrt(sigma1**2/n1 + sigma2**2/n2)
    z = (x1_bar - x2_bar) / se
    
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.norm.cdf(abs(z)))
    elif alternative == 'greater':
        p_value = 1 - stats.norm.cdf(z)
    else:
        p_value = stats.norm.cdf(z)
    
    return {'z_statistic': z, 'p_value': p_value, 'se': se, 'diff': x1_bar - x2_bar}

# Example: Factory comparison
result = z_test_two_sample_means(x1_bar=85, x2_bar=82, sigma1=10, sigma2=12, 
                                  n1=40, n2=50, alternative='two-sided')
print("\n=== Two-Sample Z-Test for Means ===")
print(f"Difference: {result['diff']:.4f}")
print(f"Z-statistic: {result['z_statistic']:.4f}")
print(f"p-value: {result['p_value']:.4f}")


# ============================================
# TWO-SAMPLE Z-TEST FOR PROPORTIONS
# ============================================
def z_test_two_sample_proportions(x1, n1, x2, n2, alternative='two-sided'):
    """
    Two-sample Z-test for comparing population proportions
    """
    p1_hat = x1 / n1
    p2_hat = x2 / n2
    p_pooled = (x1 + x2) / (n1 + n2)
    
    se = np.sqrt(p_pooled * (1 - p_pooled) * (1/n1 + 1/n2))
    z = (p1_hat - p2_hat) / se
    
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.norm.cdf(abs(z)))
    elif alternative == 'greater':
        p_value = 1 - stats.norm.cdf(z)
    else:
        p_value = stats.norm.cdf(z)
    
    return {'z_statistic': z, 'p_value': p_value, 'p1_hat': p1_hat, 
            'p2_hat': p2_hat, 'p_pooled': p_pooled}

# Example: Treatment comparison
result = z_test_two_sample_proportions(x1=120, n1=200, x2=90, n2=180, alternative='greater')
print("\n=== Two-Sample Z-Test for Proportions ===")
print(f"Proportion 1: {result['p1_hat']:.4f}")
print(f"Proportion 2: {result['p2_hat']:.4f}")
print(f"Pooled: {result['p_pooled']:.4f}")
print(f"Z-statistic: {result['z_statistic']:.4f}")
print(f"p-value: {result['p_value']:.4f}")
```

### Visualization Function

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

def visualize_z_test(z_stat, alternative='two-sided', alpha=0.05):
    """Visualize Z-test with rejection regions"""
    
    fig, ax = plt.subplots(figsize=(12, 6))
    
    x = np.linspace(-4, 4, 1000)
    y = stats.norm.pdf(x)
    
    # Plot distribution
    ax.plot(x, y, 'b-', linewidth=2, label='Standard Normal')
    ax.fill_between(x, y, alpha=0.1)
    
    # Rejection regions
    if alternative == 'two-sided':
        z_crit = stats.norm.ppf(1 - alpha/2)
        ax.fill_between(x[x >= z_crit], stats.norm.pdf(x[x >= z_crit]), 
                       color='red', alpha=0.4, label=f'Rejection (α/2={alpha/2})')
        ax.fill_between(x[x <= -z_crit], stats.norm.pdf(x[x <= -z_crit]), 
                       color='red', alpha=0.4)
        ax.axvline(-z_crit, color='red', linestyle='--')
        ax.axvline(z_crit, color='red', linestyle='--')
        p_value = 2 * (1 - stats.norm.cdf(abs(z_stat)))
        
    elif alternative == 'greater':
        z_crit = stats.norm.ppf(1 - alpha)
        ax.fill_between(x[x >= z_crit], stats.norm.pdf(x[x >= z_crit]), 
                       color='red', alpha=0.4, label=f'Rejection (α={alpha})')
        ax.axvline(z_crit, color='red', linestyle='--')
        p_value = 1 - stats.norm.cdf(z_stat)
        
    else:  # less
        z_crit = stats.norm.ppf(alpha)
        ax.fill_between(x[x <= z_crit], stats.norm.pdf(x[x <= z_crit]), 
                       color='red', alpha=0.4, label=f'Rejection (α={alpha})')
        ax.axvline(z_crit, color='red', linestyle='--')
        p_value = stats.norm.cdf(z_stat)
    
    # Test statistic
    ax.axvline(z_stat, color='green', linewidth=2.5, label=f'Z = {z_stat:.3f}')
    ax.plot(z_stat, stats.norm.pdf(z_stat), 'go', markersize=10)
    
    # Decision
    reject = p_value < alpha
    decision = "REJECT H₀" if reject else "FAIL TO REJECT H₀"
    
    ax.set_xlabel('Z-value', fontsize=12)
    ax.set_ylabel('Density', fontsize=12)
    ax.set_title(f'Z-Test ({alternative})\np-value = {p_value:.4f} | {decision}', fontsize=14)
    ax.legend()
    ax.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()

# Visualize the light bulb example
visualize_z_test(z_stat=-2.12, alternative='two-sided', alpha=0.05)
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Using Z-Test When σ is Unknown

```
❌ Wrong: Using Z-test with sample standard deviation s
✅ Correct: Use t-test when σ is unknown
```

### Mistake 2: Ignoring Sample Size Requirements

```
❌ Wrong: Z-test with n = 10
✅ Correct: Need n ≥ 30 for CLT (or use t-test)
```

### Mistake 3: Not Checking Proportion Conditions

```
❌ Wrong: Z-test for proportion when np₀ < 10
✅ Correct: Verify np₀ ≥ 10 AND n(1-p₀) ≥ 10
```

### Mistake 4: One-Tailed After Seeing Data

```
❌ Wrong: Choosing one-tailed because data goes that direction
✅ Correct: Specify alternative BEFORE collecting data
```

---

## Practice Problems 📝

### Problem 1
A coffee shop claims cups contain μ = 350ml. Testing n = 64 cups gives X̄ = 345ml. Known σ = 20ml. Test at α = 0.05.

<details>
<summary>Click for Solution</summary>

```
H₀: μ = 350, H₁: μ ≠ 350
Z = (345-350)/(20/√64) = -5/2.5 = -2.0
p-value = 2×P(Z<-2) = 0.0456 < 0.05
REJECT H₀: Cups contain significantly less.
```
</details>

### Problem 2
A website claims 30% conversion rate. Sample: 45 conversions from 200 visitors. Is it different?

<details>
<summary>Click for Solution</summary>

```
H₀: p = 0.30, H₁: p ≠ 0.30
p̂ = 45/200 = 0.225
SE = √(0.3×0.7/200) = 0.0324
Z = (0.225-0.30)/0.0324 = -2.31
p-value = 2×P(Z<-2.31) = 0.021 < 0.05
REJECT H₀: Conversion rate is significantly lower.
```
</details>

---

## Summary: The Essence of Z-Test

```
┌─────────────────────────────────────────────────────────────────┐
│                         Z-TEST                                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   WHEN TO USE:                                                   │
│   • σ is KNOWN (or testing proportions)                         │
│   • Large sample (n ≥ 30)                                       │
│                                                                  │
│   THE FORMULA:                                                   │
│                                                                  │
│              Observed - Expected                                 │
│        Z = ─────────────────────────                             │
│                Standard Error                                    │
│                                                                  │
│   DECISION RULE (α = 0.05):                                      │
│   • Two-tailed: Reject if |Z| > 1.96                            │
│   • One-tailed: Reject if Z > 1.645 (or Z < -1.645)             │
│   • Or: Reject if p-value < α                                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

> **"The Z-test transforms raw data into a standardized score, letting us ask: 'How unusual is this result if nothing special is happening?'"**

Master the Z-test, and you've mastered the foundation of hypothesis testing! 📊

---

*From sample to Z-score, from observation to decision — that's the power of the Z-test!* 🎯
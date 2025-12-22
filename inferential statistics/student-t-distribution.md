# Student's t-Distribution
## The Small Sample Hero of Statistics 🎓

---

## A Remarkable Origin Story

In 1908, a statistician working at the Guinness Brewery in Dublin, Ireland, faced a problem. **William Sealy Gosset** needed to analyze small samples of barley to ensure beer quality, but the existing statistical methods (based on the normal distribution) required large samples.

Guinness had a policy against employees publishing scientific papers (fearing trade secrets would leak). So Gosset published his groundbreaking work under the pseudonym **"Student"** — and that's why we call it the **Student's t-distribution**!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   "The probable error of a mean"                            │
│                     — Student (W.S. Gosset), 1908           │
│                                                             │
│   One of the most influential papers in statistics,         │
│   written by a brewer who couldn't use his real name!       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Problem Student Solved

### Why Can't We Always Use the Normal Distribution?

When we calculate a Z-score for testing a mean:

```
       X̄ - μ
Z = ─────────
      σ / √n
```

We need to know **σ (population standard deviation)** — but we almost never know it!

### The "Obvious" Solution That Doesn't Work

"Just replace σ with the sample standard deviation s!"

```
       X̄ - μ
Z = ─────────  ← This seems reasonable...
      s / √n
```

**But there's a problem:** When we estimate σ with s, we introduce **extra uncertainty**. The sample standard deviation s varies from sample to sample, especially with small samples!

### Student's Discovery

Student discovered that when you use s instead of σ, the resulting statistic **doesn't follow a normal distribution** — it follows a new distribution with **heavier tails**.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE t-STATISTIC                                            │
│                                                             │
│              X̄ - μ                                          │
│        t = ─────────                                        │
│             s / √n                                          │
│                                                             │
│   This follows the t-distribution, NOT the normal!          │
│   (when sampling from a normal population)                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## What is the t-Distribution?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              STUDENT'S t-DISTRIBUTION                        │
│                                                             │
│   A probability distribution that arises when estimating    │
│   the mean of a normally distributed population when the    │
│   sample size is small and population standard deviation    │
│   is unknown.                                               │
│                                                             │
│   Key Characteristics:                                      │
│   • Bell-shaped and symmetric (like normal)                 │
│   • Centered at 0 (like standard normal)                    │
│   • HEAVIER TAILS than the normal distribution             │
│   • Shape depends on DEGREES OF FREEDOM (df)               │
│   • Approaches normal as df → ∞                            │
│                                                             │
│   Notation: t ~ t(df) or t ~ t_df                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Comparing t and Normal Distributions

### Visual Comparison

```
                    Standard Normal (Z) vs t-Distribution
                    
                              ╭─╮  ← Normal (taller peak)
                            ╭─╯ ╰─╮
                           ╭╯     ╰╮
                          ╭╯  ╭─╮  ╰╮  ← t (lower peak)
                         ╭╯  ╭╯ ╰╮  ╰╮
                        ╭╯  ╭╯   ╰╮  ╰╮
                       ╭╯ ╭─╯     ╰─╮ ╰╮
                     ╭─╯╭─╯         ╰─╮╰─╮
               ▓▓▓▓╭─╯╭─╯             ╰─╮╰─╮▓▓▓▓  ← Heavier tails (t)
             ──────────────────────────────────────
                              0
                              
    Normal: Thinner tails — Extreme values are RARE
    t:      Heavier tails — Extreme values are MORE LIKELY
```

### Why Heavier Tails?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE EXTRA UNCERTAINTY                                      │
│                                                             │
│   When we use s instead of σ:                               │
│                                                             │
│   • s is a random variable (changes with each sample)       │
│   • Sometimes s underestimates σ (making t too large)       │
│   • Sometimes s overestimates σ (making t too small)        │
│                                                             │
│   This extra variability means:                             │
│   • More probability in the tails                           │
│   • Need larger critical values for same confidence         │
│   • Must be more conservative with small samples            │
│                                                             │
│   With small n, s can be quite different from σ!           │
│   With large n, s ≈ σ, so t ≈ Z                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Degrees of Freedom (df)

The **degrees of freedom** is the key parameter that determines the shape of the t-distribution.

### What Are Degrees of Freedom?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   DEGREES OF FREEDOM (df)                                    │
│                                                             │
│   The number of independent pieces of information           │
│   available to estimate a parameter.                        │
│                                                             │
│   For a sample of size n:                                   │
│   • We have n observations                                  │
│   • We use 1 to estimate the mean (X̄)                      │
│   • We have n - 1 "free" pieces left for variance          │
│                                                             │
│   df = n - 1 (for one-sample t-test)                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Intuition: Why n - 1?

```
Example: You have 3 numbers that must sum to 15

Number 1: Choose freely → say 4
Number 2: Choose freely → say 6
Number 3: MUST be 5 (to make sum = 15)

Only 2 numbers were "free" — the 3rd was determined!

Similarly:
• n observations constrained to have mean X̄
• Only n - 1 can vary freely
• The last one is determined by the constraint

df = n - 1
```

### How df Affects the Distribution

```
df = 1 (very heavy tails)
                    ╭───╮
                  ╭─╯   ╰─╮
                ╭─╯       ╰─╮
              ╭─╯           ╰─╮
           ▓▓▓╯               ╰▓▓▓▓▓▓▓▓▓▓▓▓▓▓
         ──────────────────────────────────────

df = 5 (moderate tails)
                    ╭───╮
                  ╭─╯   ╰─╮
                 ╭╯       ╰╮
                ╭╯         ╰╮
              ▓▓╯           ╰▓▓▓
         ──────────────────────────────────────

df = 30 (nearly normal)
                    ╭───╮
                  ╭─╯   ╰─╮
                 ╭╯       ╰╮
                ╭╯         ╰╮
               ▓╯           ╰▓
         ──────────────────────────────────────
                         
                         
As df increases:
• Tails get thinner
• Peak gets taller
• Distribution → Standard Normal
```

---

## The t-Distribution PDF

### Mathematical Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   PROBABILITY DENSITY FUNCTION                               │
│                                                             │
│              Γ((ν+1)/2)           t²  -(ν+1)/2              │
│   f(t) = ─────────────── × (1 + ────)                       │
│          √(νπ) × Γ(ν/2)          ν                          │
│                                                             │
│   Where:                                                    │
│   • ν (nu) = degrees of freedom (df)                        │
│   • Γ = Gamma function                                      │
│   • t ∈ (-∞, +∞)                                           │
│                                                             │
│   Don't memorize this! Just understand:                     │
│   • Bell-shaped, symmetric around 0                         │
│   • Shape controlled by df                                  │
│   • Heavier tails than normal                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Properties of the t-Distribution

### Summary Table

| Property | Value | Condition |
|----------|-------|-----------|
| **Mean** | 0 | df > 1 |
| **Median** | 0 | Always |
| **Mode** | 0 | Always |
| **Variance** | df/(df - 2) | df > 2 |
| **Skewness** | 0 | df > 3 |
| **Kurtosis** | 6/(df - 4) | df > 4 |
| **Support** | (-∞, +∞) | Always |

### Key Properties Explained

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   1. MEAN = 0 (for df > 1)                                  │
│      The distribution is centered at zero.                  │
│      (For df = 1, mean is undefined — Cauchy distribution) │
│                                                             │
│   2. VARIANCE = df/(df - 2) (for df > 2)                   │
│      Always GREATER than 1 (normal has variance = 1)       │
│      As df → ∞, Variance → 1                               │
│                                                             │
│      df = 3:  Var = 3/1 = 3.00                             │
│      df = 5:  Var = 5/3 = 1.67                             │
│      df = 10: Var = 10/8 = 1.25                            │
│      df = 30: Var = 30/28 = 1.07                           │
│      df → ∞:  Var → 1 (matches normal)                     │
│                                                             │
│   3. SYMMETRIC around 0                                     │
│      P(t > a) = P(t < -a)                                  │
│                                                             │
│   4. HEAVIER TAILS than normal                             │
│      More probability in extreme values                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## t-Distribution Critical Values

### Common Critical Values Table

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   t-DISTRIBUTION CRITICAL VALUES                                    │
│   (Two-tailed: t_α/2)                                              │
│                                                                    │
│    df │  80%     90%     95%     98%     99%     99.9%            │
│       │ (α=.20) (α=.10) (α=.05) (α=.02) (α=.01) (α=.001)          │
│   ────┼─────────────────────────────────────────────────           │
│     1 │  3.078   6.314  12.706  31.821  63.657  636.62            │
│     2 │  1.886   2.920   4.303   6.965   9.925   31.60            │
│     3 │  1.638   2.353   3.182   4.541   5.841   12.92            │
│     4 │  1.533   2.132   2.776   3.747   4.604    8.61            │
│     5 │  1.476   2.015   2.571   3.365   4.032    6.87            │
│    10 │  1.372   1.812   2.228   2.764   3.169    4.59            │
│    15 │  1.341   1.753   2.131   2.602   2.947    4.07            │
│    20 │  1.325   1.725   2.086   2.528   2.845    3.85            │
│    25 │  1.316   1.708   2.060   2.485   2.787    3.73            │
│    30 │  1.310   1.697   2.042   2.457   2.750    3.65            │
│    50 │  1.299   1.676   2.009   2.403   2.678    3.50            │
│   100 │  1.290   1.660   1.984   2.364   2.626    3.39            │
│    ∞  │  1.282   1.645   1.960   2.326   2.576    3.29 ← Normal!  │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

### Key Observations

```
1. Small df → Large critical values
   • df = 1, 95%: t* = 12.706 (much larger than 1.96!)
   • Need stronger evidence to reject H₀ with small samples

2. As df → ∞, critical values → Z values
   • df = ∞, 95%: t* = 1.960 = Z*
   • t-distribution becomes normal

3. Rule of Thumb
   • df ≥ 30: t ≈ Z (can use normal approximation)
   • df < 30: Must use t-distribution
```

### Visual: Critical Values Comparison

```
95% Confidence: How far out to capture 95%?

df = 5:   ├────────────────────[▓▓▓▓▓▓▓▓▓▓▓▓▓▓]────────────────────┤
                              -2.571          2.571

df = 10:  ├──────────────────[▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓]──────────────────┤
                            -2.228            2.228

df = 30:  ├─────────────────[▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓]─────────────────┤
                           -2.042              2.042

Normal:   ├────────────────[▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓]────────────────┤
                          -1.960                1.960

With small df, need to go further out to capture 95%!
```

---

## Derivation: Where Does t Come From?

### The Mathematical Foundation

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   If X₁, X₂, ..., Xₙ are i.i.d. from Normal(μ, σ²):        │
│                                                             │
│   1. Sample mean: X̄ = (1/n)ΣXᵢ                             │
│                                                             │
│   2. Sample variance: s² = Σ(Xᵢ - X̄)²/(n-1)               │
│                                                             │
│   3. Z-statistic: Z = (X̄ - μ)/(σ/√n) ~ N(0,1)             │
│                                                             │
│   4. Chi-square: (n-1)s²/σ² ~ χ²(n-1)                      │
│                                                             │
│   5. The t-statistic is the ratio:                         │
│                                                             │
│              Z                    (X̄ - μ)/(σ/√n)           │
│      t = ─────────────── = ─────────────────────────       │
│          √(χ²/(n-1))       √((n-1)s²/σ²)/(n-1))           │
│                                                             │
│              (X̄ - μ)/(σ/√n)      X̄ - μ                    │
│        = ───────────────────── = ─────────                  │
│               s/σ                 s/√n                      │
│                                                             │
│   The σ terms cancel! We don't need to know σ!             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Why This Matters

```
The t-statistic is a ratio of:

• Numerator: Z ~ N(0,1) — measures how far X̄ is from μ
• Denominator: √(χ²/df) — estimates σ using s

The ratio of these two independent quantities follows 
the t-distribution with df = n - 1.

This is why t has heavier tails:
• The denominator (s/σ) varies randomly
• Sometimes it's < 1 (inflating t)
• Sometimes it's > 1 (deflating t)
• This variability spreads out the distribution
```

---

## 📖 Story: Quality Control at the Textile Factory

Rina is a quality control manager at a textile factory in Gazipur. She needs to verify that fabric strength meets specifications (μ₀ = 50 kg tensile strength).

She can only test **n = 12 fabric samples** (testing destroys the fabric!):

**Sample data:** 48, 52, 49, 51, 47, 53, 50, 49, 52, 48, 51, 50

### Why t-Test, Not Z-Test?

```
❌ Z-test requires knowing σ — Rina doesn't know it!
❌ n = 12 is small — normal approximation risky
✅ t-test uses s and accounts for small sample uncertainty
```

### The Analysis

```
Step 1: Calculate sample statistics
n = 12
X̄ = (48+52+49+51+47+53+50+49+52+48+51+50)/12 = 600/12 = 50
s = √[Σ(Xᵢ - X̄)²/(n-1)] = √(36/11) = 1.81

Step 2: Set up hypotheses
H₀: μ = 50 (meets specification)
H₁: μ ≠ 50 (doesn't meet specification)
α = 0.05

Step 3: Calculate t-statistic
t = (X̄ - μ₀)/(s/√n)
t = (50 - 50)/(1.81/√12)
t = 0/(1.81/3.46)
t = 0/0.52
t = 0

Step 4: Find critical value
df = n - 1 = 11
t_crit (two-tailed, α = 0.05) = ±2.201

Step 5: Decision
|t| = 0 < 2.201 = t_crit
FAIL TO REJECT H₀

Conclusion: The fabric meets the 50 kg specification.
```

---

## t-Distribution Applications

### 1. One-Sample t-Test

Testing if a sample mean differs from a hypothesized value.

```
         X̄ - μ₀
t = ─────────────    df = n - 1
        s / √n

Use: Is this sample's mean different from μ₀?
```

### 2. Two-Sample t-Test (Independent)

Comparing means of two independent groups.

```
           X̄₁ - X̄₂
t = ─────────────────────
    √(s₁²/n₁ + s₂²/n₂)

df ≈ Welch-Satterthwaite approximation (complex formula)

Or with equal variances assumed:
df = n₁ + n₂ - 2
```

### 3. Paired t-Test

Comparing paired observations (before/after, matched pairs).

```
         d̄ - 0
t = ─────────────    df = n - 1
      s_d / √n

Where d̄ = mean of differences
      s_d = std dev of differences
```

### 4. Confidence Intervals

```
CI for μ: X̄ ± t* × (s/√n)

Where t* is the critical value for desired confidence level
with df = n - 1
```

### 5. Regression Coefficients

Testing if regression slopes are significantly different from zero.

```
         β̂ - 0
t = ─────────────    df = n - k - 1
       SE(β̂)

Where k = number of predictors
```

---

## t vs Z: When to Use Which?

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   USE t-DISTRIBUTION WHEN:                                       │
│   ─────────────────────────                                     │
│   • Population σ is UNKNOWN (almost always!)                    │
│   • Sample size is small (n < 30)                               │
│   • Testing means with estimated standard deviation             │
│   • Constructing confidence intervals for means                 │
│                                                                  │
│   USE Z (NORMAL) DISTRIBUTION WHEN:                              │
│   ───────────────────────────────────                           │
│   • Population σ is KNOWN (rare!)                               │
│   • Sample size is large (n ≥ 30) and using s                  │
│   • Testing proportions                                         │
│   • Dealing with sums of many random variables (CLT)           │
│                                                                  │
│   PRACTICAL RULE:                                                │
│   ───────────────                                               │
│   When in doubt, use t! It's always valid.                      │
│   With large n, t ≈ Z anyway.                                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Comparison Table

| Aspect | Z-Distribution | t-Distribution |
|--------|---------------|----------------|
| σ | Known | Unknown (use s) |
| Shape | Always same | Changes with df |
| Tails | Standard | Heavier |
| Critical (95%) | 1.96 | Depends on df |
| Variance | 1 | df/(df-2) > 1 |
| When n → ∞ | Stays same | Approaches Z |

---

## Relationship to Other Distributions

### The Distribution Family Tree

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    NORMAL                                   │
│                       │                                     │
│         ┌─────────────┼─────────────┐                      │
│         │             │             │                      │
│         ▼             ▼             ▼                      │
│      SQUARED      RATIO OF       SUM OF                   │
│         │        Z AND √χ²       SQUARED                   │
│         │             │             │                      │
│         ▼             ▼             ▼                      │
│      Chi-Square      t          F-distribution            │
│         │             │             │                      │
│         └─────────────┴─────────────┘                      │
│                                                             │
│   Connections:                                              │
│   • t² with df = ν is F(1, ν)                              │
│   • t with df = 1 is Cauchy distribution                   │
│   • t with df = ∞ is Standard Normal                       │
│   • (n-1)s²/σ² ~ χ²(n-1)                                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Special Cases

```
df = 1:    t-distribution = CAUCHY distribution
           (Heavy tails, no mean or variance!)

df = ∞:    t-distribution = STANDARD NORMAL
           (As sample size → ∞)

t²:        If t ~ t(df), then t² ~ F(1, df)
           (Connection to F-distribution)
```

---

## Python Implementation

### Basic t-Distribution Functions

```python
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt

# ===========================================
# t-DISTRIBUTION BASICS
# ===========================================

df = 10  # degrees of freedom

# Create t-distribution object
t_dist = stats.t(df=df)

# PDF at t = 1.5
print(f"PDF at t=1.5: {t_dist.pdf(1.5):.4f}")

# CDF: P(t ≤ 1.5)
print(f"P(t ≤ 1.5): {t_dist.cdf(1.5):.4f}")

# Survival: P(t > 1.5)
print(f"P(t > 1.5): {1 - t_dist.cdf(1.5):.4f}")

# Critical value for 95% two-tailed
t_crit = t_dist.ppf(0.975)  # 97.5th percentile
print(f"95% critical value (df={df}): ±{t_crit:.4f}")

# Mean and variance
print(f"Mean: {t_dist.mean():.4f}")
print(f"Variance: {t_dist.var():.4f}")

# Generate random samples
samples = t_dist.rvs(size=1000)
print(f"Sample mean: {samples.mean():.4f}")
print(f"Sample std: {samples.std():.4f}")
```

### Comparing t and Normal Distributions

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def compare_t_and_normal():
    """Visualize t-distributions with different df vs normal"""
    
    fig, axes = plt.subplots(1, 2, figsize=(14, 5))
    
    x = np.linspace(-5, 5, 1000)
    
    # Plot 1: Different df values
    ax1 = axes[0]
    ax1.plot(x, stats.norm.pdf(x), 'k-', linewidth=2, label='Normal (Z)')
    
    for df in [1, 3, 5, 10, 30]:
        ax1.plot(x, stats.t.pdf(x, df), '--', linewidth=1.5, label=f't (df={df})')
    
    ax1.set_xlabel('t / z', fontsize=12)
    ax1.set_ylabel('Probability Density', fontsize=12)
    ax1.set_title('t-Distribution vs Normal: Effect of df', fontsize=14)
    ax1.legend()
    ax1.grid(True, alpha=0.3)
    
    # Plot 2: Focus on tails
    ax2 = axes[1]
    x_tail = np.linspace(1.5, 5, 500)
    ax2.plot(x_tail, stats.norm.pdf(x_tail), 'k-', linewidth=2, label='Normal')
    
    for df in [3, 10, 30]:
        ax2.plot(x_tail, stats.t.pdf(x_tail, df), '--', linewidth=1.5, label=f't (df={df})')
    
    ax2.set_xlabel('t / z', fontsize=12)
    ax2.set_ylabel('Probability Density', fontsize=12)
    ax2.set_title('Focus on Tails: t has heavier tails', fontsize=14)
    ax2.legend()
    ax2.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()

compare_t_and_normal()
```

### One-Sample t-Test

```python
import numpy as np
from scipy import stats

def one_sample_t_test(data, mu_0, alternative='two-sided', alpha=0.05):
    """
    Perform one-sample t-test
    
    Parameters:
    - data: sample data (array-like)
    - mu_0: hypothesized population mean
    - alternative: 'two-sided', 'greater', or 'less'
    - alpha: significance level
    """
    data = np.array(data)
    n = len(data)
    x_bar = np.mean(data)
    s = np.std(data, ddof=1)  # Sample std dev (ddof=1 for n-1)
    df = n - 1
    
    # Standard error
    se = s / np.sqrt(n)
    
    # t-statistic
    t_stat = (x_bar - mu_0) / se
    
    # p-value
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.t.cdf(abs(t_stat), df))
    elif alternative == 'greater':
        p_value = 1 - stats.t.cdf(t_stat, df)
    else:  # less
        p_value = stats.t.cdf(t_stat, df)
    
    # Critical value
    if alternative == 'two-sided':
        t_crit = stats.t.ppf(1 - alpha/2, df)
    elif alternative == 'greater':
        t_crit = stats.t.ppf(1 - alpha, df)
    else:
        t_crit = stats.t.ppf(alpha, df)
    
    # Confidence interval
    ci_lower = x_bar - stats.t.ppf(1 - alpha/2, df) * se
    ci_upper = x_bar + stats.t.ppf(1 - alpha/2, df) * se
    
    # Effect size (Cohen's d)
    cohens_d = (x_bar - mu_0) / s
    
    # Decision
    reject = p_value < alpha
    
    return {
        'n': n,
        'mean': x_bar,
        'std': s,
        'se': se,
        'df': df,
        't_statistic': t_stat,
        't_critical': t_crit,
        'p_value': p_value,
        'ci': (ci_lower, ci_upper),
        'cohens_d': cohens_d,
        'reject_null': reject
    }

# Example: Fabric strength test
data = [48, 52, 49, 51, 47, 53, 50, 49, 52, 48, 51, 50]
result = one_sample_t_test(data, mu_0=50, alternative='two-sided')

print("=== One-Sample t-Test Results ===")
print(f"n = {result['n']}")
print(f"Sample mean = {result['mean']:.4f}")
print(f"Sample std = {result['std']:.4f}")
print(f"Standard error = {result['se']:.4f}")
print(f"df = {result['df']}")
print(f"t-statistic = {result['t_statistic']:.4f}")
print(f"t-critical = ±{result['t_critical']:.4f}")
print(f"p-value = {result['p_value']:.4f}")
print(f"95% CI: ({result['ci'][0]:.4f}, {result['ci'][1]:.4f})")
print(f"Cohen's d = {result['cohens_d']:.4f}")
print(f"Decision: {'Reject H₀' if result['reject_null'] else 'Fail to reject H₀'}")

# Using scipy directly
t_stat, p_value = stats.ttest_1samp(data, 50)
print(f"\nScipy verification: t={t_stat:.4f}, p={p_value:.4f}")
```

### Two-Sample t-Test

```python
import numpy as np
from scipy import stats

def two_sample_t_test(data1, data2, equal_var=False, alternative='two-sided'):
    """
    Two-sample t-test for independent samples
    """
    data1 = np.array(data1)
    data2 = np.array(data2)
    
    n1, n2 = len(data1), len(data2)
    mean1, mean2 = np.mean(data1), np.mean(data2)
    var1, var2 = np.var(data1, ddof=1), np.var(data2, ddof=1)
    
    if equal_var:
        # Pooled variance
        sp2 = ((n1-1)*var1 + (n2-1)*var2) / (n1 + n2 - 2)
        se = np.sqrt(sp2 * (1/n1 + 1/n2))
        df = n1 + n2 - 2
    else:
        # Welch's t-test (unequal variances)
        se = np.sqrt(var1/n1 + var2/n2)
        # Welch-Satterthwaite df
        num = (var1/n1 + var2/n2)**2
        denom = (var1/n1)**2/(n1-1) + (var2/n2)**2/(n2-1)
        df = num / denom
    
    t_stat = (mean1 - mean2) / se
    
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.t.cdf(abs(t_stat), df))
    elif alternative == 'greater':
        p_value = 1 - stats.t.cdf(t_stat, df)
    else:
        p_value = stats.t.cdf(t_stat, df)
    
    return {
        'mean1': mean1,
        'mean2': mean2,
        'difference': mean1 - mean2,
        'df': df,
        't_statistic': t_stat,
        'p_value': p_value
    }

# Example
group1 = [85, 90, 88, 92, 87, 89, 91, 86, 88, 90]
group2 = [78, 82, 80, 85, 79, 81, 83, 77, 80, 82]

result = two_sample_t_test(group1, group2)
print("=== Two-Sample t-Test ===")
print(f"Group 1 mean: {result['mean1']:.2f}")
print(f"Group 2 mean: {result['mean2']:.2f}")
print(f"Difference: {result['difference']:.2f}")
print(f"df: {result['df']:.2f}")
print(f"t-statistic: {result['t_statistic']:.4f}")
print(f"p-value: {result['p_value']:.6f}")
```

### Confidence Interval for Mean

```python
import numpy as np
from scipy import stats

def confidence_interval_mean(data, confidence=0.95):
    """
    Calculate confidence interval for population mean using t-distribution
    """
    data = np.array(data)
    n = len(data)
    mean = np.mean(data)
    se = stats.sem(data)  # Standard error of mean
    df = n - 1
    
    # t critical value
    alpha = 1 - confidence
    t_crit = stats.t.ppf(1 - alpha/2, df)
    
    margin = t_crit * se
    ci_lower = mean - margin
    ci_upper = mean + margin
    
    return {
        'mean': mean,
        'se': se,
        'df': df,
        't_critical': t_crit,
        'margin_of_error': margin,
        'ci': (ci_lower, ci_upper),
        'confidence': confidence
    }

# Example
data = [23, 25, 28, 24, 26, 27, 25, 24, 26, 28]
result = confidence_interval_mean(data, confidence=0.95)

print("=== Confidence Interval ===")
print(f"Sample mean: {result['mean']:.2f}")
print(f"Standard error: {result['se']:.4f}")
print(f"df: {result['df']}")
print(f"t-critical: {result['t_critical']:.4f}")
print(f"Margin of error: {result['margin_of_error']:.4f}")
print(f"{result['confidence']*100:.0f}% CI: ({result['ci'][0]:.2f}, {result['ci'][1]:.2f})")
```

### Critical Values Table Generator

```python
import numpy as np
from scipy import stats

def print_t_table():
    """Generate t-distribution critical values table"""
    
    dfs = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 15, 20, 25, 30, 40, 50, 100, np.inf]
    alphas_two_tail = [0.20, 0.10, 0.05, 0.02, 0.01]
    
    print("t-Distribution Critical Values (Two-Tailed)")
    print("=" * 70)
    print(f"{'df':>6} | ", end="")
    for alpha in alphas_two_tail:
        print(f"{1-alpha:.0%:>10}", end=" ")
    print()
    print("-" * 70)
    
    for df in dfs:
        if df == np.inf:
            df_str = "∞"
        else:
            df_str = str(int(df))
        print(f"{df_str:>6} | ", end="")
        
        for alpha in alphas_two_tail:
            if df == np.inf:
                t_crit = stats.norm.ppf(1 - alpha/2)
            else:
                t_crit = stats.t.ppf(1 - alpha/2, df)
            print(f"{t_crit:>10.3f}", end=" ")
        print()

print_t_table()
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Using Z When σ is Unknown

```
❌ Wrong: σ unknown, but using Z = (X̄ - μ)/(s/√n)
✅ Correct: Use t = (X̄ - μ)/(s/√n) with t-distribution
```

### Mistake 2: Wrong Degrees of Freedom

```
❌ Wrong: df = n
✅ Correct: df = n - 1 (for one-sample)

Different tests have different df:
• One-sample: df = n - 1
• Paired: df = n - 1
• Two-sample (pooled): df = n₁ + n₂ - 2
• Two-sample (Welch): df = complex formula
```

### Mistake 3: Assuming Normality Not Required

```
❌ Wrong: t-test works for any distribution
✅ Correct: t-test assumes data comes from normal distribution
           (robust with large n due to CLT)
```

### Mistake 4: Using Normal Critical Values with Small n

```
❌ Wrong: Using 1.96 for 95% CI with n = 10
✅ Correct: Use 2.262 (t-critical for df = 9)

With small samples, this matters a lot!
```

---

## Practice Problems 📝

### Problem 1: Finding Critical Values
Find the critical value for a two-tailed t-test with α = 0.05 and n = 16.

<details>
<summary>Click for Answer</summary>

```
df = n - 1 = 16 - 1 = 15

For two-tailed α = 0.05:
Need t-value such that P(|t| > t*) = 0.05
This means P(t > t*) = 0.025

t* = t₀.₀₂₅,₁₅ = 2.131

Critical values: ±2.131
```

</details>

---

### Problem 2: Confidence Interval
A sample of n = 25 has X̄ = 80 and s = 10. Find the 95% confidence interval for μ.

<details>
<summary>Click for Answer</summary>

```
df = 25 - 1 = 24
t* (95%, df=24) = 2.064

SE = s/√n = 10/√25 = 2

CI = X̄ ± t* × SE
   = 80 ± 2.064 × 2
   = 80 ± 4.128
   = (75.87, 84.13)

We are 95% confident μ is between 75.87 and 84.13.
```

</details>

---

### Problem 3: t-Test Calculation
Test H₀: μ = 100 vs H₁: μ ≠ 100 at α = 0.05
Sample: n = 20, X̄ = 95, s = 12

<details>
<summary>Click for Answer</summary>

```
df = 20 - 1 = 19

t = (X̄ - μ₀)/(s/√n)
  = (95 - 100)/(12/√20)
  = -5/(12/4.47)
  = -5/2.68
  = -1.87

t-critical (two-tailed, df=19, α=0.05) = ±2.093

Since |t| = 1.87 < 2.093:
FAIL TO REJECT H₀

p-value = 2 × P(t < -1.87 | df=19) ≈ 0.077 > 0.05

Conclusion: Insufficient evidence that μ ≠ 100.
```

</details>

---

### Problem 4: Comparing Z and t
For n = 10, why is the 95% t-critical value (2.262) larger than the Z-critical value (1.96)?

<details>
<summary>Click for Answer</summary>

```
With small n = 10:

1. We estimate σ with s, adding uncertainty
2. s varies from sample to sample
3. This extra variability spreads out the distribution

The t-distribution has heavier tails because:
• There's more chance s underestimates σ (inflating t)
• There's more chance s overestimates σ (deflating t)

To capture 95% of a distribution with heavier tails,
we need to go further out (2.262 vs 1.96).

This ensures our confidence intervals are CONSERVATIVE —
properly accounting for our uncertainty about σ.
```

</details>

---

### Problem 5: Sample Size Effect
Why does t-critical approach 1.96 as n increases?

<details>
<summary>Click for Answer</summary>

```
As n increases:

1. s becomes a better estimate of σ
   (Law of Large Numbers: s → σ)

2. The variability in s decreases
   (Var(s²) decreases with n)

3. The extra uncertainty from using s vanishes

4. The denominator s/√n ≈ σ/√n becomes stable

5. The t-statistic behaves like a Z-statistic

Mathematically:
• t-distribution variance = df/(df-2) → 1 as df → ∞
• t-distribution shape → Normal as df → ∞

At df = 30, t* ≈ 2.04 (vs 1.96)
At df = 100, t* ≈ 1.98 (very close!)
At df = ∞, t* = 1.96 exactly
```

</details>

---

## Summary: The Essence of t-Distribution

```
┌─────────────────────────────────────────────────────────────────┐
│                  STUDENT'S t-DISTRIBUTION                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "The distribution for when you don't know σ"                  │
│                                                                  │
│   WHEN TO USE:                                                   │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Population σ is UNKNOWN (use s instead)              │   │
│   │  • Small sample sizes (n < 30)                          │   │
│   │  • Constructing confidence intervals for means          │   │
│   │  • Testing hypotheses about means                       │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY CHARACTERISTICS:                                           │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Bell-shaped, symmetric, centered at 0               │   │
│   │  • HEAVIER TAILS than normal                            │   │
│   │  • Shape depends on df = n - 1                          │   │
│   │  • Approaches Normal as df → ∞                          │   │
│   │  • Variance = df/(df-2) > 1                             │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THE t-STATISTIC:                                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │              X̄ - μ                                       │   │
│   │        t = ─────────    with df = n - 1                 │   │
│   │             s / √n                                       │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   CRITICAL VALUES (95%, two-tailed):                            │
│   df=5: ±2.571 | df=10: ±2.228 | df=30: ±2.042 | df=∞: ±1.960  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## The Big Picture

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│                     THE INFERENCE FRAMEWORK                      │
│                                                                  │
│   Population                     Sample                          │
│   ══════════                     ══════                          │
│                                                                  │
│   μ (unknown) ◄───────────────── X̄ (estimate)                   │
│   σ (unknown) ◄───────────────── s (estimate)                    │
│                                                                  │
│                       │                                          │
│                       │ Because σ is unknown:                    │
│                       │                                          │
│                       ▼                                          │
│                                                                  │
│            ┌──────────────────────┐                              │
│            │   USE t-DISTRIBUTION │                              │
│            │   instead of Normal  │                              │
│            └──────────────────────┘                              │
│                                                                  │
│   Small n: Heavy tails → Conservative inference                  │
│   Large n: t ≈ Z → Same as normal-based inference               │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

> **"The t-distribution is Student's gift to small-sample statistics — it honestly accounts for our uncertainty when we estimate σ, ensuring our conclusions remain valid even when data is scarce."**

William Gosset, working at a brewery over a century ago, solved a fundamental problem that statisticians face daily. Master the t-distribution, and you'll handle small samples with confidence! 🎓

---

*From brewery to statistics, from unknown σ to valid inference — that's the legacy of Student's t!* 🍺📊
# The p-value
## The Most Misunderstood Number in Statistics 🎲

---

## The Question That Started It All

Imagine you flip a coin 10 times and get **9 heads**.

Is this coin fair? Or is it biased?

- A fair coin *could* give 9 heads... it's just unlikely
- But how unlikely is "unlikely enough" to suspect cheating?

**The p-value answers exactly this question!**

---

## 📖 Story: The Suspicious Dice

Rafiq runs a board game café in Dhaka. A customer complains that the house dice are loaded (biased). Rafiq rolls the dice 60 times and gets the following:

| Face | Expected (Fair) | Observed |
|------|-----------------|----------|
| 1 | 10 | 5 |
| 2 | 10 | 8 |
| 3 | 10 | 9 |
| 4 | 10 | 11 |
| 5 | 10 | 12 |
| 6 | 10 | 15 |

The 6 appeared more often than expected. But is this just luck, or is the die actually biased?

**Rafiq calculates the p-value = 0.23 (23%)**

This means: "If the die were fair, there's a 23% chance of seeing results this extreme or more extreme just by random chance."

23% isn't that rare, so Rafiq concludes: **"No strong evidence the die is loaded."**

---

## What Exactly IS a p-value?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    THE p-VALUE                               │
│                                                             │
│   Definition:                                               │
│   ───────────                                               │
│   The probability of obtaining results AT LEAST AS          │
│   EXTREME as what we observed, ASSUMING the null            │
│   hypothesis (H₀) is TRUE.                                  │
│                                                             │
│   In symbols:                                               │
│   ────────────                                              │
│   p-value = P(data this extreme or more | H₀ is true)      │
│                                                             │
│   Key insight:                                              │
│   ────────────                                              │
│   Small p-value = Data is UNLIKELY under H₀                │
│                 = Evidence AGAINST H₀                       │
│                                                             │
│   Large p-value = Data is CONSISTENT with H₀               │
│                 = No strong evidence against H₀             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The p-value in Plain English

### What It Measures

```
"IF the null hypothesis were true,
 HOW SURPRISING would our data be?"

p = 0.01 (1%)   → VERY surprising! Something's probably wrong with H₀
p = 0.05 (5%)   → Quite surprising. Maybe H₀ isn't true?
p = 0.20 (20%)  → Not that surprising. H₀ seems reasonable.
p = 0.80 (80%)  → Not surprising at all. H₀ fits the data well.
```

### The Analogy: Court Trial

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   COURTROOM ANALOGY                                          │
│                                                             │
│   H₀ = "The defendant is innocent" (assumed true)           │
│   Evidence = The data we collected                          │
│   p-value = How likely is this evidence if truly innocent?  │
│                                                             │
│   Small p-value:                                            │
│   "This evidence would be very unlikely if the defendant    │
│    were truly innocent. Something doesn't add up."          │
│   → Reject innocence (convict)                              │
│                                                             │
│   Large p-value:                                            │
│   "This evidence is consistent with innocence.              │
│    Nothing suspicious here."                                │
│   → Cannot reject innocence (acquit)                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Visualizing the p-value

### One-Tailed Test (Right)

```
H₀: μ = 100
H₁: μ > 100
Observed: X̄ = 108

                    Distribution under H₀
                    
                         ╭───╮
                       ╭─╯   ╰─╮
                      ╭╯       ╰╮
                     ╭╯         ╰╮
                    ╭╯           ╰╮
                   ╭╯             ╰████████████  ← p-value
                  ╭╯              │╰████████████    (shaded area)
                 ╭╯               │  ████████████
                ╯                 │    ██████████
               ───────────────────┼──────────────────
                       100       108
                       (H₀)    (observed)
                       
p-value = P(X̄ ≥ 108 | μ = 100)
        = Area in the shaded region
```

### One-Tailed Test (Left)

```
H₀: μ = 100
H₁: μ < 100
Observed: X̄ = 92

                    Distribution under H₀
                    
                              ╭───╮
                            ╭─╯   ╰─╮
                           ╭╯       ╰╮
                          ╭╯         ╰╮
                         ╭╯           ╰╮
          ████████████████╯             ╰╮
         ████████████████│               ╰╮
        ██████████████  │                 ╰╮
       ────────────────┼───────────────────╯─────
                      92        100
                  (observed)    (H₀)
                       
p-value = P(X̄ ≤ 92 | μ = 100)
```

### Two-Tailed Test

```
H₀: μ = 100
H₁: μ ≠ 100
Observed: X̄ = 108

                    Distribution under H₀
                    
                         ╭───╮
                       ╭─╯   ╰─╮
                      ╭╯       ╰╮
                     ╭╯         ╰╮
                    ╭╯           ╰╮
        ████████████╯             ╰████████████
       █████████████│             │█████████████
      ██████████    │             │    ██████████
     ───────────────┼──────┬──────┼───────────────
                   92     100    108
                   │             │
                   └──────┴──────┘
                    Both tails!
                       
p-value = P(|X̄ - 100| ≥ 8 | μ = 100)
        = P(X̄ ≤ 92) + P(X̄ ≥ 108)
        = 2 × P(X̄ ≥ 108)  [by symmetry]
```

---

## How to Interpret p-values

### The Decision Rule

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   DECISION RULE                                              │
│                                                             │
│   Choose a significance level α (typically 0.05)            │
│                                                             │
│   If p-value ≤ α:                                           │
│       → REJECT H₀                                           │
│       → "Statistically significant"                         │
│       → "Evidence against H₀"                               │
│                                                             │
│   If p-value > α:                                           │
│       → FAIL TO REJECT H₀                                   │
│       → "Not statistically significant"                     │
│       → "Insufficient evidence against H₀"                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Strength of Evidence Scale

```
┌────────────────────────────────────────────────────────────────┐
│                                                                │
│   p-VALUE INTERPRETATION GUIDE                                  │
│   (Informal scale — use with caution!)                         │
│                                                                │
│   p > 0.10        No evidence against H₀                       │
│   0.05 < p ≤ 0.10  Weak evidence against H₀                    │
│   0.01 < p ≤ 0.05  Moderate evidence against H₀                │
│   0.001 < p ≤ 0.01 Strong evidence against H₀                  │
│   p ≤ 0.001       Very strong evidence against H₀              │
│                                                                │
│   ⚠️ Warning: These are just guidelines, not strict rules!     │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

### Visual: The p-value Spectrum

```
Strong evidence                                      No evidence
against H₀                                          against H₀

│◄─────────────────────────────────────────────────────────────►│
0    0.001    0.01      0.05     0.10          0.50            1

     │         │          │        │
     │         │          │        │
     ▼         ▼          ▼        ▼
   
"Highly    "Very    "Statistically  "Not
significant" significant" significant" significant"

█████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░

──────────────────────────┼─────────────────────────────────────
                       α = 0.05
                    (common threshold)
```

---

## What p-value IS and IS NOT

### What p-value IS ✅

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ✅ p-value IS:                                            │
│                                                             │
│   • P(data this extreme or more | H₀ true)                 │
│   • A measure of compatibility between data and H₀          │
│   • Evidence against H₀ (smaller = more evidence)          │
│   • A continuous measure (not just "significant" or not)   │
│   • Calculated assuming H₀ is true                         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### What p-value IS NOT ❌

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ❌ p-value is NOT:                                        │
│                                                             │
│   • P(H₀ is true)                                          │
│   • P(H₁ is true)                                          │
│   • The probability the result is due to chance            │
│   • The probability of making a wrong decision             │
│   • A measure of effect size or importance                 │
│   • A measure of how "true" or "real" the effect is        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Common Misinterpretations (IMPORTANT!)

### Misinterpretation 1: "Probability H₀ is True"

❌ **Wrong:** "p = 0.03 means there's only 3% chance H₀ is true"

✅ **Correct:** "p = 0.03 means IF H₀ were true, there's only 3% chance of seeing data this extreme"

```
The difference:

WRONG:  P(H₀ true | data) = 0.03     ← Posterior probability
RIGHT:  P(data this extreme | H₀ true) = 0.03  ← p-value

These are VERY different!
(Related by Bayes' theorem, but NOT equal)
```

### Misinterpretation 2: "Due to Chance"

❌ **Wrong:** "p = 0.05 means 5% probability results are due to chance"

✅ **Correct:** "p = 0.05 means IF only chance were operating (H₀ true), we'd see results this extreme 5% of the time"

### Misinterpretation 3: "1 - p = Probability Effect is Real"

❌ **Wrong:** "p = 0.01, so there's 99% chance the effect is real"

✅ **Correct:** "p = 0.01 means the data is inconsistent with H₀, but we need more than p-value to estimate effect probability"

### Misinterpretation 4: "Replication Probability"

❌ **Wrong:** "p = 0.05 means there's 95% chance we'll get the same result if we repeat"

✅ **Correct:** The p-value says nothing about future replications

### Misinterpretation 5: "Effect Size"

❌ **Wrong:** "p = 0.001 means the effect is very large"

✅ **Correct:** Small p can come from tiny effects with huge samples

```
Example:
Study A: Effect = 0.1, n = 10,000  → p = 0.001 (tiny effect, huge n)
Study B: Effect = 5.0, n = 20      → p = 0.04  (large effect, small n)

Study A has smaller p but MUCH smaller effect!
```

---

## The Mathematical Formula

### General Definition

```
For test statistic T with observed value t_obs:

ONE-TAILED (right): p = P(T ≥ t_obs | H₀)
ONE-TAILED (left):  p = P(T ≤ t_obs | H₀)
TWO-TAILED:         p = P(|T| ≥ |t_obs| | H₀)
                      = 2 × P(T ≥ |t_obs| | H₀)  [if symmetric]
```

### For Z-test

```
Test statistic: Z = (X̄ - μ₀) / (σ/√n)

p-value (two-tailed) = 2 × [1 - Φ(|z|)]

Where Φ is the standard normal CDF
```

### For t-test

```
Test statistic: t = (X̄ - μ₀) / (s/√n)

p-value (two-tailed) = 2 × P(T > |t|)

Where T follows t-distribution with df = n-1
```

---

## 📖 Complete Example: Medicine Trial

### The Scenario

A pharmaceutical company claims their new headache pill works in 30 minutes on average. A researcher suspects it takes longer. She tests 25 patients.

**Results:**
- Sample mean: X̄ = 34 minutes
- Sample std dev: s = 8 minutes
- Sample size: n = 25

### Step-by-Step Calculation

**Step 1: State Hypotheses**
```
H₀: μ = 30 (pill works as claimed)
H₁: μ > 30 (pill takes longer)

This is a RIGHT-TAILED test
```

**Step 2: Calculate Test Statistic**
```
       X̄ - μ₀      34 - 30       4
t = ─────────── = ─────────── = ─── = 2.5
      s/√n         8/√25       1.6

t = 2.5 with df = 24
```

**Step 3: Calculate p-value**
```
p-value = P(t > 2.5 | df = 24)

Using t-table or software:
p-value ≈ 0.0098 ≈ 1%
```

**Step 4: Interpret**
```
p-value = 0.0098 < α = 0.05

INTERPRETATION:
"If the pill truly worked in 30 minutes on average,
there's only about 1% chance of observing a sample mean
of 34 minutes or higher in a sample of 25 patients."

CONCLUSION:
"This is unlikely. We reject H₀ and conclude the pill
likely takes longer than claimed (p = 0.01)."
```

### Visual

```
                    Distribution if H₀ true (μ = 30)
                    
                              ╭───╮
                            ╭─╯   ╰─╮
                           ╭╯       ╰╮
                          ╭╯         ╰╮
                         ╭╯           ╰╮
                        ╭╯             ╰██████  ← p = 0.01
                       ╭╯               │╰█████    (1% area)
                      ╭╯                │  ████
                     ╯                  │    ██
                    ─────────────────────┼──────────
                             30        34
                            (H₀)    (observed)
                            
Our data (34 min) is in the extreme right tail!
```

---

## p-values and Sample Size

### The Relationship

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   IMPORTANT: p-value depends on SAMPLE SIZE!                │
│                                                             │
│   Same effect size, different n:                            │
│                                                             │
│   n = 10:   p = 0.15   (not significant)                   │
│   n = 50:   p = 0.02   (significant at 0.05)               │
│   n = 500:  p = 0.0001 (highly significant)                │
│                                                             │
│   With large enough n, even TINY effects become            │
│   "statistically significant"!                              │
│                                                             │
│   This is why effect size matters, not just p-value!       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Same Effect, Different n

```
Small n (n=20)                    Large n (n=2000)

      ╭────────╮                        ╭──╮
    ╭─╯        ╰─╮                    ╭─╯  ╰─╮
   ╭╯            ╰╮                  ╭╯      ╰╮
  ╭╯              ╰╮                ╭╯        ╰╮
 ╭╯                ╰░░░░░          ╭╯          ╰█
╭╯                  │╰░░░░░░     ╭╯             │█
───────────────────┬┼──────────  ──────────────┬┼──
                  μ₀ │ X̄                       μ₀│X̄
                     │                           │
                   Wide                       Narrow
               distribution                distribution
                     │                           │
             Large p-value               Small p-value
          (effect hidden in            (effect clearly
              noise)                     visible)
```

---

## p-value vs Effect Size

### Why Both Matter

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   STATISTICAL SIGNIFICANCE ≠ PRACTICAL IMPORTANCE           │
│                                                             │
│   p-value tells us: "Is there likely an effect?"           │
│   Effect size tells us: "How BIG is the effect?"           │
│                                                             │
│   We need BOTH for complete understanding!                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Two Studies

| Study | Effect | Sample Size | p-value | Conclusion |
|-------|--------|-------------|---------|------------|
| A | 0.5 point IQ increase | 50,000 | 0.001 | "Significant" but trivial |
| B | 15 point IQ increase | 30 | 0.08 | "Not significant" but meaningful |

**Study A:** Tiny effect detected with massive sample
**Study B:** Large effect missed due to small sample

### The Right Approach

```
Always report:
1. p-value (statistical significance)
2. Effect size (practical significance)
3. Confidence interval (precision)

Example:
"The treatment reduced pain by 2.5 points (95% CI: 1.8-3.2)
on a 10-point scale, p < 0.001, Cohen's d = 0.8 (large effect)."
```

---

## Common Effect Size Measures

### Cohen's d (for means)

```
        X̄ - μ₀       Difference in means
d = ─────────── = ─────────────────────────
         s          Standard deviation

Interpretation:
• |d| < 0.2:  Small effect
• |d| ≈ 0.5:  Medium effect  
• |d| > 0.8:  Large effect
```

### Correlation r

```
• |r| < 0.1:  Small
• |r| ≈ 0.3:  Medium
• |r| > 0.5:  Large
```

### Odds Ratio / Risk Ratio

For comparing proportions or risks between groups.

---

## The p-value Controversy

### Criticisms of p-values

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   WHY p-VALUES ARE CONTROVERSIAL                             │
│                                                             │
│   1. Often misinterpreted (as shown above)                  │
│                                                             │
│   2. Encourage binary thinking ("significant" vs "not")     │
│      instead of continuous evidence                         │
│                                                             │
│   3. p-hacking: Manipulating analysis to get p < 0.05      │
│                                                             │
│   4. Publication bias: Only "significant" results publish  │
│                                                             │
│   5. Don't tell us what we really want to know:            │
│      P(hypothesis | data), not P(data | hypothesis)        │
│                                                             │
│   6. Depend heavily on sample size                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### The ASA Statement (2016)

The American Statistical Association released a statement on p-values:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ASA PRINCIPLES ON p-VALUES                                 │
│                                                             │
│   1. p-values can indicate incompatibility between data    │
│      and a statistical model                                │
│                                                             │
│   2. p-values do NOT measure probability that H₀ is true   │
│                                                             │
│   3. Scientific conclusions should NOT be based only on    │
│      whether p < 0.05                                       │
│                                                             │
│   4. Proper reporting requires transparency                 │
│                                                             │
│   5. p-value does NOT measure effect size or importance    │
│                                                             │
│   6. By itself, p-value does NOT provide good evidence     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Best Practices

### Do's ✅

```
✅ Report exact p-values (p = 0.032, not just p < 0.05)
✅ Always report effect sizes alongside p-values
✅ Include confidence intervals
✅ Consider practical significance, not just statistical
✅ Pre-register your analysis plan
✅ Report all analyses, not just significant ones
✅ Use p-values as one piece of evidence, not the only one
✅ Understand what p-value does and doesn't mean
```

### Don'ts ❌

```
❌ Don't say "p = 0.05 means 5% chance H₀ is true"
❌ Don't treat p = 0.049 and p = 0.051 as fundamentally different
❌ Don't p-hack (try many analyses until one works)
❌ Don't ignore effect size
❌ Don't conclude "no effect" just because p > 0.05
❌ Don't use p-value as the sole criterion for decisions
❌ Don't confuse statistical and practical significance
```

---

## Python Implementation

### Calculating p-values

```python
import numpy as np
from scipy import stats

# ======================
# ONE-SAMPLE T-TEST
# ======================
def calculate_p_value_ttest(data, mu_0, alternative='two-sided'):
    """
    Calculate p-value for one-sample t-test
    
    Parameters:
    - data: sample data
    - mu_0: hypothesized mean under H₀
    - alternative: 'two-sided', 'greater', or 'less'
    """
    n = len(data)
    x_bar = np.mean(data)
    s = np.std(data, ddof=1)
    
    # Test statistic
    t_stat = (x_bar - mu_0) / (s / np.sqrt(n))
    df = n - 1
    
    # p-value
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.t.cdf(abs(t_stat), df))
    elif alternative == 'greater':
        p_value = 1 - stats.t.cdf(t_stat, df)
    elif alternative == 'less':
        p_value = stats.t.cdf(t_stat, df)
    
    return t_stat, p_value

# Example
data = np.array([34, 32, 36, 35, 33, 37, 31, 35, 34, 36])
mu_0 = 30

t_stat, p_value = calculate_p_value_ttest(data, mu_0, alternative='greater')
print(f"Sample mean: {np.mean(data):.2f}")
print(f"t-statistic: {t_stat:.4f}")
print(f"p-value: {p_value:.6f}")

# Using scipy directly
t_stat_scipy, p_value_scipy = stats.ttest_1samp(data, mu_0)
print(f"\nScipy results:")
print(f"t-statistic: {t_stat_scipy:.4f}")
print(f"p-value (two-sided): {p_value_scipy:.6f}")
```

### Z-test for Proportion

```python
import numpy as np
from scipy import stats

def z_test_proportion(successes, n, p_0, alternative='two-sided'):
    """
    Z-test for population proportion
    
    Parameters:
    - successes: number of successes
    - n: sample size
    - p_0: hypothesized proportion under H₀
    - alternative: 'two-sided', 'greater', or 'less'
    """
    p_hat = successes / n
    
    # Standard error under H₀
    se = np.sqrt(p_0 * (1 - p_0) / n)
    
    # Z-statistic
    z_stat = (p_hat - p_0) / se
    
    # p-value
    if alternative == 'two-sided':
        p_value = 2 * (1 - stats.norm.cdf(abs(z_stat)))
    elif alternative == 'greater':
        p_value = 1 - stats.norm.cdf(z_stat)
    elif alternative == 'less':
        p_value = stats.norm.cdf(z_stat)
    
    return z_stat, p_value, p_hat

# Example: Coin flip (65 heads in 100 flips)
z_stat, p_value, p_hat = z_test_proportion(65, 100, 0.5, 'two-sided')
print(f"Sample proportion: {p_hat:.4f}")
print(f"Z-statistic: {z_stat:.4f}")
print(f"p-value: {p_value:.6f}")

if p_value < 0.05:
    print("Reject H₀: Evidence of bias")
else:
    print("Fail to reject H₀: No strong evidence of bias")
```

### Visualizing p-value

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_p_value(test_stat, df=None, test_type='z', alternative='two-sided'):
    """
    Visualize p-value on the appropriate distribution
    """
    fig, ax = plt.subplots(figsize=(10, 6))
    
    # Create x values
    if test_type == 'z':
        x = np.linspace(-4, 4, 1000)
        y = stats.norm.pdf(x)
        dist = stats.norm
        title = "Standard Normal Distribution"
    else:  # t-distribution
        x = np.linspace(-4, 4, 1000)
        y = stats.t.pdf(x, df)
        dist = stats.t(df)
        title = f"t-Distribution (df={df})"
    
    # Plot distribution
    ax.plot(x, y, 'b-', linewidth=2, label='Distribution under H₀')
    ax.fill_between(x, y, alpha=0.1)
    
    # Shade p-value region
    if alternative == 'two-sided':
        # Right tail
        x_right = x[x >= abs(test_stat)]
        y_right = stats.norm.pdf(x_right) if test_type == 'z' else stats.t.pdf(x_right, df)
        ax.fill_between(x_right, y_right, color='red', alpha=0.5, label='p-value region')
        
        # Left tail
        x_left = x[x <= -abs(test_stat)]
        y_left = stats.norm.pdf(x_left) if test_type == 'z' else stats.t.pdf(x_left, df)
        ax.fill_between(x_left, y_left, color='red', alpha=0.5)
        
        p_value = 2 * (1 - dist.cdf(abs(test_stat)))
        
    elif alternative == 'greater':
        x_shade = x[x >= test_stat]
        y_shade = stats.norm.pdf(x_shade) if test_type == 'z' else stats.t.pdf(x_shade, df)
        ax.fill_between(x_shade, y_shade, color='red', alpha=0.5, label='p-value region')
        p_value = 1 - dist.cdf(test_stat)
        
    else:  # less
        x_shade = x[x <= test_stat]
        y_shade = stats.norm.pdf(x_shade) if test_type == 'z' else stats.t.pdf(x_shade, df)
        ax.fill_between(x_shade, y_shade, color='red', alpha=0.5, label='p-value region')
        p_value = dist.cdf(test_stat)
    
    # Add vertical line at test statistic
    ax.axvline(x=test_stat, color='red', linestyle='--', linewidth=2, 
               label=f'Test statistic = {test_stat:.2f}')
    if alternative == 'two-sided':
        ax.axvline(x=-test_stat, color='red', linestyle='--', linewidth=2)
    
    ax.set_xlabel('Test Statistic Value', fontsize=12)
    ax.set_ylabel('Probability Density', fontsize=12)
    ax.set_title(f'{title}\np-value = {p_value:.4f}', fontsize=14)
    ax.legend()
    ax.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()
    
    return p_value

# Example
p = visualize_p_value(test_stat=2.5, df=24, test_type='t', alternative='greater')
print(f"p-value: {p:.6f}")
```

### Effect Size Calculation

```python
import numpy as np

def cohens_d(group1, group2=None, mu_0=None):
    """
    Calculate Cohen's d effect size
    
    For one-sample: compare group1 to mu_0
    For two-sample: compare group1 to group2
    """
    if group2 is not None:
        # Two-sample Cohen's d
        n1, n2 = len(group1), len(group2)
        var1, var2 = np.var(group1, ddof=1), np.var(group2, ddof=1)
        
        # Pooled standard deviation
        pooled_std = np.sqrt(((n1 - 1) * var1 + (n2 - 1) * var2) / (n1 + n2 - 2))
        
        d = (np.mean(group1) - np.mean(group2)) / pooled_std
    else:
        # One-sample Cohen's d
        d = (np.mean(group1) - mu_0) / np.std(group1, ddof=1)
    
    # Interpretation
    abs_d = abs(d)
    if abs_d < 0.2:
        interpretation = "negligible"
    elif abs_d < 0.5:
        interpretation = "small"
    elif abs_d < 0.8:
        interpretation = "medium"
    else:
        interpretation = "large"
    
    return d, interpretation

# Example
data = np.array([34, 32, 36, 35, 33, 37, 31, 35, 34, 36])
d, interp = cohens_d(data, mu_0=30)
print(f"Cohen's d: {d:.4f} ({interp} effect)")
```

---

## Practice Problems 📝

### Problem 1: Interpretation
A study reports p = 0.03. Which statement is correct?
a) There's 3% chance H₀ is true
b) There's 97% chance H₁ is true
c) If H₀ were true, data this extreme would occur ~3% of the time
d) The effect has 3% chance of being real

<details>
<summary>Click for Answer</summary>

**Answer: (c)**

The p-value is the probability of observing data this extreme 
(or more extreme) IF the null hypothesis were true.

- (a) is wrong: p-value ≠ P(H₀ is true)
- (b) is wrong: p-value ≠ P(H₁ is true)
- (d) is wrong: p-value doesn't measure "realness" of effect

</details>

---

### Problem 2: Calculation
In a Z-test, you get Z = 1.8 (one-tailed, right). What's the p-value?

<details>
<summary>Click for Answer</summary>

```
p-value = P(Z ≥ 1.8)
        = 1 - Φ(1.8)
        = 1 - 0.9641
        = 0.0359

p-value ≈ 0.036 or 3.6%

At α = 0.05, this would be significant (reject H₀).
At α = 0.01, this would not be significant.
```

</details>

---

### Problem 3: Two-Tailed Test
For a two-tailed test, t = 2.3 with df = 20. Find the p-value.

<details>
<summary>Click for Answer</summary>

```
p-value = 2 × P(t > 2.3 | df = 20)

Using t-table or calculator:
P(t > 2.3 | df = 20) ≈ 0.016

p-value = 2 × 0.016 = 0.032

p-value ≈ 0.032 or 3.2%

This is significant at α = 0.05 (since 0.032 < 0.05)
```

</details>

---

### Problem 4: Sample Size Effect
Two studies test the same hypothesis with the same effect size (d = 0.3):
- Study A: n = 50, p = 0.12
- Study B: n = 200, p = 0.008

Why are the p-values so different?

<details>
<summary>Click for Answer</summary>

```
The p-value depends on BOTH effect size AND sample size!

With same effect size d:
• Larger n → Smaller standard error (SE = σ/√n)
• Smaller SE → Larger test statistic
• Larger test statistic → Smaller p-value

Study B has 4× the sample size of Study A, giving:
• √4 = 2× larger test statistic
• Much smaller p-value

This shows why p-value alone doesn't measure effect importance!
Both studies found the SAME effect, but only Study B has
"statistical significance."

LESSON: Always report effect size alongside p-value!
```

</details>

---

### Problem 5: Critical Thinking
A researcher gets p = 0.048 and concludes the effect is "significant" at α = 0.05. A second researcher gets p = 0.052 on the same research question and concludes "no effect." Is there really a fundamental difference?

<details>
<summary>Click for Answer</summary>

```
NO! This illustrates the problem with binary thinking.

p = 0.048 and p = 0.052 are essentially the same strength 
of evidence. The arbitrary threshold of 0.05 makes them 
look fundamentally different when they're not.

Better approach:
• Report exact p-values: "p = 0.048" and "p = 0.052"
• Both indicate "weak to moderate evidence against H₀"
• Report effect sizes and confidence intervals
• Don't treat 0.05 as a magical boundary

The difference between 0.048 and 0.052 is statistically
and practically negligible. The dichotomy of 
"significant/not significant" is misleading here.
```

</details>

---

## Summary: The Essence of p-value

```
┌─────────────────────────────────────────────────────────────────┐
│                        THE p-VALUE                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "How surprising is our data if H₀ were true?"                 │
│                                                                  │
│   DEFINITION:                                                    │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  p-value = P(data this extreme or more | H₀ is true)    │   │
│   │                                                          │   │
│   │  NOT the probability H₀ is true!                        │   │
│   │  NOT the probability of "due to chance"!                │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   INTERPRETATION:                                                │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  Small p (< α):  Data inconsistent with H₀              │   │
│   │                  → Reject H₀                            │   │
│   │                                                          │   │
│   │  Large p (> α):  Data consistent with H₀                │   │
│   │                  → Fail to reject H₀                    │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   REMEMBER:                                                      │
│   • p-value depends on sample size                              │
│   • Statistical significance ≠ practical importance             │
│   • Always report effect size too!                              │
│   • p = 0.049 and p = 0.051 are essentially the same           │
│   • p-value is evidence, not proof                              │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## The Bottom Line

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   The p-value is a useful tool, but:                            │
│                                                                  │
│   • It's NOT the probability your hypothesis is true            │
│   • It's NOT a measure of effect size                           │
│   • It's NOT the final answer                                   │
│                                                                  │
│   Use p-values ALONGSIDE:                                        │
│   • Effect sizes (Cohen's d, r, etc.)                           │
│   • Confidence intervals                                         │
│   • Domain knowledge                                             │
│   • Replication studies                                          │
│   • Common sense!                                                │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

> **"The p-value tells us how surprised we should be by the data if there were no effect. It doesn't tell us whether there IS an effect, how BIG the effect is, or how IMPORTANT it is. For those questions, we need more than just a p-value."**

Master the p-value, but remember: it's just one piece of the statistical puzzle! 🧩

---

*From probability to practice, from misunderstanding to mastery — that's the journey of the p-value!* 📊
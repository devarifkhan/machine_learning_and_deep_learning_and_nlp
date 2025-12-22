# Z-Test vs T-Test
## The Ultimate Comparison Guide 🎯

---

## The Fundamental Question

You have sample data and want to test a hypothesis about a population mean. Which test do you use?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE CORE DIFFERENCE                                        │
│                                                             │
│   Z-TEST: Use when σ (population std dev) is KNOWN          │
│   T-TEST: Use when σ is UNKNOWN (use sample s instead)      │
│                                                             │
│   In practice: T-test is used ~99% of the time!             │
│   Why? We almost NEVER know the true population σ.          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: Two Quality Inspectors

### Inspector Amir (The Veteran)

Amir has worked at the light bulb factory for 30 years. Over decades, the factory has established that bulb lifetimes have a **known population standard deviation of σ = 50 hours**.

When testing a new batch, Amir can use this historical σ:

```
       X̄ - μ₀
Z = ──────────  ← Uses known σ
       σ / √n
```

**Amir uses the Z-test!**

### Inspector Fatima (The New Hire)

Fatima joins a startup making innovative LED bulbs. There's **no historical data** — she doesn't know σ.

She must estimate the standard deviation from her sample:

```
       X̄ - μ₀
t = ──────────  ← Uses sample s (estimate of σ)
       s / √n
```

**Fatima uses the T-test!**

---

## The Key Difference: Known vs Unknown σ

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    Z-TEST                                    │
│                    ──────                                   │
│                                                             │
│   • Population σ is KNOWN (rare!)                          │
│   • Test statistic follows Standard Normal N(0,1)          │
│   • Critical values don't depend on sample size            │
│   • Fixed critical values: ±1.96 for 95%                   │
│                                                             │
│   Formula:        X̄ - μ₀                                   │
│              Z = ──────────                                 │
│                    σ / √n                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    T-TEST                                    │
│                    ──────                                   │
│                                                             │
│   • Population σ is UNKNOWN (common!)                      │
│   • Must estimate σ using sample s                         │
│   • Test statistic follows t-distribution                  │
│   • Critical values DEPEND on sample size (df)             │
│   • Heavier tails than normal                              │
│                                                             │
│   Formula:        X̄ - μ₀                                   │
│              t = ──────────                                 │
│                    s / √n                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Why Does This Matter?

### The Extra Uncertainty Problem

When we use s instead of σ, we introduce **additional uncertainty**:

```
σ is FIXED (if known):
• Every sample gives the same standard error σ/√n
• No extra variability from estimating σ

s VARIES from sample to sample:
• Different samples give different s values
• Sometimes s < σ (underestimate → t inflated)
• Sometimes s > σ (overestimate → t deflated)
• This extra variability spreads out the distribution!
```

### Visual: The Extra Uncertainty

```
Sample 1: s₁ = 48  → SE₁ = 48/√25 = 9.6  → t₁ = 10/9.6 = 1.04
Sample 2: s₂ = 55  → SE₂ = 55/√25 = 11.0 → t₂ = 10/11.0 = 0.91
Sample 3: s₃ = 42  → SE₃ = 42/√25 = 8.4  → t₃ = 10/8.4 = 1.19
Sample 4: s₄ = 60  → SE₄ = 60/√25 = 12.0 → t₄ = 10/12.0 = 0.83

Even with the SAME true difference, t varies because s varies!
This extra variability → heavier tails in t-distribution
```

---

## Distribution Comparison

### Visual: Z vs t Distributions

```
                    Standard Normal (Z) vs t-Distribution
                    
                              ╭─╮  ← Z (taller, thinner)
                            ╭─╯ ╰─╮
                           ╭╯     ╰╮
                          ╭╯  ╭─╮  ╰╮  ← t (shorter, fatter tails)
                         ╭╯  ╭╯ ╰╮  ╰╮
                        ╭╯  ╭╯   ╰╮  ╰╮
                       ╭╯ ╭─╯     ╰─╮ ╰╮
                     ╭─╯╭─╯         ╰─╮╰─╮
               ▓▓▓▓╭─╯╭─╯             ╰─╮╰─╮▓▓▓▓  ← More area in tails (t)
             ──────────────────────────────────────
                              0
                              
    Z: Thinner tails → Extreme values are RARE
    t: Heavier tails → Extreme values are MORE LIKELY
    
    As sample size ↑, t-distribution → Z-distribution
```

### Why Heavier Tails?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   The t-distribution has HEAVIER TAILS because:            │
│                                                             │
│   1. We're uncertain about σ (estimated by s)              │
│   2. s can be too small → inflates the t-statistic         │
│   3. s can be too large → deflates the t-statistic         │
│   4. This variability spreads out the distribution         │
│                                                             │
│   Result:                                                   │
│   • More probability in the tails                          │
│   • Need LARGER critical values to achieve same α          │
│   • More conservative (harder to reject H₀)                │
│                                                             │
│   The smaller the sample, the more uncertain s is,         │
│   and the heavier the tails become!                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Critical Values Comparison

### The Numbers Tell the Story

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   95% CONFIDENCE CRITICAL VALUES (Two-Tailed, α = 0.05)           │
│                                                                    │
│   Sample Size │   Z-Test   │   T-Test   │   Difference            │
│   ────────────┼────────────┼────────────┼───────────────           │
│   n = 5       │   1.960    │   2.776    │   +0.816 (42% larger!)  │
│   n = 10      │   1.960    │   2.262    │   +0.302 (15% larger)   │
│   n = 15      │   1.960    │   2.145    │   +0.185 (9% larger)    │
│   n = 20      │   1.960    │   2.093    │   +0.133 (7% larger)    │
│   n = 30      │   1.960    │   2.045    │   +0.085 (4% larger)    │
│   n = 50      │   1.960    │   2.010    │   +0.050 (3% larger)    │
│   n = 100     │   1.960    │   1.984    │   +0.024 (1% larger)    │
│   n = ∞       │   1.960    │   1.960    │   0 (identical!)        │
│                                                                    │
│   Key insight: With small n, t-test requires MUCH stronger        │
│   evidence to reject H₀!                                          │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

### Visual: Critical Values Across Sample Sizes

```
Critical Value (95%, two-tailed)
    │
3.0 ┤                                              
    │  ●  t-distribution (varies with n)
2.8 ┤  
    │
2.6 ┤     ●
    │
2.4 ┤        ●
    │           ●
2.2 ┤              ●
    │                 ●  ●
2.0 ┤─────────────────────●──●──●──●──●── Z = 1.96 (constant)
    │                              
1.8 ┤
    │
    └────┬────┬────┬────┬────┬────┬────┬────┬─── Sample Size
         5   10   15   20   30   50  100  ∞
         
As n → ∞, t-critical → Z-critical = 1.96
```

---

## Side-by-Side Formula Comparison

### One-Sample Tests

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   ONE-SAMPLE Z-TEST              ONE-SAMPLE T-TEST               │
│   ─────────────────              ─────────────────               │
│                                                                  │
│         X̄ - μ₀                         X̄ - μ₀                   │
│   Z = ──────────                 t = ──────────                  │
│         σ / √n                         s / √n                    │
│                                                                  │
│   • Uses σ (KNOWN)               • Uses s (sample estimate)     │
│   • Z ~ N(0, 1)                  • t ~ t(df = n-1)              │
│   • Fixed critical values        • Critical values depend on df │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Two-Sample Tests

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   TWO-SAMPLE Z-TEST              TWO-SAMPLE T-TEST               │
│   ─────────────────              ─────────────────               │
│                                                                  │
│         X̄₁ - X̄₂                       X̄₁ - X̄₂                   │
│   Z = ─────────────────          t = ─────────────────           │
│       √(σ₁²/n₁ + σ₂²/n₂)            √(s₁²/n₁ + s₂²/n₂)          │
│                                                                  │
│   • Uses σ₁, σ₂ (KNOWN)          • Uses s₁, s₂ (estimates)      │
│   • Z ~ N(0, 1)                  • t ~ t(df = Welch formula)    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Proportion Tests (Z-Test Only!)

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   PROPORTION Z-TEST (No t-test equivalent!)                      │
│   ─────────────────                                             │
│                                                                  │
│   One-Sample:                    Two-Sample:                     │
│                                                                  │
│         p̂ - p₀                         p̂₁ - p̂₂                  │
│   Z = ─────────────              Z = ─────────────────────       │
│       √(p₀(1-p₀)/n)                  √(p̂(1-p̂)(1/n₁+1/n₂))       │
│                                                                  │
│   For proportions, we always use Z-test because:                │
│   • The variance is determined by p: Var = p(1-p)/n             │
│   • No separate σ to estimate                                   │
│   • Large sample ensures normality (np ≥ 10, n(1-p) ≥ 10)      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## When to Use Which Test

### The Decision Flowchart

```
                              START
                                │
                                ▼
                    ┌───────────────────────┐
                    │ What are you testing? │
                    └───────────┬───────────┘
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
              ▼                 ▼                 ▼
          MEAN(S)          PROPORTION(S)      VARIANCE
              │                 │                 │
              ▼                 ▼                 ▼
    ┌─────────────────┐   Always use        Chi-square
    │ Is σ KNOWN?     │    Z-TEST             test
    └────────┬────────┘
             │
      ┌──────┴──────┐
      │             │
     YES           NO
      │             │
      ▼             ▼
   Z-TEST        T-TEST
      │             │
      ▼             ▼
  ┌───────┐   ┌──────────────┐
  │N(0,1) │   │Is n ≥ 30?    │
  └───────┘   └──────┬───────┘
                     │
              ┌──────┴──────┐
              │             │
             YES           NO
              │             │
              ▼             ▼
         T-test is     T-test (check
         robust        normality!)
```

### Quick Decision Table

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   SITUATION                              │  TEST TO USE            │
│   ───────────────────────────────────────┼────────────────────     │
│   Testing mean, σ KNOWN                  │  Z-test                 │
│   Testing mean, σ UNKNOWN                │  T-test                 │
│   Testing mean, σ unknown, n ≥ 30        │  T-test (≈ Z-test)     │
│   Testing mean, σ unknown, n < 30        │  T-test (important!)   │
│   Testing proportion                     │  Z-test                 │
│   Comparing two means, σ's known         │  Two-sample Z-test     │
│   Comparing two means, σ's unknown       │  Two-sample T-test     │
│   Paired data (before/after)             │  Paired T-test         │
│   Comparing two proportions              │  Two-proportion Z-test │
│                                                                    │
│   GOLDEN RULE: When in doubt, use T-test! It's always valid.      │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

## Practical Reality Check

### When is σ Actually Known?

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   σ MIGHT BE KNOWN (rare):                                       │
│   ─────────────────────────                                     │
│   • Manufacturing with decades of quality control data          │
│   • Standardized tests (IQ: σ = 15, SAT: σ ≈ 200)              │
│   • Well-established physical measurements                      │
│   • Government statistics with huge historical datasets         │
│                                                                  │
│   σ IS ALMOST CERTAINLY UNKNOWN (common):                        │
│   ────────────────────────────────────────                      │
│   • Medical/clinical research                                   │
│   • Social science studies                                      │
│   • Business analytics                                          │
│   • Scientific experiments                                       │
│   • Any new or novel measurement                                │
│   • Basically... everything in real research!                   │
│                                                                  │
│   PRACTICAL ADVICE:                                              │
│   Unless you have a VERY good reason to believe σ is known,    │
│   use the T-test. It's always valid and more conservative.     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### The "Large Sample" Shortcut

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   WHEN n IS LARGE (n ≥ 30):                                      │
│                                                                  │
│   • s becomes a good estimate of σ                              │
│   • t-distribution ≈ normal distribution                        │
│   • Z-test and T-test give nearly identical results            │
│                                                                  │
│   Example with n = 50, α = 0.05 (two-tailed):                   │
│   Z-critical = 1.960                                            │
│   t-critical = 2.010 (only 2.5% larger!)                        │
│                                                                  │
│   HOWEVER: Even with large n, using the T-test is:             │
│   • Technically correct (we're still estimating σ)             │
│   • More conservative                                           │
│   • What modern software does by default                        │
│                                                                  │
│   Bottom line: Use T-test. With large n, it won't matter.      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Complete Example Comparison

### Scenario: Testing Average Package Weight

A shipping company claims packages weigh 50 lbs on average. You sample 16 packages:

**Sample data:** X̄ = 52.5 lbs, s = 6 lbs, n = 16

**Two scenarios:**
- **Scenario A:** You know from historical data that σ = 6 lbs
- **Scenario B:** You don't know σ, so you estimate it with s = 6 lbs

### Scenario A: Z-Test (σ = 6 Known)

```
H₀: μ = 50
H₁: μ ≠ 50
α = 0.05, two-tailed

Step 1: Calculate Z-statistic
       X̄ - μ₀     52.5 - 50     2.5
Z = ────────── = ─────────── = ───── = 1.67
       σ/√n        6/√16        1.5

Step 2: Find critical value
Z-critical (α = 0.05, two-tailed) = ±1.96

Step 3: Compare
|Z| = 1.67 < 1.96 = Z-critical

Step 4: p-value
p-value = 2 × P(Z > 1.67) = 2 × 0.0475 = 0.095

Step 5: Decision
p-value = 0.095 > 0.05 → FAIL TO REJECT H₀

Conclusion: Insufficient evidence that mean weight ≠ 50 lbs.
```

### Scenario B: T-Test (σ Unknown, s = 6)

```
H₀: μ = 50
H₁: μ ≠ 50
α = 0.05, two-tailed

Step 1: Calculate t-statistic
       X̄ - μ₀     52.5 - 50     2.5
t = ────────── = ─────────── = ───── = 1.67
       s/√n        6/√16        1.5

(Same value! Because s = σ in this example)

Step 2: Find critical value
df = n - 1 = 15
t-critical (α = 0.05, df = 15, two-tailed) = ±2.131

Step 3: Compare
|t| = 1.67 < 2.131 = t-critical

Step 4: p-value
p-value = 2 × P(t > 1.67 | df = 15) = 2 × 0.058 = 0.116

Step 5: Decision
p-value = 0.116 > 0.05 → FAIL TO REJECT H₀

Conclusion: Insufficient evidence that mean weight ≠ 50 lbs.
```

### Comparing the Results

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│                    Z-TEST          T-TEST                        │
│                    ──────          ──────                        │
│   Test statistic   1.67            1.67 (same!)                 │
│   Critical value   ±1.96           ±2.131 (larger!)             │
│   p-value          0.095           0.116 (larger!)              │
│   Decision         Fail to reject  Fail to reject               │
│                                                                  │
│   KEY OBSERVATIONS:                                              │
│   • Same test statistic (because s = σ here)                    │
│   • T-test has LARGER critical value (more conservative)       │
│   • T-test has LARGER p-value (harder to reject)               │
│   • T-test accounts for uncertainty in estimating σ            │
│                                                                  │
│   In this case, both give the same decision, but in a         │
│   borderline case (p ≈ 0.05), they could differ!              │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## When Results Differ: A Borderline Case

### Same Data, Different Conclusions

Suppose we got X̄ = 53.5 instead of 52.5:

```
Test statistic = (53.5 - 50)/1.5 = 2.33

Z-TEST:
|Z| = 2.33 > 1.96 = Z-critical
p-value = 0.020 < 0.05
→ REJECT H₀ ✓

T-TEST (df = 15):
|t| = 2.33 > 2.131 = t-critical
p-value = 0.034 < 0.05
→ REJECT H₀ ✓

Both reject, but t-test p-value is larger.
```

Now suppose we got X̄ = 53.0:

```
Test statistic = (53.0 - 50)/1.5 = 2.00

Z-TEST:
|Z| = 2.00 > 1.96 = Z-critical
p-value = 0.046 < 0.05
→ REJECT H₀ ✓

T-TEST (df = 15):
|t| = 2.00 < 2.131 = t-critical
p-value = 0.064 > 0.05
→ FAIL TO REJECT H₀ ✗

DIFFERENT CONCLUSIONS!
The t-test is more conservative and doesn't reject.
```

### Why This Matters

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   Using the WRONG test can lead to:                             │
│                                                                  │
│   If you use Z-test when you should use T-test:                │
│   • Critical values are too small                               │
│   • p-values are too small                                      │
│   • You reject H₀ more often than you should                   │
│   • Type I error rate > α (false positives!)                   │
│                                                                  │
│   This is called "LIBERAL" — too willing to reject             │
│                                                                  │
│   The T-test is CONSERVATIVE:                                   │
│   • Accounts for uncertainty in estimating σ                   │
│   • Maintains the correct Type I error rate                    │
│   • Harder to reject when you shouldn't                        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Effect of Sample Size

### Convergence of Z and T

```
As n increases, T-test → Z-test:

n = 5:   t-critical = 2.776   vs   Z-critical = 1.960   (41% diff)
n = 10:  t-critical = 2.262   vs   Z-critical = 1.960   (15% diff)
n = 20:  t-critical = 2.093   vs   Z-critical = 1.960   (7% diff)
n = 30:  t-critical = 2.045   vs   Z-critical = 1.960   (4% diff)
n = 50:  t-critical = 2.010   vs   Z-critical = 1.960   (3% diff)
n = 100: t-critical = 1.984   vs   Z-critical = 1.960   (1% diff)
n → ∞:   t-critical → 1.960 = Z-critical               (0% diff)
```

### Visual Convergence

```
                   Distribution Shape
                   
n = 5 (df = 4):
                    ╭──╮
                  ╭─╯  ╰─╮
               ▓▓▓╯      ╰▓▓▓▓▓▓▓▓▓▓▓▓▓  Very heavy tails
            ────────────────────────────

n = 15 (df = 14):
                    ╭───╮
                  ╭─╯   ╰─╮
                ▓▓╯       ╰▓▓▓▓▓▓  Moderate tails
            ────────────────────────────

n = 30 (df = 29):
                    ╭───╮
                  ╭─╯   ╰─╮
                 ▓╯       ╰▓▓  Nearly normal
            ────────────────────────────

n → ∞:
                    ╭───╮
                  ╭─╯   ╰─╮    Identical to
                 ╭╯       ╰╮   Standard Normal!
            ────────────────────────────
```

---

## Summary Comparison Table

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   FEATURE              │    Z-TEST         │    T-TEST             │
│   ─────────────────────┼───────────────────┼─────────────────────  │
│   Population σ         │    KNOWN          │    UNKNOWN            │
│   Estimate of σ        │    Not needed     │    Uses sample s      │
│   Distribution         │    N(0, 1)        │    t(df)              │
│   Tails                │    Standard       │    Heavier            │
│   Critical values      │    Fixed (1.96)   │    Depend on df       │
│   Sample size impact   │    None           │    Larger n → Z-like  │
│   Conservativeness     │    Less           │    More               │
│   Real-world use       │    Rare (~1%)     │    Common (~99%)      │
│   For proportions      │    Yes            │    No (use Z)         │
│   For small samples    │    Risky          │    Appropriate        │
│   With large samples   │    OK             │    Also OK (≈ Z)      │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

## Common Misconceptions

### Misconception 1: "Use Z for large n, T for small n"

```
❌ WRONG: "If n ≥ 30, use Z-test. If n < 30, use T-test."

✅ CORRECT: The choice depends on whether σ is KNOWN, not on n!

• If σ is known → Z-test (regardless of n)
• If σ is unknown → T-test (regardless of n)

The "n = 30 rule" is about when Z and T give SIMILAR results,
not about which test to choose!
```

### Misconception 2: "T-test is only for small samples"

```
❌ WRONG: "T-test is a small-sample version of Z-test"

✅ CORRECT: T-test is for when σ is UNKNOWN (any sample size)

With large n:
• T-test is still technically correct
• Results will be nearly identical to Z-test
• Modern software uses T-test by default
```

### Misconception 3: "The test statistic value is different"

```
❌ WRONG: "Z and t give different test statistic values"

✅ CORRECT: If σ = s, the test statistics are IDENTICAL!

       X̄ - μ₀              X̄ - μ₀
Z = ──────────  and  t = ──────────  give same value if σ = s
       σ / √n              s / √n

The DIFFERENCE is in:
• What distribution we compare to
• The critical values used
• The p-value calculation
```

### Misconception 4: "Z-test is better because it's simpler"

```
❌ WRONG: "Z-test is preferred when possible"

✅ CORRECT: T-test is preferred in almost all real situations!

• T-test is always valid (accounts for uncertainty in s)
• Z-test requires knowing σ (rarely true)
• Using Z-test incorrectly inflates Type I error
• Modern software defaults to T-test for good reason
```

---

## Python Implementation

### Complete Comparison

```python
import numpy as np
from scipy import stats

def compare_z_and_t_tests(data, mu_0, sigma=None, alpha=0.05):
    """
    Compare Z-test and T-test results
    
    Parameters:
    - data: sample data
    - mu_0: hypothesized mean
    - sigma: population std dev (if known, for Z-test)
    - alpha: significance level
    """
    data = np.array(data)
    n = len(data)
    x_bar = np.mean(data)
    s = np.std(data, ddof=1)
    
    print("=" * 60)
    print("Z-TEST vs T-TEST COMPARISON")
    print("=" * 60)
    print(f"\nSample Statistics:")
    print(f"  n = {n}")
    print(f"  X̄ = {x_bar:.4f}")
    print(f"  s = {s:.4f}")
    print(f"  μ₀ = {mu_0}")
    print(f"  α = {alpha}")
    
    # T-TEST (always possible)
    print("\n" + "-" * 60)
    print("T-TEST (σ unknown, using s)")
    print("-" * 60)
    
    se_t = s / np.sqrt(n)
    t_stat = (x_bar - mu_0) / se_t
    df = n - 1
    t_crit = stats.t.ppf(1 - alpha/2, df)
    p_value_t = 2 * (1 - stats.t.cdf(abs(t_stat), df))
    
    print(f"  Standard Error: s/√n = {se_t:.4f}")
    print(f"  t-statistic: {t_stat:.4f}")
    print(f"  Degrees of freedom: {df}")
    print(f"  Critical value (two-tailed): ±{t_crit:.4f}")
    print(f"  p-value: {p_value_t:.4f}")
    print(f"  Decision: {'REJECT H₀' if p_value_t < alpha else 'FAIL TO REJECT H₀'}")
    
    # Z-TEST (only if sigma provided)
    if sigma is not None:
        print("\n" + "-" * 60)
        print(f"Z-TEST (σ = {sigma} known)")
        print("-" * 60)
        
        se_z = sigma / np.sqrt(n)
        z_stat = (x_bar - mu_0) / se_z
        z_crit = stats.norm.ppf(1 - alpha/2)
        p_value_z = 2 * (1 - stats.norm.cdf(abs(z_stat)))
        
        print(f"  Standard Error: σ/√n = {se_z:.4f}")
        print(f"  Z-statistic: {z_stat:.4f}")
        print(f"  Critical value (two-tailed): ±{z_crit:.4f}")
        print(f"  p-value: {p_value_z:.4f}")
        print(f"  Decision: {'REJECT H₀' if p_value_z < alpha else 'FAIL TO REJECT H₀'}")
        
        # Comparison
        print("\n" + "-" * 60)
        print("COMPARISON")
        print("-" * 60)
        print(f"  Test statistic: Z = {z_stat:.4f}, t = {t_stat:.4f}")
        print(f"  Critical values: Z = ±{z_crit:.4f}, t = ±{t_crit:.4f}")
        print(f"  Critical value difference: {((t_crit - z_crit)/z_crit)*100:.1f}%")
        print(f"  p-values: Z = {p_value_z:.4f}, t = {p_value_t:.4f}")
        print(f"  Same decision? {'Yes' if (p_value_z < alpha) == (p_value_t < alpha) else 'NO!'}")
    
    return {'t_stat': t_stat, 'p_value_t': p_value_t, 
            'z_stat': z_stat if sigma else None, 'p_value_z': p_value_z if sigma else None}

# Example: Package weights
np.random.seed(42)
packages = [52, 53, 49, 54, 51, 55, 48, 53, 50, 52, 
            51, 54, 49, 53, 52, 50]

result = compare_z_and_t_tests(packages, mu_0=50, sigma=6)
```

### Visualization Function

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_z_vs_t(df, alpha=0.05):
    """Visualize Z and t distributions with critical regions"""
    
    fig, axes = plt.subplots(1, 2, figsize=(14, 5))
    
    x = np.linspace(-4, 4, 1000)
    
    # Plot 1: Overlay both distributions
    ax1 = axes[0]
    ax1.plot(x, stats.norm.pdf(x), 'b-', linewidth=2, label='Z (Normal)')
    ax1.plot(x, stats.t.pdf(x, df), 'r--', linewidth=2, label=f't (df={df})')
    ax1.fill_between(x, stats.norm.pdf(x), alpha=0.2, color='blue')
    ax1.fill_between(x, stats.t.pdf(x, df), alpha=0.2, color='red')
    ax1.set_xlabel('Value', fontsize=12)
    ax1.set_ylabel('Density', fontsize=12)
    ax1.set_title(f'Z vs t Distribution (df = {df})', fontsize=14)
    ax1.legend()
    ax1.grid(True, alpha=0.3)
    
    # Plot 2: Critical regions comparison
    ax2 = axes[1]
    
    z_crit = stats.norm.ppf(1 - alpha/2)
    t_crit = stats.t.ppf(1 - alpha/2, df)
    
    ax2.plot(x, stats.norm.pdf(x), 'b-', linewidth=2, label='Z')
    ax2.plot(x, stats.t.pdf(x, df), 'r--', linewidth=2, label=f't (df={df})')
    
    # Z critical regions
    ax2.axvline(z_crit, color='blue', linestyle=':', linewidth=1.5, label=f'Z crit = ±{z_crit:.3f}')
    ax2.axvline(-z_crit, color='blue', linestyle=':', linewidth=1.5)
    
    # t critical regions
    ax2.axvline(t_crit, color='red', linestyle=':', linewidth=1.5, label=f't crit = ±{t_crit:.3f}')
    ax2.axvline(-t_crit, color='red', linestyle=':', linewidth=1.5)
    
    ax2.set_xlabel('Value', fontsize=12)
    ax2.set_ylabel('Density', fontsize=12)
    ax2.set_title(f'Critical Values (α = {alpha}, two-tailed)', fontsize=14)
    ax2.legend()
    ax2.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()

# Visualize for different df values
for df in [5, 15, 30]:
    visualize_z_vs_t(df)
```

### Critical Values Table Generator

```python
import numpy as np
from scipy import stats

def print_critical_value_comparison():
    """Print comparison table of Z and t critical values"""
    
    sample_sizes = [5, 10, 15, 20, 25, 30, 40, 50, 100, 500, 1000]
    alphas = [0.10, 0.05, 0.01]
    
    print("=" * 80)
    print("Z-TEST vs T-TEST CRITICAL VALUES (Two-Tailed)")
    print("=" * 80)
    
    for alpha in alphas:
        z_crit = stats.norm.ppf(1 - alpha/2)
        print(f"\nα = {alpha} (Confidence = {(1-alpha)*100:.0f}%)")
        print("-" * 80)
        print(f"{'n':>6} │ {'df':>4} │ {'Z-crit':>8} │ {'t-crit':>8} │ {'Diff':>8} │ {'% Diff':>8}")
        print("-" * 80)
        
        for n in sample_sizes:
            df = n - 1
            t_crit = stats.t.ppf(1 - alpha/2, df)
            diff = t_crit - z_crit
            pct_diff = (diff / z_crit) * 100
            
            print(f"{n:>6} │ {df:>4} │ {z_crit:>8.4f} │ {t_crit:>8.4f} │ {diff:>8.4f} │ {pct_diff:>7.2f}%")
        
        print(f"{'∞':>6} │ {'∞':>4} │ {z_crit:>8.4f} │ {z_crit:>8.4f} │ {'0.0000':>8} │ {'0.00%':>8}")

print_critical_value_comparison()
```

---

## Practice Problems 📝

### Problem 1: Choosing the Right Test
A researcher measures IQ scores (known to have σ = 15 in the general population) for 25 students at a special school. Which test should they use?

<details>
<summary>Click for Answer</summary>

```
ANSWER: Z-TEST

Reason: σ = 15 is KNOWN (IQ tests are standardized with 
known population parameters).

Since σ is known, use the Z-test:
Z = (X̄ - 100)/(15/√25) = (X̄ - 100)/3

Note: This is one of the rare cases where σ is actually known!
```

</details>

---

### Problem 2: Impact of Sample Size
Two researchers test the same hypothesis with:
- Researcher A: n = 10, gets t = 2.10
- Researcher B: n = 100, gets t = 2.10

Who is more likely to reject H₀ at α = 0.05?

<details>
<summary>Click for Answer</summary>

```
ANSWER: Researcher B (larger sample)

Researcher A (n = 10, df = 9):
t-critical = 2.262
|t| = 2.10 < 2.262 → FAIL TO REJECT H₀

Researcher B (n = 100, df = 99):
t-critical ≈ 1.984
|t| = 2.10 > 1.984 → REJECT H₀

Same test statistic, DIFFERENT conclusions!

With larger n:
• df is larger
• t-distribution is closer to normal
• Critical values are smaller
• Easier to reject H₀ (more power)
```

</details>

---

### Problem 3: When Tests Disagree
With n = 12, X̄ = 105, s = 15, μ₀ = 100, α = 0.05 (two-tailed):

a) Would Z-test reject H₀?
b) Would T-test reject H₀?

<details>
<summary>Click for Answer</summary>

```
Calculate test statistic:
(105 - 100)/(15/√12) = 5/4.33 = 1.15

a) Z-TEST:
Z-critical = ±1.96
|Z| = 1.15 < 1.96 → FAIL TO REJECT H₀
p-value = 0.25

b) T-TEST (df = 11):
t-critical = ±2.201
|t| = 1.15 < 2.201 → FAIL TO REJECT H₀
p-value = 0.27

In this case, both tests agree (fail to reject).

But the t-test is MORE conservative:
• Larger critical value (2.201 vs 1.96)
• Larger p-value (0.27 vs 0.25)

If the test statistic were closer to the boundary 
(e.g., t = 2.0), they could disagree!
```

</details>

---

### Problem 4: Proportions
A political poll of 400 voters finds 55% support Candidate A. 
Which test do you use to determine if this differs from 50%?

<details>
<summary>Click for Answer</summary>

```
ANSWER: Z-TEST

For proportions, we always use Z-test because:

1. The population variance is determined by p:
   Var(p̂) = p(1-p)/n
   There's no separate σ to estimate!

2. With large n (np ≥ 10, n(1-p) ≥ 10), normal approximation applies

Calculation:
p̂ = 0.55, p₀ = 0.50, n = 400

Z = (0.55 - 0.50)/√(0.50×0.50/400)
  = 0.05/√0.000625
  = 0.05/0.025
  = 2.0

p-value = 2 × P(Z > 2.0) = 0.046 < 0.05 → REJECT H₀

There is significant evidence that support differs from 50%.
```

</details>

---

## Summary: The Final Verdict

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│                    Z-TEST vs T-TEST                              │
│                    ════════════════                              │
│                                                                  │
│   THE KEY DIFFERENCE:                                            │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  Z-Test: σ is KNOWN → Use σ in formula                  │   │
│   │  T-Test: σ is UNKNOWN → Estimate with s                 │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THE CONSEQUENCE:                                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  T-test has heavier tails → More conservative          │   │
│   │  T-test has larger critical values                      │   │
│   │  T-test is harder to reject H₀ (appropriately so!)     │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THE CONVERGENCE:                                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  As n → ∞, t-distribution → normal distribution        │   │
│   │  Large samples: Z-test ≈ T-test                        │   │
│   │  Rule of thumb: n ≥ 30 gives similar results           │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THE PRACTICAL ADVICE:                                          │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Use T-test for means (almost always!)                │   │
│   │  • Use Z-test for proportions                           │   │
│   │  • When in doubt, use T-test!                          │   │
│   │  • Modern software defaults to T-test for good reason  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────────┐
│                     QUICK REFERENCE                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   Z-TEST                        T-TEST                          │
│   ──────                        ──────                          │
│   σ known                       σ unknown                       │
│   Z = (X̄-μ₀)/(σ/√n)            t = (X̄-μ₀)/(s/√n)              │
│   Compare to N(0,1)             Compare to t(df)                │
│   95% crit: ±1.96              95% crit: depends on df          │
│                                                                  │
│   PROPORTIONS: Always Z-test                                    │
│   MEANS: Almost always T-test                                   │
│                                                                  │
│   95% t-critical values:                                        │
│   df=5: 2.571 │ df=10: 2.228 │ df=30: 2.042 │ df=∞: 1.960      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

> **"The difference between Z-test and T-test is simple: do you know σ or not? In practice, you almost never know σ, so use the T-test. It's always valid, properly accounts for uncertainty, and with large samples gives the same answer as Z-test anyway."**

Understanding when to use each test is fundamental to statistical inference. Now you know! 🎯

---

*From known to unknown, from Z to t — that's the journey of estimating σ!* 📊
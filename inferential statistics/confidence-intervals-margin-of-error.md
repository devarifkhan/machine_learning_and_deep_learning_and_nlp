# Confidence Intervals and Margin of Error
## Quantifying Uncertainty in Estimation 📊

---

## The Fundamental Problem

We want to know something about a **population**, but we can only measure a **sample**. How confident can we be in our estimate?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE ESTIMATION PROBLEM                                     │
│                                                             │
│   Population Parameter (unknown): μ, p, σ², etc.           │
│   Sample Statistic (calculated): X̄, p̂, s², etc.            │
│                                                             │
│   Sample statistic ESTIMATES the population parameter,     │
│   but it's not EXACTLY equal to it!                        │
│                                                             │
│   QUESTION: How close is our estimate likely to be?        │
│   ANSWER: Confidence Interval tells us!                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: The Election Poll

Fatima is a pollster trying to predict the upcoming election. She can't ask all 10 million voters, so she randomly surveys 1,000 people.

**Result:** 540 out of 1,000 (54%) support Candidate A.

**The Question:** Can she confidently say Candidate A will win?

```
What Fatima knows:
• Sample proportion: p̂ = 0.54 (54%)
• Sample size: n = 1,000

What Fatima wants to know:
• True population proportion: p = ???
• Is p really above 50%?

The confidence interval will answer this!
```

---

## What is a Confidence Interval?

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONFIDENCE INTERVAL (CI)                                   │
│                                                             │
│   A range of values that is likely to contain the true     │
│   population parameter with a specified level of           │
│   confidence.                                               │
│                                                             │
│   General Form:                                             │
│   ┌─────────────────────────────────────────────────────┐  │
│   │                                                      │  │
│   │  CI = Point Estimate ± Margin of Error              │  │
│   │                                                      │  │
│   │  CI = Statistic ± (Critical Value × Standard Error) │  │
│   │                                                      │  │
│   └─────────────────────────────────────────────────────┘  │
│                                                             │
│   Example: "We are 95% confident that the true mean        │
│   is between 47.5 and 52.5"                                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual Representation

```
                    Confidence Interval
                    
    ◄──────────────────────────────────────────────►
    │                                              │
    │              Point Estimate                  │
    │                    │                         │
    │         ◄────────  ●  ────────►             │
    │         │    Margin of Error    │            │
    │         │                       │            │
────┼─────────┼───────────────────────┼────────────┼────
  Lower      L                       U          Upper
  Bound                                         Bound
    
    
    L = Point Estimate - Margin of Error
    U = Point Estimate + Margin of Error
```

---

## What is Margin of Error?

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MARGIN OF ERROR (ME)                                       │
│                                                             │
│   The "±" part of a confidence interval.                   │
│   Measures the maximum expected difference between the     │
│   sample statistic and the true population parameter.      │
│                                                             │
│   Formula:                                                  │
│   ┌─────────────────────────────────────────────────────┐  │
│   │                                                      │  │
│   │  ME = Critical Value × Standard Error               │  │
│   │                                                      │  │
│   │  ME = z* × SE   (for large samples or σ known)     │  │
│   │  ME = t* × SE   (for small samples, σ unknown)     │  │
│   │                                                      │  │
│   └─────────────────────────────────────────────────────┘  │
│                                                             │
│   In news: "±3 percentage points" is the margin of error  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### The Components

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MARGIN OF ERROR = Critical Value × Standard Error        │
│                                                             │
│   CRITICAL VALUE (z* or t*):                               │
│   • Depends on confidence level (90%, 95%, 99%)           │
│   • Higher confidence → Larger critical value             │
│   • From Z or t distribution                              │
│                                                             │
│   STANDARD ERROR (SE):                                      │
│   • Measures variability of the statistic                  │
│   • SE = σ/√n (for means, σ known)                        │
│   • SE = s/√n (for means, σ unknown)                      │
│   • SE = √(p̂(1-p̂)/n) (for proportions)                   │
│   • Larger n → Smaller SE → Smaller ME                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Common Confidence Levels and Critical Values

### For Z-Distribution (Large Samples)

```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│   CRITICAL VALUES FOR Z-DISTRIBUTION                        │
│                                                            │
│   Confidence │  α    │  α/2   │  z*                        │
│   Level      │       │        │  (Critical Value)          │
│   ───────────┼───────┼────────┼──────────────────          │
│   90%        │ 0.10  │ 0.05   │  1.645                     │
│   95%        │ 0.05  │ 0.025  │  1.960                     │
│   99%        │ 0.01  │ 0.005  │  2.576                     │
│   99.9%      │ 0.001 │ 0.0005 │  3.291                     │
│                                                            │
│   Most common: 95% confidence with z* = 1.96              │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Visual: What 95% Confidence Means

```
                    Standard Normal Distribution
                    
                           ╭───╮
                         ╭─╯   ╰─╮
                        ╭╯       ╰╮
                       ╭╯         ╰╮
                      ╭╯           ╰╮
          ▓▓▓▓▓▓▓▓▓▓╭─╯             ╰─╮▓▓▓▓▓▓▓▓▓▓
         ──────────────────────────────────────────
               -1.96       0        1.96
                 │                    │
                 │◄───── 95% ────────►│
                 │                    │
               2.5%                 2.5%
               
    95% of sample means fall within ±1.96 standard errors
    of the true population mean.
```

---

## Confidence Interval for a Mean

### When σ is Known (Z-Interval)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CI FOR MEAN (σ KNOWN)                                      │
│                                                             │
│              σ                                              │
│   CI = X̄ ± z* × ────                                        │
│              √n                                             │
│                                                             │
│   Where:                                                    │
│   • X̄ = sample mean                                        │
│   • z* = critical value (1.96 for 95%)                     │
│   • σ = population standard deviation                      │
│   • n = sample size                                         │
│                                                             │
│   Margin of Error = z* × (σ/√n)                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### When σ is Unknown (t-Interval) — More Common!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CI FOR MEAN (σ UNKNOWN)                                    │
│                                                             │
│              s                                              │
│   CI = X̄ ± t* × ────                                        │
│              √n                                             │
│                                                             │
│   Where:                                                    │
│   • X̄ = sample mean                                        │
│   • t* = critical value from t-distribution               │
│   • s = sample standard deviation                          │
│   • n = sample size                                         │
│   • df = n - 1                                             │
│                                                             │
│   Margin of Error = t* × (s/√n)                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 1: Average Study Hours

A professor wants to estimate average daily study hours for students. She surveys 25 students:

**Sample:** X̄ = 4.2 hours, s = 1.5 hours, n = 25

**Find:** 95% confidence interval for the true mean.

### Solution

```
Step 1: Identify the situation
• σ unknown → Use t-interval
• n = 25, df = 24
• 95% confidence

Step 2: Find the critical value
t* = t₀.₀₂₅, ₂₄ = 2.064

Step 3: Calculate standard error
SE = s/√n = 1.5/√25 = 1.5/5 = 0.30 hours

Step 4: Calculate margin of error
ME = t* × SE = 2.064 × 0.30 = 0.62 hours

Step 5: Construct the interval
CI = X̄ ± ME
   = 4.2 ± 0.62
   = (3.58, 4.82)

INTERPRETATION:
"We are 95% confident that the true average study time
for all students is between 3.58 and 4.82 hours per day."
```

### Visual

```
                    95% Confidence Interval
                    
    ◄───────────────────────────────────────────►
    │                                           │
    │              X̄ = 4.2                      │
    │                 │                         │
    │      ◄── ME ────●──── ME ──►             │
    │        0.62           0.62                │
    │                                           │
────┼─────────────────────────────────────────────┼────
   3.58                                        4.82
    │                                           │
    Lower                                     Upper
    Bound                                     Bound
```

---

## Confidence Interval for a Proportion

### Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CI FOR PROPORTION                                          │
│                                                             │
│                    ┌───────────                             │
│                   │ p̂(1 - p̂)                               │
│   CI = p̂ ± z* ×  │ ─────────                               │
│                  √     n                                    │
│                                                             │
│   Where:                                                    │
│   • p̂ = sample proportion = x/n                            │
│   • z* = critical value (1.96 for 95%)                     │
│   • n = sample size                                         │
│                                                             │
│   CONDITIONS:                                               │
│   • np̂ ≥ 10 and n(1-p̂) ≥ 10 (for normal approximation)    │
│   • Random sample                                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 2: Election Poll (Solving Fatima's Problem)

Fatima's poll: 540 out of 1,000 support Candidate A.

**Find:** 95% confidence interval for true support.

### Solution

```
Step 1: Calculate sample proportion
p̂ = 540/1000 = 0.54

Step 2: Check conditions
np̂ = 1000 × 0.54 = 540 ≥ 10 ✓
n(1-p̂) = 1000 × 0.46 = 460 ≥ 10 ✓

Step 3: Find critical value
z* = 1.96 (for 95% confidence)

Step 4: Calculate standard error
SE = √(p̂(1-p̂)/n) = √(0.54 × 0.46 / 1000)
   = √(0.2484 / 1000)
   = √0.0002484
   = 0.01576

Step 5: Calculate margin of error
ME = z* × SE = 1.96 × 0.01576 = 0.031 (or 3.1%)

Step 6: Construct the interval
CI = p̂ ± ME
   = 0.54 ± 0.031
   = (0.509, 0.571)
   = (50.9%, 57.1%)

INTERPRETATION:
"We are 95% confident that between 50.9% and 57.1%
of ALL voters support Candidate A."

Since the ENTIRE interval is above 50%, Fatima can 
confidently report that Candidate A is leading!
```

### What If the Result Was Closer?

```
Scenario: 510 out of 1000 (51%) support Candidate A

p̂ = 0.51
SE = √(0.51 × 0.49 / 1000) = 0.0158
ME = 1.96 × 0.0158 = 0.031

CI = 0.51 ± 0.031 = (0.479, 0.541) = (47.9%, 54.1%)

The interval includes 50%!
We CANNOT confidently say Candidate A is winning.
The race is "too close to call."
```

---

## Understanding Confidence Level

### What Does "95% Confident" Mean?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CORRECT INTERPRETATION:                                    │
│   ─────────────────────────                                 │
│   "If we repeated this sampling procedure many times,       │
│   95% of the resulting confidence intervals would           │
│   contain the true population parameter."                   │
│                                                             │
│   INCORRECT INTERPRETATIONS:                                 │
│   ──────────────────────────                                │
│   ✗ "There's a 95% probability the parameter is in         │
│      this interval" (Parameter is fixed, not random!)      │
│                                                             │
│   ✗ "95% of the data falls in this interval"               │
│      (CI is about the parameter, not the data!)            │
│                                                             │
│   ✗ "We are 95% sure our estimate is correct"              │
│      (The interval, not the point estimate, matters!)      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: What 95% Confidence Really Means

```
Imagine taking 20 different samples and computing CIs:

Sample 1:  ├──────[═══●═══]──────┤     Contains μ ✓
Sample 2:  ├─────[═══●═══]───────┤     Contains μ ✓
Sample 3:  ├──────[═══●═══]──────┤     Contains μ ✓
Sample 4:  ├───────[═══●═══]─────┤     Contains μ ✓
Sample 5:  ├─────[═══●═══]───────┤     Contains μ ✓
Sample 6:  ├────[═══●═══]────────┤     Contains μ ✓
Sample 7:  ├──────[═══●═══]──────┤     Contains μ ✓
Sample 8:  ├───[═══●═══]─────────┤     MISSES μ ✗
Sample 9:  ├─────[═══●═══]───────┤     Contains μ ✓
Sample 10: ├──────[═══●═══]──────┤     Contains μ ✓
Sample 11: ├────────[═══●═══]────┤     Contains μ ✓
Sample 12: ├─────[═══●═══]───────┤     Contains μ ✓
Sample 13: ├──────[═══●═══]──────┤     Contains μ ✓
Sample 14: ├─────[═══●═══]───────┤     Contains μ ✓
Sample 15: ├───────[═══●═══]─────┤     Contains μ ✓
Sample 16: ├────[═══●═══]────────┤     Contains μ ✓
Sample 17: ├──────[═══●═══]──────┤     Contains μ ✓
Sample 18: ├─────[═══●═══]───────┤     Contains μ ✓
Sample 19: ├──────[═══●═══]──────┤     Contains μ ✓
Sample 20: ├────────[═══●═══]────┤     Contains μ ✓
           │         │
           │         │
           │         ▼
           │    True μ (unknown)
           
19 out of 20 (95%) contain the true μ!
1 out of 20 (5%) misses — this is expected!
```

---

## Factors Affecting Confidence Interval Width

### What Makes CIs Wider or Narrower?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CI WIDTH depends on:                                       │
│                                                             │
│   1. CONFIDENCE LEVEL                                        │
│      Higher confidence → WIDER interval                     │
│      99% CI is wider than 95% CI                           │
│                                                             │
│   2. SAMPLE SIZE (n)                                        │
│      Larger n → NARROWER interval                          │
│      (SE decreases as n increases)                         │
│                                                             │
│   3. VARIABILITY (σ or s)                                   │
│      More variability → WIDER interval                     │
│      (More spread = more uncertainty)                      │
│                                                             │
│   4. FOR PROPORTIONS: Value of p̂                           │
│      p̂ near 0.5 → WIDEST interval                         │
│      p̂ near 0 or 1 → NARROWER interval                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Effect of Confidence Level

```
Same data, different confidence levels:

90% CI:     ├────[════●════]────┤
                 Narrower

95% CI:     ├──[══════●══════]──┤
                 Medium

99% CI:     ├[════════●════════]┤
                 Wider

Higher confidence = Cast a wider net to be more sure
                   you catch the true parameter!
```

### Visual: Effect of Sample Size

```
Same population, different sample sizes:

n = 25:     ├──[══════●══════]──┤
                 Wide

n = 100:    ├────[════●════]────┤
                Narrower

n = 400:    ├──────[══●══]──────┤
               Even narrower

n = 1600:   ├───────[=●=]───────┤
                Very narrow

Quadrupling n cuts the width in HALF!
(Because SE = σ/√n)
```

---

## The Trade-Off: Confidence vs Precision

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE CONFIDENCE-PRECISION TRADE-OFF                         │
│                                                             │
│   HIGHER CONFIDENCE (99% vs 95%):                           │
│   + More likely to contain true parameter                   │
│   − Wider interval (less precise)                          │
│   − Less useful for decision-making                        │
│                                                             │
│   LOWER CONFIDENCE (90% vs 95%):                            │
│   + Narrower interval (more precise)                       │
│   − Less likely to contain true parameter                  │
│   − Higher risk of being wrong                             │
│                                                             │
│   THE SOLUTION: Increase sample size!                       │
│   Larger n gives both high confidence AND precision        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Sample Size Calculation

### How Large a Sample Do We Need?

For a **desired margin of error** (ME) at a given confidence level:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SAMPLE SIZE FORMULAS                                       │
│                                                             │
│   For MEANS:                                                │
│                    ⎛ z* × σ ⎞²                              │
│              n = ⎜ ─────── ⎟                                │
│                    ⎝   ME   ⎠                               │
│                                                             │
│   For PROPORTIONS:                                          │
│                         z*²                                 │
│              n = p̂(1-p̂) × ────                              │
│                         ME²                                 │
│                                                             │
│   If p̂ unknown, use p̂ = 0.5 (conservative)                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Poll Sample Size

**Goal:** 95% CI for proportion with margin of error ≤ 3%

```
z* = 1.96 (for 95%)
ME = 0.03
p̂ = 0.5 (unknown, use conservative estimate)

n = p̂(1-p̂) × (z*/ME)²
  = 0.5 × 0.5 × (1.96/0.03)²
  = 0.25 × (65.33)²
  = 0.25 × 4268.4
  = 1067.1

Round up: n = 1068

Need at least 1,068 people for ±3% margin of error!
```

### Sample Size Quick Reference

```
For 95% CI with proportion p̂ = 0.5:

┌────────────────────────────────────────┐
│  Desired ME  │  Required n             │
│  ────────────┼────────────             │
│  ±10%        │  97                     │
│  ±5%         │  385                    │
│  ±4%         │  601                    │
│  ±3%         │  1,068                  │
│  ±2%         │  2,401                  │
│  ±1%         │  9,604                  │
│  ±0.5%       │  38,416                 │
└────────────────────────────────────────┘

Cutting ME in half requires 4× the sample size!
```

---

## Common Confidence Intervals

### Summary of Formulas

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   CONFIDENCE INTERVAL FORMULAS                                   │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   MEAN (σ known):          X̄ ± z* × (σ/√n)                      │
│                                                                  │
│   MEAN (σ unknown):        X̄ ± t* × (s/√n)                      │
│                            df = n - 1                           │
│                                                                  │
│   PROPORTION:              p̂ ± z* × √(p̂(1-p̂)/n)                 │
│                                                                  │
│   DIFFERENCE OF MEANS      (X̄₁ - X̄₂) ± t* × SE                  │
│   (Independent):           SE = √(s₁²/n₁ + s₂²/n₂)             │
│                                                                  │
│   DIFFERENCE OF MEANS      d̄ ± t* × (s_d/√n)                    │
│   (Paired):                df = n - 1                           │
│                                                                  │
│   DIFFERENCE OF            (p̂₁ - p̂₂) ± z* × SE                  │
│   PROPORTIONS:             SE = √(p̂₁(1-p̂₁)/n₁ + p̂₂(1-p̂₂)/n₂)  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 3: Difference of Two Means

A company tests two training methods:
- Method A: n₁ = 30, X̄₁ = 85, s₁ = 8
- Method B: n₂ = 35, X̄₂ = 78, s₂ = 10

**Find:** 95% CI for the difference in means (μ₁ - μ₂)

### Solution

```
Step 1: Calculate the difference
X̄₁ - X̄₂ = 85 - 78 = 7

Step 2: Calculate standard error
SE = √(s₁²/n₁ + s₂²/n₂)
   = √(64/30 + 100/35)
   = √(2.133 + 2.857)
   = √4.99
   = 2.23

Step 3: Find critical value (using Welch df or approximation)
df ≈ 62 (Welch-Satterthwaite)
t* ≈ 2.00

Step 4: Calculate margin of error
ME = t* × SE = 2.00 × 2.23 = 4.46

Step 5: Construct the interval
CI = (X̄₁ - X̄₂) ± ME
   = 7 ± 4.46
   = (2.54, 11.46)

INTERPRETATION:
"We are 95% confident that Method A produces scores
between 2.54 and 11.46 points higher than Method B."

Since 0 is NOT in the interval, the difference is
statistically significant!
```

---

## Confidence Intervals vs Hypothesis Tests

### The Connection

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CI AND HYPOTHESIS TEST ARE RELATED!                        │
│                                                             │
│   For a two-tailed test at significance level α:           │
│                                                             │
│   If (1-α) CI does NOT contain null value → Reject H₀     │
│   If (1-α) CI CONTAINS null value → Fail to reject H₀      │
│                                                             │
│   Example:                                                  │
│   H₀: μ = 50                                               │
│   95% CI: (52.3, 58.7)                                     │
│                                                             │
│   50 is NOT in the interval → Reject H₀ at α = 0.05       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Why CIs Are Often Better Than p-values

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ADVANTAGES OF CONFIDENCE INTERVALS                         │
│                                                             │
│   1. Shows MAGNITUDE of effect, not just "significant"     │
│      • p-value: "The effect is significant"               │
│      • CI: "The effect is between 3 and 7 units"          │
│                                                             │
│   2. Shows PRECISION of estimate                           │
│      • Narrow CI = Precise estimate                        │
│      • Wide CI = Uncertain estimate                        │
│                                                             │
│   3. Shows practical significance                          │
│      • Statistical significance ≠ Practical importance    │
│      • CI helps assess if effect is meaningful            │
│                                                             │
│   4. Allows comparison across studies                      │
│      • CIs from different studies can be compared         │
│      • More informative than "p < 0.05" everywhere        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Common Mistakes and Misconceptions

### Mistake 1: Wrong Interpretation of Confidence Level

```
❌ WRONG: "There's a 95% probability that μ is in this interval"

✅ CORRECT: "If we repeated sampling, 95% of intervals would 
   contain μ"

The parameter μ is FIXED (not random). Either it's in the 
interval or it's not. The "95%" refers to the procedure,
not this specific interval.
```

### Mistake 2: Confusing CI for Data Range

```
❌ WRONG: "95% of students study between 3.58 and 4.82 hours"

✅ CORRECT: "We're 95% confident the TRUE MEAN is between 
   3.58 and 4.82 hours"

CI is about the parameter (mean), not individual data points!
```

### Mistake 3: Non-Overlapping CIs Mean Significant Difference

```
❌ WRONG: "If two CIs don't overlap, they're significantly different"

⚠️ PARTIALLY CORRECT: Non-overlap implies significance, BUT
   overlap does NOT necessarily mean non-significance!

Two CIs can overlap and still have a significant difference.
Use a CI for the DIFFERENCE to properly test this.
```

### Mistake 4: Ignoring Sample Size Implications

```
❌ WRONG: "My 95% CI is (45, 55), so I'm very confident about 50"

✅ CORRECT: Consider the width! 
   (45, 55) with n = 25 is much less precise than
   (49, 51) with n = 1000
```

---

## Reporting Confidence Intervals

### How to Write CIs in Reports

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   REPORTING FORMATS                                          │
│                                                             │
│   Format 1: Point estimate with CI                          │
│   "The mean score was 75.3 (95% CI: 72.1 to 78.5)"         │
│                                                             │
│   Format 2: CI with margin of error                         │
│   "Support was 54% ± 3% (95% CI)"                          │
│                                                             │
│   Format 3: Formal notation                                 │
│   "M = 75.3, 95% CI [72.1, 78.5]"                          │
│                                                             │
│   ALWAYS REPORT:                                            │
│   • The confidence level (90%, 95%, 99%)                   │
│   • Both lower and upper bounds                            │
│   • The point estimate                                      │
│   • Sample size (helpful for context)                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Python Implementation

### Complete CI Functions

```python
import numpy as np
from scipy import stats

def ci_mean_z(x_bar, sigma, n, confidence=0.95):
    """
    Confidence interval for mean (sigma known)
    """
    alpha = 1 - confidence
    z_star = stats.norm.ppf(1 - alpha/2)
    se = sigma / np.sqrt(n)
    me = z_star * se
    
    return {
        'point_estimate': x_bar,
        'margin_of_error': me,
        'ci_lower': x_bar - me,
        'ci_upper': x_bar + me,
        'confidence': confidence,
        'se': se,
        'z_star': z_star
    }

def ci_mean_t(data=None, x_bar=None, s=None, n=None, confidence=0.95):
    """
    Confidence interval for mean (sigma unknown)
    """
    if data is not None:
        x_bar = np.mean(data)
        s = np.std(data, ddof=1)
        n = len(data)
    
    alpha = 1 - confidence
    df = n - 1
    t_star = stats.t.ppf(1 - alpha/2, df)
    se = s / np.sqrt(n)
    me = t_star * se
    
    return {
        'point_estimate': x_bar,
        'margin_of_error': me,
        'ci_lower': x_bar - me,
        'ci_upper': x_bar + me,
        'confidence': confidence,
        'se': se,
        't_star': t_star,
        'df': df
    }

def ci_proportion(x, n, confidence=0.95):
    """
    Confidence interval for proportion
    """
    p_hat = x / n
    alpha = 1 - confidence
    z_star = stats.norm.ppf(1 - alpha/2)
    se = np.sqrt(p_hat * (1 - p_hat) / n)
    me = z_star * se
    
    return {
        'point_estimate': p_hat,
        'margin_of_error': me,
        'ci_lower': max(0, p_hat - me),
        'ci_upper': min(1, p_hat + me),
        'confidence': confidence,
        'se': se,
        'z_star': z_star
    }

# Examples
print("=" * 60)
print("CONFIDENCE INTERVAL EXAMPLES")
print("=" * 60)

# Example 1: Mean with known sigma
result = ci_mean_z(x_bar=50, sigma=10, n=100, confidence=0.95)
print("\n1. CI for Mean (σ known)")
print(f"   X̄ = {result['point_estimate']}")
print(f"   SE = {result['se']:.4f}")
print(f"   z* = {result['z_star']:.3f}")
print(f"   ME = {result['margin_of_error']:.4f}")
print(f"   95% CI: ({result['ci_lower']:.2f}, {result['ci_upper']:.2f})")

# Example 2: Mean with unknown sigma
data = [4.2, 3.8, 5.1, 4.5, 3.9, 4.8, 4.1, 3.7, 4.6, 4.3,
        5.0, 3.6, 4.4, 4.7, 3.5, 4.9, 4.0, 4.2, 3.8, 4.5,
        4.3, 5.2, 3.9, 4.1, 4.4]
result = ci_mean_t(data=data, confidence=0.95)
print(f"\n2. CI for Mean (σ unknown), n={len(data)}")
print(f"   X̄ = {result['point_estimate']:.2f}")
print(f"   s = {np.std(data, ddof=1):.2f}")
print(f"   SE = {result['se']:.4f}")
print(f"   t* = {result['t_star']:.3f} (df={result['df']})")
print(f"   ME = {result['margin_of_error']:.4f}")
print(f"   95% CI: ({result['ci_lower']:.2f}, {result['ci_upper']:.2f})")

# Example 3: Proportion
result = ci_proportion(x=540, n=1000, confidence=0.95)
print("\n3. CI for Proportion")
print(f"   p̂ = {result['point_estimate']:.3f}")
print(f"   SE = {result['se']:.4f}")
print(f"   z* = {result['z_star']:.3f}")
print(f"   ME = {result['margin_of_error']:.4f} ({result['margin_of_error']*100:.1f}%)")
print(f"   95% CI: ({result['ci_lower']:.3f}, {result['ci_upper']:.3f})")
print(f"   In %: ({result['ci_lower']*100:.1f}%, {result['ci_upper']*100:.1f}%)")
```

### Sample Size Calculation

```python
import numpy as np
from scipy import stats

def sample_size_mean(sigma, me, confidence=0.95):
    """
    Required sample size for estimating mean with given margin of error
    """
    alpha = 1 - confidence
    z_star = stats.norm.ppf(1 - alpha/2)
    n = (z_star * sigma / me) ** 2
    return int(np.ceil(n))

def sample_size_proportion(p_hat, me, confidence=0.95):
    """
    Required sample size for estimating proportion with given margin of error
    If p_hat unknown, use 0.5 for conservative estimate
    """
    alpha = 1 - confidence
    z_star = stats.norm.ppf(1 - alpha/2)
    n = p_hat * (1 - p_hat) * (z_star / me) ** 2
    return int(np.ceil(n))

# Sample size examples
print("\n" + "=" * 60)
print("SAMPLE SIZE CALCULATIONS")
print("=" * 60)

# For mean
print("\nFor estimating mean (σ = 10, 95% CI):")
for me in [5, 2, 1, 0.5]:
    n = sample_size_mean(sigma=10, me=me)
    print(f"   ME = ±{me}: n = {n}")

# For proportion
print("\nFor estimating proportion (p̂ = 0.5, 95% CI):")
for me in [0.10, 0.05, 0.03, 0.02, 0.01]:
    n = sample_size_proportion(p_hat=0.5, me=me)
    print(f"   ME = ±{me*100:.0f}%: n = {n}")
```

### Visualization

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_confidence_intervals(true_mu=50, sigma=10, n=30, 
                                    num_samples=20, confidence=0.95):
    """
    Visualize multiple confidence intervals to show coverage
    """
    np.random.seed(42)
    
    alpha = 1 - confidence
    z_star = stats.norm.ppf(1 - alpha/2)
    se = sigma / np.sqrt(n)
    
    fig, ax = plt.subplots(figsize=(12, 8))
    
    contains_mu = 0
    
    for i in range(num_samples):
        # Generate sample
        sample = np.random.normal(true_mu, sigma, n)
        x_bar = np.mean(sample)
        
        # Calculate CI
        ci_lower = x_bar - z_star * se
        ci_upper = x_bar + z_star * se
        
        # Check if contains true mu
        if ci_lower <= true_mu <= ci_upper:
            color = 'blue'
            contains_mu += 1
        else:
            color = 'red'
        
        # Plot
        ax.plot([ci_lower, ci_upper], [i, i], color=color, linewidth=2)
        ax.plot(x_bar, i, 'o', color=color, markersize=6)
    
    # True mean line
    ax.axvline(true_mu, color='green', linestyle='--', linewidth=2, 
               label=f'True μ = {true_mu}')
    
    ax.set_xlabel('Value', fontsize=12)
    ax.set_ylabel('Sample Number', fontsize=12)
    ax.set_title(f'{confidence*100:.0f}% Confidence Intervals from {num_samples} Samples\n'
                 f'{contains_mu}/{num_samples} ({contains_mu/num_samples*100:.0f}%) contain true μ',
                fontsize=14)
    ax.legend(loc='upper right')
    
    plt.tight_layout()
    plt.show()
    
    return contains_mu / num_samples

# Visualize
coverage = visualize_confidence_intervals(num_samples=20)
```

---

## Practice Problems 📝

### Problem 1: Basic CI for Mean
A sample of 36 light bulbs has a mean life of 1200 hours with s = 120 hours. Find the 95% confidence interval for the true mean life.

<details>
<summary>Click for Solution</summary>

```
Given: n = 36, X̄ = 1200, s = 120, confidence = 95%

Since σ unknown, use t-interval:
df = n - 1 = 35
t* ≈ 2.030 (for 95%, df = 35)

SE = s/√n = 120/√36 = 120/6 = 20

ME = t* × SE = 2.030 × 20 = 40.6

CI = X̄ ± ME = 1200 ± 40.6 = (1159.4, 1240.6)

ANSWER: We are 95% confident the true mean bulb life 
is between 1159.4 and 1240.6 hours.
```

</details>

---

### Problem 2: CI for Proportion
In a survey of 400 customers, 280 said they were satisfied. Find the 99% confidence interval for the true proportion of satisfied customers.

<details>
<summary>Click for Solution</summary>

```
Given: x = 280, n = 400, confidence = 99%

p̂ = 280/400 = 0.70

Check conditions:
np̂ = 400 × 0.70 = 280 ≥ 10 ✓
n(1-p̂) = 400 × 0.30 = 120 ≥ 10 ✓

z* = 2.576 (for 99%)

SE = √(p̂(1-p̂)/n) = √(0.70 × 0.30 / 400)
   = √(0.21/400) = √0.000525 = 0.0229

ME = z* × SE = 2.576 × 0.0229 = 0.059

CI = p̂ ± ME = 0.70 ± 0.059 = (0.641, 0.759)

ANSWER: We are 99% confident that between 64.1% and 
75.9% of all customers are satisfied.
```

</details>

---

### Problem 3: Sample Size
A researcher wants to estimate the mean IQ of a population (σ = 15). What sample size is needed for a 95% CI with margin of error ≤ 3 points?

<details>
<summary>Click for Solution</summary>

```
Given: σ = 15, ME = 3, confidence = 95%

z* = 1.96

n = (z* × σ / ME)²
  = (1.96 × 15 / 3)²
  = (29.4 / 3)²
  = (9.8)²
  = 96.04

Round up: n = 97

ANSWER: Need at least 97 people to achieve ±3 point 
margin of error.
```

</details>

---

### Problem 4: Interpreting CI
A 95% CI for the difference in means is (2.3, 8.7). What can you conclude about whether there's a significant difference?

<details>
<summary>Click for Solution</summary>

```
The interval (2.3, 8.7) does NOT contain 0.

This means:
1. At α = 0.05, we would REJECT H₀: μ₁ - μ₂ = 0
2. The difference IS statistically significant

Interpretation:
• The difference is between 2.3 and 8.7 units
• Since both bounds are positive, Group 1 has a 
  significantly higher mean than Group 2
• The effect is meaningful: at least 2.3 units difference

ANSWER: Yes, there is a statistically significant 
difference at the 0.05 level. Group 1's mean is 
significantly higher by 2.3 to 8.7 units.
```

</details>

---

### Problem 5: Effect of Sample Size
Two polls each find 52% support for a candidate. Poll A has n = 100, Poll B has n = 2500. Calculate the 95% ME for each. Which poll provides more useful information?

<details>
<summary>Click for Solution</summary>

```
p̂ = 0.52, z* = 1.96

Poll A (n = 100):
SE = √(0.52 × 0.48 / 100) = √0.002496 = 0.0500
ME = 1.96 × 0.0500 = 0.098 = 9.8%
CI = (42.2%, 61.8%)

Poll B (n = 2500):
SE = √(0.52 × 0.48 / 2500) = √0.00009984 = 0.00999
ME = 1.96 × 0.00999 = 0.0196 = 2.0%
CI = (50.0%, 54.0%)

ANSWER:
Poll A: 52% ± 9.8% — includes 50%, race is "too close to call"
Poll B: 52% ± 2.0% — barely includes 50%, suggests a lead

Poll B is FAR more useful! With 25× the sample size,
it has 1/5 the margin of error and can detect smaller
differences with confidence.
```

</details>

---

## Summary: The Essence of CIs

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│            CONFIDENCE INTERVALS & MARGIN OF ERROR                │
│            ══════════════════════════════════════                │
│                                                                  │
│   CONFIDENCE INTERVAL:                                           │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  CI = Point Estimate ± Margin of Error                  │   │
│   │     = Statistic ± (Critical Value × Standard Error)    │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   MARGIN OF ERROR:                                               │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  ME = z* × SE  or  ME = t* × SE                         │   │
│   │  Affected by: confidence level, sample size, variance  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   CORRECT INTERPRETATION:                                        │
│   "If we repeated sampling many times, 95% of the               │
│   resulting CIs would contain the true parameter."              │
│                                                                  │
│   KEY RELATIONSHIPS:                                             │
│   • ↑ Confidence level → ↑ Width (wider interval)              │
│   • ↑ Sample size → ↓ Width (narrower interval)                │
│   • ↑ Variability → ↑ Width (wider interval)                   │
│                                                                  │
│   GOLDEN RULE:                                                   │
│   To get both high confidence AND precision,                    │
│   INCREASE SAMPLE SIZE!                                         │
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
│   CRITICAL VALUES (z*):                                          │
│   90%: 1.645 │ 95%: 1.960 │ 99%: 2.576                         │
│                                                                  │
│   FORMULAS:                                                      │
│   Mean (σ known):   X̄ ± z*(σ/√n)                                │
│   Mean (σ unknown): X̄ ± t*(s/√n)                                │
│   Proportion:       p̂ ± z*√(p̂(1-p̂)/n)                          │
│                                                                  │
│   SAMPLE SIZE:                                                   │
│   Mean: n = (z*σ/ME)²                                           │
│   Prop: n = p̂(1-p̂)(z*/ME)²                                     │
│                                                                  │
│   CI WIDTH HALVED → Need 4× sample size                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

> **"A confidence interval doesn't just give you a number — it gives you a range that honestly acknowledges the uncertainty in your estimate. It's not just about being right; it's about knowing how wrong you might be."**

From election polls to medical research, confidence intervals are the honest way to report what we learn from data! 📊

---

*From point estimates to intervals, from certainty to honest uncertainty — that's the power of confidence intervals!* 🎯
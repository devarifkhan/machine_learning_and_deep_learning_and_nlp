# Hypothesis Testing
## The Scientific Method of Statistical Decision Making 🔬

---

## The Art of Making Decisions with Data

Every day, we face questions that require evidence-based decisions:

- Does this new medicine actually work?
- Is this coin fair or biased?
- Did the marketing campaign increase sales?
- Is the factory producing defective products?

**Hypothesis Testing** is the formal statistical framework for answering such questions using data.

---

## 📖 Story: The Suspicious Coin

Karim suspects his friend's coin is biased. He flips it 100 times and gets **65 heads**.

**The Question:** Is this enough evidence to conclude the coin is unfair?

- If the coin is fair, we'd expect about 50 heads
- But 65 seems high... is it "too high" to be just luck?
- Or could a fair coin reasonably produce 65 heads?

**This is exactly the kind of question hypothesis testing answers!**

---

## What is Hypothesis Testing?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              HYPOTHESIS TESTING                              │
│                                                             │
│   A formal procedure for using sample data to evaluate      │
│   a claim (hypothesis) about a population parameter.        │
│                                                             │
│   Key Idea:                                                 │
│   ─────────                                                 │
│   We assume the claim is TRUE, then check if our data       │
│   is consistent with that assumption.                       │
│                                                             │
│   If the data is VERY UNLIKELY under the assumption,        │
│   we REJECT the claim.                                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Two Hypotheses

Every hypothesis test involves two competing claims:

### The Null Hypothesis (H₀)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   NULL HYPOTHESIS (H₀)                                       │
│   ────────────────────                                      │
│                                                             │
│   • The "default" or "status quo" claim                     │
│   • Usually states "no effect" or "no difference"           │
│   • What we assume is TRUE unless proven otherwise          │
│   • Contains an equality (=, ≤, or ≥)                       │
│                                                             │
│   Examples:                                                 │
│   • H₀: The coin is fair (p = 0.5)                         │
│   • H₀: The drug has no effect (μ_treatment = μ_control)   │
│   • H₀: The mean is 100 (μ = 100)                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### The Alternative Hypothesis (H₁ or Hₐ)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ALTERNATIVE HYPOTHESIS (H₁ or Hₐ)                         │
│   ─────────────────────────────────                         │
│                                                             │
│   • The "research" claim we want to support                 │
│   • States there IS an effect or difference                 │
│   • What we conclude if we reject H₀                        │
│   • Contains inequality (≠, <, or >)                        │
│                                                             │
│   Examples:                                                 │
│   • H₁: The coin is biased (p ≠ 0.5)                       │
│   • H₁: The drug has an effect (μ_treatment ≠ μ_control)   │
│   • H₁: The mean is not 100 (μ ≠ 100)                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Logic of Hypothesis Testing

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              THE LOGIC (Proof by Contradiction)              │
│                                                             │
│   1. ASSUME H₀ is true                                      │
│                                                             │
│   2. CALCULATE probability of observing data this          │
│      extreme (or more extreme) if H₀ were true              │
│                                                             │
│   3. DECIDE:                                                │
│      • If probability is LOW → Reject H₀ (data too rare)   │
│      • If probability is HIGH → Fail to reject H₀          │
│                                                             │
│   It's like a court trial:                                  │
│   • H₀: Defendant is innocent (default assumption)          │
│   • H₁: Defendant is guilty                                 │
│   • Evidence (data) is evaluated                            │
│   • Verdict: Guilty (reject H₀) or Not Guilty (fail to     │
│     reject H₀)                                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Hypothesis Testing Framework

```
                    ┌─────────────────────┐
                    │  State Hypotheses   │
                    │    H₀ and H₁        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Choose Significance │
                    │   Level (α)         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Select Appropriate  │
                    │   Test Statistic    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Collect Data and   │
                    │ Calculate Statistic │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Calculate p-value  │
                    │  or Critical Value  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Make Decision     │
                    │ Reject or Fail to   │
                    │    Reject H₀        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ State Conclusion in │
                    │      Context        │
                    └─────────────────────┘
```

---

## Step 1: State the Hypotheses

### Types of Alternative Hypotheses

```
TWO-TAILED TEST (≠)                 
──────────────────                  
H₀: μ = μ₀                          
H₁: μ ≠ μ₀                          
                                    
"Is there ANY difference?"          

         ╭───╮
       ╭─╯   ╰─╮
      ╭╯       ╰╮
     █╯         ╰█    ← Rejection regions
    █╯           ╰█      on BOTH sides
   █╯             ╰█
─────────┬─────────────
        μ₀


LEFT-TAILED TEST (<)                RIGHT-TAILED TEST (>)
────────────────────                ─────────────────────
H₀: μ ≥ μ₀                          H₀: μ ≤ μ₀
H₁: μ < μ₀                          H₁: μ > μ₀

"Is it LESS than?"                  "Is it GREATER than?"

         ╭───╮                               ╭───╮
       ╭─╯   ╰─╮                           ╭─╯   ╰─╮
      ╭╯       ╰╮                         ╭╯       ╰╮
     █╯         ╰╮                       ╭╯         ╰█
    █╯           ╰╮                     ╭╯           ╰█
   █╯             ╰╮                   ╭╯             ╰█
─────────┬─────────────           ─────────┬─────────────
        μ₀                                μ₀

Rejection on LEFT                   Rejection on RIGHT
```

### Choosing the Right Test

| Research Question | H₀ | H₁ | Test Type |
|-------------------|----|----|-----------|
| Is there any difference? | μ = μ₀ | μ ≠ μ₀ | Two-tailed |
| Is it greater? | μ ≤ μ₀ | μ > μ₀ | Right-tailed |
| Is it less? | μ ≥ μ₀ | μ < μ₀ | Left-tailed |

---

## Step 2: Choose Significance Level (α)

The **significance level (α)** is the probability of rejecting H₀ when it's actually true (false positive rate).

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SIGNIFICANCE LEVEL (α)                                     │
│   ──────────────────────                                    │
│                                                             │
│   Common values:                                            │
│   • α = 0.05 (5%)  — Most common, "statistically           │
│                       significant"                          │
│   • α = 0.01 (1%)  — More stringent                        │
│   • α = 0.10 (10%) — More lenient                          │
│   • α = 0.001      — Very stringent (particle physics)     │
│                                                             │
│   α determines:                                             │
│   • How much evidence we need to reject H₀                 │
│   • The probability of Type I error                        │
│   • The critical value(s) for our test                     │
│                                                             │
│   Smaller α = Harder to reject H₀ = More conservative      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### How α Affects the Test

```
α = 0.10 (Lenient)          α = 0.05 (Standard)         α = 0.01 (Strict)

      ╭───╮                       ╭───╮                       ╭───╮
    ╭─╯   ╰─╮                   ╭─╯   ╰─╮                   ╭─╯   ╰─╮
   ╭╯       ╰╮                 ╭╯       ╰╮                 ╭╯       ╰╮
  █╯         ╰█               █╯         ╰█               █╯         ╰█
 ██╯         ╰██             █╯           ╰█             █╯           ╰█
███           ███           ──────┬──────────           ──────┬──────────
────────┬────────                 μ₀                          μ₀
        μ₀
                            
Large rejection             Medium rejection            Small rejection
regions (easy to reject)    regions                     regions (hard to reject)
```

---

## Step 3: Select the Test Statistic

A **test statistic** measures how far our sample result is from what H₀ predicts.

### Common Test Statistics

| Situation | Test | Statistic | Distribution |
|-----------|------|-----------|--------------|
| Mean (σ known) | Z-test | Z = (X̄ - μ₀)/(σ/√n) | Standard Normal |
| Mean (σ unknown) | t-test | t = (X̄ - μ₀)/(s/√n) | t with df = n-1 |
| Proportion | Z-test | Z = (p̂ - p₀)/√(p₀(1-p₀)/n) | Standard Normal |
| Variance | Chi-square | χ² = (n-1)s²/σ₀² | Chi-square |
| Two means | t-test | t = (X̄₁ - X̄₂)/SE | t distribution |
| Independence | Chi-square | χ² = Σ(O-E)²/E | Chi-square |

### The General Form

```
                 Sample Statistic - Hypothesized Value
Test Statistic = ─────────────────────────────────────────
                      Standard Error of Statistic

         θ̂ - θ₀
    Z = ─────────
         SE(θ̂)
```

---

## Step 4: Calculate the Test Statistic

### 📖 Back to the Coin Example

Karim got 65 heads in 100 flips. Is the coin biased?

**Setup:**
```
H₀: p = 0.5 (coin is fair)
H₁: p ≠ 0.5 (coin is biased)
α = 0.05

Sample: n = 100, p̂ = 65/100 = 0.65
```

**Calculate Test Statistic:**
```
       p̂ - p₀              0.65 - 0.50
Z = ───────────────── = ─────────────────────
    √(p₀(1-p₀)/n)       √(0.5 × 0.5 / 100)

       0.15           0.15
Z = ───────────── = ─────── = 3.0
    √(0.25/100)       0.05
```

**Result: Z = 3.0**

This means our sample proportion is **3 standard errors away** from what we'd expect if the coin were fair!

---

## Step 5: Calculate the p-value

The **p-value** is the probability of observing data as extreme as (or more extreme than) what we got, assuming H₀ is true.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   p-value = P(observing this extreme result | H₀ is true)  │
│                                                             │
│   Small p-value → Data is unlikely under H₀                │
│                 → Evidence against H₀                       │
│                                                             │
│   Large p-value → Data is consistent with H₀               │
│                 → No strong evidence against H₀             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visualizing p-value

```
For Z = 3.0 (two-tailed test):

p-value = P(|Z| ≥ 3.0) = P(Z ≤ -3.0) + P(Z ≥ 3.0)

                    ╭───╮
                  ╭─╯   ╰─╮
                 ╭╯       ╰╮
                ╭╯         ╰╮
              ╭─╯           ╰─╮
          ███╯               ╰███     ← Shaded areas
         ────┬───────┬───────┬────       = p-value
            -3       0       3
            
p-value = 2 × 0.00135 = 0.0027 = 0.27%

Very small! Only 0.27% chance of getting 65+ or 35- heads
if the coin were truly fair!
```

### p-value for Different Test Types

```
LEFT-TAILED:               TWO-TAILED:                RIGHT-TAILED:
p = P(Z ≤ z_obs)           p = 2 × P(Z ≥ |z_obs|)     p = P(Z ≥ z_obs)

     ╭───╮                      ╭───╮                      ╭───╮
   ╭─╯   ╰─╮                  ╭─╯   ╰─╮                  ╭─╯   ╰─╮
  ╭╯       ╰╮                ╭╯       ╰╮                ╭╯       ╰╮
 ╭╯         ╰╮              ╭╯         ╰╮              ╭╯         ╰╮
█╯           ╰╮            █╯           ╰█            ╭╯           ╰█
─────────────────          ─────────────────          ─────────────────
      z_obs                -|z|       |z|                  z_obs
```

---

## Step 6: Make a Decision

### Decision Rule

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE DECISION RULE                                          │
│   ─────────────────                                         │
│                                                             │
│   If p-value ≤ α:  REJECT H₀                                │
│                    "Statistically significant"               │
│                    "Evidence supports H₁"                   │
│                                                             │
│   If p-value > α:  FAIL TO REJECT H₀                        │
│                    "Not statistically significant"          │
│                    "Insufficient evidence against H₀"       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### For Our Coin Example

```
p-value = 0.0027
α = 0.05

Since 0.0027 < 0.05:

DECISION: REJECT H₀

CONCLUSION: There is statistically significant evidence
that the coin is biased (p = 0.0027).
```

---

## Alternative Approach: Critical Values

Instead of p-values, we can use **critical values** to define rejection regions.

### Critical Value Method

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CRITICAL VALUE METHOD                                      │
│   ─────────────────────                                     │
│                                                             │
│   1. Find critical value(s) that cut off α in the tails    │
│   2. Compare test statistic to critical value              │
│   3. If test statistic is in rejection region → Reject H₀  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Critical Values for Common α Levels

| α | Two-tailed (z*) | One-tailed (z*) |
|---|-----------------|-----------------|
| 0.10 | ±1.645 | ±1.28 |
| 0.05 | ±1.96 | ±1.645 |
| 0.01 | ±2.576 | ±2.33 |
| 0.001 | ±3.29 | ±3.09 |

### Visual: Rejection Regions

```
Two-tailed test, α = 0.05:

                        ╭───╮
                      ╭─╯   ╰─╮
                     ╭╯       ╰╮
                    ╭╯         ╰╮
                   ╭╯           ╰╮
              ████╭╯             ╰╮████
             █████╯               ╰█████
         ─────┬───────────┬───────────┬─────
            -1.96         0         1.96
              │                       │
              │    FAIL TO REJECT     │
              │                       │
        REJECT│                       │REJECT
         H₀   │                       │  H₀
         
If |Z| > 1.96 → Reject H₀
Our Z = 3.0 > 1.96 → REJECT H₀ ✓
```

---

## Step 7: State the Conclusion

### Writing a Proper Conclusion

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   A GOOD CONCLUSION INCLUDES:                                │
│   ───────────────────────────                               │
│                                                             │
│   1. Decision (Reject or Fail to Reject H₀)                 │
│   2. Significance level used                                │
│   3. Context-specific interpretation                        │
│   4. p-value (or test statistic)                           │
│                                                             │
│   Example:                                                  │
│   "At the α = 0.05 significance level, we reject H₀.       │
│    There is statistically significant evidence that the     │
│    coin is biased (Z = 3.0, p = 0.0027)."                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Important Language

| Say This | NOT This |
|----------|----------|
| "Fail to reject H₀" | "Accept H₀" |
| "Evidence against H₀" | "Proved H₁" |
| "Statistically significant" | "Definitely true" |
| "Suggests" or "indicates" | "Proves" |

---

## Type I and Type II Errors

### The Two Types of Mistakes

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    TRUTH (Unknown)                          │
│                 ┌─────────────┬─────────────┐               │
│                 │   H₀ True   │  H₀ False   │               │
│   ┌─────────────┼─────────────┼─────────────┤               │
│   │ Reject H₀   │  TYPE I     │  CORRECT    │               │
│ D │             │  ERROR (α)  │  (Power)    │               │
│ E │             │ False       │  True       │               │
│ C │             │ Positive    │  Positive   │               │
│ I ├─────────────┼─────────────┼─────────────┤               │
│ S │ Fail to     │  CORRECT    │  TYPE II    │               │
│ I │ Reject H₀   │  (1-α)      │  ERROR (β)  │               │
│ O │             │  True       │  False      │               │
│ N │             │  Negative   │  Negative   │               │
│   └─────────────┴─────────────┴─────────────┘               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Understanding the Errors

```
TYPE I ERROR (α)                    TYPE II ERROR (β)
────────────────                    ─────────────────

• Rejecting H₀ when H₀ is TRUE      • Failing to reject H₀ when H₀
• "False Positive"                     is FALSE
• "False Alarm"                      • "False Negative"
• "Convicting an innocent person"    • "Missing the effect"
                                     • "Letting a guilty person go free"

P(Type I Error) = α                  P(Type II Error) = β

We CONTROL α (we choose it)          β depends on:
                                     • Sample size (n)
                                     • Effect size
                                     • α level
                                     • Variability
```

### Real-World Examples

| Context | H₀ | Type I Error | Type II Error |
|---------|----|--------------| --------------|
| Medical Test | No disease | Diagnosing disease when healthy | Missing actual disease |
| Court Trial | Innocent | Convicting innocent | Acquitting guilty |
| Quality Control | Product OK | Rejecting good batch | Accepting bad batch |
| Drug Trial | Drug doesn't work | Approving ineffective drug | Rejecting effective drug |

### The Error Tradeoff

```
                    α (Type I)
                         ▲
                         │
                     ┌───┴───┐
                     │       │
              High α │       │ Low α
            Low β    │       │ High β
            (Good    │       │ (Poor
             Power)  │       │  Power)
                     │       │
                     └───┬───┘
                         │
                         ▼
                    β (Type II)

As α decreases → β increases (and vice versa)
The only way to reduce BOTH is to increase sample size!
```

---

## Power of a Test

**Power** is the probability of correctly rejecting H₀ when it's false.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   POWER = 1 - β = P(Reject H₀ | H₀ is false)               │
│                                                             │
│   Power tells us: "How likely are we to detect a real      │
│   effect if one exists?"                                    │
│                                                             │
│   Good power: ≥ 0.80 (80%)                                 │
│   Ideal power: ≥ 0.90 (90%)                                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Factors Affecting Power

```
POWER INCREASES WHEN:

1. Sample size (n) increases     ┌─────────────────┐
                                 │                 │
2. Effect size increases         │     POWER       │
                                 │     = 1 - β     │
3. α increases                   │                 │
                                 └─────────────────┘
4. Variability (σ) decreases

5. One-tailed test (vs two-tailed)
```

### Visual: Power and Effect Size

```
H₀ Distribution          H₁ Distribution (True)
(Under null)             (Effect exists)

       ╭───╮                    ╭───╮
     ╭─╯   ╰─╮                ╭─╯   ╰─╮
    ╭╯       ╰╮              ╭╯       ╰╮
   ╭╯         ╰╮            ╭╯    █████╰╮
  ╭╯           ╰██████████╭╯     █████  ╰╮
 ╭╯            │╰███████╭╯      ██████   ╰╮
╯              │  ████╰╯        ██████    ╰
───────────────┼────────────────████████─────
              μ₀          │      μ₁
               │          │
               │  Critical│
               │  Value   │
               │          │
        β      │          │   Power = 1-β
  (Type II     │          │   (Correct
   Error)      │          │    Rejection)
```

---

## Effect Size

**Effect Size** measures the magnitude of the difference, independent of sample size.

### Why Effect Size Matters

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Statistical significance ≠ Practical importance!          │
│                                                             │
│   With large n, even TINY differences can be significant.  │
│   With small n, even LARGE differences may not be.         │
│                                                             │
│   Effect size tells us: "How BIG is the effect?"           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Common Effect Size Measures

#### Cohen's d (for means)

```
        X̄ - μ₀       Mean Difference
d = ─────────── = ──────────────────────
          s        Standard Deviation

Interpretation:
• |d| < 0.2:  Small effect
• |d| ≈ 0.5:  Medium effect
• |d| > 0.8:  Large effect
```

#### Correlation (r)

```
r = correlation between variables

Interpretation:
• |r| < 0.1:  Small
• |r| ≈ 0.3:  Medium
• |r| > 0.5:  Large
```

#### Odds Ratio and Risk Ratio

For categorical outcomes, measuring association strength.

---

## 📖 Complete Example: Drug Effectiveness

A pharmaceutical company tests a new blood pressure medication.

### Step 1: State Hypotheses

```
H₀: μ = 0 (no change in blood pressure)
H₁: μ ≠ 0 (blood pressure changes)

Two-tailed test
α = 0.05
```

### Step 2: Collect Data

```
n = 50 patients
Mean BP change: X̄ = -8.5 mmHg (decrease)
Standard deviation: s = 15 mmHg
```

### Step 3: Calculate Test Statistic

```
       X̄ - μ₀      -8.5 - 0       -8.5
t = ─────────── = ────────── = ─────────
      s/√n        15/√50        2.12

t = -4.01

df = n - 1 = 49
```

### Step 4: Find p-value

```
For t = -4.01 with df = 49:

p-value = 2 × P(t < -4.01) ≈ 0.0002
```

### Step 5: Make Decision

```
p-value = 0.0002 < α = 0.05

REJECT H₀
```

### Step 6: Calculate Effect Size

```
       X̄ - μ₀     -8.5
d = ─────────── = ────── = -0.57
         s          15

Medium effect size (Cohen's d ≈ 0.5)
```

### Step 7: Conclusion

```
"At the α = 0.05 significance level, we reject H₀. 
There is statistically significant evidence that the 
medication changes blood pressure (t = -4.01, p = 0.0002).

The medication reduced blood pressure by an average of 
8.5 mmHg, which represents a medium effect size (d = 0.57).
This reduction appears to be both statistically significant 
and clinically meaningful."
```

---

## Common Hypothesis Tests

### 1. One-Sample Z-Test (σ known)

```
Use when: Testing a mean with known population σ
Statistic: Z = (X̄ - μ₀)/(σ/√n)
Distribution: Standard Normal
```

### 2. One-Sample t-Test (σ unknown)

```
Use when: Testing a mean with unknown σ
Statistic: t = (X̄ - μ₀)/(s/√n)
Distribution: t with df = n - 1
```

### 3. Two-Sample t-Test

```
Use when: Comparing means of two independent groups
Statistic: t = (X̄₁ - X̄₂)/SE
Distribution: t with df (various formulas)
```

### 4. Paired t-Test

```
Use when: Comparing means of paired/matched samples
Statistic: t = d̄/(s_d/√n)
Distribution: t with df = n - 1
Where d̄ = mean of differences
```

### 5. Z-Test for Proportion

```
Use when: Testing a population proportion
Statistic: Z = (p̂ - p₀)/√(p₀(1-p₀)/n)
Distribution: Standard Normal
```

### 6. Chi-Square Test

```
Use when: Testing variance or independence
Statistic: χ² = (n-1)s²/σ₀² (variance)
           χ² = Σ(O-E)²/E (independence)
Distribution: Chi-square
```

### 7. F-Test (ANOVA)

```
Use when: Comparing means of 3+ groups
Statistic: F = MS_between/MS_within
Distribution: F distribution
```

---

## Summary Table: Test Selection

```
┌──────────────────────────────────────────────────────────────────┐
│   What are you testing?          │  Test to use                  │
├──────────────────────────────────┼───────────────────────────────┤
│ One mean (σ known)               │  Z-test                       │
│ One mean (σ unknown)             │  One-sample t-test            │
│ One proportion                   │  Z-test for proportion        │
│ Two means (independent)          │  Two-sample t-test            │
│ Two means (paired)               │  Paired t-test                │
│ Two proportions                  │  Two-proportion Z-test        │
│ One variance                     │  Chi-square test              │
│ Two variances                    │  F-test                       │
│ 3+ means                         │  ANOVA (F-test)               │
│ Independence (categorical)       │  Chi-square test              │
│ Correlation                      │  t-test for r                 │
└──────────────────────────────────┴───────────────────────────────┘
```

---

## Python Implementation

### One-Sample t-Test

```python
import numpy as np
from scipy import stats

# Sample data
data = np.array([98.6, 98.4, 99.0, 98.8, 98.5, 98.9, 98.7, 98.3, 99.1, 98.6])

# Hypothesis: Is mean body temperature different from 98.6°F?
# H₀: μ = 98.6
# H₁: μ ≠ 98.6

mu_0 = 98.6  # Hypothesized mean
alpha = 0.05

# Perform one-sample t-test
t_stat, p_value = stats.ttest_1samp(data, mu_0)

print(f"Sample mean: {np.mean(data):.4f}")
print(f"Sample std: {np.std(data, ddof=1):.4f}")
print(f"t-statistic: {t_stat:.4f}")
print(f"p-value: {p_value:.4f}")

# Decision
if p_value < alpha:
    print(f"\nReject H₀ at α = {alpha}")
else:
    print(f"\nFail to reject H₀ at α = {alpha}")

# Effect size (Cohen's d)
d = (np.mean(data) - mu_0) / np.std(data, ddof=1)
print(f"Cohen's d: {d:.4f}")
```

### Two-Sample t-Test

```python
import numpy as np
from scipy import stats

# Two independent groups
group1 = np.array([85, 90, 88, 92, 87, 89, 91, 86, 88, 90])
group2 = np.array([78, 82, 80, 85, 79, 81, 83, 77, 80, 82])

# H₀: μ₁ = μ₂ (no difference)
# H₁: μ₁ ≠ μ₂ (different means)

alpha = 0.05

# Perform two-sample t-test (assuming equal variances)
t_stat, p_value = stats.ttest_ind(group1, group2)

print(f"Group 1 mean: {np.mean(group1):.2f}")
print(f"Group 2 mean: {np.mean(group2):.2f}")
print(f"Difference: {np.mean(group1) - np.mean(group2):.2f}")
print(f"t-statistic: {t_stat:.4f}")
print(f"p-value: {p_value:.6f}")

# Decision
if p_value < alpha:
    print(f"\nReject H₀: Groups have significantly different means")
else:
    print(f"\nFail to reject H₀: No significant difference")

# Effect size (Cohen's d for two groups)
pooled_std = np.sqrt(((len(group1)-1)*np.var(group1, ddof=1) + 
                       (len(group2)-1)*np.var(group2, ddof=1)) / 
                      (len(group1) + len(group2) - 2))
d = (np.mean(group1) - np.mean(group2)) / pooled_std
print(f"Cohen's d: {d:.4f}")
```

### Z-Test for Proportion

```python
import numpy as np
from scipy import stats

# Sample data
n = 500       # Sample size
x = 280       # Number of successes
p_hat = x / n  # Sample proportion

# H₀: p = 0.5
# H₁: p ≠ 0.5
p_0 = 0.5
alpha = 0.05

# Calculate Z-statistic
se = np.sqrt(p_0 * (1 - p_0) / n)
z_stat = (p_hat - p_0) / se

# Calculate p-value (two-tailed)
p_value = 2 * (1 - stats.norm.cdf(abs(z_stat)))

print(f"Sample proportion: {p_hat:.4f}")
print(f"Z-statistic: {z_stat:.4f}")
print(f"p-value: {p_value:.6f}")

# Decision
if p_value < alpha:
    print(f"\nReject H₀: Proportion is significantly different from {p_0}")
else:
    print(f"\nFail to reject H₀: No significant difference from {p_0}")
```

### Chi-Square Test for Independence

```python
import numpy as np
from scipy import stats

# Contingency table
#              | Smoker | Non-smoker |
# -------------|--------|------------|
# Heart Disease|   30   |     20     |
# No Disease   |   25   |     75     |

observed = np.array([[30, 20],
                     [25, 75]])

# H₀: Smoking and heart disease are independent
# H₁: They are associated

chi2, p_value, dof, expected = stats.chi2_contingency(observed)

print("Observed frequencies:")
print(observed)
print("\nExpected frequencies (under independence):")
print(expected)
print(f"\nChi-square statistic: {chi2:.4f}")
print(f"Degrees of freedom: {dof}")
print(f"p-value: {p_value:.6f}")

# Decision
alpha = 0.05
if p_value < alpha:
    print(f"\nReject H₀: Variables are associated")
else:
    print(f"\nFail to reject H₀: No significant association")
```

### Power Analysis

```python
from scipy import stats
import numpy as np

def calculate_power(n, effect_size, alpha=0.05, alternative='two-sided'):
    """
    Calculate power for a one-sample t-test
    """
    # Critical value
    if alternative == 'two-sided':
        t_crit = stats.t.ppf(1 - alpha/2, df=n-1)
    else:
        t_crit = stats.t.ppf(1 - alpha, df=n-1)
    
    # Non-centrality parameter
    ncp = effect_size * np.sqrt(n)
    
    # Power = P(reject H₀ | H₁ is true)
    if alternative == 'two-sided':
        power = 1 - stats.nct.cdf(t_crit, df=n-1, nc=ncp) + \
                stats.nct.cdf(-t_crit, df=n-1, nc=ncp)
    else:
        power = 1 - stats.nct.cdf(t_crit, df=n-1, nc=ncp)
    
    return power

# Example: What power do we have to detect d = 0.5 with n = 30?
n = 30
d = 0.5
power = calculate_power(n, d)
print(f"Power with n={n}, d={d}: {power:.4f}")

# What n do we need for 80% power?
for n in range(10, 100, 5):
    power = calculate_power(n, d)
    if power >= 0.80:
        print(f"Need n ≥ {n} for 80% power")
        break
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Accepting H₀

❌ **Wrong:** "We accept H₀"

✅ **Correct:** "We fail to reject H₀"

*We can never "prove" H₀ is true; we only say we don't have enough evidence against it.*

---

### Mistake 2: p-value is NOT P(H₀ is true)

❌ **Wrong:** "p = 0.03 means 3% chance H₀ is true"

✅ **Correct:** "p = 0.03 means 3% chance of seeing this data (or more extreme) if H₀ were true"

---

### Mistake 3: Significant ≠ Important

❌ **Wrong:** "p < 0.05 means the effect is large"

✅ **Correct:** Statistical significance doesn't imply practical importance. Always report effect size!

---

### Mistake 4: One-Tailed Tests to Get Significance

❌ **Wrong:** Switching to one-tailed after seeing the data

✅ **Correct:** Choose the test direction BEFORE seeing the data, based on research question

---

### Mistake 5: Multiple Testing Without Correction

❌ **Wrong:** Running 20 tests at α = 0.05 and finding 1 "significant"

✅ **Correct:** Use Bonferroni correction (α/k) or control False Discovery Rate

---

## Practice Problems 📝

### Problem 1: Setting Up Hypotheses
A school claims average SAT score is 1100. You suspect it's higher. Set up the hypotheses.

<details>
<summary>Click for Answer</summary>

```
H₀: μ ≤ 1100 (or μ = 1100)
H₁: μ > 1100

This is a RIGHT-TAILED test because we're testing 
if the mean is GREATER than the claimed value.
```

</details>

---

### Problem 2: Calculating Test Statistic
Sample: n = 36, X̄ = 52, s = 6. Test H₀: μ = 50 vs H₁: μ ≠ 50.

<details>
<summary>Click for Answer</summary>

```
       X̄ - μ₀      52 - 50
t = ─────────── = ─────────
      s/√n         6/√36

       2
t = ───── = 2.0
       1

t = 2.0 with df = 35

For two-tailed test at α = 0.05:
Critical values: ±2.03

Since |2.0| < 2.03, we FAIL TO REJECT H₀
(Or: p-value ≈ 0.053 > 0.05)
```

</details>

---

### Problem 3: Interpreting p-value
You get p-value = 0.08 with α = 0.05. What's your conclusion?

<details>
<summary>Click for Answer</summary>

```
Since p-value (0.08) > α (0.05):

DECISION: Fail to reject H₀

INTERPRETATION: 
"At the α = 0.05 significance level, there is 
insufficient evidence to reject H₀. The results 
are not statistically significant."

Note: This does NOT mean H₀ is true! We simply 
don't have enough evidence against it.
```

</details>

---

### Problem 4: Type I and Type II Errors
In a drug trial, what are the Type I and Type II errors?

<details>
<summary>Click for Answer</summary>

```
H₀: Drug has no effect
H₁: Drug has an effect

TYPE I ERROR (α):
Concluding the drug works when it actually doesn't.
• Consequence: Ineffective drug gets approved
• Patients receive useless treatment
• Called "false positive"

TYPE II ERROR (β):
Concluding the drug doesn't work when it actually does.
• Consequence: Effective drug gets rejected
• Patients miss out on beneficial treatment
• Called "false negative"

In drug trials, Type I errors are often considered 
more serious (hence we use small α like 0.05 or 0.01).
```

</details>

---

### Problem 5: Power Calculation
With n = 25, σ = 10, α = 0.05, what's the power to detect μ = 52 when H₀: μ = 50?

<details>
<summary>Click for Answer</summary>

```
Effect size (standardized):
d = (52 - 50) / 10 = 0.2 (small effect)

For one-sample Z-test, power formula:
Power = P(Z > z_α - d√n) for right-tailed

z_α = 1.645 (for α = 0.05, one-tailed)
d√n = 0.2 × √25 = 0.2 × 5 = 1.0

Power = P(Z > 1.645 - 1.0)
      = P(Z > 0.645)
      = 1 - 0.740
      ≈ 0.26 = 26%

This is LOW power! We'd need larger n to reliably 
detect such a small effect.

For 80% power: n ≈ (z_α + z_β)²/d² 
             = (1.645 + 0.84)²/0.04 ≈ 155
```

</details>

---

## Summary: The Essence of Hypothesis Testing

```
┌─────────────────────────────────────────────────────────────────┐
│                    HYPOTHESIS TESTING                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "Making data-driven decisions about population claims"         │
│                                                                  │
│   THE FRAMEWORK:                                                 │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  1. State H₀ and H₁                                      │   │
│   │  2. Choose α (significance level)                        │   │
│   │  3. Calculate test statistic                             │   │
│   │  4. Find p-value (or critical value)                     │   │
│   │  5. Make decision: Reject or Fail to Reject H₀           │   │
│   │  6. State conclusion in context                          │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY CONCEPTS:                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • p-value: P(data this extreme | H₀ true)              │   │
│   │  • Type I Error (α): Rejecting true H₀                  │   │
│   │  • Type II Error (β): Not rejecting false H₀            │   │
│   │  • Power (1-β): Detecting real effects                   │   │
│   │  • Effect Size: Practical magnitude of difference        │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   DECISION RULE:                                                 │
│   • p-value ≤ α → Reject H₀ ("significant")                     │
│   • p-value > α → Fail to reject H₀ ("not significant")         │
│                                                                  │
│   REMEMBER:                                                      │
│   • Statistical significance ≠ Practical importance             │
│   • Always report effect sizes                                   │
│   • "Fail to reject" ≠ "Accept"                                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## The Big Picture

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│     POPULATION                         SAMPLE                    │
│   (Unknown Truth)                    (Our Data)                  │
│                                                                  │
│   ┌───────────┐                     ┌───────────┐                │
│   │           │     Sample          │           │                │
│   │    θ      │ ◄─────────────────► │    θ̂     │                │
│   │ (unknown) │                     │(estimate) │                │
│   │           │                     │           │                │
│   └───────────┘                     └─────┬─────┘                │
│                                           │                      │
│   We make a CLAIM                         │ Test                 │
│   about θ (H₀)                            │ Statistic            │
│                                           │                      │
│                                           ▼                      │
│                                    ┌────────────┐                │
│                                    │  p-value   │                │
│                                    │            │                │
│                                    │ How likely │                │
│                                    │ is this    │                │
│                                    │ data if H₀ │                │
│                                    │ is true?   │                │
│                                    └──────┬─────┘                │
│                                           │                      │
│                                           ▼                      │
│                              ┌────────────────────────┐          │
│                              │       DECISION         │          │
│                              │                        │          │
│                              │  p ≤ α: Reject H₀     │          │
│                              │  p > α: Fail to Reject│          │
│                              └────────────────────────┘          │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

> **"Hypothesis testing is the statistical courtroom where data serves as evidence, probability acts as judge, and conclusions are the verdict — never certain, but supported by the weight of evidence."**

Master hypothesis testing, and you've mastered the core of statistical inference — the ability to make principled, evidence-based decisions in the face of uncertainty! ⚖️

---

*From claims to conclusions, from data to decisions — that's the power of hypothesis testing!* 🔬
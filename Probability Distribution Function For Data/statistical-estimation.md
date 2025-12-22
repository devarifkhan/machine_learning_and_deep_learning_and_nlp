# Statistical Estimation
## From Samples to Population Insights 🎯

---

## The Fundamental Problem

Imagine you want to know:
- The **average income** of all Bangladeshis (170 million people!)
- The **proportion** of voters supporting a candidate
- The **average lifespan** of a new smartphone battery

You **can't** measure everyone or everything. So you take a **sample** and use it to **estimate** the truth about the entire population.

This is **Statistical Estimation** — the art and science of drawing conclusions about populations from samples.

---

## 📖 Story: The Tea Quality Inspector

Fatima is a quality inspector at a tea factory. Each day, 100,000 tea bags are produced. She can't test every bag, so she randomly samples 50 bags and measures their weight.

**Her sample results:**
- Sample mean: X̄ = 2.02 grams
- Sample standard deviation: s = 0.15 grams

**Her questions:**
1. What's the true average weight of ALL tea bags? (Point Estimate)
2. How confident can she be in her estimate? (Interval Estimate)
3. Is her estimation method reliable? (Properties of Estimators)

This is statistical estimation in action!

---

## Two Types of Estimates

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                   TYPES OF ESTIMATES                         │
│                                                             │
├─────────────────────────┬───────────────────────────────────┤
│                         │                                    │
│   POINT ESTIMATE        │      INTERVAL ESTIMATE             │
│                         │                                    │
│   A single number       │   A range of values                │
│   "Best guess"          │   With confidence level            │
│                         │                                    │
│   Example:              │   Example:                         │
│   μ̂ = 2.02 grams       │   (1.98, 2.06) grams              │
│                         │   with 95% confidence              │
│                         │                                    │
│   Simple but            │   More informative                 │
│   no uncertainty info   │   Shows precision                  │
│                         │                                    │
└─────────────────────────┴───────────────────────────────────┘
```

---

# Part 1: Point Estimation
## *Finding the Best Single Value*

---

## What is a Point Estimate?

A **point estimate** is a single number calculated from sample data that serves as our "best guess" for an unknown population parameter.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              POINT ESTIMATION                                │
│                                                             │
│   Population Parameter (unknown)  →  θ (theta)              │
│   Sample Statistic (calculated)   →  θ̂ (theta-hat)         │
│                                                             │
│   θ̂ is our ESTIMATE of θ                                   │
│                                                             │
│   The formula/rule for calculating θ̂ is called an          │
│   ESTIMATOR                                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Parameter vs Statistic vs Estimator

| Term | Symbol | Definition | Example |
|------|--------|------------|---------|
| **Parameter** | θ, μ, σ, p | Fixed (unknown) population value | True mean μ |
| **Statistic** | θ̂, X̄, s, p̂ | Value calculated from sample | Sample mean X̄ |
| **Estimator** | — | The rule/formula for calculating | X̄ = ΣXᵢ/n |
| **Estimate** | — | The actual number obtained | X̄ = 2.02 |

### The Relationship

```
Population              Sample                 Estimate
═══════════            ════════               ══════════

   θ        ──────►    Data      ──────►        θ̂
(unknown)            x₁,x₂,...,xₙ            (calculated)
                           │
                           │ Apply
                           ▼ Estimator
                        Formula
```

---

## Common Point Estimators

### 1. Population Mean (μ)

**Estimator:** Sample Mean

```
       n
X̄ = (Σ Xᵢ) / n
      i=1

"Add all values and divide by n"
```

### 2. Population Variance (σ²)

**Estimator:** Sample Variance

```
       n
s² = [Σ (Xᵢ - X̄)²] / (n - 1)
      i=1

Note: We divide by (n-1), not n! (for unbiasedness)
```

### 3. Population Standard Deviation (σ)

**Estimator:** Sample Standard Deviation

```
s = √s² = √[Σ(Xᵢ - X̄)² / (n-1)]
```

### 4. Population Proportion (p)

**Estimator:** Sample Proportion

```
p̂ = X / n

Where X = number of "successes" in sample
```

### 5. Population Median

**Estimator:** Sample Median

```
Median = Middle value when data is sorted
       = (n+1)/2 th value if n is odd
       = Average of n/2 and (n/2)+1 values if n is even
```

---

## Summary Table: Common Estimators

| Parameter | Symbol | Estimator | Formula |
|-----------|--------|-----------|---------|
| Mean | μ | Sample mean | X̄ = ΣXᵢ/n |
| Variance | σ² | Sample variance | s² = Σ(Xᵢ-X̄)²/(n-1) |
| Std Dev | σ | Sample std dev | s = √s² |
| Proportion | p | Sample proportion | p̂ = X/n |
| Difference of means | μ₁-μ₂ | X̄₁ - X̄₂ | — |
| Ratio of variances | σ₁²/σ₂² | s₁²/s₂² | — |

---

# Part 2: Properties of Good Estimators
## *What Makes an Estimator "Good"?*

---

## The Four Desirable Properties

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│           PROPERTIES OF GOOD ESTIMATORS                      │
│                                                             │
│   1. UNBIASEDNESS  — On average, hits the true value        │
│   2. CONSISTENCY   — Gets better with more data             │
│   3. EFFICIENCY    — Has smallest variance among unbiased   │
│   4. SUFFICIENCY   — Uses all relevant information          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Property 1: Unbiasedness

An estimator θ̂ is **unbiased** if its expected value equals the true parameter:

```
E[θ̂] = θ

"On average, the estimator equals the true value"
```

### Visual: Unbiased vs Biased

```
        UNBIASED                          BIASED
        
    Sampling Distribution             Sampling Distribution
    of θ̂                              of θ̂
    
         ╭───╮                              ╭───╮
       ╭─╯   ╰─╮                          ╭─╯   ╰─╮
      ╭╯       ╰╮                        ╭╯       ╰╮
     ╭╯         ╰╮                      ╭╯         ╰╮
    ╭╯           ╰╮                    ╭╯           ╰╮
   ╯               ╰                  ╯               ╰
   ───────┬─────────                  ───────────┬─────
          │                                      │
          θ                              θ      E[θ̂]
     (true value)                               │
                                                │
    Center is at θ!                    Center is SHIFTED!
                                       Bias = E[θ̂] - θ
```

### Bias Formula

```
Bias(θ̂) = E[θ̂] - θ

If Bias = 0, the estimator is unbiased.
```

### Examples

| Estimator | Unbiased? | Reason |
|-----------|-----------|--------|
| X̄ for μ | ✅ Yes | E[X̄] = μ |
| s² for σ² | ✅ Yes | E[s²] = σ² (that's why we use n-1) |
| s for σ | ❌ No | E[s] ≠ σ (slightly biased) |
| p̂ for p | ✅ Yes | E[p̂] = p |
| Σ(Xᵢ-X̄)²/n | ❌ No | E[...] = (n-1)σ²/n ≠ σ² |

---

## Property 2: Consistency

An estimator is **consistent** if it converges to the true parameter as sample size increases:

```
θ̂ₙ → θ  as n → ∞  (in probability)

"More data = Better estimate"
```

### Visual: Consistency

```
n = 10                n = 50               n = 500
                      
   ╭────────╮           ╭────╮              ╭──╮
 ╭─╯        ╰─╮       ╭─╯    ╰─╮          ╭─╯  ╰─╮
╭╯            ╰╮     ╭╯        ╰╮        ╭╯      ╰╮
╯              ╰    ╭╯          ╰╮      ╭╯        ╰╮
────────┬────────   ╯            ╰     ╯          ╰
        θ           ──────┬──────      ─────┬─────
                          θ                 θ
                          
Wide spread          Narrower            Very concentrated
                                         around θ
                                         
As n increases, distribution of θ̂ concentrates around θ
```

### Most Common Estimators are Consistent

- X̄ is consistent for μ ✅
- s² is consistent for σ² ✅
- p̂ is consistent for p ✅

---

## Property 3: Efficiency

Among all unbiased estimators, the **efficient** one has the **smallest variance**.

```
Efficiency = Var(Best Unbiased Estimator) / Var(θ̂)

Efficiency = 1 means θ̂ is the best (minimum variance)
```

### Cramér-Rao Lower Bound

There's a theoretical minimum variance for any unbiased estimator:

```
Var(θ̂) ≥ 1 / I(θ)

Where I(θ) is the Fisher Information
```

An estimator achieving this bound is called **efficient** or **MVUE** (Minimum Variance Unbiased Estimator).

### Example: Comparing Estimators for μ

| Estimator | Unbiased? | Variance | Efficiency |
|-----------|-----------|----------|------------|
| Sample Mean X̄ | Yes | σ²/n | 100% (Best!) |
| Sample Median | Yes | πσ²/(2n) | 64% |
| Midrange | Yes | σ²/(2n) for Uniform | Depends |

For normal populations, X̄ is the most efficient estimator of μ.

---

## Property 4: Sufficiency

An estimator is **sufficient** if it captures all the information in the sample about the parameter.

```
"No other statistic can provide additional information about θ"
```

### Example

For normal distribution with known variance:
- X̄ is **sufficient** for μ
- Once you know X̄, knowing individual values doesn't help estimate μ better

### Factorization Theorem

θ̂ is sufficient for θ if the likelihood can be factored as:

```
L(θ|x₁,...,xₙ) = g(θ̂, θ) × h(x₁,...,xₙ)

Where h doesn't depend on θ
```

---

## Summary: Properties Comparison

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   PROPERTY        MEANING              FORMULA              │
│   ─────────       ───────              ───────              │
│                                                             │
│   Unbiasedness    Center at θ          E[θ̂] = θ            │
│                                                             │
│   Consistency     Improves with n      θ̂ₙ →ᵖ θ as n→∞      │
│                                                             │
│   Efficiency      Smallest variance    Var(θ̂) = CRLB       │
│                                                             │
│   Sufficiency     Uses all info        Factorization        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Bias-Variance Tradeoff

Sometimes we accept a **biased** estimator if it has **much lower variance**!

```
Mean Squared Error (MSE) = Variance + Bias²

MSE(θ̂) = Var(θ̂) + [Bias(θ̂)]²
```

### Visual: The Tradeoff

```
                    ┌───────────────────────────────────────┐
                    │                                       │
     MSE            │         Total Error (MSE)             │
       │            │        ╱                              │
       │            │       ╱                               │
       │    Var     │  ────╱  Variance                      │
       │      ╲     │ ╱                                     │
       │       ╲   ╱│                                       │
       │        ╲╱  │                                       │
       │        ╱╲  │                                       │
       │       ╱  ╲ │                                       │
       │      ╱    ╲│  Bias²                                │
       │     ╱      │╲                                      │
       └────────────┴───────────────────────────────────────
                Complexity/Flexibility
                
       Simple models: High bias, low variance
       Complex models: Low bias, high variance
       OPTIMAL: Balance that minimizes MSE
```

### Example: Ridge Regression

In ridge regression, we intentionally introduce bias to reduce variance, often achieving lower overall MSE!

---

# Part 3: Methods of Estimation
## *How Do We Find Estimators?*

---

## Three Main Methods

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              ESTIMATION METHODS                              │
│                                                             │
│   1. METHOD OF MOMENTS (MoM)                                │
│      Match sample moments to population moments             │
│                                                             │
│   2. MAXIMUM LIKELIHOOD ESTIMATION (MLE)                    │
│      Find parameter that maximizes probability of data      │
│                                                             │
│   3. BAYESIAN ESTIMATION                                    │
│      Combine prior knowledge with data                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Method 1: Method of Moments (MoM)

### The Idea

Set **sample moments** equal to **population moments** and solve for parameters.

```
Population moment = Sample moment

E[Xᵏ] = (1/n)ΣXᵢᵏ

Solve for unknown parameters!
```

### Example: Normal Distribution

For X ~ Normal(μ, σ²):

**First moment (mean):**
```
E[X] = μ   →   μ̂ = X̄
```

**Second central moment (variance):**
```
E[(X-μ)²] = σ²   →   σ̂² = (1/n)Σ(Xᵢ - X̄)²
```

### Example: Exponential Distribution

For X ~ Exponential(λ):

```
E[X] = 1/λ

So: 1/λ̂ = X̄
    λ̂ = 1/X̄
```

### Pros and Cons

| Pros | Cons |
|------|------|
| Simple to compute | May not be efficient |
| Always gives an answer | Can give invalid estimates |
| Good starting point | Ignores some information |

---

## Method 2: Maximum Likelihood Estimation (MLE)

### The Idea

Find the parameter value that makes the observed data **most probable**.

```
θ̂_MLE = argmax L(θ | data)
              θ

"What θ would make this data most likely to occur?"
```

### The Likelihood Function

```
L(θ | x₁, x₂, ..., xₙ) = P(observing this data | θ)

For independent observations:
L(θ) = f(x₁|θ) × f(x₂|θ) × ... × f(xₙ|θ)
     = ∏ f(xᵢ|θ)
```

### Log-Likelihood (Easier to Work With)

```
ℓ(θ) = ln L(θ) = Σ ln f(xᵢ|θ)

Since ln is monotonic, maximizing ℓ = maximizing L
```

### MLE Procedure

```
Step 1: Write the likelihood L(θ|data)
Step 2: Take log to get ℓ(θ)
Step 3: Take derivative: dℓ/dθ
Step 4: Set equal to zero: dℓ/dθ = 0
Step 5: Solve for θ̂
Step 6: Verify it's a maximum (second derivative < 0)
```

### Example: Normal Distribution MLE

Data: x₁, x₂, ..., xₙ from Normal(μ, σ²)

**Likelihood:**
```
L(μ, σ²) = ∏ (1/√(2πσ²)) exp(-(xᵢ-μ)²/(2σ²))
```

**Log-likelihood:**
```
ℓ(μ, σ²) = -n/2 ln(2π) - n/2 ln(σ²) - (1/2σ²)Σ(xᵢ-μ)²
```

**Take derivatives and solve:**
```
∂ℓ/∂μ = (1/σ²)Σ(xᵢ-μ) = 0   →   μ̂ = X̄

∂ℓ/∂σ² = -n/(2σ²) + (1/2σ⁴)Σ(xᵢ-μ)² = 0   →   σ̂² = (1/n)Σ(xᵢ-X̄)²
```

**Results:**
```
μ̂_MLE = X̄           (unbiased)
σ̂²_MLE = (1/n)Σ(xᵢ-X̄)²   (biased! but consistent)
```

### Example: Bernoulli MLE

Data: n trials, k successes

```
L(p) = p^k × (1-p)^(n-k)

ℓ(p) = k ln(p) + (n-k) ln(1-p)

dℓ/dp = k/p - (n-k)/(1-p) = 0

p̂_MLE = k/n = Sample proportion ✓
```

### Properties of MLE

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MLE PROPERTIES (for large samples)                        │
│                                                             │
│   ✓ Consistent: θ̂_MLE → θ as n → ∞                         │
│   ✓ Asymptotically normal: √n(θ̂-θ) → N(0, 1/I(θ))         │
│   ✓ Asymptotically efficient: Achieves CRLB                │
│   ✓ Invariant: If θ̂ is MLE of θ, then g(θ̂) is MLE of g(θ) │
│                                                             │
│   Note: MLE may be biased for small samples                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Method 3: Bayesian Estimation

### The Idea

Combine **prior knowledge** with **observed data** to get a **posterior distribution**.

```
Posterior ∝ Likelihood × Prior

P(θ|data) ∝ P(data|θ) × P(θ)
```

### Bayes' Theorem for Estimation

```
P(θ|x) = P(x|θ) × P(θ) / P(x)

         Likelihood × Prior
       = ─────────────────────
             Evidence
```

### Point Estimates from Posterior

```
• MAP (Maximum A Posteriori): Mode of posterior
• Posterior Mean: E[θ|data]
• Posterior Median: Median of posterior
```

### Example: Estimating a Proportion

**Prior:** θ ~ Beta(α, β) — our belief before seeing data

**Data:** k successes in n trials

**Posterior:** θ|data ~ Beta(α + k, β + n - k)

**Posterior Mean:**
```
θ̂_Bayes = (α + k) / (α + β + n)
```

### Comparison: Frequentist vs Bayesian

| Aspect | Frequentist (MLE) | Bayesian |
|--------|-------------------|----------|
| Parameter | Fixed but unknown | Random variable |
| Prior | Not used | Required |
| Result | Point estimate + CI | Full distribution |
| Interpretation | Long-run frequency | Degree of belief |

---

## Comparison of Methods

| Method | Advantages | Disadvantages |
|--------|------------|---------------|
| **Method of Moments** | Simple, intuitive | May be inefficient |
| **MLE** | Efficient, well-understood | Computationally harder |
| **Bayesian** | Uses prior info, full distribution | Requires prior specification |

---

# Part 4: Standard Error
## *Measuring Estimation Uncertainty*

---

## What is Standard Error?

The **Standard Error (SE)** measures the variability of an estimator across repeated samples.

```
SE(θ̂) = Standard Deviation of the Sampling Distribution of θ̂

SE = SD(θ̂) = √Var(θ̂)
```

### Standard Error of Common Estimators

| Estimator | Standard Error |
|-----------|----------------|
| Sample Mean X̄ | SE(X̄) = σ/√n |
| Sample Proportion p̂ | SE(p̂) = √(p(1-p)/n) |
| Difference of Means | SE(X̄₁-X̄₂) = √(σ₁²/n₁ + σ₂²/n₂) |
| Sample Variance s² | SE(s²) = σ²√(2/(n-1)) |

---

## Standard Error of the Mean (SEM)

The most common standard error:

```
SEM = σ / √n

If σ is unknown, estimate it:

SEM ≈ s / √n

Where s = sample standard deviation
```

### Visual: SEM and Sample Size

```
SE = σ/√n

n = 1:   SE = σ/1 = σ        ←── Very uncertain
n = 4:   SE = σ/2 = σ/2      
n = 9:   SE = σ/3            
n = 16:  SE = σ/4            
n = 25:  SE = σ/5            
n = 100: SE = σ/10           ←── Much more precise!

To HALVE the SE, you need to QUADRUPLE the sample size!
(Because SE ∝ 1/√n)
```

---

## Why Standard Error Matters

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SE tells us HOW PRECISE our estimate is!                  │
│                                                             │
│   Small SE → Estimate is precise (trustworthy)              │
│   Large SE → Estimate is imprecise (uncertain)              │
│                                                             │
│   SE is used to:                                            │
│   • Construct confidence intervals                          │
│   • Calculate test statistics                               │
│   • Compare estimators                                      │
│   • Determine required sample size                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

# Part 5: Interval Estimation
## *Confidence Intervals*

---

## From Point to Interval

A **confidence interval** provides a range of plausible values for the parameter, along with a confidence level.

```
Point Estimate:  μ̂ = 50

Interval Estimate:  (48.5, 51.5) with 95% confidence

"We are 95% confident the true mean is between 48.5 and 51.5"
```

---

## General Form of Confidence Interval

```
CI = Point Estimate ± Margin of Error

CI = θ̂ ± (Critical Value) × SE(θ̂)
```

### For the Mean (σ known)

```
CI = X̄ ± z* × (σ/√n)

Where z* depends on confidence level:
• 90% CI: z* = 1.645
• 95% CI: z* = 1.960
• 99% CI: z* = 2.576
```

### For the Mean (σ unknown)

```
CI = X̄ ± t* × (s/√n)

Where t* comes from t-distribution with df = n-1
```

### For a Proportion

```
CI = p̂ ± z* × √(p̂(1-p̂)/n)
```

---

## Interpreting Confidence Intervals

### The Correct Interpretation

```
"If we repeated this sampling procedure many times and 
constructed a 95% CI each time, about 95% of those 
intervals would contain the true parameter."
```

### Visual: What 95% Confidence Means

```
Sample 1:  ├────●────┤              contains μ ✓
Sample 2:  ├───●───┤                contains μ ✓
Sample 3:      ├───●───┤            contains μ ✓
Sample 4:  ├──────●──────┤          contains μ ✓
Sample 5:                ├───●───┤  MISSES μ ✗
Sample 6:  ├────●────┤              contains μ ✓
Sample 7:   ├────●────┤             contains μ ✓
...
                       │
                       μ (true value)

About 95 out of 100 intervals will capture μ!
```

### Common Misinterpretations

❌ "There's a 95% probability μ is in this interval"
❌ "95% of the data falls in this interval"
❌ "This interval contains 95% of sample means"

✅ "95% of similarly constructed intervals contain μ"

---

## Factors Affecting CI Width

```
CI Width = 2 × z* × SE = 2 × z* × (σ/√n)

Wider CI when:
• Higher confidence level (larger z*)
• Larger population variability (larger σ)
• Smaller sample size (smaller n)

Narrower CI when:
• Lower confidence level (smaller z*)
• Less population variability (smaller σ)
• Larger sample size (larger n)
```

### The Tradeoff

```
High Confidence (99%) → Wide interval → Less precise
Low Confidence (90%)  → Narrow interval → More precise

You can't have both high confidence AND narrow interval
without increasing sample size!
```

---

## 📖 Complete Example: Factory Quality Control

**Scenario:** A factory claims batteries last μ = 500 hours. You test n = 36 batteries.

**Sample Results:**
- X̄ = 485 hours
- s = 30 hours

### Point Estimate

```
μ̂ = X̄ = 485 hours
```

### Standard Error

```
SE = s/√n = 30/√36 = 30/6 = 5 hours
```

### 95% Confidence Interval

```
For 95% CI with n = 36, use t* ≈ 2.03 (or z* = 1.96 for large n)

CI = 485 ± 1.96 × 5
   = 485 ± 9.8
   = (475.2, 494.8) hours
```

### Interpretation

```
We are 95% confident the true mean battery life is 
between 475.2 and 494.8 hours.

Since 500 is NOT in this interval, we have evidence 
the factory's claim may be false!
```

---

## Python Implementation

### Point Estimation

```python
import numpy as np
from scipy import stats

# Sample data
data = np.array([485, 490, 478, 492, 488, 475, 498, 482, 
                 489, 491, 484, 479, 495, 487, 483, 490])

# Point estimates
mean_estimate = np.mean(data)
var_estimate = np.var(data, ddof=1)  # ddof=1 for unbiased
std_estimate = np.std(data, ddof=1)
median_estimate = np.median(data)

print(f"Sample Mean (μ̂): {mean_estimate:.2f}")
print(f"Sample Variance (σ̂²): {var_estimate:.2f}")
print(f"Sample Std Dev (σ̂): {std_estimate:.2f}")
print(f"Sample Median: {median_estimate:.2f}")
```

### Standard Error

```python
import numpy as np

def standard_error_mean(data):
    """Standard error of the mean"""
    n = len(data)
    s = np.std(data, ddof=1)
    return s / np.sqrt(n)

def standard_error_proportion(p_hat, n):
    """Standard error of proportion"""
    return np.sqrt(p_hat * (1 - p_hat) / n)

# Example
data = np.random.normal(100, 15, size=50)
se = standard_error_mean(data)
print(f"Standard Error: {se:.4f}")
```

### Confidence Intervals

```python
import numpy as np
from scipy import stats

def confidence_interval_mean(data, confidence=0.95):
    """
    Confidence interval for population mean
    Uses t-distribution for unknown sigma
    """
    n = len(data)
    mean = np.mean(data)
    se = stats.sem(data)  # Standard error of mean
    
    # t critical value
    alpha = 1 - confidence
    t_crit = stats.t.ppf(1 - alpha/2, df=n-1)
    
    margin = t_crit * se
    return (mean - margin, mean + margin)

def confidence_interval_proportion(successes, n, confidence=0.95):
    """
    Confidence interval for population proportion
    Uses normal approximation
    """
    p_hat = successes / n
    
    # z critical value
    alpha = 1 - confidence
    z_crit = stats.norm.ppf(1 - alpha/2)
    
    se = np.sqrt(p_hat * (1 - p_hat) / n)
    margin = z_crit * se
    
    return (p_hat - margin, p_hat + margin)

# Example: Mean
data = np.array([485, 490, 478, 492, 488, 475, 498, 482, 489, 491])
ci = confidence_interval_mean(data, 0.95)
print(f"95% CI for mean: ({ci[0]:.2f}, {ci[1]:.2f})")

# Example: Proportion
ci_prop = confidence_interval_proportion(successes=45, n=100, confidence=0.95)
print(f"95% CI for proportion: ({ci_prop[0]:.4f}, {ci_prop[1]:.4f})")
```

### Maximum Likelihood Estimation

```python
import numpy as np
from scipy import stats
from scipy.optimize import minimize

def mle_normal(data):
    """MLE for normal distribution parameters"""
    n = len(data)
    mu_mle = np.mean(data)
    sigma2_mle = np.sum((data - mu_mle)**2) / n  # Note: dividing by n, not n-1
    return mu_mle, sigma2_mle

def mle_exponential(data):
    """MLE for exponential distribution rate parameter"""
    lambda_mle = 1 / np.mean(data)
    return lambda_mle

def mle_poisson(data):
    """MLE for Poisson distribution parameter"""
    lambda_mle = np.mean(data)
    return lambda_mle

# Example
normal_data = np.random.normal(loc=50, scale=10, size=100)
mu_hat, sigma2_hat = mle_normal(normal_data)
print(f"MLE estimates: μ = {mu_hat:.2f}, σ² = {sigma2_hat:.2f}")

# Using scipy for comparison
mu_scipy, sigma_scipy = stats.norm.fit(normal_data)
print(f"Scipy fit: μ = {mu_scipy:.2f}, σ = {sigma_scipy:.2f}")
```

### Comparing Estimators via Simulation

```python
import numpy as np
import matplotlib.pyplot as plt

def compare_estimators(true_mean=100, true_std=20, n_samples=1000, sample_size=30):
    """Compare sample mean vs median as estimators of population mean"""
    
    means = []
    medians = []
    
    for _ in range(n_samples):
        sample = np.random.normal(true_mean, true_std, sample_size)
        means.append(np.mean(sample))
        medians.append(np.median(sample))
    
    means = np.array(means)
    medians = np.array(medians)
    
    print("Sample Mean as Estimator:")
    print(f"  Bias: {np.mean(means) - true_mean:.4f}")
    print(f"  Variance: {np.var(means):.4f}")
    print(f"  MSE: {np.mean((means - true_mean)**2):.4f}")
    
    print("\nSample Median as Estimator:")
    print(f"  Bias: {np.mean(medians) - true_mean:.4f}")
    print(f"  Variance: {np.var(medians):.4f}")
    print(f"  MSE: {np.mean((medians - true_mean)**2):.4f}")
    
    # Plot
    fig, axes = plt.subplots(1, 2, figsize=(12, 4))
    
    axes[0].hist(means, bins=50, density=True, alpha=0.7, label='Sample Mean')
    axes[0].axvline(true_mean, color='red', linestyle='--', label='True Mean')
    axes[0].set_title('Distribution of Sample Mean')
    axes[0].legend()
    
    axes[1].hist(medians, bins=50, density=True, alpha=0.7, label='Sample Median')
    axes[1].axvline(true_mean, color='red', linestyle='--', label='True Mean')
    axes[1].set_title('Distribution of Sample Median')
    axes[1].legend()
    
    plt.tight_layout()
    plt.show()

compare_estimators()
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Confusing σ and s

❌ **Wrong:** Using σ when you only have sample data

✅ **Correct:** Use s (sample std dev) and t-distribution when σ is unknown

---

### Mistake 2: Dividing by n for Variance

❌ **Wrong:** s² = Σ(xᵢ - x̄)² / n

✅ **Correct:** s² = Σ(xᵢ - x̄)² / (n-1) for unbiased estimate

---

### Mistake 3: Misinterpreting CI

❌ **Wrong:** "95% probability that μ is in this interval"

✅ **Correct:** "95% of similarly constructed intervals contain μ"

---

### Mistake 4: SE vs SD Confusion

❌ **Wrong:** "The standard error is 15" (when you mean std dev)

✅ **Correct:** 
- SD measures spread of DATA
- SE measures precision of ESTIMATE

---

### Mistake 5: Ignoring Sample Size

❌ **Wrong:** Same confidence in estimates regardless of n

✅ **Correct:** Larger n → Smaller SE → More precise estimates

---

## Practice Problems 📝

### Problem 1: Point Estimation
A sample of 25 students has mean height 168 cm and std dev 8 cm. Estimate the population mean and its standard error.

<details>
<summary>Click for Answer</summary>

```
Point estimate: μ̂ = X̄ = 168 cm

Standard Error: SE = s/√n = 8/√25 = 8/5 = 1.6 cm

We estimate the population mean is 168 cm with 
standard error of 1.6 cm.
```

</details>

---

### Problem 2: Confidence Interval
Using the data from Problem 1, construct a 95% confidence interval.

<details>
<summary>Click for Answer</summary>

```
X̄ = 168, s = 8, n = 25, SE = 1.6

For 95% CI with df = 24: t* ≈ 2.064

CI = X̄ ± t* × SE
   = 168 ± 2.064 × 1.6
   = 168 ± 3.30
   = (164.7, 171.3) cm

We are 95% confident the true mean height is 
between 164.7 and 171.3 cm.
```

</details>

---

### Problem 3: Sample Size Determination
How large a sample is needed to estimate μ within ±2 units with 95% confidence, if σ = 10?

<details>
<summary>Click for Answer</summary>

```
Margin of Error = z* × σ/√n ≤ 2

For 95% CI: z* = 1.96

1.96 × 10/√n ≤ 2
19.6/√n ≤ 2
√n ≥ 9.8
n ≥ 96.04

We need at least n = 97 observations.
```

</details>

---

### Problem 4: Comparing Estimators
For estimating μ from a normal population, compare the bias and variance of X̄ and the sample median.

<details>
<summary>Click for Answer</summary>

```
Sample Mean X̄:
• Bias: E[X̄] - μ = μ - μ = 0 (unbiased)
• Variance: Var(X̄) = σ²/n

Sample Median:
• Bias: ≈ 0 for large n (asymptotically unbiased)
• Variance: Var(Median) ≈ πσ²/(2n) ≈ 1.57σ²/n

Comparison:
• Both are unbiased (asymptotically)
• X̄ has SMALLER variance (more efficient)
• For normal populations, X̄ is preferred!
• Efficiency of median relative to mean: (σ²/n)/(1.57σ²/n) ≈ 64%
```

</details>

---

### Problem 5: MLE
Find the MLE for λ in a Poisson distribution given data: 3, 5, 4, 2, 6, 3, 4, 5.

<details>
<summary>Click for Answer</summary>

```
For Poisson: P(X = x) = (λ^x × e^(-λ)) / x!

Log-likelihood:
ℓ(λ) = Σxᵢ ln(λ) - nλ - Σln(xᵢ!)

dℓ/dλ = Σxᵢ/λ - n = 0

λ̂ = Σxᵢ/n = X̄

Data: 3, 5, 4, 2, 6, 3, 4, 5
Sum = 32, n = 8

λ̂_MLE = 32/8 = 4

The MLE for λ is 4.
```

</details>

---

## Summary: The Essence of Estimation

```
┌─────────────────────────────────────────────────────────────────┐
│                   STATISTICAL ESTIMATION                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "Using sample data to learn about population parameters"       │
│                                                                  │
│   TYPES OF ESTIMATES:                                            │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  POINT: Single best guess (X̄, s², p̂)                   │   │
│   │  INTERVAL: Range with confidence (CI)                    │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   GOOD ESTIMATOR PROPERTIES:                                     │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Unbiased: E[θ̂] = θ                                   │   │
│   │  • Consistent: θ̂ → θ as n → ∞                          │   │
│   │  • Efficient: Minimum variance                           │   │
│   │  • Sufficient: Uses all information                      │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   ESTIMATION METHODS:                                            │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Method of Moments: Match moments                      │   │
│   │  • MLE: Maximize likelihood                              │   │
│   │  • Bayesian: Prior + Likelihood = Posterior             │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY FORMULAS:                                                  │
│   • Standard Error: SE(X̄) = σ/√n                               │
│   • 95% CI: X̄ ± 1.96 × SE                                       │
│   • MSE = Variance + Bias²                                       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Estimation Matters

| Application | What We Estimate | Method |
|-------------|------------------|--------|
| **Polling** | Voter preference | Sample proportion + CI |
| **Quality Control** | Defect rate | MLE + control charts |
| **Medicine** | Treatment effect | Difference of means |
| **Finance** | Expected return | Sample mean + SE |
| **Science** | Physical constants | MLE + uncertainty |

> **"Estimation is the bridge between the sample we have and the population we care about."**

Every statistical inference — from opinion polls to clinical trials to quality control — relies on sound estimation principles! 🎯

---

*From samples to insights, from uncertainty to confidence — that's the power of statistical estimation!* ✨
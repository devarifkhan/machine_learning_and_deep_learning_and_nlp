# Power Law Distribution
## The Mathematics of Extremes and Inequality 📊

---

## The World of Extremes

Have you noticed these strange patterns?

- **Wealth:** The richest 1% own more than the bottom 50% combined 💰
- **Cities:** A few mega-cities, millions of small towns 🏙️
- **Websites:** Google gets billions of visits; most sites get almost none 🌐
- **Earthquakes:** Many tiny tremors, rare devastating quakes 🌍
- **Words:** "The" appears millions of times; most words are rare 📚
- **Social Media:** A few influencers have millions of followers; most have few 📱

These aren't coincidences. They all follow **Power Law Distributions** — the mathematics of extreme inequality and "the rich get richer."

---

## 📖 Story: The YouTube Paradox

Imagine you're analyzing YouTube channels in Bangladesh:

| Channel Size | Number of Channels | Total Subscribers |
|--------------|-------------------|-------------------|
| 10M+ subscribers | 5 | 75 million |
| 1M-10M | 50 | 150 million |
| 100K-1M | 500 | 200 million |
| 10K-100K | 5,000 | 150 million |
| 1K-10K | 50,000 | 150 million |
| < 1K | 500,000 | 75 million |

**The Pattern:**
- A tiny fraction of channels (top 0.01%) have most subscribers
- Each "tier" down has ~10× more channels but similar total reach
- This is the **Power Law** at work!

---

## What is a Power Law Distribution?

A **Power Law Distribution** describes phenomena where the probability of an event decreases as a **power** of its size.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              POWER LAW DISTRIBUTION                          │
│                                                             │
│   Basic Form:                                               │
│                                                             │
│       P(X = x) ∝ x^(-α)                                     │
│                                                             │
│   Where:                                                    │
│   • x = the value (size, frequency, etc.)                   │
│   • α = the power law exponent (typically 2 < α < 3)        │
│   • ∝ means "proportional to"                               │
│                                                             │
│   Key Feature: "HEAVY TAIL" — extreme events are            │
│                more likely than normal distributions        │
│                would predict!                               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Power Law Formula

### Probability Density Function (PDF)

For continuous power law with minimum value x_min:

```
f(x) = (α - 1) / x_min × (x / x_min)^(-α)

     = C × x^(-α)    for x ≥ x_min

Where C is a normalization constant
```

### Complementary CDF (Survival Function)

The probability of being **greater than** x:

```
P(X > x) = (x / x_min)^(-α + 1) = (x / x_min)^(1-α)
```

### The Signature: Linear on Log-Log Plot

```
log(P(X > x)) = (1-α) × log(x) + constant

On a log-log plot, power law appears as a STRAIGHT LINE!
```

---

## Visualization: The Heavy Tail

### Power Law vs Normal Distribution

```
LINEAR SCALE                          LOG-LOG SCALE
                                      
P(x)                                  log P(x)
│                                     │
│█                                    │●
│█                                    │ ●
│█                                    │  ●
│█░                                   │   ●
│█░░                                  │    ●
│█░░░                                 │     ●
│█░░░░░░░░░░░░                        │      ●●●●●●●●
└──────────────────── x               └──────────────────── log x

█ = Power Law                         Power Law = STRAIGHT LINE
░ = Normal                            Normal = Curved (falls off fast)

The "heavy tail" extends much further than normal!
```

### Why "Heavy Tail" Matters

```
Normal Distribution:                 Power Law Distribution:
                                     
     ╭───╮                           │█
    ╭╯   ╰╮                          │█
   ╭╯     ╰╮                         │█
  ╭╯       ╰╮                        │█░
 ╭╯         ╰╮                       │█░░
╭╯           ╰╮                      │█░░░░░░░░░░░░░░░░░░
────────────────                     └──────────────────────────

Tails die off                        Tail extends FAR
exponentially fast                   (extreme events more likely)

P(X > 6σ) ≈ 0.000000001             P(X > 100×median) = significant!
```

---

## The Pareto Distribution (Type I Power Law)

The most famous power law, named after Vilfredo Pareto who studied wealth distribution.

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              PARETO DISTRIBUTION                             │
│                                                             │
│   PDF:  f(x) = (α × x_min^α) / x^(α+1)    for x ≥ x_min    │
│                                                             │
│   CDF:  F(x) = 1 - (x_min / x)^α                           │
│                                                             │
│   Survival: P(X > x) = (x_min / x)^α                        │
│                                                             │
│   Parameters:                                               │
│   • x_min = minimum value (scale parameter)                 │
│   • α = shape parameter (Pareto index)                      │
│                                                             │
│   Notation: X ~ Pareto(x_min, α)                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Key Properties of Pareto

| Property | Formula | Condition |
|----------|---------|-----------|
| **Mean** | α × x_min / (α - 1) | α > 1 |
| **Variance** | x_min² × α / ((α-1)² × (α-2)) | α > 2 |
| **Median** | x_min × 2^(1/α) | Always |
| **Mode** | x_min | Always |

**Warning:** Mean is **infinite** if α ≤ 1, variance is **infinite** if α ≤ 2!

---

## The 80/20 Rule (Pareto Principle)

The famous principle: **80% of effects come from 20% of causes**

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                   THE 80/20 RULE                             │
│                                                             │
│   • 80% of wealth owned by 20% of people                    │
│   • 80% of sales from 20% of customers                      │
│   • 80% of bugs in 20% of code                              │
│   • 80% of results from 20% of effort                       │
│   • 80% of complaints from 20% of customers                 │
│                                                             │
│   Mathematically: Pareto with α ≈ 1.16 gives 80/20          │
│                                                             │
│   General form: Top p fraction has (1-p)^α of total         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visualizing 80/20

```
Cumulative % of Total
100%│                              ●────────
    │                         ●────╯
 80%├─────────────────────●───╯
    │                 ●───╯│
    │            ●────╯    │
    │       ●────╯         │
    │  ●────╯              │
    │●─╯                   │
  0%├──────────────────────┼────────────────
    0%                    20%              100%
              % of Population
              
    Top 20% owns 80% of the total!
```

---

## Zipf's Law (Discrete Power Law)

For **ranked** discrete data (like word frequencies):

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                    ZIPF'S LAW                                │
│                                                             │
│   Frequency of rank r:  f(r) ∝ 1/r^s                        │
│                                                             │
│   Where:                                                    │
│   • r = rank (1st most common, 2nd most common, etc.)       │
│   • s = Zipf exponent (often ≈ 1)                           │
│                                                             │
│   Example (Word frequencies):                               │
│   • "the" (rank 1): frequency = f                           │
│   • "of" (rank 2): frequency ≈ f/2                          │
│   • "and" (rank 3): frequency ≈ f/3                         │
│   • "to" (rank 4): frequency ≈ f/4                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: City Populations

| Rank | City | Population | Expected (Zipf) |
|------|------|------------|-----------------|
| 1 | Dhaka | 22 million | 22 million |
| 2 | Chittagong | 5 million | 11 million |
| 3 | Khulna | 1.5 million | 7.3 million |
| 4 | Rajshahi | 0.9 million | 5.5 million |

*Real data doesn't follow Zipf perfectly, but the pattern is clear!*

---

## Scale-Free Property

Power laws are **scale-free** — they look the same at any scale!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              SCALE-FREE (SELF-SIMILAR)                       │
│                                                             │
│   If you "zoom in" on a power law distribution,             │
│   it looks the same as the original!                        │
│                                                             │
│   Mathematically: P(X > cx) / P(X > x) = c^(-α+1)           │
│                                                             │
│   This ratio depends only on c, not on x!                   │
│                                                             │
│   Example:                                                  │
│   • P(wealth > $10M) / P(wealth > $1M) = ratio             │
│   • P(wealth > $100M) / P(wealth > $10M) = SAME ratio      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Self-Similarity

```
Full Distribution        Zoomed In (×10)        Zoomed In More (×100)

   │█                         │█                        │█
   │█                         │█                        │█
   │█░                        │█░                       │█░
   │█░░░                      │█░░░                     │█░░░
   │█░░░░░░░░                 │█░░░░░░░░                │█░░░░░░░░
   └────────────              └────────────             └────────────
   
   SAME SHAPE at every scale! (Unlike normal distribution)
```

---

## "The Rich Get Richer" (Preferential Attachment)

Power laws often emerge from **preferential attachment** — success breeds more success.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│           PREFERENTIAL ATTACHMENT MECHANISM                  │
│                                                             │
│   "The probability of getting more is proportional          │
│    to how much you already have"                            │
│                                                             │
│   Examples:                                                 │
│   • Popular videos get recommended more → more views        │
│   • Cited papers get noticed more → more citations          │
│   • Rich people have more investment opportunities          │
│   • Big cities attract more migrants                        │
│   • Popular websites get more backlinks                     │
│                                                             │
│   This FEEDBACK LOOP creates power law distributions!       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Mathematical Model (Barabási-Albert)

```
New node connects to existing node i with probability:

P(connect to i) = k_i / Σ k_j

Where k_i = current number of connections of node i

Result: Degree distribution follows power law!
```

---

## The Exponent α: What It Tells Us

The **exponent α** determines how "extreme" the inequality is:

| α Value | Inequality | Mean | Variance | Example |
|---------|------------|------|----------|---------|
| 1 < α ≤ 2 | Extreme | Infinite | Infinite | Wealth in some countries |
| 2 < α ≤ 3 | High | Finite | Infinite | City sizes, citations |
| α > 3 | Moderate | Finite | Finite | Word frequencies |

### Visual: Effect of α

```
α = 1.5 (Extreme)          α = 2.5 (Moderate)         α = 4 (Mild)

│█                         │█                         │█░
│█                         │█░                        │█░░
│█                         │█░░                       │█░░░░
│█░                        │█░░░░                     │█░░░░░░░░
│█░░░░░░░░░░░░░░░░░░      │█░░░░░░░░░░░░            │█░░░░░░░░░░░░░░
└──────────────────────    └──────────────────────   └──────────────────────

Heavy tail, extreme         Moderate tail              Lighter tail, closer
inequality                                             to exponential
```

### Typical α Values in Nature

| Phenomenon | α Value |
|------------|---------|
| Word frequency (Zipf) | ≈ 1.0 |
| City populations | ≈ 1.1 |
| Wealth distribution | 1.5 - 2.0 |
| Website traffic | ≈ 2.0 |
| Citations | 2.5 - 3.0 |
| Earthquake magnitude | ≈ 2.0 |
| Moon crater sizes | ≈ 2.0 |
| Solar flare intensity | ≈ 2.0 |

---

## 📖 Real-Life Examples

### Example 1: Wealth Distribution

Wealth in most countries follows a Pareto distribution:

```
X ~ Pareto(x_min = $10,000, α = 1.5)

Top 1%: P(X > x_99) where x_99 ≈ $1.7 million
This 1% owns about 40% of total wealth!

Top 0.1%: P(X > x_99.9) where x_99.9 ≈ $17 million
This 0.1% owns about 20% of total wealth!
```

### Example 2: Earthquake Magnitudes

The Gutenberg-Richter law:

```
log₁₀(N) = a - bM

Where:
N = number of earthquakes ≥ magnitude M
b ≈ 1 (globally)

This means: For every magnitude 7 earthquake,
there are ~10 magnitude 6 earthquakes,
~100 magnitude 5 earthquakes, etc.
```

### Example 3: Website Traffic

```
Daily visits follow power law with α ≈ 2:

• Top 100 sites: Billions of visits
• Next 1,000 sites: Millions each
• Next 10,000 sites: Thousands each
• Next 100,000 sites: Hundreds each
• Millions of sites: Single digits
```

### Example 4: Social Media Followers

```
Followers ~ PowerLaw(α ≈ 2.1)

• 1 account: 100M+ followers (top celebrity)
• 10 accounts: 10M+ followers
• 100 accounts: 1M+ followers
• 1,000 accounts: 100K+ followers
• 10,000 accounts: 10K+ followers
• 100,000 accounts: 1K+ followers
• 1,000,000 accounts: < 100 followers
```

### Example 5: File Sizes

```
File sizes on hard drives:

• Few huge files (videos, databases)
• Some large files (photos, documents)
• Many small files (text, configs)

Size distribution ≈ Pareto(α ≈ 1.5)
```

---

## Power Law vs Other Distributions

### Comparison Table

| Property | Normal | Exponential | Power Law |
|----------|--------|-------------|-----------|
| **Tail** | Light (dies fast) | Medium | Heavy (dies slow) |
| **Extreme events** | Very rare | Rare | Not so rare! |
| **Scale-free** | No | No | Yes |
| **Mean** | Always finite | Always finite | May be infinite |
| **Variance** | Always finite | Always finite | May be infinite |
| **Log-log plot** | Curved down | Curved down | **Straight line** |

### Visual Comparison

```
P(X > x) on log-log scale

log P(X>x)
    │
    │●                          
    │●●○                        ● Power Law (straight)
    │  ●○○                      ○ Exponential (curved)
    │   ●○○○                    □ Normal (very curved)
    │    ●●○○○□
    │      ●●○○○○□□
    │        ●●●○○○○○□□□□□
    │           ●●●●○○○○○○○□□□□□□□□□
    └───────────────────────────────────── log x
    
Power law maintains straight line (constant slope)
Others curve downward (tail dies off faster)
```

---

## Detecting Power Laws

### Method 1: Log-Log Plot

```python
import numpy as np
import matplotlib.pyplot as plt

# If power law, log-log plot should be LINEAR
log_x = np.log10(x_values)
log_p = np.log10(probabilities)

plt.plot(log_x, log_p, 'o')
plt.xlabel('log(x)')
plt.ylabel('log(P(X > x))')
# Should see straight line!
```

### Method 2: Fit and Compare (MLE)

```python
import powerlaw  # pip install powerlaw

# Fit power law
fit = powerlaw.Fit(data)
print(f"Estimated α: {fit.alpha}")
print(f"x_min: {fit.xmin}")

# Compare to alternatives
R, p = fit.distribution_compare('power_law', 'exponential')
# If R > 0 and p < 0.05: power law is better fit
```

### Method 3: Kolmogorov-Smirnov Test

Compare empirical CDF to theoretical power law CDF.

---

## Mathematical Properties

### Moments

```
E[X^n] = α × x_min^n / (α - n)    for n < α

• E[X] exists only if α > 1
• E[X²] exists only if α > 2
• Higher moments require larger α
```

### Generating Power Law Random Variables

Using inverse transform:

```
If U ~ Uniform(0, 1), then:

X = x_min × (1 - U)^(-1/α) ~ Pareto(x_min, α)

Or equivalently:

X = x_min × U^(-1/α)
```

### Sum of Power Laws

Unlike normal distributions, sum of power law variables is **NOT** power law!

However, the **maximum** of power law variables IS power law:

```
max(X₁, X₂, ..., Xₙ) ~ Pareto(x_min, α)  (approximately, for large max)
```

---

## Python Implementation

### Using SciPy (Pareto)

```python
import numpy as np
from scipy import stats

# Pareto distribution: shape=α, scale=x_min
alpha = 2.5
x_min = 1

pareto = stats.pareto(b=alpha, scale=x_min)

# PDF and CDF at x = 3
print(f"f(3) = {pareto.pdf(3):.4f}")
print(f"P(X ≤ 3) = {pareto.cdf(3):.4f}")
print(f"P(X > 3) = {1 - pareto.cdf(3):.4f}")

# Mean (only exists if α > 1)
if alpha > 1:
    theoretical_mean = alpha * x_min / (alpha - 1)
    print(f"Theoretical mean: {theoretical_mean:.4f}")
    print(f"SciPy mean: {pareto.mean():.4f}")

# Generate samples
samples = pareto.rvs(size=10000)
print(f"Sample mean: {samples.mean():.4f}")
print(f"Sample median: {np.median(samples):.4f}")
```

### Using powerlaw Package

```python
import powerlaw
import numpy as np

# Generate synthetic power law data
alpha_true = 2.5
x_min = 1
n = 10000
data = x_min * np.random.pareto(alpha_true - 1, n) + x_min

# Fit power law
fit = powerlaw.Fit(data, xmin=x_min)
print(f"Estimated α: {fit.alpha:.4f}")
print(f"True α: {alpha_true}")

# Plot
fig = fit.plot_pdf(color='b', linewidth=2)
fit.power_law.plot_pdf(color='r', linestyle='--', ax=fig)
plt.show()

# Compare to other distributions
print("\nComparing to alternatives:")
R, p = fit.distribution_compare('power_law', 'exponential')
print(f"vs Exponential: R={R:.3f}, p={p:.4f}")

R, p = fit.distribution_compare('power_law', 'lognormal')
print(f"vs Log-Normal: R={R:.3f}, p={p:.4f}")
```

### Manual Implementation

```python
import numpy as np

def pareto_pdf(x, x_min, alpha):
    """Pareto PDF"""
    if x < x_min:
        return 0
    return alpha * (x_min ** alpha) / (x ** (alpha + 1))

def pareto_cdf(x, x_min, alpha):
    """Pareto CDF"""
    if x < x_min:
        return 0
    return 1 - (x_min / x) ** alpha

def pareto_survival(x, x_min, alpha):
    """P(X > x)"""
    if x < x_min:
        return 1
    return (x_min / x) ** alpha

def pareto_quantile(p, x_min, alpha):
    """Inverse CDF (quantile function)"""
    return x_min / ((1 - p) ** (1/alpha))

def generate_pareto(n, x_min, alpha):
    """Generate n Pareto random variables"""
    u = np.random.uniform(0, 1, n)
    return x_min / (u ** (1/alpha))

# Example
alpha, x_min = 2.5, 1

# Generate samples
samples = generate_pareto(10000, x_min, alpha)

# Verify
print(f"Sample mean: {samples.mean():.4f}")
print(f"Theoretical mean: {alpha * x_min / (alpha - 1):.4f}")

# Find extreme values
print(f"Max value: {samples.max():.2f}")
print(f"99th percentile: {np.percentile(samples, 99):.2f}")
```

### Visualization

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

fig, axes = plt.subplots(2, 2, figsize=(14, 10))

# Parameters
alpha = 2.5
x_min = 1

# Plot 1: PDF (linear scale)
ax1 = axes[0, 0]
x = np.linspace(1, 10, 1000)
pareto = stats.pareto(b=alpha, scale=x_min)
ax1.plot(x, pareto.pdf(x), 'b-', linewidth=2)
ax1.fill_between(x, pareto.pdf(x), alpha=0.3)
ax1.set_xlabel('x')
ax1.set_ylabel('f(x)')
ax1.set_title(f'Pareto PDF (α={alpha})')

# Plot 2: PDF (log-log scale)
ax2 = axes[0, 1]
x = np.logspace(0, 3, 1000)
ax2.loglog(x, pareto.pdf(x), 'b-', linewidth=2)
ax2.set_xlabel('x (log scale)')
ax2.set_ylabel('f(x) (log scale)')
ax2.set_title('Log-Log Plot (Should be straight line)')
ax2.grid(True, alpha=0.3)

# Plot 3: CCDF (survival function)
ax3 = axes[1, 0]
x = np.logspace(0, 3, 1000)
ax3.loglog(x, 1 - pareto.cdf(x), 'b-', linewidth=2)
ax3.set_xlabel('x (log scale)')
ax3.set_ylabel('P(X > x) (log scale)')
ax3.set_title('Complementary CDF (Log-Log)')
ax3.grid(True, alpha=0.3)

# Plot 4: Different α values
ax4 = axes[1, 1]
x = np.linspace(1, 5, 1000)
for a in [1.5, 2.0, 2.5, 3.0, 4.0]:
    pareto_a = stats.pareto(b=a, scale=1)
    ax4.plot(x, pareto_a.pdf(x), label=f'α = {a}')
ax4.set_xlabel('x')
ax4.set_ylabel('f(x)')
ax4.set_title('Effect of α on PDF')
ax4.legend()

plt.tight_layout()
plt.show()
```

---

## Power Laws in Networks

Many real networks follow power law degree distributions:

### Examples

| Network | α (degree distribution) |
|---------|------------------------|
| World Wide Web | ≈ 2.1 |
| Citation networks | ≈ 3.0 |
| Social networks | 2.0 - 3.0 |
| Protein interactions | ≈ 2.5 |
| Power grid | ≈ 4.0 |

### The "Hub" Effect

```
Power law networks have HUBS — highly connected nodes

    ○           ○
     \         /
      \   ●   /        ● = Hub (very high degree)
       \ /|\ /         ○ = Regular nodes (low degree)
        ●─┼─●
       / \|/ \
      /   ●   \
     /         \
    ○           ○

A few hubs connect to most of the network!
```

---

## Truncated Power Laws

Real-world power laws often have **cutoffs**:

```
f(x) ∝ x^(-α) × exp(-x/x_max)

• Power law behavior for small x
• Exponential cutoff for large x
• x_max = characteristic scale where cutoff occurs
```

### Why Truncation?

- **Physical limits:** Maximum city size, maximum wealth
- **Finite sample:** We don't observe infinite data
- **Mechanism changes:** Different processes at extremes

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Claiming Power Law Without Testing

❌ **Wrong:** "This histogram looks heavy-tailed, must be power law!"

✅ **Correct:** Use statistical tests (log-likelihood ratio, KS test)
Many distributions have heavy tails (log-normal, stretched exponential)

---

### Mistake 2: Fitting Entire Range

❌ **Wrong:** Fitting power law from x = 0

✅ **Correct:** Power laws only hold **above some x_min**
The lower part often follows different distribution

---

### Mistake 3: Linear Regression on Log-Log

❌ **Wrong:** Using OLS regression on log-transformed data

✅ **Correct:** Use Maximum Likelihood Estimation (MLE)
OLS gives biased estimates for power laws

---

### Mistake 4: Ignoring x_min

❌ **Wrong:** "α = 2" (without specifying x_min)

✅ **Correct:** Both α AND x_min are needed to fully specify the distribution

---

### Mistake 5: Assuming Infinite Mean Always

❌ **Wrong:** "Power laws have infinite mean"

✅ **Correct:** Mean is infinite only if α ≤ 1 (for Pareto parameterization)
Many real power laws have α > 2 and finite mean

---

## Practice Problems 📝

### Problem 1: Basic Pareto
For X ~ Pareto(x_min = 100, α = 2), find P(X > 200).

<details>
<summary>Click for Answer</summary>

```
P(X > x) = (x_min / x)^α

P(X > 200) = (100 / 200)^2
           = (0.5)^2
           = 0.25 = 25%
```

</details>

---

### Problem 2: Finding the Mean
For X ~ Pareto(x_min = 1000, α = 3), find the mean.

<details>
<summary>Click for Answer</summary>

```
E[X] = α × x_min / (α - 1)

E[X] = 3 × 1000 / (3 - 1)
     = 3000 / 2
     = 1500

The mean (1500) is higher than x_min (1000) due to heavy tail!
```

</details>

---

### Problem 3: Percentile
For X ~ Pareto(x_min = 50, α = 1.5), find the 95th percentile.

<details>
<summary>Click for Answer</summary>

```
Quantile function: x_p = x_min / (1 - p)^(1/α)

x_0.95 = 50 / (1 - 0.95)^(1/1.5)
       = 50 / (0.05)^(0.667)
       = 50 / 0.136
       ≈ 368

The top 5% have values above 368 (compared to minimum of 50!)
```

</details>

---

### Problem 4: 80/20 Check
For Pareto with α = 1.16, verify the 80/20 rule.

<details>
<summary>Click for Answer</summary>

```
For Pareto, top (1-p) fraction owns:
Fraction of total = p^(1 - 1/α)

Top 20% (p = 0.8):
Fraction = 0.8^(1 - 1/1.16)
         = 0.8^(1 - 0.862)
         = 0.8^0.138
         ≈ 0.80

Yes! Top 20% owns about 80% of total when α ≈ 1.16
```

</details>

---

### Problem 5: Comparing Extremes
If X ~ Pareto(1, 2) and Y ~ Exponential(1), compare P(X > 10) vs P(Y > 10).

<details>
<summary>Click for Answer</summary>

```
Power Law (Pareto):
P(X > 10) = (1/10)^2 = 0.01 = 1%

Exponential:
P(Y > 10) = e^(-10) ≈ 0.0000454 = 0.00454%

Ratio: 1% / 0.00454% ≈ 220

The power law gives extreme events 220× more probability!
This is the essence of "heavy tail."
```

</details>

---

## Applications Summary

| Field | Application | What follows Power Law |
|-------|-------------|----------------------|
| **Economics** | Wealth inequality | Income, firm sizes |
| **Sociology** | Social influence | Followers, citations |
| **Technology** | Internet | Website traffic, file sizes |
| **Natural Science** | Catastrophes | Earthquakes, fires, floods |
| **Biology** | Ecology | Species abundance, gene expression |
| **Linguistics** | Language | Word frequencies |
| **Urban Planning** | Demographics | City sizes |
| **Finance** | Risk | Market crashes, returns |

---

## Summary: The Essence of Power Law

```
┌─────────────────────────────────────────────────────────────────┐
│                    POWER LAW DISTRIBUTION                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "The mathematics of extreme inequality"                        │
│                                                                  │
│   BASIC FORM:                                                    │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  P(X > x) ∝ x^(-α+1)                                     │   │
│   │                                                          │   │
│   │  Or equivalently: P(X = x) ∝ x^(-α)                      │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY FEATURES:                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Heavy tail: Extreme events are NOT rare!              │   │
│   │  • Scale-free: Same pattern at all scales                │   │
│   │  • 80/20 rule: Few entities dominate                     │   │
│   │  • May have infinite mean/variance                       │   │
│   │  • Straight line on log-log plot                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   ARISES FROM:                                                   │
│   • Preferential attachment ("rich get richer")                  │
│   • Self-organized criticality                                   │
│   • Multiplicative processes                                     │
│   • Optimization under constraints                               │
│                                                                  │
│   COMMON FORMS:                                                  │
│   • Pareto distribution (continuous)                             │
│   • Zipf's law (discrete, ranked)                               │
│   • Power law with cutoff (truncated)                            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Power Laws Matter

> **"Power laws reveal that extreme events are not anomalies — they're built into the system."**

Understanding power laws helps you:

| Insight | Implication |
|---------|-------------|
| **Expect extremes** | Plan for outliers, not just averages |
| **Avoid underestimating risk** | "Once in a century" events happen often |
| **Understand inequality** | Few winners, many losers is natural |
| **Design robust systems** | Networks, economies, infrastructure |
| **Model correctly** | Don't use normal distribution for everything |

The world is more extreme than we intuitively expect. Power laws quantify just how extreme! 🚀

---

*From wealth to websites, earthquakes to epidemics — when the math goes extreme, power laws explain why!* ⚡
# Pareto Distribution
## The Mathematics of the 80/20 Rule 💰

---

## The Discovery of Inequality

In 1896, Italian economist **Vilfredo Pareto** made a startling observation while studying wealth in Italy:

> *"About 80% of the land was owned by 20% of the population."*

He found the same pattern across different countries and time periods. This wasn't a coincidence — it was a **mathematical law** governing how wealth, resources, and many other quantities distribute themselves.

Welcome to the **Pareto Distribution** — the mathematics of inequality!

---

## 📖 Story: The Startup Ecosystem

Venture capitalist Rahim is analyzing the Bangladeshi startup ecosystem:

| Category | Number of Startups | Total Valuation |
|----------|-------------------|-----------------|
| Unicorns (৳1000+ crore) | 5 (0.5%) | ৳8,000 crore (40%) |
| Series B+ (৳100-1000 crore) | 45 (4.5%) | ৳6,000 crore (30%) |
| Series A (৳10-100 crore) | 150 (15%) | ৳4,000 crore (20%) |
| Seed Stage (৳1-10 crore) | 800 (80%) | ৳2,000 crore (10%) |
| **Total** | **1,000** | **৳20,000 crore** |

**The Pattern:**
- Top 5% of startups hold 70% of total valuation
- Bottom 80% hold only 10%
- This is the **Pareto Distribution** at work!

---

## What is the Pareto Distribution?

The Pareto distribution is a **continuous probability distribution** that models phenomena where a small number of items account for a large portion of the total.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│              PARETO DISTRIBUTION                             │
│                                                             │
│   "The few have most, the many have little"                 │
│                                                             │
│   Key Characteristics:                                      │
│   ✓ Defined only for x ≥ x_min (minimum value)              │
│   ✓ Heavy right tail (extreme values are likely)            │
│   ✓ Models inequality and concentration                     │
│   ✓ Related to the 80/20 rule                               │
│                                                             │
│   Named after Vilfredo Pareto (1848-1923)                   │
│   Italian economist and sociologist                         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Two Parameters

| Parameter | Symbol | Meaning | Typical Values |
|-----------|--------|---------|----------------|
| **Scale** | x_min (or x_m) | Minimum possible value | > 0 |
| **Shape** | α (alpha) | Controls inequality/tail heaviness | 1 to 4 |

**Notation:** X ~ Pareto(x_min, α) or X ~ Pareto(α, x_min)

---

## The Pareto Formulas

### PDF (Probability Density Function)

```
f(x) = (α × x_min^α) / x^(α+1)    for x ≥ x_min
f(x) = 0                          for x < x_min
```

Or equivalently:

```
f(x) = α/x_min × (x_min/x)^(α+1)
```

### CDF (Cumulative Distribution Function)

```
F(x) = P(X ≤ x) = 1 - (x_min/x)^α    for x ≥ x_min
```

### Survival Function (CCDF)

The probability of exceeding x:

```
P(X > x) = (x_min/x)^α
```

This is the most intuitive form — probability decreases as a **power** of x!

### Quantile Function (Inverse CDF)

```
x_p = x_min / (1-p)^(1/α)

Where p is the desired percentile (0 to 1)
```

---

## Visualization: The Pareto Shape

### The Heavy Tail

```
f(x)
  │
  │█
  │██
  │███
  │████
  │█████
  │██████
  │███████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  ← Heavy tail
  └─────────────────────────────────────────────────────
   x_min                                              x
   
Most probability mass is near x_min, but the tail extends FAR!
```

### Effect of α (Shape Parameter)

```
α = 1 (Extreme inequality)     α = 2 (High inequality)      α = 4 (Moderate)

f(x)│                          f(x)│                         f(x)│
    │█                             │█                            │██
    │█                             │██                           │███
    │█░                            │███                          │█████
    │█░░░░░░░░░░░░░░░░░░          │████░░░░░░░░░░░              │███████░░░░
    └──────────────────            └──────────────────           └──────────────────
    
    VERY heavy tail               Heavy tail                    Lighter tail
    Mean = INFINITE!              Mean exists                   Mean & Var exist
```

### Log-Log Plot (Signature of Pareto)

```
log f(x)
    │
    │●
    │ ●
    │  ●
    │   ●
    │    ●
    │     ●
    │      ●
    │       ●●●●●●●●●●●●●●●●
    └────────────────────────── log x
    
    STRAIGHT LINE on log-log plot!
    Slope = -(α + 1)
```

---

## Key Properties

### 1. Mean (Expected Value)

```
E[X] = α × x_min / (α - 1)    if α > 1
E[X] = ∞ (infinite)            if α ≤ 1
```

**Example:** If x_min = 100 and α = 2:
```
E[X] = 2 × 100 / (2 - 1) = 200
```

### 2. Variance

```
Var(X) = x_min² × α / ((α-1)² × (α-2))    if α > 2
Var(X) = ∞ (infinite)                      if α ≤ 2
```

### 3. Standard Deviation

```
SD(X) = √Var(X)    if α > 2
```

### 4. Median

```
Median = x_min × 2^(1/α)
```

**Example:** If x_min = 100 and α = 2:
```
Median = 100 × 2^(1/2) = 100 × 1.414 = 141.4
```

### 5. Mode

```
Mode = x_min    (always!)
```

The mode is always at the minimum — most values are near the minimum!

### 6. Relationship: Mode < Median < Mean

```
Mode = x_min < Median < Mean (when mean exists)

This reflects the RIGHT SKEWNESS caused by the heavy tail.
```

---

## Properties Summary Table

| Property | Formula | α = 2, x_min = 100 | α = 3, x_min = 100 |
|----------|---------|-------------------|-------------------|
| **Mean** | αx_min/(α-1) | 200 | 150 |
| **Median** | x_min × 2^(1/α) | 141.4 | 126.0 |
| **Mode** | x_min | 100 | 100 |
| **Variance** | x²_min × α/((α-1)²(α-2)) | ∞ | 7,500 |
| **Std Dev** | √Variance | ∞ | 86.6 |
| **Skewness** | 2(1+α)√(α-2)/((α-3)) | ∞ | undefined |
| **CV** | 1/(α-1) × √(α/(α-2)) | ∞ | 0.577 |

---

## When Properties Exist

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   EXISTENCE OF MOMENTS                                       │
│                                                             │
│   α > 1  →  Mean exists (finite)                            │
│   α > 2  →  Variance exists (finite)                        │
│   α > 3  →  Skewness exists (finite)                        │
│   α > 4  →  Kurtosis exists (finite)                        │
│   α > n  →  n-th moment exists                              │
│                                                             │
│   The n-th moment E[X^n] exists only if α > n               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: How α Affects Properties

```
        α = 1      α = 2      α = 3      α = 4
        ────────────────────────────────────────►
        
Mean    │   ∞    │ Exists │ Exists │ Exists │
        │        │        │        │        │
Var     │   ∞    │   ∞    │ Exists │ Exists │
        │        │        │        │        │
Skew    │   ∞    │   ∞    │   ∞    │ Exists │
        
More extreme ◄──────────────────────► Less extreme
inequality                            inequality
```

---

## The 80/20 Rule (Pareto Principle)

The famous principle that **80% of effects come from 20% of causes**.

### Mathematical Derivation

For a Pareto distribution, the fraction of total owned by the top (1-p) fraction is:

```
Fraction of total = p^(1 - 1/α)
```

For **80/20 rule** (top 20% owns 80%):
```
0.80 = 0.80^(1 - 1/α)
```

Solving: **α ≈ 1.161**

### Generalized Pareto Principle

| α | Top 20% owns | Top 10% owns | Top 1% owns |
|---|--------------|--------------|-------------|
| 1.0 | 100% | 100% | 100% |
| 1.16 | 80% | 70% | 50% |
| 1.5 | 64% | 52% | 32% |
| 2.0 | 55% | 42% | 22% |
| 3.0 | 48% | 35% | 15% |

### Visual: The 80/20 Rule

```
Cumulative % of Total
     │
100% ├─────────────────────────────────────●
     │                              ●●●●●●●╯
 80% ├─────────────────────────●●●●╯
     │                    ●●●●╯│
     │               ●●●●╯     │
 50% ├─────────●●●●╯           │
     │    ●●●●╯                │
     │●●●╯                     │
  0% ├─────────────────────────┼───────────
     0%        20%            50%         100%
             % of Population

Top 20% owns 80% of the total!
```

---

## 📖 Real-Life Examples

### Example 1: Wealth Distribution

Global wealth follows approximately Pareto(x_min, α ≈ 1.5):

```
x_min = $10,000 (minimum wealth for inclusion)
α = 1.5

Mean wealth = 1.5 × 10,000 / (1.5 - 1) = $30,000

P(wealth > $1,000,000) = (10,000/1,000,000)^1.5
                        = (0.01)^1.5
                        = 0.001 = 0.1%

About 0.1% are millionaires!
```

### Example 2: City Populations

City populations often follow Pareto with α ≈ 1.1:

```
If x_min = 100,000 (minimum city size):

P(city > 1,000,000) = (100,000/1,000,000)^1.1 = 0.079 ≈ 8%

About 8% of cities have over 1 million people.
```

### Example 3: Income Distribution

Annual incomes in many countries:

```
x_min = ৳200,000 (minimum taxable income)
α = 2.0

Mean income = 2 × 200,000 / (2-1) = ৳400,000

Median income = 200,000 × 2^(1/2) = ৳282,843

Top 10% threshold: x_0.90 = 200,000 / (0.10)^0.5 = ৳632,456

People earning above ৳632,456 are in the top 10%!
```

### Example 4: Website Traffic

Daily visitors to websites:

```
x_min = 100 visitors (threshold for "active" site)
α = 2.0

P(visitors > 1,000,000) = (100/1,000,000)^2 = 10^-8

Only 1 in 100 million sites get over 1M daily visitors!

But this is still MUCH more likely than normal distribution would predict.
```

### Example 5: Insurance Claims

Claim sizes often follow Pareto:

```
x_min = $1,000 (deductible)
α = 2.5

Mean claim = 2.5 × 1,000 / (2.5 - 1) = $1,667

P(claim > $10,000) = (1,000/10,000)^2.5 = 0.00316 = 0.316%

About 0.3% of claims exceed $10,000.
```

---

## Pareto Distribution in Different Fields

| Field | Application | Typical α |
|-------|-------------|-----------|
| **Economics** | Wealth, income | 1.5 - 2.5 |
| **Finance** | Stock returns, losses | 2 - 4 |
| **Insurance** | Claim sizes | 2 - 3 |
| **Business** | Company sizes, sales | 1 - 2 |
| **Technology** | File sizes, traffic | 1.5 - 2.5 |
| **Demography** | City populations | 1 - 1.5 |
| **Linguistics** | Word frequencies | 1 - 1.5 |
| **Biology** | Species abundance | 1.5 - 2.5 |
| **Geology** | Earthquake energy | 1.5 - 2 |

---

## Types of Pareto Distributions

### Type I (Classical Pareto)

The standard form we've been discussing:

```
P(X > x) = (x_min/x)^α    for x ≥ x_min
```

### Type II (Lomax Distribution)

Shifted to start at 0:

```
P(X > x) = (1 + x/σ)^(-α)    for x ≥ 0

Where σ is a scale parameter
```

### Type III

```
F(x) = 1 - exp(-((x-μ)/σ)^(1/α))
```

### Type IV (Generalized Pareto)

Used in Extreme Value Theory:

```
P(X > x) = (1 + ξ(x-μ)/σ)^(-1/ξ)
```

### Bounded Pareto

Limited to range [L, H]:

```
f(x) = (α × L^α × x^(-α-1)) / (1 - (L/H)^α)    for L ≤ x ≤ H
```

---

## Pareto vs Other Distributions

### Comparison with Common Distributions

| Property | Normal | Exponential | Pareto |
|----------|--------|-------------|--------|
| **Support** | (-∞, +∞) | [0, +∞) | [x_min, +∞) |
| **Tail** | Light | Medium | **Heavy** |
| **Mean** | Always finite | Always finite | May be infinite |
| **Variance** | Always finite | Always finite | May be infinite |
| **Extreme events** | Very rare | Rare | **Not so rare!** |
| **Log-log plot** | Curved | Curved | **Straight line** |

### Visual Comparison: Tail Behavior

```
P(X > x)  [log scale]

    │●○□
    │ ●○□
    │  ●○□
    │   ●○□□
    │    ● ○ □□□
    │     ●  ○  □□□□□
    │      ●   ○    □□□□□□□□
    │       ●●●●○○○○○
    └─────────────────────────── x [log scale]
    
    ● Pareto (straight line — heavy tail)
    ○ Exponential (curved)
    □ Normal (very curved — dies fast)
```

### Key Difference from Log-Normal

| Aspect | Log-Normal | Pareto |
|--------|------------|--------|
| **Origin** | Multiplicative CLT | Power law mechanism |
| **All moments** | Finite | May be infinite |
| **Log-log plot** | Eventually curves | Straight line |
| **Extreme tail** | Less extreme | More extreme |

---

## Mathematical Properties

### Moments

The n-th moment (when it exists):

```
E[X^n] = α × x_min^n / (α - n)    for α > n
```

### Moment Generating Function

The MGF does **not exist** for Pareto (due to heavy tail).

### Characteristic Function

```
φ(t) = α × (-it × x_min)^α × Γ(-α, -it × x_min)
```

Where Γ is the incomplete gamma function.

### Entropy

```
H(X) = ln(x_min/α) + 1/α + 1
```

### Lorenz Curve

The Lorenz curve for Pareto is:

```
L(p) = 1 - (1-p)^(1 - 1/α)
```

### Gini Coefficient

```
G = 1 / (2α - 1)    for α > 1/2
```

**Examples:**
- α = 1.16: G = 0.76 (high inequality)
- α = 2: G = 0.33 (moderate inequality)
- α = 3: G = 0.20 (lower inequality)

---

## Generating Pareto Random Variables

### Method 1: Inverse Transform

If U ~ Uniform(0, 1):

```
X = x_min / U^(1/α) ~ Pareto(x_min, α)

Or equivalently:
X = x_min × (1 - U)^(-1/α)
```

### Method 2: From Exponential

If E ~ Exponential(α):

```
X = x_min × e^E ~ Pareto(x_min, α)
```

---

## Estimating Parameters from Data

### Maximum Likelihood Estimation (MLE)

Given data x₁, x₂, ..., xₙ (all ≥ x_min):

```
x̂_min = min(x₁, x₂, ..., xₙ)

α̂ = n / Σᵢ ln(xᵢ / x̂_min)
```

### Method of Moments

```
α̂ = (2 × s² × x̄) / (s² + (x̄ - x_min)²)

Where x̄ = sample mean, s² = sample variance
```

### Hill Estimator (For Tail)

Using only the k largest observations:

```
α̂_Hill = k / Σᵢ₌₁ᵏ ln(x_(n-i+1) / x_(n-k))
```

---

## Python Implementation

### Using SciPy

```python
import numpy as np
from scipy import stats

# Pareto distribution
# SciPy parameterization: pareto(b) has PDF = b/x^(b+1) for x >= 1
# To get Pareto(x_min, α): use pareto(b=α, scale=x_min)

alpha = 2.5
x_min = 100

pareto = stats.pareto(b=alpha, scale=x_min)

# PDF at x = 200
print(f"f(200) = {pareto.pdf(200):.6f}")

# CDF: P(X ≤ 200)
print(f"P(X ≤ 200) = {pareto.cdf(200):.4f}")

# Survival: P(X > 200)
print(f"P(X > 200) = {1 - pareto.cdf(200):.4f}")

# Alternative: P(X > 200) = (x_min/200)^α
print(f"P(X > 200) direct = {(x_min/200)**alpha:.4f}")

# Mean
print(f"Mean = {pareto.mean():.2f}")  # α*x_min/(α-1)
expected_mean = alpha * x_min / (alpha - 1)
print(f"Expected mean = {expected_mean:.2f}")

# Median
print(f"Median = {pareto.median():.2f}")
expected_median = x_min * (2 ** (1/alpha))
print(f"Expected median = {expected_median:.2f}")

# Percentiles
print(f"90th percentile = {pareto.ppf(0.90):.2f}")
print(f"99th percentile = {pareto.ppf(0.99):.2f}")

# Generate samples
samples = pareto.rvs(size=10000)
print(f"\nSample statistics:")
print(f"Sample mean = {samples.mean():.2f}")
print(f"Sample median = {np.median(samples):.2f}")
print(f"Sample max = {samples.max():.2f}")
```

### Manual Implementation

```python
import numpy as np

class ParetoDistribution:
    def __init__(self, x_min, alpha):
        self.x_min = x_min
        self.alpha = alpha
    
    def pdf(self, x):
        """Probability density function"""
        if np.isscalar(x):
            if x < self.x_min:
                return 0
            return (self.alpha * self.x_min**self.alpha) / (x**(self.alpha + 1))
        else:
            result = np.zeros_like(x, dtype=float)
            mask = x >= self.x_min
            result[mask] = (self.alpha * self.x_min**self.alpha) / (x[mask]**(self.alpha + 1))
            return result
    
    def cdf(self, x):
        """Cumulative distribution function"""
        if np.isscalar(x):
            if x < self.x_min:
                return 0
            return 1 - (self.x_min / x)**self.alpha
        else:
            result = np.zeros_like(x, dtype=float)
            mask = x >= self.x_min
            result[mask] = 1 - (self.x_min / x[mask])**self.alpha
            return result
    
    def survival(self, x):
        """Survival function P(X > x)"""
        return 1 - self.cdf(x)
    
    def quantile(self, p):
        """Quantile function (inverse CDF)"""
        return self.x_min / ((1 - p)**(1/self.alpha))
    
    def mean(self):
        """Expected value"""
        if self.alpha <= 1:
            return np.inf
        return self.alpha * self.x_min / (self.alpha - 1)
    
    def variance(self):
        """Variance"""
        if self.alpha <= 2:
            return np.inf
        return (self.x_min**2 * self.alpha) / ((self.alpha - 1)**2 * (self.alpha - 2))
    
    def median(self):
        """Median"""
        return self.x_min * (2**(1/self.alpha))
    
    def rvs(self, size=1):
        """Generate random samples"""
        u = np.random.uniform(0, 1, size)
        return self.x_min / (u**(1/self.alpha))
    
    def gini(self):
        """Gini coefficient"""
        if self.alpha <= 0.5:
            return np.inf
        return 1 / (2 * self.alpha - 1)


# Example usage
pareto = ParetoDistribution(x_min=100, alpha=2.5)

print(f"Mean: {pareto.mean():.2f}")
print(f"Median: {pareto.median():.2f}")
print(f"Variance: {pareto.variance():.2f}")
print(f"Gini coefficient: {pareto.gini():.4f}")
print(f"P(X > 500): {pareto.survival(500):.4f}")
print(f"95th percentile: {pareto.quantile(0.95):.2f}")

# Generate and analyze samples
samples = pareto.rvs(10000)
print(f"\nSample mean: {samples.mean():.2f}")
print(f"Sample median: {np.median(samples):.2f}")
```

### Parameter Estimation

```python
import numpy as np

def estimate_pareto_mle(data, x_min=None):
    """
    Estimate Pareto parameters using MLE
    """
    data = np.array(data)
    
    if x_min is None:
        x_min = data.min()
    
    # Filter data >= x_min
    valid_data = data[data >= x_min]
    n = len(valid_data)
    
    # MLE estimate for alpha
    alpha = n / np.sum(np.log(valid_data / x_min))
    
    return x_min, alpha

# Example
np.random.seed(42)
true_alpha = 2.5
true_x_min = 100

# Generate samples
samples = true_x_min / np.random.uniform(0, 1, 1000)**(1/true_alpha)

# Estimate parameters
est_x_min, est_alpha = estimate_pareto_mle(samples)
print(f"True: x_min={true_x_min}, α={true_alpha}")
print(f"Estimated: x_min={est_x_min:.2f}, α={est_alpha:.4f}")
```

### Visualization

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats

fig, axes = plt.subplots(2, 2, figsize=(14, 10))

alpha = 2.5
x_min = 100

# Plot 1: PDF
ax1 = axes[0, 0]
x = np.linspace(100, 500, 1000)
pareto = stats.pareto(b=alpha, scale=x_min)
ax1.plot(x, pareto.pdf(x), 'b-', linewidth=2)
ax1.fill_between(x, pareto.pdf(x), alpha=0.3)
ax1.axvline(x_min, color='red', linestyle='--', label=f'x_min = {x_min}')
ax1.set_xlabel('x')
ax1.set_ylabel('f(x)')
ax1.set_title(f'Pareto PDF (α={alpha}, x_min={x_min})')
ax1.legend()

# Plot 2: Log-Log PDF
ax2 = axes[0, 1]
x = np.logspace(2, 4, 1000)
ax2.loglog(x, pareto.pdf(x), 'b-', linewidth=2)
ax2.set_xlabel('x (log scale)')
ax2.set_ylabel('f(x) (log scale)')
ax2.set_title('Log-Log Plot (Should be straight line)')
ax2.grid(True, alpha=0.3)

# Plot 3: CCDF (Survival)
ax3 = axes[1, 0]
x = np.logspace(2, 5, 1000)
ax3.loglog(x, 1 - pareto.cdf(x), 'b-', linewidth=2)
ax3.set_xlabel('x (log scale)')
ax3.set_ylabel('P(X > x) (log scale)')
ax3.set_title('Complementary CDF (Log-Log)')
ax3.grid(True, alpha=0.3)

# Plot 4: Effect of α
ax4 = axes[1, 1]
x = np.linspace(100, 400, 1000)
for a in [1.5, 2.0, 2.5, 3.0, 4.0]:
    pareto_a = stats.pareto(b=a, scale=100)
    ax4.plot(x, pareto_a.pdf(x), label=f'α = {a}')
ax4.set_xlabel('x')
ax4.set_ylabel('f(x)')
ax4.set_title('Effect of α on PDF shape')
ax4.legend()

plt.tight_layout()
plt.show()
```

---

## Testing for Pareto Distribution

### Method 1: Log-Log Plot

```python
import numpy as np
import matplotlib.pyplot as plt

# Sort data and compute empirical CCDF
sorted_data = np.sort(data)[::-1]
n = len(data)
ranks = np.arange(1, n + 1)
ccdf = ranks / n

# Plot log-log
plt.loglog(sorted_data, ccdf, 'bo', markersize=3)
plt.xlabel('x')
plt.ylabel('P(X > x)')
plt.title('Log-Log Plot: Check for straight line')
plt.show()

# If straight line → Pareto
# Slope gives -(α-1)
```

### Method 2: Mean Excess Function

For Pareto, the Mean Excess Function is **linear**:

```python
def mean_excess_function(data, thresholds):
    """Compute mean excess over thresholds"""
    me = []
    for u in thresholds:
        excesses = data[data > u] - u
        if len(excesses) > 0:
            me.append(excesses.mean())
        else:
            me.append(np.nan)
    return np.array(me)

thresholds = np.linspace(data.min(), np.percentile(data, 95), 50)
me = mean_excess_function(data, thresholds)

plt.plot(thresholds, me, 'bo-')
plt.xlabel('Threshold u')
plt.ylabel('E[X - u | X > u]')
plt.title('Mean Excess Function (Linear → Pareto)')
plt.show()
```

### Method 3: Kolmogorov-Smirnov Test

```python
from scipy import stats

# Fit Pareto
alpha_fit, loc_fit, scale_fit = stats.pareto.fit(data, floc=0)

# KS test
ks_stat, p_value = stats.kstest(data, 'pareto', args=(alpha_fit, loc_fit, scale_fit))
print(f"KS statistic: {ks_stat:.4f}")
print(f"p-value: {p_value:.4f}")

if p_value > 0.05:
    print("Data is consistent with Pareto distribution")
else:
    print("Data may not follow Pareto distribution")
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Ignoring x_min

❌ **Wrong:** "This data follows Pareto with α = 2"

✅ **Correct:** "This data follows Pareto(x_min = 100, α = 2)"
Both parameters are needed!

---

### Mistake 2: Expecting Finite Mean for All α

❌ **Wrong:** "The mean is αx_min/(α-1)" (without checking α)

✅ **Correct:** Mean only exists if **α > 1**! If α ≤ 1, mean is infinite.

---

### Mistake 3: Using OLS on Log-Log

❌ **Wrong:** Linear regression on log-transformed data

✅ **Correct:** Use Maximum Likelihood Estimation (MLE)
OLS gives biased α estimates for heavy-tailed data

---

### Mistake 4: Confusing α Parameterization

Different sources use different conventions!

```
Some use: f(x) = α × x_min^α / x^(α+1)   [our convention]
Others:   f(x) = α × x_min^α / x^(α)     [shifted by 1]
SciPy:    pareto(b) means α = b

Always check which convention is being used!
```

---

### Mistake 5: Applying Pareto to Bounded Data

❌ **Wrong:** Fitting Pareto to data with a known maximum

✅ **Correct:** Use Bounded Pareto or Truncated Pareto if data has upper limit

---

## Practice Problems 📝

### Problem 1: Basic Probability
For X ~ Pareto(x_min = 50, α = 2), find P(X > 100).

<details>
<summary>Click for Answer</summary>

```
P(X > x) = (x_min/x)^α

P(X > 100) = (50/100)^2
           = (0.5)^2
           = 0.25 = 25%
```

</details>

---

### Problem 2: Mean and Median
For X ~ Pareto(x_min = 1000, α = 3), find the mean and median.

<details>
<summary>Click for Answer</summary>

```
Mean = α × x_min / (α - 1)
     = 3 × 1000 / (3 - 1)
     = 3000 / 2
     = 1500

Median = x_min × 2^(1/α)
       = 1000 × 2^(1/3)
       = 1000 × 1.26
       = 1260

Note: Mean (1500) > Median (1260) > Mode (1000)
This confirms right skewness!
```

</details>

---

### Problem 3: Finding a Percentile
For X ~ Pareto(x_min = 200, α = 1.5), find the 95th percentile.

<details>
<summary>Click for Answer</summary>

```
x_p = x_min / (1 - p)^(1/α)

x_0.95 = 200 / (1 - 0.95)^(1/1.5)
       = 200 / (0.05)^(0.667)
       = 200 / 0.136
       ≈ 1,470

The top 5% have values above 1,470!
```

</details>

---

### Problem 4: Inequality Measurement
For X ~ Pareto(x_min = 100, α = 1.5), what fraction of total is owned by the top 10%?

<details>
<summary>Click for Answer</summary>

```
Fraction owned by top (1-p) = p^(1 - 1/α)

For top 10% (1-p = 0.10, so p = 0.90):
Fraction = 0.90^(1 - 1/1.5)
         = 0.90^(1 - 0.667)
         = 0.90^0.333
         ≈ 0.965

The top 10% owns about 96.5% of the total!
(This is extreme inequality with α = 1.5)
```

</details>

---

### Problem 5: Parameter Estimation
Data sample has minimum = 50, mean = 80. Estimate α.

<details>
<summary>Click for Answer</summary>

```
Mean = α × x_min / (α - 1)
80 = α × 50 / (α - 1)
80(α - 1) = 50α
80α - 80 = 50α
30α = 80
α = 80/30 = 2.67

Verify: Mean = 2.67 × 50 / (2.67 - 1) = 133.5/1.67 = 80 ✓
```

</details>

---

## Applications Summary

| Field | Application | Why Pareto? |
|-------|-------------|-------------|
| **Wealth Economics** | Income/wealth distribution | "Rich get richer" dynamics |
| **Insurance** | Modeling large claims | Heavy tail for extreme losses |
| **Finance** | Risk management (VaR) | Fat tails in returns |
| **Business** | Customer value (CLV) | Few customers = most revenue |
| **Technology** | File sizes, traffic | Few large files, many small |
| **Quality** | Defect analysis | Few causes = most defects |
| **Urban Planning** | City sizes | Few mega-cities, many towns |
| **Science** | Citations, impact | Few papers highly cited |

---

## Summary: The Essence of Pareto

```
┌─────────────────────────────────────────────────────────────────┐
│                      PARETO DISTRIBUTION                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   "The mathematics of inequality — the few have most"            │
│                                                                  │
│   FORMULAS:                                                      │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  PDF: f(x) = α × x_min^α / x^(α+1)   for x ≥ x_min      │   │
│   │  CDF: F(x) = 1 - (x_min/x)^α                            │   │
│   │  Survival: P(X > x) = (x_min/x)^α                       │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   KEY PROPERTIES:                                                │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  • Mean = αx_min/(α-1)     [exists if α > 1]            │   │
│   │  • Median = x_min × 2^(1/α)                              │   │
│   │  • Mode = x_min (always at minimum!)                     │   │
│   │  • Mode < Median < Mean (right-skewed)                  │   │
│   │  • Heavy tail: Extreme values not rare!                  │   │
│   │  • Straight line on log-log plot                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THE 80/20 RULE:                                                │
│   α ≈ 1.16 gives "80% of total owned by 20%"                    │
│                                                                  │
│   GINI COEFFICIENT: G = 1/(2α - 1)                               │
│   Smaller α → More inequality                                    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Pareto Matters

> **"The Pareto distribution quantifies what we see everywhere: extreme inequality is not an anomaly — it's a mathematical certainty in many systems."**

Understanding Pareto helps you:

| Insight | Application |
|---------|-------------|
| **Expect concentration** | 80/20 rule in business, quality |
| **Model extreme events** | Insurance, risk management |
| **Understand inequality** | Wealth, income, influence |
| **Plan for heavy tails** | Don't rely only on averages |
| **Identify Pareto phenomena** | Customer value, defects, traffic |

From wealth to websites, claims to cities — when a few dominate and many are small, Pareto explains why! 💰

---

*The mathematics of "the vital few and trivial many" — that's the power of Pareto!* ✨
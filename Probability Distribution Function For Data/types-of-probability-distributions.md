# Types of Probability Distributions
## A Complete Guide Through Real-Life Stories 🎲📊

---

## The Big Picture

Imagine you're trying to predict random events in life. Different situations follow different **patterns**. These patterns are called **probability distributions**.

```
                    PROBABILITY DISTRIBUTIONS
                            │
            ┌───────────────┴───────────────┐
            │                               │
      ┌─────┴─────┐                   ┌─────┴─────┐
      │ DISCRETE  │                   │ CONTINUOUS│
      │ (Countable)│                   │(Measurable)│
      └─────┬─────┘                   └─────┬─────┘
            │                               │
    ┌───┬───┼───┬───┬───┐         ┌───┬───┼───┬───┬───┐
    │   │   │   │   │   │         │   │   │   │   │   │
   Ber Bin Poi Geo NB  Hyp      Uni Nor Exp Gam Bet  t
```

---

## Quick Reference: When to Use What?

| Distribution | Use When... | Real Example |
|--------------|-------------|--------------|
| **Bernoulli** | Single yes/no trial | One coin flip |
| **Binomial** | Fixed trials, counting successes | 10 free throws, how many score? |
| **Poisson** | Counting events in time/space | Customers per hour |
| **Geometric** | Trials until first success | Attempts until first sale |
| **Negative Binomial** | Trials until k successes | Games until 3rd win |
| **Hypergeometric** | Sampling without replacement | Cards drawn from deck |
| **Uniform** | Equal chance in a range | Random number generator |
| **Normal** | Natural phenomena, averages | Heights, test scores |
| **Exponential** | Time between events | Time until next call |
| **Gamma** | Time until k events | Time for 5 customers |
| **Beta** | Probabilities/proportions | Success rates |
| **Chi-squared** | Variance testing | Goodness of fit tests |
| **Student's t** | Small sample means | Testing with n < 30 |

---

# 🎯 PART 1: DISCRETE DISTRIBUTIONS
## *For things you can COUNT*

---

# 1. Bernoulli Distribution
## *The Single Coin Flip*

---

## 📖 Story: The Job Interview

Fatima has a job interview tomorrow. Based on her preparation, she estimates:
- **70% chance** of getting the job (Success)
- **30% chance** of not getting it (Failure)

This is the simplest distribution — **one trial, two outcomes**.

### The Bernoulli Distribution

| Outcome | X | Probability |
|---------|---|-------------|
| Failure | 0 | 1 - p = 0.30 |
| Success | 1 | p = 0.70 |

### Key Properties

```
Parameter: p (probability of success)

Mean:     μ = p
Variance: σ² = p(1-p)

For Fatima:
Mean = 0.70 (expected value)
Variance = 0.70 × 0.30 = 0.21
```

### Visualization

```
P(X)
 │
0.7├──────────────────────●
 │                        │
0.3├────────●             │
 │         │              │
 0─────────┴──────────────┴────
           0              1
        Failure        Success
```

### Real-Life Bernoulli Examples

- Will it rain today? (Yes/No)
- Does a machine produce a defective item? (Yes/No)
- Does a patient respond to treatment? (Yes/No)
- Does a customer buy? (Yes/No)

---

# 2. Binomial Distribution
## *Counting Successes in Fixed Trials*

---

## 📖 Story: The Basketball Free Throws

Karim is a basketball player with a **60% free throw success rate**. He takes **10 free throws** in practice.

Question: *What's the probability he makes exactly 7 shots?*

### The Binomial Distribution

When you repeat a Bernoulli trial **n times** and count successes:

```
Parameters:
- n = number of trials (10 shots)
- p = probability of success (0.60)

X = number of successes (0, 1, 2, ..., n)
```

### The Formula

```
P(X = k) = C(n,k) × p^k × (1-p)^(n-k)

Where C(n,k) = n! / (k!(n-k)!)  ← "n choose k"
```

### Solving Karim's Question

```
P(X = 7) = C(10,7) × (0.60)^7 × (0.40)^3
P(X = 7) = 120 × 0.0280 × 0.064
P(X = 7) ≈ 0.215 or 21.5%
```

### Visualization

```
P(X)
 │
 │           ●
0.2├        ● ●
 │        ●     ●
0.1├      ●       ●
 │      ●           ●
 │    ●               ●
 0──●───────────────────●──
    0 1 2 3 4 5 6 7 8 9 10
         Number of successful shots
         
Peak is around np = 10 × 0.6 = 6
```

### Key Properties

```
Mean:     μ = np = 10 × 0.60 = 6 shots
Variance: σ² = np(1-p) = 10 × 0.60 × 0.40 = 2.4
Std Dev:  σ = √2.4 ≈ 1.55 shots
```

### Real-Life Binomial Examples

| Scenario | n | p | X counts... |
|----------|---|---|-------------|
| 20 coin flips | 20 | 0.5 | Heads |
| 100 emails, spam check | 100 | 0.3 | Spam emails |
| 15 patients given drug | 15 | 0.8 | Patients cured |
| 50 products inspected | 50 | 0.02 | Defective items |

---

# 3. Poisson Distribution
## *Counting Events in Time or Space*

---

## 📖 Story: The Call Center

Rashida manages a call center. On average, they receive **4 calls per minute**.

Question: *What's the probability of receiving exactly 6 calls in one minute?*

### The Poisson Distribution

Used when counting **how many times** something happens in a **fixed interval** (time, area, volume).

```
Parameter: λ (lambda) = average rate of events

λ = 4 calls per minute
```

### The Formula

```
P(X = k) = (λ^k × e^(-λ)) / k!

Where e ≈ 2.71828
```

### Solving Rashida's Question

```
P(X = 6) = (4^6 × e^(-4)) / 6!
P(X = 6) = (4096 × 0.0183) / 720
P(X = 6) ≈ 0.104 or 10.4%
```

### Visualization

```
P(X)
 │
 │      ●
0.2├    ● ●
 │    ●   ●
0.1├  ●     ●
 │  ●       ●
 │●           ●
 0──────────────●──●──●──
   0 1 2 3 4 5 6 7 8 9 10
        Number of calls
        
Peak is around λ = 4
```

### Key Properties

```
Mean:     μ = λ = 4
Variance: σ² = λ = 4

Special: Mean = Variance in Poisson!
```

### When to Use Poisson vs Binomial?

| Use Poisson When... | Use Binomial When... |
|---------------------|---------------------|
| Counting events in continuous time/space | Counting successes in fixed trials |
| n is very large, p is very small | n is fixed and known |
| Events occur independently at constant rate | Each trial is independent |
| λ = np is moderate | You know exact n and p |

### Real-Life Poisson Examples

| Scenario | λ (average rate) |
|----------|------------------|
| Typos per page | 2 typos/page |
| Car accidents per day | 5 accidents/day |
| Meteors per hour | 3 meteors/hour |
| Server requests per second | 100 requests/second |
| Earthquakes per year | 12 earthquakes/year |

---

# 4. Geometric Distribution
## *Waiting for the First Success*

---

## 📖 Story: The Sales Call

Imran is a salesperson. He knows that **20% of his calls result in a sale**.

Question: *What's the probability his FIRST sale happens on the 4th call?*

### The Geometric Distribution

Counts **how many trials until the first success**.

```
Parameter: p = probability of success per trial

p = 0.20 (20% chance of sale)
```

### The Formula

```
P(X = k) = (1-p)^(k-1) × p

"Fail (k-1) times, then succeed"
```

### Solving Imran's Question

```
P(X = 4) = (0.80)^3 × (0.20)
P(X = 4) = 0.512 × 0.20
P(X = 4) = 0.1024 or 10.24%
```

### Visualization

```
P(X)
 │
0.2├●
 │  ╲
0.15├ ●
 │   ╲
0.1├   ●
 │     ╲●
0.05├     ╲●
 │         ╲●──●──●──●
 0────────────────────────
    1  2  3  4  5  6  7  8
       Trial of first success
       
Always decreasing (memoryless property)
```

### Key Properties

```
Mean:     μ = 1/p = 1/0.20 = 5 calls
Variance: σ² = (1-p)/p² = 0.80/0.04 = 20

Imran expects his first sale on the 5th call on average.
```

### The Memoryless Property

Amazing fact: The geometric distribution "forgets" the past!

If Imran has already made 10 calls with no sale, the probability of success on the next call is **still 20%** — not higher!

### Real-Life Geometric Examples

| Scenario | p | Counting... |
|----------|---|-------------|
| Flipping until heads | 0.5 | Flips until first heads |
| Rolling until 6 | 1/6 | Rolls until first 6 |
| Interviews until hired | 0.15 | Interviews until first offer |
| Attempts until login success | 0.9 | Tries until correct password |

---

# 5. Negative Binomial Distribution
## *Waiting for the k-th Success*

---

## 📖 Story: The Cricket Match

Sabbir is watching cricket. His favorite team wins **40% of matches**.

Question: *What's the probability they achieve their 3rd win on the 7th match?*

### The Negative Binomial Distribution

Counts **trials until you get k successes** (generalization of geometric).

```
Parameters:
- k = number of successes needed (3 wins)
- p = probability of success (0.40)
```

### The Logic

For the 3rd win to happen on the 7th match:
- Matches 1-6 must have exactly 2 wins (and 4 losses)
- Match 7 must be a win

### The Formula

```
P(X = n) = C(n-1, k-1) × p^k × (1-p)^(n-k)
```

### Solving Sabbir's Question

```
P(X = 7) = C(6,2) × (0.40)^3 × (0.60)^4
P(X = 7) = 15 × 0.064 × 0.1296
P(X = 7) ≈ 0.124 or 12.4%
```

### Key Properties

```
Mean:     μ = k/p = 3/0.40 = 7.5 matches
Variance: σ² = k(1-p)/p² = 3(0.60)/(0.16) = 11.25

On average, it takes 7.5 matches to see 3 wins.
```

### Real-Life Examples

| Scenario | k | p |
|----------|---|---|
| Wait for 5th customer | 5 | 0.3/min |
| Games until 10th win | 10 | 0.55 |
| Trials until 3rd success | 3 | 0.25 |

---

# 6. Hypergeometric Distribution
## *Sampling Without Replacement*

---

## 📖 Story: The Quality Inspector

A factory has a batch of **100 phones**, and **10 are defective**. An inspector randomly selects **15 phones** (without replacement).

Question: *What's the probability exactly 2 are defective?*

### Why Not Binomial?

In binomial, each trial is **independent** (with replacement).
Here, once you pick a phone, **probabilities change**!

### The Hypergeometric Distribution

```
Parameters:
- N = population size (100 phones)
- K = successes in population (10 defective)
- n = sample size (15 selected)

X = defective phones in sample
```

### The Formula

```
P(X = k) = [C(K,k) × C(N-K, n-k)] / C(N,n)

"Ways to choose k defective × Ways to choose (n-k) good"
─────────────────────────────────────────────────────────
              "Total ways to choose n items"
```

### Solving the Inspector's Question

```
P(X = 2) = [C(10,2) × C(90,13)] / C(100,15)

C(10,2) = 45
C(90,13) = [large number]
C(100,15) = [large number]

P(X = 2) ≈ 0.276 or 27.6%
```

### Key Properties

```
Mean:     μ = n × (K/N) = 15 × (10/100) = 1.5 defective
Variance: σ² = n × (K/N) × (1-K/N) × (N-n)/(N-1)
```

### Binomial vs Hypergeometric

| Aspect | Binomial | Hypergeometric |
|--------|----------|----------------|
| Sampling | With replacement | Without replacement |
| Probability | Stays constant | Changes after each draw |
| Independence | Trials independent | Trials dependent |
| Population | Infinite or very large | Finite |

### Real-Life Examples

| Scenario | N | K | n |
|----------|---|---|---|
| Cards: Drawing hearts | 52 | 13 | 5 |
| Lottery numbers | 49 | 6 | 6 |
| Survey sampling | 1000 | 400 | 50 |
| Committee selection | 20 | 8 women | 5 |

---

# 📈 PART 2: CONTINUOUS DISTRIBUTIONS
## *For things you MEASURE*

---

# 7. Uniform Distribution
## *Equal Chance for Everything*

---

## 📖 Story: The Random Bus

A bus arrives randomly between **2:00 PM and 2:30 PM**. Every moment in this 30-minute window is equally likely.

Question: *What's the probability the bus arrives between 2:10 and 2:20?*

### The Uniform Distribution

```
Parameters:
- a = minimum value (0 minutes)
- b = maximum value (30 minutes)

All values between a and b are equally likely.
```

### Visualization

```
Density
   │
1/30├────┬─────────────────────────┬────
   │    │█████████████████████████│
   │    │█████████████████████████│
   │    │█████████████████████████│
   0────┴─────────────────────────┴────
        0      10      20      30
              Minutes after 2:00
              
Height = 1/(b-a) = 1/30
```

### The Formula

```
PDF:  f(x) = 1/(b-a)  for a ≤ x ≤ b
             0        otherwise

P(c < X < d) = (d-c)/(b-a)
```

### Solving the Bus Question

```
P(10 < X < 20) = (20-10)/(30-0)
P(10 < X < 20) = 10/30 = 1/3 ≈ 33.3%
```

### Key Properties

```
Mean:     μ = (a+b)/2 = (0+30)/2 = 15 minutes
Variance: σ² = (b-a)²/12 = 900/12 = 75
Std Dev:  σ = √75 ≈ 8.66 minutes
```

### Real-Life Examples

- Random number generators
- Arrival times in a window
- Rounding errors
- Random angle (0 to 360°)

---

# 8. Normal (Gaussian) Distribution
## *The Bell Curve — The Most Important Distribution!*

---

## 📖 Story: The National Exam

Bangladesh's SSC exam scores follow a normal distribution with:
- **Mean (μ) = 65%**
- **Standard Deviation (σ) = 12%**

Question: *What percentage of students score between 53% and 77%?*

### Why Normal is So Important

The **Central Limit Theorem** says: When you add up many independent random variables, the result tends to be normal — regardless of the original distributions!

This is why heights, weights, test scores, measurement errors, and countless natural phenomena follow the normal distribution.

### Visualization: The Bell Curve

```
                        │
                       ╭┴╮
                      ╭╯ ╰╮
                     ╭╯   ╰╮
                    ╭╯     ╰╮
                   ╭╯       ╰╮
                  ╭╯         ╰╮
                 ╭╯           ╰╮
              ╭──╯             ╰──╮
         ╭────╯                   ╰────╮
    ─────╯                             ╰─────
    
    ├──────┼──────┼──────┼──────┼──────┼──────┤
   μ-3σ  μ-2σ  μ-1σ    μ    μ+1σ  μ+2σ  μ+3σ
    29    41    53    65    77    89   101
```

### The 68-95-99.7 Rule (Empirical Rule)

```
┌────────────────────────────────────────────────────────┐
│                                                        │
│   68% of data falls within μ ± 1σ  (53% to 77%)       │
│   95% of data falls within μ ± 2σ  (41% to 89%)       │
│   99.7% of data falls within μ ± 3σ (29% to 101%)     │
│                                                        │
└────────────────────────────────────────────────────────┘
```

### Solving the Exam Question

Scores between 53% and 77% = μ ± 1σ

**Answer: About 68% of students!**

### The Z-Score (Standardization)

To use normal tables, convert to **standard normal** (μ=0, σ=1):

```
Z = (X - μ) / σ

Example: What Z-score is 89%?
Z = (89 - 65) / 12 = 24/12 = 2

A score of 89% is 2 standard deviations above the mean.
```

### Key Properties

```
Parameters: μ (mean), σ (standard deviation)

Mean:     μ (center of the curve)
Variance: σ²
Mode:     μ (peak is at the mean)
Median:   μ (symmetric distribution)

The curve is symmetric around μ.
```

### Real-Life Examples

| Phenomenon | μ | σ |
|------------|---|---|
| Adult male height (BD) | 165 cm | 7 cm |
| IQ scores | 100 | 15 |
| Manufacturing tolerance | 50 mm | 0.5 mm |
| Daily stock returns | 0.05% | 1.5% |

---

# 9. Exponential Distribution
## *Time Between Events*

---

## 📖 Story: The Emergency Room

An ER receives patients at an average rate of **3 per hour** (Poisson process).

Question: *What's the probability the next patient arrives within 30 minutes?*

### The Connection: Poisson ↔ Exponential

| Poisson | Exponential |
|---------|-------------|
| Counts events in time | Time between events |
| Discrete | Continuous |
| λ = events per unit time | Same λ parameter |

### Visualization

```
Density f(x)
   │
 λ ├●
   │╲
   │ ╲
   │  ╲
   │   ╲
   │    ╲
   │     ╲──
   │        ╲───
   │            ╲─────────────
   0──────────────────────────────
         Time until next event
         
Always decreasing — "memoryless"
```

### The Formula

```
Parameter: λ = rate (3 patients per hour)

PDF: f(x) = λ × e^(-λx)  for x ≥ 0

CDF: P(X ≤ t) = 1 - e^(-λt)
```

### Solving the ER Question

```
λ = 3 per hour
t = 0.5 hours (30 minutes)

P(X ≤ 0.5) = 1 - e^(-3 × 0.5)
P(X ≤ 0.5) = 1 - e^(-1.5)
P(X ≤ 0.5) = 1 - 0.223
P(X ≤ 0.5) ≈ 0.777 or 77.7%
```

### Key Properties

```
Mean:     μ = 1/λ = 1/3 hour = 20 minutes
Variance: σ² = 1/λ²

Average wait time = 20 minutes between patients.
```

### The Memoryless Property

Just like geometric distribution, exponential "forgets" the past!

If you've already waited 10 minutes, the expected additional wait is **still** 20 minutes — not 10 minutes!

### Real-Life Examples

| Scenario | λ | Mean (1/λ) |
|----------|---|------------|
| Time between calls | 5/hour | 12 minutes |
| Lifetime of a lightbulb | 0.001/hour | 1000 hours |
| Time between earthquakes | 0.08/year | 12.5 years |
| Time until component failure | 0.02/day | 50 days |

---

# 10. Gamma Distribution
## *Time Until k Events*

---

## 📖 Story: The Restaurant Kitchen

A busy restaurant gets orders at a rate of **6 per hour**. The chef wants to know:

*What's the average time until the 5th order arrives?*

### The Gamma Distribution

Generalization of exponential — waits for **k events** instead of 1.

```
Parameters:
- k (or α) = shape = number of events (5 orders)
- λ (or 1/β) = rate (6 per hour)
```

### Visualization

```
Density
   │
   │       ╭──╮
   │      ╭╯  ╰╮
   │     ╭╯    ╰╮
   │    ╭╯      ╰─╮
   │  ╭─╯         ╰──╮
   │╭─╯              ╰────────
   0────────────────────────────
           Time
           
Shape depends on k:
- k=1: Exponential (always decreasing)
- k>1: Rises then falls (has a peak)
```

### Key Properties

```
Mean:     μ = k/λ = 5/6 hour ≈ 50 minutes
Variance: σ² = k/λ²

On average, 50 minutes until 5 orders.
```

### Special Cases

| k value | Distribution |
|---------|--------------|
| k = 1 | Exponential |
| k = n/2, λ = 1/2 | Chi-squared (n degrees of freedom) |

### Real-Life Examples

- Time until nth customer
- Total rainfall over k days
- Aggregate insurance claims
- Time to complete k tasks

---

# 11. Beta Distribution
## *Modeling Probabilities*

---

## 📖 Story: The A/B Test

Nadia is running an A/B test for a website. After some data:
- Version A: 80 conversions, 20 non-conversions
- She wants to model **uncertainty about the true conversion rate**

### The Beta Distribution

Perfect for modeling **unknown probabilities** or **proportions**.

```
Parameters:
- α (alpha) = "pseudo-successes" + 1
- β (beta) = "pseudo-failures" + 1

Values are between 0 and 1 (like probabilities!)
```

### Visualization

```
Different shapes based on α and β:

α=1,β=1 (Uniform)      α=5,β=2              α=2,β=5
│                      │      ╭╮            │   ╭╮
│────────────          │     ╭╯╰╮           │  ╭╯╰╮
│                      │    ╭╯  ╰─          │╭─╯  ╰╮
│                      │  ╭─╯               ╰╯     ╰──
0────────1             0────────1           0────────1
 "No info"              "Skewed right"       "Skewed left"
```

### Key Properties

```
Mean:     μ = α/(α+β)
Variance: σ² = αβ/[(α+β)²(α+β+1)]

For Nadia: α=81, β=21
Mean = 81/102 ≈ 0.794 or 79.4% conversion rate
```

### Why Beta is Special

The Beta distribution is the **conjugate prior** for binomial likelihood in Bayesian statistics. This makes updating beliefs elegant:

```
Prior: Beta(α, β)
Data: k successes in n trials
Posterior: Beta(α+k, β+n-k)
```

### Real-Life Examples

- Conversion rates
- Batting averages
- Defect rates
- Election polling (proportion of votes)

---

# 12. Chi-Squared (χ²) Distribution
## *Testing Variance and Fit*

---

## 📖 Story: The Quality Control Test

A machine is supposed to produce bolts with diameter variance of **0.04 mm²**. The quality manager takes 25 samples and calculates the sample variance.

*Is the machine variance significantly different from specification?*

### The Chi-Squared Distribution

Arises when you sum squared standard normal variables:

```
If Z₁, Z₂, ..., Zₖ are standard normal,
then Z₁² + Z₂² + ... + Zₖ² ~ χ²(k)

Parameter: k = degrees of freedom
```

### Visualization

```
Density
   │
   │  ╭─╮
   │ ╭╯ ╰╮
   │╭╯   ╰─╮
   │╯      ╰──╮
   │          ╰────╮
   │               ╰──────────
   0──────────────────────────
          χ² value
          
Right-skewed, becomes more normal as k increases
```

### Key Properties

```
Mean:     μ = k
Variance: σ² = 2k

For k=25: Mean=25, Variance=50
```

### Common Uses

1. **Testing variance:** Is σ² equal to a specified value?
2. **Goodness of fit:** Does data follow expected distribution?
3. **Independence tests:** Are two categorical variables related?

---

# 13. Student's t-Distribution
## *Small Sample Inference*

---

## 📖 Story: The New Medicine

Dr. Rahman tests a new medicine on **12 patients** and measures improvement. With such a small sample, can he trust the results?

### The Problem with Small Samples

When n is small:
- Sample mean is variable
- Sample standard deviation is unreliable
- Normal distribution assumptions don't hold well

### The t-Distribution

Accounts for uncertainty in estimating σ from small samples.

```
Parameter: ν (nu) = degrees of freedom = n - 1

As ν → ∞, t-distribution → normal distribution
```

### Visualization: t vs Normal

```
         │
         │    ╭─ Normal ─╮
         │   ╱     │     ╲
         │  ╱      │      ╲
         │ ╱   ╱───┼───╲   ╲  ← t-distribution
         │╱  ╱     │     ╲  ╲    (heavier tails)
    ─────┴─────────┼───────────
                   0
                   
t-distribution has "fatter tails" (more probability in extremes)
```

### Key Properties

```
Mean:     μ = 0 (for ν > 1)
Variance: σ² = ν/(ν-2) for ν > 2

When ν=10: Variance = 10/8 = 1.25 (larger than normal's 1)
```

### When to Use t vs Normal

| Sample Size | Use |
|-------------|-----|
| n < 30 | t-distribution |
| n ≥ 30 | Normal (approximately) |

### Real-Life Uses

- Testing means with small samples
- Confidence intervals for mean
- Regression coefficients
- A/B tests with limited data

---

# 14. F-Distribution
## *Comparing Variances*

---

## 📖 Story: Two Factories

Two factories produce the same product. Management wants to know:

*Is the variance in quality the same at both factories?*

### The F-Distribution

Ratio of two chi-squared distributions:

```
F = (χ₁²/d₁) / (χ₂²/d₂)

Parameters:
- d₁ = numerator degrees of freedom
- d₂ = denominator degrees of freedom
```

### Key Properties

```
Mean:     μ = d₂/(d₂-2)  for d₂ > 2
```

### Visualization

```
Density
   │
   │╮
   │╰╮
   │ ╰╮
   │  ╰─╮
   │    ╰──╮
   │       ╰────╮
   │            ╰──────────────
   0──────────────────────────
          F value
          
Right-skewed, only positive values
```

### Common Uses

1. **ANOVA:** Comparing means across groups
2. **Variance comparison:** Are two variances equal?
3. **Regression:** Testing overall model significance

---

# Distribution Family Tree

```
                         ┌─────────────────┐
                         │    BERNOULLI    │
                         │   (Single trial)│
                         └────────┬────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    ↓             ↓             ↓
            ┌───────────┐  ┌───────────┐  ┌───────────┐
            │ BINOMIAL  │  │ GEOMETRIC │  │  POISSON  │
            │(n trials) │  │(1st success)│  │(rare events)
            └─────┬─────┘  └─────┬─────┘  └─────┬─────┘
                  │              │              │
                  ↓              ↓              ↓
            ┌───────────┐  ┌───────────┐  ┌───────────┐
            │  NORMAL   │  │ NEGATIVE  │  │EXPONENTIAL│
            │(n→∞, CLT) │  │ BINOMIAL  │  │(wait time)│
            └─────┬─────┘  │(k successes)│  └─────┬─────┘
                  │        └───────────┘        │
       ┌──────────┼──────────┐                  ↓
       ↓          ↓          ↓           ┌───────────┐
 ┌──────────┐ ┌──────┐ ┌──────────┐      │   GAMMA   │
 │CHI-SQUARE│ │  t   │ │ LOGNORMAL│      │(k waits)  │
 │  (Z²s)   │ │(small n)│          │      └───────────┘
 └────┬─────┘ └──────┘ └──────────┘
      │
      ↓
 ┌──────────┐
 │    F     │
 │(χ² ratio)│
 └──────────┘
```

---

# Quick Reference Summary

## Discrete Distributions

| Distribution | Parameters | Mean | Variance | Use Case |
|--------------|------------|------|----------|----------|
| Bernoulli | p | p | p(1-p) | Single yes/no |
| Binomial | n, p | np | np(1-p) | Successes in n trials |
| Poisson | λ | λ | λ | Events per interval |
| Geometric | p | 1/p | (1-p)/p² | Trials until first success |
| Neg. Binomial | k, p | k/p | k(1-p)/p² | Trials until k successes |
| Hypergeometric | N, K, n | nK/N | Complex | Sampling without replacement |

## Continuous Distributions

| Distribution | Parameters | Mean | Variance | Use Case |
|--------------|------------|------|----------|----------|
| Uniform | a, b | (a+b)/2 | (b-a)²/12 | Equal probability in range |
| Normal | μ, σ | μ | σ² | Natural phenomena |
| Exponential | λ | 1/λ | 1/λ² | Time between events |
| Gamma | k, λ | k/λ | k/λ² | Time until k events |
| Beta | α, β | α/(α+β) | Complex | Modeling probabilities |
| Chi-squared | k | k | 2k | Variance testing |
| t | ν | 0 | ν/(ν-2) | Small sample means |
| F | d₁, d₂ | d₂/(d₂-2) | Complex | Comparing variances |

---

# Decision Flowchart: Which Distribution?

```
START: What are you measuring?
         │
    ┌────┴────┐
    │         │
Countable?  Measurable?
    │         │
    ↓         ↓
DISCRETE   CONTINUOUS
    │         │
    │    ┌────┴────┬────────┬──────────┐
    │    │         │        │          │
    │  Time?   Proportion? Testing?  Natural?
    │    │         │        │          │
    │    ↓         ↓        ↓          ↓
    │  Expo/    Beta    Chi-sq/t/F  Normal
    │  Gamma
    │
    └────┬────────────────────────┐
         │                        │
    Fixed trials?          Events in interval?
         │                        │
         ↓                        ↓
      ┌──┴──┐                  POISSON
      │     │
 With repl? Without?
      │     │
      ↓     ↓
  BINOMIAL HYPERGEOMETRIC
```

---

## Final Wisdom 🌟

> **Every random phenomenon in nature follows some distribution.**
> 
> Your job is to recognize the pattern and choose the right tool!

Understanding distributions is the foundation of:
- Statistical inference
- Machine learning
- Quality control
- Risk analysis
- Scientific research

---

*Master these distributions, and you can model almost anything in the world! 🌍*
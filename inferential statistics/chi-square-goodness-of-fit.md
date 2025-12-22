# Chi-Square Goodness of Fit Test
## Does Your Data Fit the Expected Pattern? 🎯

---

## What is Goodness of Fit?

The Chi-Square Goodness of Fit test determines whether your observed data **fits** (matches) a specific expected distribution. It answers: "Does what I observed match what I expected?"

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CHI-SQUARE GOODNESS OF FIT TEST                            │
│                                                             │
│   Purpose:                                                  │
│   Test whether observed frequencies match expected          │
│   frequencies from a hypothesized distribution              │
│                                                             │
│   Question:                                                 │
│   "Does my data fit the expected pattern?"                 │
│                                                             │
│   Examples:                                                 │
│   • Is this die fair? (expect equal frequencies)           │
│   • Do births occur equally across weekdays?               │
│   • Does this follow a specific ratio (like 9:3:3:1)?     │
│   • Is the slot machine paying out as advertised?          │
│                                                             │
│   ONE categorical variable with k categories               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: The Suspicious Slot Machine

Rahim owns a small casino in Cox's Bazar. A customer complains that the slot machine seems rigged — it never lands on the jackpot symbol!

The machine has 5 symbols, and the manufacturer claims each should appear equally (20% each):
- 🍒 Cherry
- 🍋 Lemon  
- 🔔 Bell
- ⭐ Star
- 💎 Diamond (Jackpot)

Rahim records 500 spins:

| Symbol | 🍒 Cherry | 🍋 Lemon | 🔔 Bell | ⭐ Star | 💎 Diamond |
|--------|-----------|----------|---------|---------|------------|
| **Observed** | 95 | 110 | 105 | 120 | 70 |

**Question:** Is the machine fair, or is it rigged to reduce jackpots?

---

## The Hypotheses

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   HYPOTHESES FOR GOODNESS OF FIT                             │
│                                                             │
│   H₀: The data FITS the expected distribution               │
│       (Observed frequencies match expected frequencies)     │
│       "The machine is fair"                                │
│                                                             │
│   H₁: The data does NOT fit the expected distribution       │
│       (Observed frequencies differ from expected)          │
│       "The machine is NOT fair"                            │
│                                                             │
│   This is always a TWO-SIDED test conceptually,            │
│   but uses the RIGHT TAIL of chi-square distribution       │
│   (we only care if χ² is "too large")                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Formula

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CHI-SQUARE GOODNESS OF FIT FORMULA                         │
│                                                             │
│              k   (Oᵢ - Eᵢ)²                                 │
│        χ² = Σ  ────────────                                 │
│             i=1     Eᵢ                                      │
│                                                             │
│   Where:                                                    │
│   • Oᵢ = Observed frequency in category i                  │
│   • Eᵢ = Expected frequency in category i                  │
│   • k = number of categories                               │
│                                                             │
│   Degrees of Freedom:                                       │
│   df = k - 1                                               │
│                                                             │
│   Why k - 1?                                               │
│   Once you know k-1 frequencies and the total,             │
│   the last frequency is determined!                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Understanding the Formula

```
Each term (Oᵢ - Eᵢ)²/Eᵢ measures:

(Oᵢ - Eᵢ)² : How far is observed from expected?
             Squared to make all values positive
             and penalize large deviations more

    Eᵢ     : Divide by expected to STANDARDIZE
             A difference of 10 matters more when
             expected is 20 than when expected is 200


χ² = Sum of all standardized squared deviations

Small χ² → Good fit (observed ≈ expected)
Large χ² → Poor fit (observed ≠ expected)
```

---

## Solving the Slot Machine Problem

### Step 1: State the Hypotheses

```
H₀: All symbols appear with equal probability (20% each)
    P(🍒) = P(🍋) = P(🔔) = P(⭐) = P(💎) = 0.20

H₁: The symbols do NOT appear with equal probability
    (At least one probability differs from 0.20)

α = 0.05
```

### Step 2: Calculate Expected Frequencies

```
If H₀ is true (all equally likely):

Expected for each symbol = Total spins × P(each symbol)
                        = 500 × 0.20
                        = 100

| Symbol | Observed (O) | Expected (E) |
|--------|--------------|--------------|
| 🍒     | 95           | 100          |
| 🍋     | 110          | 100          |
| 🔔     | 105          | 100          |
| ⭐     | 120          | 100          |
| 💎     | 70           | 100          |
| Total  | 500          | 500          |
```

### Step 3: Check Conditions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONDITIONS FOR CHI-SQUARE GOODNESS OF FIT                  │
│                                                             │
│   1. RANDOM SAMPLE                                          │
│      Observations are randomly selected ✓                  │
│                                                             │
│   2. INDEPENDENCE                                           │
│      Each observation is independent ✓                     │
│      (Each spin is independent)                            │
│                                                             │
│   3. EXPECTED COUNT CONDITION                               │
│      All expected frequencies ≥ 5 ✓                        │
│      (All are 100, which is ≥ 5)                          │
│                                                             │
│   All conditions satisfied! Proceed with test.             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Step 4: Calculate Chi-Square Statistic

```
       (O - E)²
χ² = Σ ─────────
          E

| Symbol | O   | E   | O - E | (O-E)² | (O-E)²/E |
|--------|-----|-----|-------|--------|----------|
| 🍒     | 95  | 100 | -5    | 25     | 0.25     |
| 🍋     | 110 | 100 | +10   | 100    | 1.00     |
| 🔔     | 105 | 100 | +5    | 25     | 0.25     |
| ⭐     | 120 | 100 | +20   | 400    | 4.00     |
| 💎     | 70  | 100 | -30   | 900    | 9.00     |
|--------|-----|-----|-------|--------|----------|
| Total  | 500 | 500 |   0   |        | χ²=14.50 |

χ² = 0.25 + 1.00 + 0.25 + 4.00 + 9.00 = 14.50
```

### Step 5: Find Degrees of Freedom and Critical Value

```
df = k - 1 = 5 - 1 = 4

For α = 0.05 and df = 4:
χ²_critical = 9.488

p-value = P(χ² > 14.50 | df = 4) ≈ 0.006
```

### Step 6: Visualize the Test

```
                Chi-Square Distribution (df = 4)
                
    │
    │╲
    │ ╲
    │  ╲
    │   ╲
    │    ╲
    │     ╲─────────
    │              ╲
    │               ╲────────
    │                       ╲───────███████████
    └──────────────────────────┼───────┼────────────►
                             9.488  14.50         χ²
                               │       │
                         Critical   Our χ²
                          Value   
                               │
                          ◄────┴────►
                         Rejection
                          Region
                          
    χ² = 14.50 falls in the rejection region!
```

### Step 7: Make a Decision

```
METHOD 1: Using Critical Value
χ² = 14.50 > χ²_critical = 9.488
→ REJECT H₀

METHOD 2: Using P-value
p-value = 0.006 < α = 0.05
→ REJECT H₀
```

### Step 8: State the Conclusion

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONCLUSION                                                 │
│                                                             │
│   At the α = 0.05 significance level, we REJECT H₀.        │
│   There is statistically significant evidence that the     │
│   slot machine is NOT fair (χ² = 14.50, df = 4, p = 0.006).│
│                                                             │
│   Looking at the data:                                      │
│   • Diamond (💎) appeared 70 times (expected: 100)         │
│   • This is 30% LESS than expected!                        │
│   • Star (⭐) appeared 120 times (expected: 100)           │
│   • This is 20% MORE than expected                         │
│                                                             │
│   The customer's complaint appears justified!              │
│   The machine seems rigged to reduce jackpots.             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Which Category Contributed Most?

```
Looking at individual (O-E)²/E contributions:

| Symbol | (O-E)²/E | % of χ² |
|--------|----------|---------|
| 💎     | 9.00     | 62.1%   | ← Biggest contributor!
| ⭐     | 4.00     | 27.6%   |
| 🍋     | 1.00     | 6.9%    |
| 🔔     | 0.25     | 1.7%    |
| 🍒     | 0.25     | 1.7%    |

Diamond alone contributes 62% of the chi-square value!
This is the main source of "unfairness."
```

---

## Types of Expected Distributions

### Type 1: Equal Proportions (Uniform)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   EQUAL/UNIFORM DISTRIBUTION                                 │
│                                                             │
│   All categories expected to be equal                       │
│                                                             │
│   Expected for each = Total / k                            │
│                                                             │
│   Examples:                                                 │
│   • Fair die: Each face = n/6                              │
│   • Fair coin: Heads = Tails = n/2                         │
│   • Days of week: Each day = n/7                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Type 2: Specified Proportions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SPECIFIED PROPORTIONS                                      │
│                                                             │
│   Each category has a specified probability                │
│                                                             │
│   Expected for category i = Total × pᵢ                     │
│                                                             │
│   Examples:                                                 │
│   • Genetics: 9:3:3:1 ratio                               │
│   • M&M colors: Company-stated percentages                 │
│   • Market share: Based on prior data                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Type 3: Theoretical Distribution

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THEORETICAL DISTRIBUTION                                   │
│                                                             │
│   Expected from a probability distribution                  │
│                                                             │
│   Expected = Total × P(X = xᵢ) from distribution          │
│                                                             │
│   Examples:                                                 │
│   • Poisson: Testing if counts follow Poisson             │
│   • Binomial: Testing if data is binomial                 │
│   • Normal: Testing if data is normal (with bins)         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 2: Is the Die Fair?

A gambler rolls a die 120 times and records:

| Face | 1 | 2 | 3 | 4 | 5 | 6 |
|------|---|---|---|---|---|---|
| **Observed** | 25 | 17 | 15 | 23 | 24 | 16 |

Is the die fair at α = 0.05?

### Solution

```
H₀: Die is fair (each face has probability 1/6)
H₁: Die is not fair
α = 0.05

Expected for each face = 120 × (1/6) = 20

| Face | O  | E  | O - E | (O-E)² | (O-E)²/E |
|------|----|----|-------|--------|----------|
| 1    | 25 | 20 | +5    | 25     | 1.25     |
| 2    | 17 | 20 | -3    | 9      | 0.45     |
| 3    | 15 | 20 | -5    | 25     | 1.25     |
| 4    | 23 | 20 | +3    | 9      | 0.45     |
| 5    | 24 | 20 | +4    | 16     | 0.80     |
| 6    | 16 | 20 | -4    | 16     | 0.80     |
|------|----|----|-------|--------|----------|
| Total| 120| 120|   0   |        | χ² = 5.00|

df = 6 - 1 = 5
χ²_critical (α = 0.05, df = 5) = 11.07
p-value = P(χ² > 5.00 | df = 5) ≈ 0.416

χ² = 5.00 < 11.07 → FAIL TO REJECT H₀

CONCLUSION:
At α = 0.05, there is insufficient evidence to conclude 
the die is unfair (χ² = 5.00, df = 5, p = 0.416).

The observed variations are within normal random chance.
```

---

## 📖 Example 3: Mendelian Genetics (Specified Ratios)

A biologist crosses pea plants. Mendel's law predicts a 9:3:3:1 phenotype ratio. She observes 556 offspring:

| Phenotype | Round Yellow | Round Green | Wrinkled Yellow | Wrinkled Green |
|-----------|--------------|-------------|-----------------|----------------|
| **Observed** | 315 | 108 | 101 | 32 |
| **Expected Ratio** | 9 | 3 | 3 | 1 |

### Solution

```
H₀: Offspring follow 9:3:3:1 ratio (Mendelian inheritance)
H₁: Offspring do NOT follow 9:3:3:1 ratio
α = 0.05

Step 1: Calculate expected frequencies
Total parts = 9 + 3 + 3 + 1 = 16
Total offspring = 556

Expected:
• Round Yellow:    556 × 9/16 = 312.75
• Round Green:     556 × 3/16 = 104.25
• Wrinkled Yellow: 556 × 3/16 = 104.25
• Wrinkled Green:  556 × 1/16 = 34.75

Step 2: Calculate χ²
| Phenotype        | O   | E      | (O-E)²/E |
|------------------|-----|--------|----------|
| Round Yellow     | 315 | 312.75 | 0.016    |
| Round Green      | 108 | 104.25 | 0.135    |
| Wrinkled Yellow  | 101 | 104.25 | 0.101    |
| Wrinkled Green   | 32  | 34.75  | 0.218    |
|------------------|-----|--------|----------|
| Total            | 556 | 556    | χ² = 0.47|

Step 3: Find critical value
df = 4 - 1 = 3
χ²_critical (α = 0.05, df = 3) = 7.815
p-value ≈ 0.925

Step 4: Decision
χ² = 0.47 < 7.815 → FAIL TO REJECT H₀

CONCLUSION:
The data is consistent with Mendelian 9:3:3:1 ratio 
(χ² = 0.47, df = 3, p = 0.925).

This is remarkably good fit! Mendel's laws are supported.
(Historically, this data was crucial in validating genetics!)
```

### Visual: How Close is the Fit?

```
                Expected vs Observed

Round Yellow:  ████████████████████████████████ 315 (E: 312.75)
               ████████████████████████████████ Expected

Round Green:   ███████████ 108 (E: 104.25)
               ███████████ Expected

Wrinkled Yel:  ██████████ 101 (E: 104.25)
               ██████████ Expected

Wrinkled Grn:  ███ 32 (E: 34.75)
               ███ Expected

Almost perfect match! χ² = 0.47 (very small)
```

---

## 📖 Example 4: M&M Color Distribution

Mars Inc. claims M&M colors are distributed as:
- Brown: 13%
- Red: 13%
- Yellow: 14%
- Green: 16%
- Orange: 20%
- Blue: 24%

You count 500 M&Ms from various bags:

| Color | Brown | Red | Yellow | Green | Orange | Blue |
|-------|-------|-----|--------|-------|--------|------|
| **Observed** | 70 | 85 | 65 | 75 | 90 | 115 |
| **Claimed %** | 13% | 13% | 14% | 16% | 20% | 24% |

### Solution

```
H₀: Colors match claimed distribution
H₁: Colors do NOT match claimed distribution
α = 0.05

Expected frequencies:
• Brown:  500 × 0.13 = 65
• Red:    500 × 0.13 = 65
• Yellow: 500 × 0.14 = 70
• Green:  500 × 0.16 = 80
• Orange: 500 × 0.20 = 100
• Blue:   500 × 0.24 = 120

| Color  | O   | E   | (O-E)²/E |
|--------|-----|-----|----------|
| Brown  | 70  | 65  | 0.385    |
| Red    | 85  | 65  | 6.154    |
| Yellow | 65  | 70  | 0.357    |
| Green  | 75  | 80  | 0.313    |
| Orange | 90  | 100 | 1.000    |
| Blue   | 115 | 120 | 0.208    |
|--------|-----|-----|----------|
| Total  | 500 | 500 | χ² = 8.42|

df = 6 - 1 = 5
χ²_critical (α = 0.05, df = 5) = 11.07
p-value ≈ 0.134

χ² = 8.42 < 11.07 → FAIL TO REJECT H₀

CONCLUSION:
At α = 0.05, there is insufficient evidence that the 
M&M distribution differs from what Mars claims 
(χ² = 8.42, df = 5, p = 0.134).

Note: Red had 85 vs expected 65 — this contributed most
to χ². But overall, the fit is acceptable.
```

---

## 📖 Example 5: Day of Week Births

A hospital wants to know if births are equally distributed across days of the week. Data from 700 births:

| Day | Sun | Mon | Tue | Wed | Thu | Fri | Sat |
|-----|-----|-----|-----|-----|-----|-----|-----|
| **Births** | 84 | 110 | 115 | 108 | 105 | 98 | 80 |

### Solution

```
H₀: Births are equally distributed across days
H₁: Births are NOT equally distributed
α = 0.05

Expected for each day = 700/7 = 100

| Day | O   | E   | (O-E)²/E |
|-----|-----|-----|----------|
| Sun | 84  | 100 | 2.56     |
| Mon | 110 | 100 | 1.00     |
| Tue | 115 | 100 | 2.25     |
| Wed | 108 | 100 | 0.64     |
| Thu | 105 | 100 | 0.25     |
| Fri | 98  | 100 | 0.04     |
| Sat | 80  | 100 | 4.00     |
|-----|-----|-----|----------|
| Total|700 | 700 | χ²=10.74 |

df = 7 - 1 = 6
χ²_critical (α = 0.05, df = 6) = 12.59
p-value ≈ 0.097

χ² = 10.74 < 12.59 → FAIL TO REJECT H₀

CONCLUSION:
At α = 0.05, there is insufficient evidence that births
are unequally distributed across days (χ² = 10.74, df = 6, 
p = 0.097).

However, note p = 0.097 is close to 0.05. There's a hint
that weekends (Sun=84, Sat=80) have fewer births, possibly 
due to fewer scheduled C-sections/inductions. At α = 0.10,
we would reject H₀!
```

---

## 📖 Example 6: Testing for Poisson Distribution

A call center receives calls. Are the number of calls per minute Poisson distributed?

Data from 200 one-minute intervals:

| Calls/minute | 0 | 1 | 2 | 3 | 4 | 5+ |
|--------------|---|---|---|---|---|----|
| **Observed** | 18 | 45 | 56 | 42 | 27 | 12 |

The mean number of calls = 2.3 per minute.

### Solution

```
H₀: Data follows Poisson distribution with λ = 2.3
H₁: Data does NOT follow Poisson distribution
α = 0.05

Calculate Poisson probabilities for λ = 2.3:
P(X=0) = e^(-2.3) × 2.3^0 / 0! = 0.1003
P(X=1) = e^(-2.3) × 2.3^1 / 1! = 0.2306
P(X=2) = e^(-2.3) × 2.3^2 / 2! = 0.2652
P(X=3) = e^(-2.3) × 2.3^3 / 3! = 0.2033
P(X=4) = e^(-2.3) × 2.3^4 / 4! = 0.1169
P(X≥5) = 1 - sum of above = 0.0837

Expected frequencies = 200 × P(X=k):

| Calls | O  | E     | (O-E)²/E |
|-------|----|-------|----------|
| 0     | 18 | 20.06 | 0.212    |
| 1     | 45 | 46.12 | 0.027    |
| 2     | 56 | 53.04 | 0.165    |
| 3     | 42 | 40.66 | 0.044    |
| 4     | 27 | 23.38 | 0.561    |
| 5+    | 12 | 16.74 | 1.343    |
|-------|----|----- -|----------|
| Total |200 | 200   | χ² = 2.35|

df = 6 - 1 - 1 = 4  (subtract 1 for estimated λ)
χ²_critical (α = 0.05, df = 4) = 9.488
p-value ≈ 0.672

χ² = 2.35 < 9.488 → FAIL TO REJECT H₀

CONCLUSION:
The data is consistent with a Poisson distribution 
(χ² = 2.35, df = 4, p = 0.672).

The call arrivals can be modeled as Poisson with λ = 2.3.
```

### Note on Degrees of Freedom

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   DEGREES OF FREEDOM ADJUSTMENT                              │
│                                                             │
│   Basic formula: df = k - 1                                 │
│                                                             │
│   BUT: If you ESTIMATE parameters from the data,           │
│   subtract 1 for EACH estimated parameter:                 │
│                                                             │
│   df = k - 1 - (number of estimated parameters)            │
│                                                             │
│   Examples:                                                 │
│   • Testing uniform: df = k - 1 (nothing estimated)        │
│   • Testing Poisson: df = k - 1 - 1 (estimated λ)         │
│   • Testing Normal: df = k - 1 - 2 (estimated μ and σ)    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Step-by-Step Procedure

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   GOODNESS OF FIT TEST: STEP BY STEP                         │
│                                                             │
│   1. STATE HYPOTHESES                                       │
│      H₀: Data fits the specified distribution              │
│      H₁: Data does not fit the distribution                │
│                                                             │
│   2. CALCULATE EXPECTED FREQUENCIES                         │
│      E = n × p for each category                           │
│      Or E = n/k for uniform distribution                   │
│                                                             │
│   3. CHECK CONDITIONS                                       │
│      • Random sample                                        │
│      • Independent observations                             │
│      • All expected frequencies ≥ 5                        │
│                                                             │
│   4. CALCULATE TEST STATISTIC                               │
│      χ² = Σ (O - E)² / E                                   │
│                                                             │
│   5. FIND DEGREES OF FREEDOM                                │
│      df = k - 1 - (estimated parameters)                   │
│                                                             │
│   6. FIND CRITICAL VALUE OR P-VALUE                         │
│      From chi-square table or software                     │
│                                                             │
│   7. MAKE DECISION                                          │
│      Reject H₀ if χ² > χ²_critical                         │
│      Or if p-value < α                                     │
│                                                             │
│   8. STATE CONCLUSION                                       │
│      In context of the problem                             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Critical Values Table

```
┌────────────────────────────────────────────────────────────────┐
│                                                                │
│   CHI-SQUARE CRITICAL VALUES FOR GOODNESS OF FIT               │
│                                                                │
│    df │  α=0.10  │  α=0.05  │  α=0.01  │  α=0.001            │
│   ────┼──────────┼──────────┼──────────┼──────────            │
│     1 │   2.706  │   3.841  │   6.635  │  10.828             │
│     2 │   4.605  │   5.991  │   9.210  │  13.816             │
│     3 │   6.251  │   7.815  │  11.345  │  16.266             │
│     4 │   7.779  │   9.488  │  13.277  │  18.467             │
│     5 │   9.236  │  11.070  │  15.086  │  20.515             │
│     6 │  10.645  │  12.592  │  16.812  │  22.458             │
│     7 │  12.017  │  14.067  │  18.475  │  24.322             │
│     8 │  13.362  │  15.507  │  20.090  │  26.124             │
│     9 │  14.684  │  16.919  │  21.666  │  27.877             │
│    10 │  15.987  │  18.307  │  23.209  │  29.588             │
│                                                                │
│   Reject H₀ if χ² > critical value                            │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

---

## When Expected Counts Are Too Small

### What If E < 5?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   HANDLING SMALL EXPECTED FREQUENCIES                        │
│                                                             │
│   If any E < 5, the chi-square approximation may be poor   │
│                                                             │
│   OPTIONS:                                                  │
│                                                             │
│   1. COMBINE CATEGORIES                                     │
│      Merge adjacent categories until E ≥ 5                 │
│      (df decreases accordingly)                            │
│                                                             │
│   2. EXACT TEST                                             │
│      Use exact multinomial test                            │
│      (computationally intensive)                           │
│                                                             │
│   3. SIMULATION                                             │
│      Monte Carlo simulation for p-value                    │
│                                                             │
│   4. COLLECT MORE DATA                                      │
│      If possible, increase sample size                     │
│                                                             │
│   5. USE CORRECTION                                         │
│      Some use Yates' correction (controversial)            │
│                                                             │
│   RULE OF THUMB:                                            │
│   • All E ≥ 5: Good                                        │
│   • All E ≥ 1 and 80% ≥ 5: Acceptable                     │
│   • Any E < 1: Problematic                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Combining Categories

```
Original data with small expected counts:

| Category | O  | E    |
|----------|----|----- |
| A        | 45 | 40   | ✓
| B        | 30 | 35   | ✓
| C        | 8  | 10   | ✓
| D        | 4  | 3    | ✗ E < 5
| E        | 3  | 2    | ✗ E < 5
| Total    | 90 | 90   |

Solution: Combine D and E into "D or E":

| Category | O  | E    |
|----------|----|----- |
| A        | 45 | 40   | ✓
| B        | 30 | 35   | ✓
| C        | 8  | 10   | ✓
| D or E   | 7  | 5    | ✓ Now E ≥ 5!
| Total    | 90 | 90   |

df = 4 - 1 = 3 (reduced from 4)
```

---

## Python Implementation

### Complete Goodness of Fit Function

```python
import numpy as np
from scipy import stats

def goodness_of_fit_test(observed, expected=None, probabilities=None, alpha=0.05):
    """
    Chi-Square Goodness of Fit Test
    
    Parameters:
    - observed: list/array of observed frequencies
    - expected: list/array of expected frequencies (optional)
    - probabilities: list/array of expected probabilities (optional)
    - alpha: significance level
    
    Provide either 'expected' OR 'probabilities', not both.
    If neither provided, assumes uniform distribution.
    """
    observed = np.array(observed)
    n = observed.sum()
    k = len(observed)
    
    # Calculate expected frequencies
    if expected is not None:
        expected = np.array(expected)
    elif probabilities is not None:
        probabilities = np.array(probabilities)
        if not np.isclose(probabilities.sum(), 1.0):
            print(f"⚠️ Warning: Probabilities sum to {probabilities.sum()}, not 1.0")
        expected = n * probabilities
    else:
        # Uniform distribution
        expected = np.array([n/k] * k)
    
    # Check condition
    small_expected = (expected < 5).sum()
    if small_expected > 0:
        print(f"⚠️ Warning: {small_expected} categories have expected frequency < 5")
    
    # Calculate chi-square statistic
    chi_sq = np.sum((observed - expected)**2 / expected)
    
    # Degrees of freedom
    df = k - 1
    
    # p-value
    p_value = 1 - stats.chi2.cdf(chi_sq, df)
    
    # Critical value
    chi_critical = stats.chi2.ppf(1 - alpha, df)
    
    # Decision
    reject = chi_sq > chi_critical
    
    # Contributions to chi-square
    contributions = (observed - expected)**2 / expected
    
    return {
        'chi_square': chi_sq,
        'df': df,
        'p_value': p_value,
        'chi_critical': chi_critical,
        'reject_null': reject,
        'alpha': alpha,
        'observed': observed,
        'expected': expected,
        'contributions': contributions,
        'residuals': (observed - expected) / np.sqrt(expected)
    }

def print_gof_results(result, categories=None):
    """Pretty print the goodness of fit results"""
    k = len(result['observed'])
    if categories is None:
        categories = [f"Cat {i+1}" for i in range(k)]
    
    print("=" * 60)
    print("CHI-SQUARE GOODNESS OF FIT TEST")
    print("=" * 60)
    
    print(f"\n{'Category':<15} {'Observed':>10} {'Expected':>10} {'(O-E)²/E':>10}")
    print("-" * 50)
    for i, cat in enumerate(categories):
        print(f"{cat:<15} {result['observed'][i]:>10.0f} "
              f"{result['expected'][i]:>10.2f} "
              f"{result['contributions'][i]:>10.3f}")
    print("-" * 50)
    print(f"{'Total':<15} {result['observed'].sum():>10.0f} "
          f"{result['expected'].sum():>10.2f} "
          f"{result['chi_square']:>10.3f}")
    
    print(f"\nTest Statistics:")
    print(f"  χ² = {result['chi_square']:.4f}")
    print(f"  df = {result['df']}")
    print(f"  p-value = {result['p_value']:.4f}")
    print(f"  Critical value (α={result['alpha']}) = {result['chi_critical']:.4f}")
    
    print(f"\nDecision: ", end="")
    if result['reject_null']:
        print("REJECT H₀")
        print("  The data does NOT fit the expected distribution.")
    else:
        print("FAIL TO REJECT H₀")
        print("  The data is consistent with the expected distribution.")

# ============================================
# EXAMPLES
# ============================================

# Example 1: Slot Machine
print("\n" + "=" * 60)
print("EXAMPLE 1: SLOT MACHINE")
print("=" * 60)

observed = [95, 110, 105, 120, 70]  # Cherry, Lemon, Bell, Star, Diamond
categories = ['🍒 Cherry', '🍋 Lemon', '🔔 Bell', '⭐ Star', '💎 Diamond']

result = goodness_of_fit_test(observed)  # Uniform expected
print_gof_results(result, categories)

# Example 2: Mendelian Genetics (9:3:3:1)
print("\n" + "=" * 60)
print("EXAMPLE 2: MENDELIAN GENETICS (9:3:3:1 ratio)")
print("=" * 60)

observed = [315, 108, 101, 32]
probabilities = [9/16, 3/16, 3/16, 1/16]
categories = ['Round Yellow', 'Round Green', 'Wrinkled Yellow', 'Wrinkled Green']

result = goodness_of_fit_test(observed, probabilities=probabilities)
print_gof_results(result, categories)

# Example 3: Die Fairness
print("\n" + "=" * 60)
print("EXAMPLE 3: DIE FAIRNESS")
print("=" * 60)

observed = [25, 17, 15, 23, 24, 16]
categories = ['Face 1', 'Face 2', 'Face 3', 'Face 4', 'Face 5', 'Face 6']

result = goodness_of_fit_test(observed)
print_gof_results(result, categories)
```

### Visualization Function

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_goodness_of_fit(observed, expected, categories=None, title="Goodness of Fit"):
    """Visualize observed vs expected frequencies"""
    
    k = len(observed)
    if categories is None:
        categories = [f"Cat {i+1}" for i in range(k)]
    
    x = np.arange(k)
    width = 0.35
    
    fig, axes = plt.subplots(1, 2, figsize=(14, 5))
    
    # Plot 1: Bar chart comparison
    ax1 = axes[0]
    bars1 = ax1.bar(x - width/2, observed, width, label='Observed', color='steelblue')
    bars2 = ax1.bar(x + width/2, expected, width, label='Expected', color='coral')
    
    ax1.set_xlabel('Category', fontsize=12)
    ax1.set_ylabel('Frequency', fontsize=12)
    ax1.set_title(f'{title}\nObserved vs Expected Frequencies', fontsize=14)
    ax1.set_xticks(x)
    ax1.set_xticklabels(categories, rotation=45, ha='right')
    ax1.legend()
    ax1.grid(True, alpha=0.3, axis='y')
    
    # Add value labels
    for bar in bars1:
        height = bar.get_height()
        ax1.annotate(f'{height:.0f}',
                    xy=(bar.get_x() + bar.get_width()/2, height),
                    xytext=(0, 3), textcoords="offset points",
                    ha='center', va='bottom', fontsize=9)
    for bar in bars2:
        height = bar.get_height()
        ax1.annotate(f'{height:.1f}',
                    xy=(bar.get_x() + bar.get_width()/2, height),
                    xytext=(0, 3), textcoords="offset points",
                    ha='center', va='bottom', fontsize=9)
    
    # Plot 2: Contribution to chi-square
    ax2 = axes[1]
    contributions = (np.array(observed) - np.array(expected))**2 / np.array(expected)
    colors = ['green' if c < 1 else 'orange' if c < 4 else 'red' for c in contributions]
    
    bars = ax2.bar(categories, contributions, color=colors)
    ax2.set_xlabel('Category', fontsize=12)
    ax2.set_ylabel('(O - E)² / E', fontsize=12)
    ax2.set_title('Contribution to Chi-Square\n(Green < 1, Orange < 4, Red ≥ 4)', fontsize=14)
    ax2.set_xticklabels(categories, rotation=45, ha='right')
    ax2.grid(True, alpha=0.3, axis='y')
    
    chi_sq = contributions.sum()
    ax2.axhline(y=chi_sq/k, color='black', linestyle='--', 
                label=f'Average contribution = {chi_sq/k:.2f}')
    ax2.legend()
    
    plt.tight_layout()
    plt.show()
    
    return chi_sq

def visualize_chi_square_test(chi_sq, df, alpha=0.05):
    """Visualize the chi-square test result"""
    
    chi_critical = stats.chi2.ppf(1 - alpha, df)
    p_value = 1 - stats.chi2.cdf(chi_sq, df)
    
    fig, ax = plt.subplots(figsize=(12, 6))
    
    x_max = max(chi_sq * 1.5, chi_critical * 1.5, df * 3)
    x = np.linspace(0.01, x_max, 500)
    y = stats.chi2.pdf(x, df)
    
    # Distribution
    ax.plot(x, y, 'b-', linewidth=2, label=f'χ² distribution (df={df})')
    ax.fill_between(x, y, alpha=0.1)
    
    # Rejection region
    x_reject = x[x >= chi_critical]
    y_reject = stats.chi2.pdf(x_reject, df)
    ax.fill_between(x_reject, y_reject, color='red', alpha=0.4,
                    label=f'Rejection region (α={alpha})')
    
    # Critical value line
    ax.axvline(chi_critical, color='red', linestyle='--', linewidth=1.5,
               label=f'Critical value = {chi_critical:.3f}')
    
    # Test statistic line
    ax.axvline(chi_sq, color='green', linewidth=2.5,
               label=f'χ² = {chi_sq:.3f}')
    
    decision = "REJECT H₀" if chi_sq > chi_critical else "FAIL TO REJECT H₀"
    ax.set_title(f'Chi-Square Goodness of Fit Test\n{decision} (p-value = {p_value:.4f})',
                fontsize=14)
    ax.set_xlabel('χ²', fontsize=12)
    ax.set_ylabel('Density', fontsize=12)
    ax.legend(loc='upper right')
    ax.grid(True, alpha=0.3)
    ax.set_xlim(0, x_max)
    
    plt.tight_layout()
    plt.show()

# Visualize the slot machine example
observed = [95, 110, 105, 120, 70]
expected = [100, 100, 100, 100, 100]
categories = ['Cherry', 'Lemon', 'Bell', 'Star', 'Diamond']

chi_sq = visualize_goodness_of_fit(observed, expected, categories, "Slot Machine Test")
visualize_chi_square_test(chi_sq, df=4)
```

---

## Common Applications

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   COMMON APPLICATIONS OF GOODNESS OF FIT TEST               │
│                                                             │
│   1. FAIRNESS TESTING                                       │
│      • Dice, coins, random number generators               │
│      • Lottery and gambling devices                        │
│      • A/B test random assignment                          │
│                                                             │
│   2. GENETICS                                               │
│      • Mendelian inheritance ratios                        │
│      • Hardy-Weinberg equilibrium                          │
│      • Gene frequency distributions                        │
│                                                             │
│   3. DISTRIBUTION FITTING                                   │
│      • Testing for Poisson (arrivals, events)             │
│      • Testing for Normal distribution                     │
│      • Testing for Exponential (waiting times)            │
│                                                             │
│   4. MARKET RESEARCH                                        │
│      • Brand preference distributions                      │
│      • Customer demographic matching                       │
│      • Response rate verification                          │
│                                                             │
│   5. QUALITY CONTROL                                        │
│      • Defect distribution across shifts                  │
│      • Product category verification                       │
│      • Equipment calibration testing                       │
│                                                             │
│   6. SOCIAL SCIENCES                                        │
│      • Population distribution verification               │
│      • Survey response patterns                            │
│      • Behavior frequency analysis                         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Practice Problems 📝

### Problem 1: Coin Flipping
A coin is flipped 200 times: 118 heads, 82 tails. Is the coin fair at α = 0.05?

<details>
<summary>Click for Solution</summary>

```
H₀: Coin is fair (P(H) = P(T) = 0.5)
H₁: Coin is not fair
α = 0.05

Expected: 200 × 0.5 = 100 each

| Outcome | O   | E   | (O-E)²/E |
|---------|-----|-----|----------|
| Heads   | 118 | 100 | 3.24     |
| Tails   | 82  | 100 | 3.24     |
| Total   | 200 | 200 | χ² = 6.48|

df = 2 - 1 = 1
χ²_critical (α = 0.05, df = 1) = 3.841
p-value = 0.011

χ² = 6.48 > 3.841 → REJECT H₀

Conclusion: At α = 0.05, there is significant evidence 
the coin is not fair (χ² = 6.48, p = 0.011).
The coin appears biased toward heads.
```

</details>

---

### Problem 2: Customer Preferences
A company claims its 3 products are equally preferred. Survey of 150 customers:
- Product A: 65
- Product B: 50
- Product C: 35

Test at α = 0.05.

<details>
<summary>Click for Solution</summary>

```
H₀: Products are equally preferred (1/3 each)
H₁: Products are not equally preferred
α = 0.05

Expected: 150 × (1/3) = 50 each

| Product | O  | E  | (O-E)²/E |
|---------|----|----|----------|
| A       | 65 | 50 | 4.50     |
| B       | 50 | 50 | 0.00     |
| C       | 35 | 50 | 4.50     |
| Total   |150 |150 | χ² = 9.00|

df = 3 - 1 = 2
χ²_critical (α = 0.05, df = 2) = 5.991
p-value = 0.011

χ² = 9.00 > 5.991 → REJECT H₀

Conclusion: Products are NOT equally preferred.
Product A is most preferred (43%), Product C least (23%).
```

</details>

---

### Problem 3: Blood Type Distribution
A region's blood type distribution is claimed to be: O: 45%, A: 40%, B: 11%, AB: 4%.
Sample of 500 people: O: 210, A: 215, B: 50, AB: 25.
Does the sample match the claimed distribution at α = 0.05?

<details>
<summary>Click for Solution</summary>

```
H₀: Blood types match claimed distribution
H₁: Blood types do not match claimed distribution
α = 0.05

Expected frequencies:
O:  500 × 0.45 = 225
A:  500 × 0.40 = 200
B:  500 × 0.11 = 55
AB: 500 × 0.04 = 20

| Type | O   | E   | (O-E)²/E |
|------|-----|-----|----------|
| O    | 210 | 225 | 1.00     |
| A    | 215 | 200 | 1.13     |
| B    | 50  | 55  | 0.45     |
| AB   | 25  | 20  | 1.25     |
| Total| 500 | 500 | χ² = 3.83|

df = 4 - 1 = 3
χ²_critical (α = 0.05, df = 3) = 7.815
p-value = 0.280

χ² = 3.83 < 7.815 → FAIL TO REJECT H₀

Conclusion: The sample is consistent with the claimed 
blood type distribution (χ² = 3.83, p = 0.280).
```

</details>

---

### Problem 4: Last Digit Fraud Detection
Fraudulent data often has unnatural digit patterns. The last digits of 200 expense reports:

| Digit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Count | 35| 12| 18| 15| 22| 38| 14| 16| 18| 12|

Are the digits uniformly distributed (as expected in natural data)?

<details>
<summary>Click for Solution</summary>

```
H₀: Last digits are uniformly distributed (10% each)
H₁: Last digits are not uniformly distributed
α = 0.05

Expected: 200 × 0.10 = 20 each

| Digit | O  | E  | (O-E)²/E |
|-------|----|----|----------|
| 0     | 35 | 20 | 11.25    |
| 1     | 12 | 20 | 3.20     |
| 2     | 18 | 20 | 0.20     |
| 3     | 15 | 20 | 1.25     |
| 4     | 22 | 20 | 0.20     |
| 5     | 38 | 20 | 16.20    |
| 6     | 14 | 20 | 1.80     |
| 7     | 16 | 20 | 0.80     |
| 8     | 18 | 20 | 0.20     |
| 9     | 12 | 20 | 3.20     |
|-------|----|----|----------|
| Total | 200| 200| χ² =38.30|

df = 10 - 1 = 9
χ²_critical (α = 0.05, df = 9) = 16.919
p-value < 0.0001

χ² = 38.30 > 16.919 → REJECT H₀

Conclusion: The last digits are NOT uniformly distributed!
Digits 0 and 5 appear far more often than expected 
(35 and 38 vs expected 20). This is a red flag for 
potential fraud — people tend to round to 0 and 5!
```

</details>

---

## Summary: The Essence of Goodness of Fit

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│            CHI-SQUARE GOODNESS OF FIT TEST                       │
│            ═══════════════════════════════                       │
│                                                                  │
│   PURPOSE:                                                       │
│   Test if observed data fits an expected distribution           │
│                                                                  │
│   THE FORMULA:                                                   │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │              (Observed - Expected)²                      │   │
│   │       χ² = Σ ──────────────────────                      │   │
│   │                   Expected                               │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   DEGREES OF FREEDOM:                                            │
│   df = k - 1 - (number of estimated parameters)                 │
│                                                                  │
│   CONDITIONS:                                                    │
│   • Random sample                                               │
│   • Independent observations                                     │
│   • All expected frequencies ≥ 5                                │
│                                                                  │
│   INTERPRETATION:                                                │
│   • Small χ² → Good fit (observed ≈ expected)                  │
│   • Large χ² → Poor fit (observed ≠ expected)                  │
│                                                                  │
│   APPLICATIONS:                                                  │
│   • Fairness testing (dice, coins, RNG)                        │
│   • Genetics (Mendelian ratios)                                 │
│   • Distribution fitting (Poisson, Normal)                      │
│   • Fraud detection (digit analysis)                            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────────┐
│                 GOODNESS OF FIT QUICK REFERENCE                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   FORMULA: χ² = Σ (O - E)² / E                                  │
│                                                                  │
│   EXPECTED FREQUENCIES:                                          │
│   • Uniform: E = n / k                                          │
│   • Specified: E = n × pᵢ                                       │
│                                                                  │
│   DEGREES OF FREEDOM:                                            │
│   df = k - 1 - (estimated parameters)                           │
│                                                                  │
│   CRITICAL VALUES (α = 0.05):                                    │
│   df=1: 3.841 │ df=2: 5.991 │ df=3: 7.815 │ df=4: 9.488        │
│   df=5: 11.07 │ df=6: 12.59 │ df=7: 14.07 │ df=8: 15.51        │
│                                                                  │
│   CONDITIONS:                                                    │
│   ✓ Random sample                                               │
│   ✓ Independent observations                                    │
│   ✓ All E ≥ 5 (or combine categories)                          │
│                                                                  │
│   DECISION: Reject H₀ if χ² > χ²_critical                       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

> **"The Goodness of Fit test answers a simple but powerful question: Does reality match expectation? When the gap is too large to blame on chance, something interesting is happening — whether it's a rigged slot machine, genetic mutation, or fraudulent data!"**

From testing dice fairness to detecting fraud, the Goodness of Fit test is your tool for comparing what IS to what SHOULD BE! 🎯

---

*From observed to expected, from data to distribution — that's the power of Goodness of Fit!* 📊
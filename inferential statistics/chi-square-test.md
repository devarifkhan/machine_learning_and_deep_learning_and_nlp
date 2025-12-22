# Chi-Square Test
## The Test for Categorical Data 📊

---

## What is the Chi-Square Test?

The Chi-Square (χ²) test is a statistical test used to analyze **categorical data** — data that can be divided into groups or categories. It answers questions like:

- Does this die roll fairly?
- Is there a relationship between gender and voting preference?
- Do different treatments have different success rates?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CHI-SQUARE TEST                                            │
│                                                             │
│   Purpose: Analyze categorical (count) data                │
│                                                             │
│   Core Question:                                            │
│   "Is the difference between what we OBSERVED and what     │
│   we EXPECTED large enough to be statistically significant?"│
│                                                             │
│   Key Formula:                                              │
│                   (Observed - Expected)²                    │
│         χ² = Σ ─────────────────────────                    │
│                      Expected                               │
│                                                             │
│   Compares: Observed frequencies vs Expected frequencies   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Three Types of Chi-Square Tests

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THREE TYPES OF CHI-SQUARE TESTS                            │
│                                                             │
│   1. GOODNESS OF FIT TEST                                   │
│      Does our data fit a specific distribution?            │
│      "Is this die fair?"                                   │
│      One categorical variable                              │
│                                                             │
│   2. TEST OF INDEPENDENCE                                   │
│      Are two categorical variables related?                │
│      "Is smoking related to lung cancer?"                  │
│      Two categorical variables, one sample                 │
│                                                             │
│   3. TEST OF HOMOGENEITY                                    │
│      Do different populations have same distribution?      │
│      "Do men and women have same voting patterns?"         │
│      One categorical variable, multiple populations        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Chi-Square Distribution

### What Does It Look Like?

```
                    Chi-Square Distribution
                    
    │
    │╲
    │ ╲
    │  ╲   df = 1
    │   ╲
    │    ╲
    │     ╲
    │      ╲────  df = 3
    │         ╲
    │          ╲──────  df = 5
    │            ╲
    │             ╲────────  df = 10
    │               ╲
    │                ╲──────────
    └─────────────────────────────────────────►
    0                                        χ²
    
    Properties:
    • Always positive (χ² ≥ 0)
    • Right-skewed (especially for small df)
    • Becomes more symmetric as df increases
    • Mean = df, Variance = 2×df
```

### Key Properties

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CHI-SQUARE DISTRIBUTION PROPERTIES                         │
│                                                             │
│   • Notation: χ² ~ χ²(df)                                  │
│   • Domain: [0, ∞) — always non-negative                   │
│   • Mean (μ) = df                                          │
│   • Variance (σ²) = 2 × df                                 │
│   • Shape: Right-skewed, approaches normal as df → ∞      │
│                                                             │
│   Degrees of Freedom depend on test type:                  │
│   • Goodness of Fit: df = k - 1                           │
│   • Independence: df = (r - 1)(c - 1)                     │
│   • Homogeneity: df = (r - 1)(c - 1)                      │
│                                                             │
│   Where: k = categories, r = rows, c = columns            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Chi-Square Formula

### The Core Calculation

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CHI-SQUARE TEST STATISTIC                                  │
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
│   Interpretation:                                           │
│   • Small χ² → Observed ≈ Expected (good fit)             │
│   • Large χ² → Observed ≠ Expected (poor fit)             │
│                                                             │
│   The test is always ONE-TAILED (right tail)               │
│   We only care if χ² is "too large"                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Why Square the Difference?

```
Without squaring:
• Positive and negative differences would cancel out
• Total could be zero even with bad fit!

With squaring:
• All differences become positive
• Larger differences are penalized more heavily
• Dividing by E standardizes the contribution
```

---

# Part 1: Chi-Square Goodness of Fit Test
## *Does our data fit the expected distribution?*

---

## When to Use Goodness of Fit Test

- Testing if a die is fair
- Testing if births are equally distributed across days
- Testing if observed ratios match theoretical ratios
- Testing if data follows a specific distribution

---

## 📖 Story: Is the Casino Die Fair?

Rafiq suspects a casino is using loaded dice. He secretly records 600 rolls of a die:

| Outcome | 1 | 2 | 3 | 4 | 5 | 6 |
|---------|---|---|---|---|---|---|
| **Observed** | 89 | 95 | 105 | 115 | 108 | 88 |

**Question:** Is the die fair, or is there evidence of cheating?

### Step 1: State the Hypotheses

```
H₀: The die is fair (all outcomes equally likely)
    P(1) = P(2) = P(3) = P(4) = P(5) = P(6) = 1/6

H₁: The die is NOT fair (outcomes not equally likely)

α = 0.05
```

### Step 2: Calculate Expected Frequencies

```
If the die is fair, each outcome should appear 1/6 of the time:

Expected for each outcome = Total rolls × (1/6)
                         = 600 × (1/6)
                         = 100

| Outcome | Observed (O) | Expected (E) |
|---------|--------------|--------------|
| 1       | 89           | 100          |
| 2       | 95           | 100          |
| 3       | 105          | 100          |
| 4       | 115          | 100          |
| 5       | 108          | 100          |
| 6       | 88           | 100          |
| Total   | 600          | 600          |
```

### Step 3: Calculate Chi-Square Statistic

```
       (O - E)²
χ² = Σ ─────────
          E

| Outcome | O    | E    | O - E  | (O-E)² | (O-E)²/E |
|---------|------|------|--------|--------|----------|
| 1       | 89   | 100  | -11    | 121    | 1.21     |
| 2       | 95   | 100  | -5     | 25     | 0.25     |
| 3       | 105  | 100  | +5     | 25     | 0.25     |
| 4       | 115  | 100  | +15    | 225    | 2.25     |
| 5       | 108  | 100  | +8     | 64     | 0.64     |
| 6       | 88   | 100  | -12    | 144    | 1.44     |
|---------|------|------|--------|--------|----------|
| Total   | 600  | 600  |   0    |        | χ² = 6.04|
```

### Step 4: Find Degrees of Freedom and Critical Value

```
df = k - 1 = 6 - 1 = 5

For α = 0.05 and df = 5:
χ²_critical = 11.07

Or find p-value:
p-value = P(χ² > 6.04 | df = 5) ≈ 0.303
```

### Step 5: Make a Decision

```
χ² = 6.04 < χ²_critical = 11.07

OR

p-value = 0.303 > α = 0.05

DECISION: FAIL TO REJECT H₀
```

### Step 6: State the Conclusion

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONCLUSION                                                 │
│                                                             │
│   At the α = 0.05 significance level, there is             │
│   INSUFFICIENT evidence to conclude that the die is        │
│   unfair (χ² = 6.04, df = 5, p = 0.303).                  │
│                                                             │
│   The observed differences from expected frequencies       │
│   could reasonably occur by chance with a fair die.       │
│                                                             │
│   Rafiq cannot prove the casino is cheating.               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 2: Genetics (Mendelian Ratios)

A biologist crosses plants and observes offspring phenotypes. Mendelian genetics predicts a 9:3:3:1 ratio.

**Observed:** 315 round yellow, 108 round green, 101 wrinkled yellow, 32 wrinkled green

**Total:** 556 plants

### Solution

```
Step 1: Hypotheses
H₀: Offspring follow 9:3:3:1 ratio
H₁: Offspring do NOT follow 9:3:3:1 ratio
α = 0.05

Step 2: Expected frequencies (based on 9:3:3:1)
Total parts = 9 + 3 + 3 + 1 = 16

Expected:
• Round Yellow: 556 × 9/16 = 312.75
• Round Green: 556 × 3/16 = 104.25
• Wrinkled Yellow: 556 × 3/16 = 104.25
• Wrinkled Green: 556 × 1/16 = 34.75

Step 3: Calculate χ²
| Phenotype        | O    | E      | (O-E)²/E |
|------------------|------|--------|----------|
| Round Yellow     | 315  | 312.75 | 0.016    |
| Round Green      | 108  | 104.25 | 0.135    |
| Wrinkled Yellow  | 101  | 104.25 | 0.101    |
| Wrinkled Green   | 32   | 34.75  | 0.218    |
|------------------|------|--------|----------|
| Total            | 556  | 556    | χ² = 0.47|

Step 4: Critical value
df = 4 - 1 = 3
χ²_critical (α = 0.05, df = 3) = 7.815
p-value ≈ 0.925

Step 5: Decision
χ² = 0.47 < 7.815 → FAIL TO REJECT H₀

Conclusion: The data is consistent with Mendelian 9:3:3:1 ratio.
This is a classic result that supported Mendel's theory!
```

---

# Part 2: Chi-Square Test of Independence
## *Are two categorical variables related?*

---

## When to Use Test of Independence

- Is there a relationship between smoking and lung cancer?
- Is education level related to political preference?
- Is customer satisfaction related to product type?
- Is treatment type related to recovery outcome?

---

## 📖 Story: Smoking and Lung Cancer

Dr. Fatima studies the relationship between smoking and lung cancer. She collects data from 1,000 patients:

```
                    CONTINGENCY TABLE (Observed)
                    
                    │  Lung Cancer  │  No Cancer  │  Total
    ────────────────┼───────────────┼─────────────┼────────
    Smoker          │      90       │     210     │   300
    Non-Smoker      │      60       │     640     │   700
    ────────────────┼───────────────┼─────────────┼────────
    Total           │     150       │     850     │  1000
```

**Question:** Is smoking related to (associated with) lung cancer?

### Step 1: State the Hypotheses

```
H₀: Smoking and lung cancer are INDEPENDENT
    (No relationship between them)

H₁: Smoking and lung cancer are NOT independent
    (There IS a relationship)

α = 0.05
```

### Step 2: Calculate Expected Frequencies

```
If H₀ is true (variables are independent):

Expected = (Row Total × Column Total) / Grand Total

E₁₁ (Smoker, Cancer) = (300 × 150) / 1000 = 45
E₁₂ (Smoker, No Cancer) = (300 × 850) / 1000 = 255
E₂₁ (Non-Smoker, Cancer) = (700 × 150) / 1000 = 105
E₂₂ (Non-Smoker, No Cancer) = (700 × 850) / 1000 = 595

                    EXPECTED FREQUENCIES
                    
                    │  Lung Cancer  │  No Cancer  │  Total
    ────────────────┼───────────────┼─────────────┼────────
    Smoker          │      45       │     255     │   300
    Non-Smoker      │     105       │     595     │   700
    ────────────────┼───────────────┼─────────────┼────────
    Total           │     150       │     850     │  1000
```

### Step 3: Check Expected Count Condition

```
All expected counts should be ≥ 5:
45, 255, 105, 595 — all ≥ 5 ✓

Condition satisfied!
```

### Step 4: Calculate Chi-Square Statistic

```
       (O - E)²
χ² = Σ ─────────
          E

| Cell            | O    | E    | O - E  | (O-E)²  | (O-E)²/E |
|-----------------|------|------|--------|---------|----------|
| Smoker+Cancer   | 90   | 45   | +45    | 2025    | 45.00    |
| Smoker+NoCancer | 210  | 255  | -45    | 2025    | 7.94     |
| NonSmkr+Cancer  | 60   | 105  | -45    | 2025    | 19.29    |
| NonSmkr+NoCancer| 640  | 595  | +45    | 2025    | 3.40     |
|-----------------|------|------|--------|---------|----------|
| Total           | 1000 | 1000 |   0    |         | χ²=75.63 |
```

### Step 5: Find Degrees of Freedom and Critical Value

```
df = (rows - 1) × (columns - 1)
   = (2 - 1) × (2 - 1)
   = 1 × 1
   = 1

For α = 0.05 and df = 1:
χ²_critical = 3.841

p-value = P(χ² > 75.63 | df = 1) < 0.0001
```

### Step 6: Make a Decision

```
χ² = 75.63 >> χ²_critical = 3.841

p-value < 0.0001 << α = 0.05

DECISION: REJECT H₀
```

### Step 7: State the Conclusion

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONCLUSION                                                 │
│                                                             │
│   At α = 0.05, there is STRONG evidence of a relationship  │
│   between smoking and lung cancer (χ² = 75.63, df = 1,    │
│   p < 0.0001).                                             │
│                                                             │
│   Smoking and lung cancer are NOT independent.             │
│                                                             │
│   Looking at the data:                                      │
│   • Smokers: 90/300 = 30% have lung cancer                │
│   • Non-smokers: 60/700 = 8.6% have lung cancer           │
│                                                             │
│   Smokers have ~3.5× higher rate of lung cancer!          │
│                                                             │
│   ⚠️ Note: This shows ASSOCIATION, not necessarily        │
│   CAUSATION (though in this case, causation is proven).   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Observed vs Expected

```
                OBSERVED                      EXPECTED (if independent)
                
    Cancer  │████████░░│ 90            Cancer  │████░░░░░░│ 45
    No Canc │██████████│ 210           No Canc │██████████│ 255
            └──────────┘ Smoker                └──────────┘ Smoker
            
    Cancer  │██████░░░░│ 60            Cancer  │██████████│ 105
    No Canc │██████████│ 640           No Canc │██████████│ 595
            └──────────┘ Non-Smoker            └──────────┘ Non-Smoker

    Smokers have WAY more cancer than expected if independent!
```

---

## 📖 Example 3: Education and Political Preference

A survey asks 500 people about education and political preference:

```
                    │ Liberal │ Conservative │ Independent │ Total
    ────────────────┼─────────┼──────────────┼─────────────┼───────
    High School     │   40    │      80      │     30      │  150
    College         │   70    │      70      │     60      │  200
    Graduate        │   60    │      30      │     60      │  150
    ────────────────┼─────────┼──────────────┼─────────────┼───────
    Total           │  170    │     180      │    150      │  500
```

### Solution

```
H₀: Education and political preference are independent
H₁: Education and political preference are related
α = 0.05

Expected frequencies: E = (Row Total × Col Total) / 500

| Cell                    | O  | E    | (O-E)²/E |
|-------------------------|----|------|----------|
| HS + Liberal            | 40 | 51   | 2.37     |
| HS + Conservative       | 80 | 54   | 12.52    |
| HS + Independent        | 30 | 45   | 5.00     |
| College + Liberal       | 70 | 68   | 0.06     |
| College + Conservative  | 70 | 72   | 0.06     |
| College + Independent   | 60 | 60   | 0.00     |
| Grad + Liberal          | 60 | 51   | 1.59     |
| Grad + Conservative     | 30 | 54   | 10.67    |
| Grad + Independent      | 60 | 45   | 5.00     |
|-------------------------|----|------|----------|
| Total                   |500 | 500  | χ²=37.27 |

df = (3-1)(3-1) = 4
χ²_critical (α=0.05, df=4) = 9.488
p-value < 0.0001

χ² = 37.27 > 9.488 → REJECT H₀

Conclusion: There IS a significant relationship between 
education level and political preference.

Observations:
• High school: More conservative
• Graduate: More liberal and independent
• College: Relatively balanced
```

---

# Part 3: Chi-Square Test of Homogeneity
## *Do different populations have the same distribution?*

---

## When to Use Test of Homogeneity

- Do men and women have the same voting patterns?
- Do different age groups have the same brand preferences?
- Do patients from different hospitals have the same recovery rates?

---

## Test of Independence vs Homogeneity

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   INDEPENDENCE vs HOMOGENEITY                                │
│                                                             │
│   TEST OF INDEPENDENCE:                                      │
│   • ONE sample from ONE population                         │
│   • Two variables measured on each subject                 │
│   • Question: Are the two variables related?               │
│   • Example: Survey 1000 people, ask about smoking AND    │
│     cancer status                                          │
│                                                             │
│   TEST OF HOMOGENEITY:                                       │
│   • Multiple samples from DIFFERENT populations            │
│   • One variable measured                                  │
│   • Question: Same distribution across populations?        │
│   • Example: Sample from Men and Women separately,        │
│     ask about voting preference                            │
│                                                             │
│   MATHEMATICALLY: Same calculation!                         │
│   The difference is in study design and interpretation.    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Example 4: Treatment Effectiveness Across Hospitals

Three hospitals use different treatments. Do they have the same recovery rates?

```
                    │ Recovered │ Not Recovered │ Total
    ────────────────┼───────────┼───────────────┼───────
    Hospital A      │    80     │      20       │  100
    Hospital B      │    90     │      60       │  150
    Hospital C      │   130     │      70       │  200
    ────────────────┼───────────┼───────────────┼───────
    Total           │   300     │     150       │  450
```

### Solution

```
H₀: Recovery rates are the SAME across all hospitals
H₁: Recovery rates DIFFER between hospitals
α = 0.05

Expected frequencies:
E = (Row Total × Col Total) / 450

| Cell              | O   | E     | (O-E)²/E |
|-------------------|-----|-------|----------|
| A + Recovered     | 80  | 66.67 | 2.67     |
| A + Not Recovered | 20  | 33.33 | 5.33     |
| B + Recovered     | 90  | 100   | 1.00     |
| B + Not Recovered | 60  | 50    | 2.00     |
| C + Recovered     | 130 | 133.33| 0.08     |
| C + Not Recovered | 70  | 66.67 | 0.17     |
|-------------------|-----|-------|----------|
| Total             | 450 | 450   | χ²=11.25 |

df = (3-1)(2-1) = 2
χ²_critical (α=0.05, df=2) = 5.991
p-value ≈ 0.0036

χ² = 11.25 > 5.991 → REJECT H₀

Conclusion: Recovery rates DIFFER significantly across hospitals.

Recovery Rates:
• Hospital A: 80/100 = 80%
• Hospital B: 90/150 = 60%
• Hospital C: 130/200 = 65%

Hospital A has significantly better outcomes!
```

---

## Critical Values Table

```
┌────────────────────────────────────────────────────────────────┐
│                                                                │
│   CHI-SQUARE CRITICAL VALUES                                    │
│                                                                │
│    df │  α=0.10  │  α=0.05  │  α=0.025 │  α=0.01  │  α=0.001 │
│   ────┼──────────┼──────────┼──────────┼──────────┼──────────│
│     1 │   2.706  │   3.841  │   5.024  │   6.635  │  10.828  │
│     2 │   4.605  │   5.991  │   7.378  │   9.210  │  13.816  │
│     3 │   6.251  │   7.815  │   9.348  │  11.345  │  16.266  │
│     4 │   7.779  │   9.488  │  11.143  │  13.277  │  18.467  │
│     5 │   9.236  │  11.070  │  12.833  │  15.086  │  20.515  │
│     6 │  10.645  │  12.592  │  14.449  │  16.812  │  22.458  │
│     7 │  12.017  │  14.067  │  16.013  │  18.475  │  24.322  │
│     8 │  13.362  │  15.507  │  17.535  │  20.090  │  26.124  │
│     9 │  14.684  │  16.919  │  19.023  │  21.666  │  27.877  │
│    10 │  15.987  │  18.307  │  20.483  │  23.209  │  29.588  │
│    15 │  22.307  │  24.996  │  27.488  │  30.578  │  37.697  │
│    20 │  28.412  │  31.410  │  34.170  │  37.566  │  45.315  │
│                                                                │
│   If χ² > critical value → REJECT H₀                          │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

---

## Assumptions and Conditions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CONDITIONS FOR CHI-SQUARE TEST                             │
│                                                             │
│   1. RANDOM SAMPLE                                          │
│      Data must be randomly selected                         │
│                                                             │
│   2. INDEPENDENT OBSERVATIONS                               │
│      Each observation must be independent                   │
│      Each subject counted in only one cell                 │
│                                                             │
│   3. EXPECTED COUNT CONDITION                               │
│      All expected frequencies should be ≥ 5               │
│      (Some texts say ≥ 1 with 80% ≥ 5)                    │
│                                                             │
│   4. CATEGORICAL DATA                                       │
│      Variables must be categorical (not continuous)        │
│                                                             │
│   IF EXPECTED < 5:                                          │
│   • Combine categories if logical                          │
│   • Use Fisher's Exact Test (for 2×2 tables)              │
│   • Use simulation-based methods                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Effect Size: Cramér's V

### Measuring Strength of Association

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   CRAMÉR'S V                                                 │
│                                                             │
│   Measures the STRENGTH of association (effect size)       │
│   for chi-square test of independence/homogeneity          │
│                                                             │
│              ┌─────────────                                 │
│             │     χ²                                        │
│   V =      │ ─────────────                                  │
│           √  n × (k - 1)                                    │
│                                                             │
│   Where:                                                    │
│   • χ² = chi-square statistic                              │
│   • n = total sample size                                  │
│   • k = min(rows, columns)                                 │
│                                                             │
│   INTERPRETATION:                                           │
│   V ≈ 0.1: Small effect                                    │
│   V ≈ 0.3: Medium effect                                   │
│   V ≈ 0.5: Large effect                                    │
│                                                             │
│   Range: 0 (no association) to 1 (perfect association)     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Example: Smoking and Cancer Effect Size

```
χ² = 75.63
n = 1000
k = min(2, 2) = 2

V = √(75.63 / (1000 × (2-1)))
  = √(75.63 / 1000)
  = √0.07563
  = 0.275

V ≈ 0.28 → Medium effect size

There's a moderately strong association between 
smoking and lung cancer.
```

---

## Chi-Square vs Other Tests

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   WHEN TO USE WHAT?                                              │
│                                                                  │
│   CHI-SQUARE TEST:                                               │
│   • Categorical variables (counts/frequencies)                  │
│   • Comparing observed vs expected distributions               │
│   • Testing independence/homogeneity                           │
│                                                                  │
│   T-TEST / Z-TEST:                                               │
│   • Continuous variables (means)                                │
│   • Comparing group means                                       │
│                                                                  │
│   FISHER'S EXACT TEST:                                           │
│   • 2×2 tables with small expected counts (< 5)               │
│   • More accurate than chi-square for small samples            │
│                                                                  │
│   MCNEMAR'S TEST:                                                │
│   • Paired categorical data (before/after)                     │
│   • Same subjects measured twice                                │
│                                                                  │
│   G-TEST (Likelihood Ratio):                                    │
│   • Alternative to chi-square                                   │
│   • Better for small samples or sparse data                    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Python Implementation

### Complete Chi-Square Functions

```python
import numpy as np
from scipy import stats

def chi_square_goodness_of_fit(observed, expected=None, alpha=0.05):
    """
    Chi-Square Goodness of Fit Test
    
    Parameters:
    - observed: list/array of observed frequencies
    - expected: list/array of expected frequencies (default: equal)
    - alpha: significance level
    """
    observed = np.array(observed)
    n = observed.sum()
    k = len(observed)
    
    if expected is None:
        expected = np.array([n/k] * k)
    else:
        expected = np.array(expected)
    
    # Check condition
    if (expected < 5).any():
        print("⚠️ Warning: Some expected frequencies < 5")
    
    # Calculate chi-square
    chi_sq = np.sum((observed - expected)**2 / expected)
    
    # Degrees of freedom
    df = k - 1
    
    # p-value
    p_value = 1 - stats.chi2.cdf(chi_sq, df)
    
    # Critical value
    chi_critical = stats.chi2.ppf(1 - alpha, df)
    
    # Decision
    reject = chi_sq > chi_critical
    
    return {
        'chi_square': chi_sq,
        'df': df,
        'p_value': p_value,
        'chi_critical': chi_critical,
        'reject_null': reject,
        'observed': observed,
        'expected': expected
    }

# Example: Die fairness
observed = [89, 95, 105, 115, 108, 88]
result = chi_square_goodness_of_fit(observed)

print("=" * 50)
print("CHI-SQUARE GOODNESS OF FIT TEST")
print("=" * 50)
print(f"Observed: {result['observed']}")
print(f"Expected: {result['expected']}")
print(f"\nχ² = {result['chi_square']:.4f}")
print(f"df = {result['df']}")
print(f"p-value = {result['p_value']:.4f}")
print(f"Critical value (α=0.05) = {result['chi_critical']:.4f}")
print(f"Decision: {'Reject H₀' if result['reject_null'] else 'Fail to reject H₀'}")
```

### Test of Independence

```python
import numpy as np
from scipy import stats

def chi_square_independence(contingency_table, alpha=0.05):
    """
    Chi-Square Test of Independence
    
    Parameters:
    - contingency_table: 2D array of observed frequencies
    - alpha: significance level
    """
    observed = np.array(contingency_table)
    rows, cols = observed.shape
    n = observed.sum()
    
    # Row and column totals
    row_totals = observed.sum(axis=1)
    col_totals = observed.sum(axis=0)
    
    # Expected frequencies
    expected = np.outer(row_totals, col_totals) / n
    
    # Check condition
    if (expected < 5).any():
        print("⚠️ Warning: Some expected frequencies < 5")
        print(f"   Cells with E < 5: {(expected < 5).sum()}")
    
    # Calculate chi-square
    chi_sq = np.sum((observed - expected)**2 / expected)
    
    # Degrees of freedom
    df = (rows - 1) * (cols - 1)
    
    # p-value
    p_value = 1 - stats.chi2.cdf(chi_sq, df)
    
    # Critical value
    chi_critical = stats.chi2.ppf(1 - alpha, df)
    
    # Effect size (Cramér's V)
    cramers_v = np.sqrt(chi_sq / (n * (min(rows, cols) - 1)))
    
    # Decision
    reject = chi_sq > chi_critical
    
    return {
        'chi_square': chi_sq,
        'df': df,
        'p_value': p_value,
        'chi_critical': chi_critical,
        'cramers_v': cramers_v,
        'reject_null': reject,
        'observed': observed,
        'expected': expected
    }

# Example: Smoking and Lung Cancer
observed = np.array([
    [90, 210],   # Smoker: Cancer, No Cancer
    [60, 640]    # Non-Smoker: Cancer, No Cancer
])

result = chi_square_independence(observed)

print("\n" + "=" * 50)
print("CHI-SQUARE TEST OF INDEPENDENCE")
print("=" * 50)
print("Observed frequencies:")
print(result['observed'])
print("\nExpected frequencies:")
print(result['expected'].round(2))
print(f"\nχ² = {result['chi_square']:.4f}")
print(f"df = {result['df']}")
print(f"p-value = {result['p_value']:.6f}")
print(f"Critical value (α=0.05) = {result['chi_critical']:.4f}")
print(f"Cramér's V = {result['cramers_v']:.4f} (effect size)")
print(f"Decision: {'Reject H₀' if result['reject_null'] else 'Fail to reject H₀'}")

# Using scipy directly
chi2, p, dof, expected = stats.chi2_contingency(observed)
print(f"\nScipy verification: χ²={chi2:.4f}, p={p:.6f}")
```

### Visualization

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_chi_square(df_values=[1, 3, 5, 10], x_max=20):
    """Visualize chi-square distributions with different df"""
    
    fig, ax = plt.subplots(figsize=(12, 6))
    
    x = np.linspace(0.01, x_max, 500)
    
    for df in df_values:
        y = stats.chi2.pdf(x, df)
        ax.plot(x, y, linewidth=2, label=f'df = {df}')
    
    ax.set_xlabel('χ²', fontsize=12)
    ax.set_ylabel('Probability Density', fontsize=12)
    ax.set_title('Chi-Square Distribution for Various Degrees of Freedom', fontsize=14)
    ax.legend()
    ax.grid(True, alpha=0.3)
    ax.set_xlim(0, x_max)
    ax.set_ylim(0, 0.5)
    
    plt.tight_layout()
    plt.show()

def visualize_test_result(chi_sq, df, alpha=0.05):
    """Visualize chi-square test result"""
    
    fig, ax = plt.subplots(figsize=(12, 6))
    
    chi_critical = stats.chi2.ppf(1 - alpha, df)
    x = np.linspace(0.01, max(chi_sq * 1.5, chi_critical * 1.5), 500)
    y = stats.chi2.pdf(x, df)
    
    # Plot distribution
    ax.plot(x, y, 'b-', linewidth=2, label=f'χ² distribution (df={df})')
    ax.fill_between(x, y, alpha=0.1)
    
    # Rejection region
    x_reject = x[x >= chi_critical]
    y_reject = stats.chi2.pdf(x_reject, df)
    ax.fill_between(x_reject, y_reject, color='red', alpha=0.4, 
                    label=f'Rejection region (α={alpha})')
    
    # Critical value
    ax.axvline(chi_critical, color='red', linestyle='--', linewidth=1.5,
               label=f'Critical value = {chi_critical:.3f}')
    
    # Test statistic
    ax.axvline(chi_sq, color='green', linewidth=2.5,
               label=f'χ² = {chi_sq:.3f}')
    
    # p-value
    p_value = 1 - stats.chi2.cdf(chi_sq, df)
    decision = "REJECT H₀" if chi_sq > chi_critical else "FAIL TO REJECT H₀"
    
    ax.set_xlabel('χ²', fontsize=12)
    ax.set_ylabel('Density', fontsize=12)
    ax.set_title(f'Chi-Square Test Result: {decision}\np-value = {p_value:.4f}', fontsize=14)
    ax.legend()
    ax.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()

# Visualize
visualize_chi_square()
visualize_test_result(chi_sq=75.63, df=1)
```

---

## Common Mistakes to Avoid ⚠️

### Mistake 1: Using Percentages Instead of Counts

```
❌ WRONG: Using percentages or proportions in the table

✅ CORRECT: Always use raw counts (frequencies)

Chi-square requires COUNTS, not percentages!
```

### Mistake 2: Ignoring Expected Count Condition

```
❌ WRONG: Running chi-square when expected counts < 5

✅ CORRECT: 
   • Combine categories
   • Use Fisher's Exact Test (for 2×2)
   • Report the violation
```

### Mistake 3: Confusing Independence with No Effect

```
❌ WRONG: "Chi-square proves smoking CAUSES cancer"

✅ CORRECT: Chi-square shows ASSOCIATION, not causation

The test shows variables are related, but can't prove
one causes the other!
```

### Mistake 4: Using Chi-Square for Continuous Data

```
❌ WRONG: Applying chi-square to continuous variables

✅ CORRECT: Use t-test or ANOVA for continuous data

Chi-square is for categorical data only!
```

### Mistake 5: Dependent Observations

```
❌ WRONG: Same person counted in multiple cells

✅ CORRECT: Each subject appears in exactly ONE cell

If observations are paired/matched, use McNemar's test.
```

---

## Practice Problems 📝

### Problem 1: Goodness of Fit
A bag claims to have equal numbers of red, blue, green, and yellow candies. You sample 200 candies: 60 red, 45 blue, 55 green, 40 yellow. At α = 0.05, is the claim accurate?

<details>
<summary>Click for Solution</summary>

```
H₀: Colors are equally distributed (25% each)
H₁: Colors are not equally distributed
α = 0.05

Expected: 200 × 0.25 = 50 for each color

| Color  | O  | E  | (O-E)²/E |
|--------|----|----|----------|
| Red    | 60 | 50 | 2.00     |
| Blue   | 45 | 50 | 0.50     |
| Green  | 55 | 50 | 0.50     |
| Yellow | 40 | 50 | 2.00     |
| Total  |200 |200 | χ²= 5.00 |

df = 4 - 1 = 3
χ²_critical (α=0.05, df=3) = 7.815
p-value ≈ 0.172

χ² = 5.00 < 7.815 → FAIL TO REJECT H₀

Conclusion: Insufficient evidence to reject the claim 
that colors are equally distributed.
```

</details>

---

### Problem 2: Test of Independence
Is there a relationship between exercise frequency and stress level?

```
              │ Low Stress │ High Stress │ Total
──────────────┼────────────┼─────────────┼───────
Never         │     30     │     70      │  100
Sometimes     │     50     │     50      │  100
Regular       │     70     │     30      │  100
──────────────┼────────────┼─────────────┼───────
Total         │    150     │    150      │  300
```

<details>
<summary>Click for Solution</summary>

```
H₀: Exercise frequency and stress are independent
H₁: Exercise frequency and stress are related
α = 0.05

Expected frequencies (each cell):
E = (Row Total × Col Total) / 300 = (100 × 150) / 300 = 50

| Cell              | O  | E  | (O-E)²/E |
|-------------------|----|----|----------|
| Never + Low       | 30 | 50 | 8.00     |
| Never + High      | 70 | 50 | 8.00     |
| Sometimes + Low   | 50 | 50 | 0.00     |
| Sometimes + High  | 50 | 50 | 0.00     |
| Regular + Low     | 70 | 50 | 8.00     |
| Regular + High    | 30 | 50 | 8.00     |
| Total             |300 |300 | χ²=32.00 |

df = (3-1)(2-1) = 2
χ²_critical (α=0.05, df=2) = 5.991
p-value < 0.0001

χ² = 32.00 >> 5.991 → REJECT H₀

Conclusion: There IS a significant relationship between 
exercise frequency and stress level.

• Never exercise: 70% high stress
• Regular exercise: 30% high stress

Regular exercise is associated with lower stress!
```

</details>

---

### Problem 3: Degrees of Freedom
For a 4×3 contingency table, what are the degrees of freedom?

<details>
<summary>Click for Solution</summary>

```
df = (rows - 1) × (columns - 1)
   = (4 - 1) × (3 - 1)
   = 3 × 2
   = 6

Answer: df = 6
```

</details>

---

### Problem 4: Effect Size
Given χ² = 25, n = 400, for a 3×3 table, calculate Cramér's V and interpret it.

<details>
<summary>Click for Solution</summary>

```
V = √(χ² / (n × (k - 1)))
  = √(25 / (400 × (3 - 1)))
  = √(25 / 800)
  = √0.03125
  = 0.177

V ≈ 0.18

Interpretation: Small to medium effect size

There is a statistically significant but relatively 
weak association between the variables.
```

</details>

---

## Summary: The Essence of Chi-Square

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│                    CHI-SQUARE TEST                               │
│                    ═══════════════                               │
│                                                                  │
│   THE FORMULA:                                                   │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │              (Observed - Expected)²                      │   │
│   │       χ² = Σ ──────────────────────                      │   │
│   │                   Expected                               │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   THREE TYPES:                                                   │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  1. Goodness of Fit: Does data match distribution?      │   │
│   │     df = k - 1                                          │   │
│   │                                                          │   │
│   │  2. Independence: Are two variables related?            │   │
│   │     df = (r-1)(c-1)                                     │   │
│   │                                                          │   │
│   │  3. Homogeneity: Same distribution across groups?       │   │
│   │     df = (r-1)(c-1)                                     │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   CONDITIONS:                                                    │
│   • Random sample                                               │
│   • Independent observations                                     │
│   • Expected frequencies ≥ 5                                    │
│   • Categorical data                                            │
│                                                                  │
│   KEY INSIGHT:                                                   │
│   Large χ² → Observed very different from Expected             │
│           → Evidence against H₀                                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────────┐
│                     CHI-SQUARE QUICK REFERENCE                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   FORMULA: χ² = Σ (O - E)² / E                                  │
│                                                                  │
│   EXPECTED (Independence):                                       │
│   E = (Row Total × Col Total) / Grand Total                     │
│                                                                  │
│   DEGREES OF FREEDOM:                                            │
│   • Goodness of Fit: df = k - 1                                 │
│   • Independence/Homogeneity: df = (r-1)(c-1)                   │
│                                                                  │
│   CRITICAL VALUES (α = 0.05):                                    │
│   df=1: 3.841 │ df=2: 5.991 │ df=3: 7.815 │ df=4: 9.488        │
│                                                                  │
│   EFFECT SIZE (Cramér's V):                                      │
│   V = √(χ² / (n × (k-1)))                                       │
│   Small: ~0.1 │ Medium: ~0.3 │ Large: ~0.5                      │
│                                                                  │
│   DECISION: Reject H₀ if χ² > χ²_critical                       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

> **"The chi-square test is elegantly simple: compare what you observed to what you expected. If the difference is too large to be explained by chance, something interesting is going on!"**

From testing dice fairness to discovering medical associations, the chi-square test is the go-to tool for categorical data! 📊

---

*From observed to expected, from counts to conclusions — that's the power of chi-square!* 🎲
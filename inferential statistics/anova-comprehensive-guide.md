# ANOVA (Analysis of Variance)
## Comparing Means Across Multiple Groups 📊

---

## What is ANOVA?

ANOVA (Analysis of Variance) is a statistical test used to compare means across **three or more groups**. Despite its name focusing on "variance," ANOVA actually tests whether group means are equal.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ANOVA: ANALYSIS OF VARIANCE                                │
│                                                             │
│   Purpose:                                                  │
│   Test whether the means of 3 or more groups are equal     │
│                                                             │
│   The Key Question:                                         │
│   "Is there a significant difference between group means?" │
│                                                             │
│   H₀: μ₁ = μ₂ = μ₃ = ... = μₖ (all means are equal)       │
│   H₁: At least one mean is different                       │
│                                                             │
│   Why not multiple t-tests?                                │
│   • 3 groups → 3 t-tests → inflated Type I error          │
│   • 5 groups → 10 t-tests → even worse!                   │
│   • ANOVA controls the overall error rate                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: The Teaching Methods Experiment

Professor Anika wants to compare three teaching methods for her statistics course:
- **Method A:** Traditional lectures
- **Method B:** Flipped classroom  
- **Method C:** Problem-based learning

She randomly assigns 30 students (10 per method) and measures their final exam scores.

**Question:** Is there a significant difference in exam performance across teaching methods?

```
Method A (Lecture):     72, 75, 78, 71, 74, 76, 73, 77, 75, 74
Method B (Flipped):     82, 85, 79, 88, 84, 86, 81, 83, 87, 85
Method C (Problem):     78, 81, 76, 82, 79, 80, 77, 83, 81, 78

Means:
• Method A: X̄₁ = 74.5
• Method B: X̄₂ = 84.0
• Method C: X̄₃ = 79.5
• Grand Mean: X̄ = 79.33
```

---

## Why Not Multiple t-Tests?

### The Multiple Comparison Problem

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE PROBLEM WITH MULTIPLE T-TESTS                          │
│                                                             │
│   For k groups, you need C(k,2) = k(k-1)/2 comparisons:    │
│                                                             │
│   3 groups → 3 comparisons  (A vs B, A vs C, B vs C)       │
│   4 groups → 6 comparisons                                 │
│   5 groups → 10 comparisons                                │
│   10 groups → 45 comparisons!                              │
│                                                             │
│   INFLATED TYPE I ERROR:                                    │
│   If α = 0.05 for each test:                               │
│                                                             │
│   P(at least one false positive) = 1 - (1-α)^c             │
│                                                             │
│   3 comparisons: 1 - (0.95)³ = 0.143 (14.3%!)             │
│   5 comparisons: 1 - (0.95)⁵ = 0.226 (22.6%!)             │
│   10 comparisons: 1 - (0.95)¹⁰ = 0.401 (40.1%!)           │
│                                                             │
│   ANOVA solves this by testing ALL groups at once!         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Logic of ANOVA

### Comparing Two Types of Variance

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE ANOVA LOGIC                                            │
│                                                             │
│   ANOVA compares two sources of variability:               │
│                                                             │
│   1. BETWEEN-GROUP VARIANCE (Treatment Effect)             │
│      How much do GROUP MEANS differ from the GRAND MEAN?   │
│      If treatments have an effect, this will be LARGE      │
│                                                             │
│   2. WITHIN-GROUP VARIANCE (Random Error)                  │
│      How much do INDIVIDUAL SCORES vary within each group? │
│      This is natural variability (noise)                   │
│                                                             │
│   THE QUESTION:                                             │
│   Is between-group variance LARGER than we'd expect        │
│   from random chance (within-group variance)?              │
│                                                             │
│              Between-Group Variance                         │
│   F-ratio = ─────────────────────────                       │
│              Within-Group Variance                          │
│                                                             │
│   If F is LARGE → Group means are significantly different  │
│   If F is SMALL → Differences are just random noise        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: The Two Types of Variance

```
    SCENARIO 1: No Treatment Effect (H₀ True)
    Between-group variance ≈ Within-group variance
    
    Group A      Group B      Group C
       ●            ●            ●
      ●●●          ●●●          ●●●
     ●●●●●        ●●●●●        ●●●●●
    ───────────────────────────────────
    Means are similar, lots of overlap
    F-ratio will be SMALL


    SCENARIO 2: Strong Treatment Effect (H₁ True)
    Between-group variance >> Within-group variance
    
    Group A           Group B           Group C
       ●                                    
      ●●●                ●                  ●
     ●●●●●              ●●●                ●●●
    ─────────         ●●●●●              ●●●●●
                     ─────────          ─────────
    Means are very different, little overlap
    F-ratio will be LARGE
```

---

# Partitioning of Variance in ANOVA

## The Fundamental Equation

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   PARTITIONING OF TOTAL VARIANCE                             │
│                                                             │
│           SST = SSB + SSW                                   │
│                                                             │
│   Total Sum    Between-Group    Within-Group                │
│   of Squares = Sum of Squares + Sum of Squares              │
│                                                             │
│   Or equivalently:                                          │
│                                                             │
│   SS_Total = SS_Treatment + SS_Error                        │
│                                                             │
│   TOTAL VARIABILITY = EXPLAINED + UNEXPLAINED              │
│                       (by groups)  (random error)          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Partitioning Variance

```
                    TOTAL VARIANCE (SST)
    ════════════════════════════════════════════════
    
    ┌────────────────────────┬─────────────────────┐
    │                        │                     │
    │   BETWEEN-GROUP (SSB)  │  WITHIN-GROUP (SSW) │
    │                        │                     │
    │   Variance due to      │  Variance due to    │
    │   group differences    │  individual         │
    │   (treatment effect)   │  differences        │
    │                        │  (random error)     │
    │                        │                     │
    │   "Signal"             │  "Noise"            │
    │                        │                     │
    └────────────────────────┴─────────────────────┘
    
    F = MSB/MSW = Signal/Noise
    
    Large F → Signal > Noise → Reject H₀
```

---

## The Formulas

### Sum of Squares Calculations

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SUM OF SQUARES FORMULAS                                    │
│                                                             │
│   TOTAL SUM OF SQUARES (SST):                               │
│   ─────────────────────────────                             │
│   SST = Σᵢ Σⱼ (Xᵢⱼ - X̄)²                                   │
│                                                             │
│   Sum of squared deviations of ALL observations             │
│   from the GRAND MEAN                                       │
│                                                             │
│   ─────────────────────────────────────────────────────     │
│                                                             │
│   BETWEEN-GROUP SUM OF SQUARES (SSB):                       │
│   ────────────────────────────────────                      │
│   SSB = Σᵢ nᵢ(X̄ᵢ - X̄)²                                     │
│                                                             │
│   Sum of squared deviations of GROUP MEANS                  │
│   from the GRAND MEAN (weighted by group size)             │
│                                                             │
│   ─────────────────────────────────────────────────────     │
│                                                             │
│   WITHIN-GROUP SUM OF SQUARES (SSW):                        │
│   ───────────────────────────────────                       │
│   SSW = Σᵢ Σⱼ (Xᵢⱼ - X̄ᵢ)²                                  │
│                                                             │
│   Sum of squared deviations of observations                │
│   from their OWN GROUP MEAN                                │
│                                                             │
│   SSW = SST - SSB (by definition)                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Mean Squares and F-Ratio

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MEAN SQUARES (Variance Estimates)                          │
│                                                             │
│              SSB                                            │
│   MSB = ───────────                                         │
│           k - 1                                             │
│                                                             │
│   (k = number of groups)                                   │
│   (k - 1 = between-group degrees of freedom)               │
│                                                             │
│              SSW                                            │
│   MSW = ───────────                                         │
│           N - k                                             │
│                                                             │
│   (N = total sample size)                                  │
│   (N - k = within-group degrees of freedom)                │
│                                                             │
│   ─────────────────────────────────────────────────────     │
│                                                             │
│   F-STATISTIC:                                              │
│                                                             │
│         MSB     Between-group variance estimate            │
│   F = ───── = ─────────────────────────────────            │
│         MSW     Within-group variance estimate             │
│                                                             │
│   F follows F-distribution with df₁ = k-1, df₂ = N-k       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Complete Example: Teaching Methods

### Step-by-Step Calculation

```
Data:
Method A (n₁=10): 72, 75, 78, 71, 74, 76, 73, 77, 75, 74  → X̄₁ = 74.5
Method B (n₂=10): 82, 85, 79, 88, 84, 86, 81, 83, 87, 85  → X̄₂ = 84.0
Method C (n₃=10): 78, 81, 76, 82, 79, 80, 77, 83, 81, 78  → X̄₃ = 79.5

Grand Mean: X̄ = (74.5 + 84.0 + 79.5)/3 = 79.33
Total N = 30, k = 3
```

### Step 1: Calculate SSB (Between-Group)

```
SSB = Σ nᵢ(X̄ᵢ - X̄)²

SSB = 10(74.5 - 79.33)² + 10(84.0 - 79.33)² + 10(79.5 - 79.33)²
    = 10(-4.83)² + 10(4.67)² + 10(0.17)²
    = 10(23.33) + 10(21.81) + 10(0.03)
    = 233.3 + 218.1 + 0.3
    = 451.7

SSB = 451.7
```

### Step 2: Calculate SSW (Within-Group)

```
SSW = Σᵢ Σⱼ (Xᵢⱼ - X̄ᵢ)²

For Method A (X̄₁ = 74.5):
(72-74.5)² + (75-74.5)² + ... + (74-74.5)²
= 6.25 + 0.25 + 12.25 + 12.25 + 0.25 + 2.25 + 2.25 + 6.25 + 0.25 + 0.25
= 42.5

For Method B (X̄₂ = 84.0):
= 4 + 1 + 25 + 16 + 0 + 4 + 9 + 1 + 9 + 1 = 70.0

For Method C (X̄₃ = 79.5):
= 2.25 + 2.25 + 12.25 + 6.25 + 0.25 + 0.25 + 6.25 + 12.25 + 2.25 + 2.25
= 46.5

SSW = 42.5 + 70.0 + 46.5 = 159.0
```

### Step 3: Calculate SST (Total)

```
SST = SSB + SSW = 451.7 + 159.0 = 610.7
```

### Step 4: Calculate Mean Squares

```
df_between = k - 1 = 3 - 1 = 2
df_within = N - k = 30 - 3 = 27

MSB = SSB / df_between = 451.7 / 2 = 225.85
MSW = SSW / df_within = 159.0 / 27 = 5.89
```

### Step 5: Calculate F-Ratio

```
F = MSB / MSW = 225.85 / 5.89 = 38.35
```

### Step 6: Find Critical Value and P-Value

```
df₁ = 2, df₂ = 27, α = 0.05

F_critical = 3.35 (from F-table)
p-value < 0.0001

F = 38.35 >> F_critical = 3.35 → REJECT H₀!
```

### The ANOVA Table

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│   ANOVA TABLE: Teaching Methods Example                          │
│                                                                  │
│   Source      │  SS     │  df  │   MS    │   F    │  p-value    │
│   ────────────┼─────────┼──────┼─────────┼────────┼─────────    │
│   Between     │ 451.7   │  2   │ 225.85  │ 38.35  │ < 0.0001   │
│   (Treatment) │         │      │         │        │             │
│   ────────────┼─────────┼──────┼─────────┼────────┼─────────    │
│   Within      │ 159.0   │  27  │  5.89   │        │             │
│   (Error)     │         │      │         │        │             │
│   ────────────┼─────────┼──────┼─────────┼────────┼─────────    │
│   Total       │ 610.7   │  29  │         │        │             │
│                                                                  │
│   Conclusion: Teaching methods significantly affect exam scores  │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## Effect Size: η² (Eta-Squared)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ETA-SQUARED (η²)                                           │
│                                                             │
│         SSB     Between-group variance                      │
│   η² = ───── = ──────────────────────                       │
│         SST        Total variance                           │
│                                                             │
│   For our example:                                          │
│   η² = 451.7 / 610.7 = 0.74                                │
│                                                             │
│   74% of variance is explained by teaching method!         │
│                                                             │
│   INTERPRETATION:                                           │
│   η² < 0.01: Negligible effect                             │
│   η² ≈ 0.01-0.06: Small effect                             │
│   η² ≈ 0.06-0.14: Medium effect                            │
│   η² > 0.14: Large effect                                  │
│                                                             │
│   η² = 0.74 is a VERY LARGE effect!                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

# Assumptions of ANOVA

## The Four Key Assumptions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ASSUMPTIONS OF ANOVA                                       │
│                                                             │
│   1. INDEPENDENCE                                           │
│   2. NORMALITY                                              │
│   3. HOMOGENEITY OF VARIANCES (Homoscedasticity)           │
│   4. RANDOM SAMPLING                                        │
│                                                             │
│   Mnemonic: "I Never Have Rats"                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Assumption 1: Independence

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   INDEPENDENCE                                               │
│                                                             │
│   Definition:                                               │
│   Observations must be independent of each other           │
│   • Within groups: subjects don't influence each other     │
│   • Between groups: groups don't influence each other      │
│                                                             │
│   Violations:                                               │
│   • Repeated measures on same subjects                     │
│   • Clustered data (students in classrooms)               │
│   • Time series data                                        │
│                                                             │
│   How to check:                                             │
│   • Study design (was randomization proper?)               │
│   • Durbin-Watson test for autocorrelation                 │
│                                                             │
│   If violated:                                              │
│   • Use Repeated Measures ANOVA                            │
│   • Use Mixed-Effects Models                               │
│                                                             │
│   SEVERITY: Most critical assumption!                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Assumption 2: Normality

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   NORMALITY                                                  │
│                                                             │
│   Definition:                                               │
│   The dependent variable should be approximately           │
│   normally distributed WITHIN each group                   │
│                                                             │
│   How to check:                                             │
│   • Visual: Histograms, Q-Q plots                         │
│   • Statistical: Shapiro-Wilk test, K-S test              │
│                                                             │
│   If violated:                                              │
│   • Transform data (log, sqrt, Box-Cox)                   │
│   • Use non-parametric alternative (Kruskal-Wallis)       │
│   • ANOVA is robust with n > 30 per group (CLT)           │
│                                                             │
│   ROBUSTNESS:                                               │
│   ANOVA is fairly robust to normality violations with:    │
│   • Equal sample sizes                                     │
│   • Large samples (n > 30 per group)                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Checking Normality

```
NORMAL (Good):              SKEWED (Problematic):
    
    ╭───╮                          ╭───╮
  ╭─╯   ╰─╮                       ╭╯   ╰───╮
 ╭╯       ╰╮                     ╭╯         ╰───╮
╭╯         ╰╮                   ╭╯              ╰───
──────────────                  ────────────────────
```

---

## Assumption 3: Homogeneity of Variances

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   HOMOGENEITY OF VARIANCES (Homoscedasticity)                │
│                                                             │
│   Definition:                                               │
│   The variance should be approximately equal across groups │
│                                                             │
│   σ₁² ≈ σ₂² ≈ σ₃² ≈ ... ≈ σₖ²                              │
│                                                             │
│   How to check:                                             │
│   • Visual: Box plots (similar spread?)                   │
│   • Levene's Test (robust to non-normality)               │
│   • Bartlett's Test (sensitive to non-normality)          │
│   • Rule of thumb: largest s² / smallest s² < 4           │
│                                                             │
│   If violated:                                              │
│   • Welch's ANOVA (does not assume equal variances)       │
│   • Transform data                                         │
│   • Kruskal-Wallis test                                    │
│                                                             │
│   ROBUSTNESS:                                               │
│   ANOVA is robust if:                                       │
│   • Sample sizes are equal                                 │
│   • Variance ratio < 4:1                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Homogeneity Check

```
GOOD (Equal Variances):           BAD (Unequal Variances):

Group A  ├────[██████]────┤       Group A  ├─[██]─┤
Group B  ├────[██████]────┤       Group B  ├────[████████]────┤
Group C  ├────[██████]────┤       Group C  ├──[████]──┤

Similar spread = OK               Different spreads = Problem!
```

---

## Assumption 4: Random Sampling

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   RANDOM SAMPLING / RANDOM ASSIGNMENT                        │
│                                                             │
│   Definition:                                               │
│   • Subjects randomly selected from population, OR         │
│   • Subjects randomly assigned to treatment groups         │
│                                                             │
│   Why it matters:                                           │
│   • Ensures groups are comparable at baseline              │
│   • Allows causal inference (with random assignment)      │
│   • Avoids selection bias                                  │
│                                                             │
│   If violated:                                              │
│   • Include covariates (ANCOVA)                           │
│   • Use matching/propensity scores                        │
│   • Interpret with caution (association, not causation)   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Assumption Summary Table

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   ASSUMPTION       │ HOW TO CHECK      │ IF VIOLATED              │
│   ─────────────────┼───────────────────┼──────────────────────    │
│   Independence     │ Study design      │ Repeated Measures        │
│                    │ Durbin-Watson     │ ANOVA, Mixed Models      │
│   ─────────────────┼───────────────────┼──────────────────────    │
│   Normality        │ Shapiro-Wilk      │ Transform, Kruskal-      │
│                    │ Q-Q plots         │ Wallis, or proceed       │
│                    │ Histograms        │ if n > 30                │
│   ─────────────────┼───────────────────┼──────────────────────    │
│   Homogeneity of   │ Levene's test     │ Welch's ANOVA,          │
│   Variances        │ Box plots         │ Transform, Kruskal-      │
│                    │ Variance ratio    │ Wallis                   │
│   ─────────────────┼───────────────────┼──────────────────────    │
│   Random Sampling  │ Study design      │ ANCOVA, propensity      │
│                    │ Baseline compare  │ matching, caution       │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

# Types of ANOVA

## Overview of ANOVA Types

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TYPES OF ANOVA                                             │
│                                                             │
│   1. ONE-WAY ANOVA                                          │
│      One independent variable (factor)                     │
│      Example: Effect of teaching method on scores          │
│                                                             │
│   2. TWO-WAY ANOVA (Factorial ANOVA)                        │
│      Two independent variables                             │
│      Example: Effect of teaching method AND gender         │
│                                                             │
│   3. REPEATED MEASURES ANOVA                                │
│      Same subjects measured multiple times                 │
│      Example: Scores at Week 1, Week 4, Week 8            │
│                                                             │
│   4. MIXED ANOVA (Split-Plot)                              │
│      Combines between-subjects and within-subjects        │
│      Example: Treatment (between) × Time (within)         │
│                                                             │
│   5. MANOVA (Multivariate ANOVA)                           │
│      Multiple dependent variables                          │
│      Example: Effect on both scores AND satisfaction      │
│                                                             │
│   6. ANCOVA (Analysis of Covariance)                       │
│      Includes continuous covariate                         │
│      Example: Controlling for prior GPA                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type 1: One-Way ANOVA

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ONE-WAY ANOVA                                              │
│                                                             │
│   Structure:                                                │
│   • One categorical independent variable (factor)          │
│   • One continuous dependent variable                      │
│   • 3 or more groups (levels)                              │
│                                                             │
│   Hypotheses:                                               │
│   H₀: μ₁ = μ₂ = μ₃ = ... = μₖ                              │
│   H₁: At least one μᵢ is different                         │
│                                                             │
│   Example:                                                  │
│   Factor: Drug type (Drug A, Drug B, Placebo)              │
│   DV: Blood pressure reduction                             │
│                                                             │
│   Design:                                                   │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐                   │
│   │ Drug A  │  │ Drug B  │  │ Placebo │                   │
│   │  ●●●●●  │  │  ●●●●●  │  │  ●●●●●  │                   │
│   │  ●●●●●  │  │  ●●●●●  │  │  ●●●●●  │                   │
│   └─────────┘  └─────────┘  └─────────┘                   │
│   Compare means across groups                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type 2: Two-Way ANOVA (Factorial)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TWO-WAY ANOVA                                              │
│                                                             │
│   Structure:                                                │
│   • Two categorical independent variables (factors)        │
│   • One continuous dependent variable                      │
│   • Tests MAIN EFFECTS and INTERACTION                     │
│                                                             │
│   Three Hypotheses:                                         │
│   1. Main Effect A: Are row means equal?                   │
│   2. Main Effect B: Are column means equal?                │
│   3. Interaction A×B: Does effect of A depend on B?        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Two-Way ANOVA Design

```
Example: Effect of Teaching Method AND Gender on Scores

                        GENDER
                    Male      Female
              ┌──────────┬──────────┐
    Method A  │  Cell 11 │  Cell 12 │
              ├──────────┼──────────┤
TEACHING      │  Cell 21 │  Cell 22 │
METHOD  B     ├──────────┼──────────┤
              │  Cell 31 │  Cell 32 │
    Method C  └──────────┴──────────┘

This is a 3 × 2 factorial design

MAIN EFFECT of Method: Do methods differ (ignoring gender)?
MAIN EFFECT of Gender: Do genders differ (ignoring method)?
INTERACTION: Does the effect of method depend on gender?
```

### Understanding Interaction

```
NO INTERACTION:                   INTERACTION PRESENT:
(Lines are parallel)              (Lines cross or converge)

Score │                           Score │
   90 │  ●────────────●              90 │        ●────●
      │  ●────────────●                  │     ●──
   80 │                              80 │  ●──    ──────●
      │  ●────────────●                  │        
   70 │                              70 │  ●────────────●
      └────────────────              └────────────────
        Male    Female                   Male    Female

Effect of method is the            Effect of method is
SAME for both genders              DIFFERENT for each gender
```

### Two-Way ANOVA Table

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   Source          │  SS     │  df       │   MS    │   F        │
│   ────────────────┼─────────┼───────────┼─────────┼────────    │
│   Factor A        │  SSₐ    │  a - 1    │  MSₐ    │ MSₐ/MSₑ   │
│   Factor B        │  SSᵦ    │  b - 1    │  MSᵦ    │ MSᵦ/MSₑ   │
│   Interaction A×B │  SSₐᵦ   │(a-1)(b-1) │  MSₐᵦ   │ MSₐᵦ/MSₑ  │
│   Error           │  SSₑ    │ N - ab    │  MSₑ    │            │
│   ────────────────┼─────────┼───────────┼─────────┼────────    │
│   Total           │  SSₜ    │  N - 1    │         │            │
│                                                                 │
│   Total SS = SSₐ + SSᵦ + SSₐᵦ + SSₑ                            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Type 3: Repeated Measures ANOVA

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   REPEATED MEASURES ANOVA                                    │
│                                                             │
│   Structure:                                                │
│   • Same subjects measured at MULTIPLE time points         │
│   • Or same subjects under MULTIPLE conditions             │
│   • Each subject serves as their own control               │
│                                                             │
│   Design:                                                   │
│   Subject │  Time 1  │  Time 2  │  Time 3                  │
│   ────────┼──────────┼──────────┼──────────                │
│   S1      │    72    │    78    │    85                    │
│   S2      │    68    │    75    │    82                    │
│   S3      │    75    │    80    │    88                    │
│   ...     │   ...    │   ...    │   ...                    │
│                                                             │
│   Advantages:                                               │
│   • More powerful (controls individual differences)        │
│   • Requires fewer subjects                                │
│                                                             │
│   Additional Assumption: SPHERICITY                         │
│   • Variances of differences between conditions are equal  │
│   • Test with Mauchly's test                              │
│   • If violated: use Greenhouse-Geisser correction        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type 4: Mixed ANOVA (Split-Plot)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MIXED ANOVA                                                │
│                                                             │
│   Structure:                                                │
│   • At least one BETWEEN-subjects factor                   │
│   • At least one WITHIN-subjects factor                    │
│                                                             │
│   Example:                                                  │
│   Between-subjects: Treatment (Drug vs Placebo)            │
│   Within-subjects: Time (Week 1, Week 4, Week 8)          │
│                                                             │
│   Tests:                                                    │
│   • Main effect of Treatment (between)                    │
│   • Main effect of Time (within)                          │
│   • Treatment × Time interaction                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type 5: MANOVA (Multivariate ANOVA)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   MANOVA: MULTIVARIATE ANOVA                                 │
│                                                             │
│   Structure:                                                │
│   • One or more independent variables                      │
│   • TWO OR MORE dependent variables                        │
│   • Tests all DVs simultaneously                           │
│                                                             │
│   Example:                                                  │
│   IV: Teaching method (A, B, C)                            │
│   DVs: Exam score, Course satisfaction, Study hours       │
│                                                             │
│   Advantages:                                               │
│   • Controls Type I error (one test, not multiple)        │
│   • Detects patterns across multiple DVs                  │
│   • More powerful when DVs are correlated                 │
│                                                             │
│   Test Statistics:                                          │
│   • Wilks' Lambda (Λ) — most common                       │
│   • Pillai's Trace                                         │
│   • Hotelling's Trace                                      │
│   • Roy's Largest Root                                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type 6: ANCOVA (Analysis of Covariance)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ANCOVA: ANALYSIS OF COVARIANCE                             │
│                                                             │
│   Structure:                                                │
│   • Standard ANOVA + continuous covariate(s)               │
│   • Controls for pre-existing differences                  │
│   • Increases precision by reducing error variance         │
│                                                             │
│   Example:                                                  │
│   IV: Teaching method (A, B, C)                            │
│   DV: Final exam score                                     │
│   Covariate: Pre-test score (prior knowledge)             │
│                                                             │
│   Why use ANCOVA?                                           │
│   1. Control for confounding variables                     │
│   2. Increase statistical power                            │
│   3. Adjust for pre-existing group differences            │
│                                                             │
│   Additional Assumptions:                                   │
│   • Linear relationship between covariate and DV          │
│   • Homogeneity of regression slopes                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Summary: Choosing the Right ANOVA

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│   WHICH ANOVA TO USE?                                                │
│                                                                     │
│   One IV, One DV, Different subjects      → ONE-WAY ANOVA          │
│   Two IVs, One DV, Different subjects     → TWO-WAY ANOVA          │
│   One IV, One DV, Same subjects           → REPEATED MEASURES      │
│   Between + Within factors                → MIXED ANOVA            │
│   One+ IVs, Multiple DVs                  → MANOVA                 │
│   Need to control for covariate           → ANCOVA                 │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Post-Hoc Tests

### When ANOVA is Significant, Then What?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   POST-HOC TESTS                                             │
│                                                             │
│   ANOVA tells you: "At least one mean is different"        │
│   Post-hoc tells you: "WHICH means are different"          │
│                                                             │
│   COMMON POST-HOC TESTS:                                    │
│                                                             │
│   1. TUKEY'S HSD (Honestly Significant Difference)         │
│      • Most common, for all pairwise comparisons          │
│                                                             │
│   2. BONFERRONI                                             │
│      • More conservative, divides α by comparisons         │
│                                                             │
│   3. SCHEFFÉ                                                │
│      • Most conservative, for complex comparisons         │
│                                                             │
│   4. DUNNETT                                                │
│      • Compare all groups to ONE control group             │
│                                                             │
│   5. GAMES-HOWELL                                           │
│      • When variances are unequal                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Python Implementation

```python
import numpy as np
from scipy import stats

def one_way_anova(groups, group_names=None, alpha=0.05):
    """Perform one-way ANOVA"""
    k = len(groups)
    if group_names is None:
        group_names = [f"Group {i+1}" for i in range(k)]
    
    n = [len(g) for g in groups]
    N = sum(n)
    means = [np.mean(g) for g in groups]
    grand_mean = np.mean([x for g in groups for x in g])
    
    # Sum of Squares
    SSB = sum(n[i] * (means[i] - grand_mean)**2 for i in range(k))
    SSW = sum(sum((x - means[i])**2 for x in groups[i]) for i in range(k))
    SST = SSB + SSW
    
    # Degrees of freedom
    df_between = k - 1
    df_within = N - k
    
    # Mean Squares
    MSB = SSB / df_between
    MSW = SSW / df_within
    
    # F-statistic
    F = MSB / MSW
    p_value = 1 - stats.f.cdf(F, df_between, df_within)
    
    # Effect size
    eta_squared = SSB / SST
    
    print("=" * 60)
    print("ONE-WAY ANOVA RESULTS")
    print("=" * 60)
    print(f"\nSource      │   SS    │  df │    MS   │    F    │ p-value")
    print("-" * 60)
    print(f"Between     │{SSB:>8.2f} │ {df_between:>3} │{MSB:>8.2f} │{F:>8.2f} │ {p_value:.4f}")
    print(f"Within      │{SSW:>8.2f} │ {df_within:>3} │{MSW:>8.2f} │")
    print("-" * 60)
    print(f"Total       │{SST:>8.2f} │ {N-1:>3} │")
    print(f"\nη² = {eta_squared:.4f} ({eta_squared*100:.1f}% variance explained)")
    print(f"Decision: {'REJECT H₀' if p_value < alpha else 'FAIL TO REJECT H₀'}")
    
    return {'F': F, 'p_value': p_value, 'eta_squared': eta_squared}

# Example
method_a = [72, 75, 78, 71, 74, 76, 73, 77, 75, 74]
method_b = [82, 85, 79, 88, 84, 86, 81, 83, 87, 85]
method_c = [78, 81, 76, 82, 79, 80, 77, 83, 81, 78]

result = one_way_anova([method_a, method_b, method_c],
                       ['Lecture', 'Flipped', 'Problem-Based'])

# Verify with scipy
f_stat, p_val = stats.f_oneway(method_a, method_b, method_c)
print(f"\nScipy verification: F = {f_stat:.2f}, p = {p_val:.6f}")
```

---

## Practice Problems 📝

### Problem 1: Basic One-Way ANOVA
Three fertilizers are tested on crop yield (kg):
- Fertilizer A: 45, 48, 50, 47, 49
- Fertilizer B: 52, 55, 53, 56, 54
- Fertilizer C: 48, 51, 49, 50, 52

Test at α = 0.05 whether fertilizers differ.

<details>
<summary>Click for Solution</summary>

```
Means: A = 47.8, B = 54.0, C = 50.0
Grand Mean = 50.6

SSB = 5(47.8-50.6)² + 5(54.0-50.6)² + 5(50.0-50.6)²
    = 39.2 + 57.8 + 1.8 = 98.8

SSW = 13.2 + 10.0 + 10.0 = 33.2

MSB = 98.8/2 = 49.4
MSW = 33.2/12 = 2.77

F = 49.4/2.77 = 17.84
F_critical (α=0.05, df=2,12) = 3.89

F = 17.84 > 3.89 → REJECT H₀

Conclusion: Fertilizers differ significantly.
η² = 98.8/132 = 0.75 (very large effect)
```

</details>

---

## Summary: The Complete ANOVA Picture

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│                    ANOVA SUMMARY                                     │
│                    ═════════════                                    │
│                                                                     │
│   CORE CONCEPT:                                                     │
│   F = MSB/MSW = Between-group variance / Within-group variance     │
│   Large F → Group means differ significantly                        │
│                                                                     │
│   VARIANCE PARTITIONING:                                            │
│   SST = SSB + SSW                                                   │
│   Total = Between (Explained) + Within (Error)                     │
│                                                                     │
│   ASSUMPTIONS (I Never Have Rats):                                  │
│   1. Independence (critical!)                                       │
│   2. Normality (robust with n > 30)                                │
│   3. Homogeneity of variances (use Welch's if violated)           │
│   4. Random sampling                                               │
│                                                                     │
│   TYPES:                                                            │
│   • One-Way: 1 IV, 1 DV                                           │
│   • Two-Way: 2 IVs, test interaction                              │
│   • Repeated Measures: Same subjects, multiple times              │
│   • Mixed: Between + Within factors                                │
│   • MANOVA: Multiple DVs                                           │
│   • ANCOVA: Control for covariates                                 │
│                                                                     │
│   AFTER SIGNIFICANT F:                                              │
│   Use post-hoc tests (Tukey, Bonferroni) to find which differ     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────────────┐
│                        ANOVA QUICK REFERENCE                         │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   SST = Σ(Xᵢⱼ - X̄)²           SSB = Σnᵢ(X̄ᵢ - X̄)²                  │
│   SSW = Σ(Xᵢⱼ - X̄ᵢ)²          SST = SSB + SSW                       │
│                                                                     │
│   MSB = SSB/(k-1)              MSW = SSW/(N-k)                      │
│   F = MSB/MSW                  η² = SSB/SST                         │
│                                                                     │
│   df_between = k - 1           df_within = N - k                    │
│                                                                     │
│   EFFECT SIZE (η²):                                                 │
│   < 0.01: Negligible │ 0.01-0.06: Small                            │
│   0.06-0.14: Medium  │ > 0.14: Large                               │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

> **"ANOVA partitions variance into 'signal' (between-groups) and 'noise' (within-groups). If the signal is loud enough to hear above the noise, we reject H₀."**

From teaching methods to drug trials, ANOVA is the workhorse for comparing multiple groups! 📊
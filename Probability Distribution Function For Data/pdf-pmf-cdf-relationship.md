# The Relationship Between PDF, PMF, and CDF
## A Beginner's Journey Through Probability Functions 📊

---

## The Three Musketeers of Probability

Imagine you're trying to answer questions about random events. You'll need different tools depending on what you're measuring:

| Function | Full Name | Used For | Think of it as... |
|----------|-----------|----------|-------------------|
| **PMF** | Probability Mass Function | Countable outcomes (discrete) | "What's the chance of EXACTLY this?" |
| **PDF** | Probability Density Function | Measurable outcomes (continuous) | "How likely is this region?" |
| **CDF** | Cumulative Distribution Function | Both types | "What's the chance of this OR LESS?" |

Let's explore each through stories!

---

# Part 1: PMF — Probability Mass Function
## *For things you can COUNT*

---

## 📖 Story 1: The Dice Game

Meet Rafiq, who runs a dice game at a local fair. Players roll a die and win prizes based on the number they get.

Rafiq needs to know: *"What's the probability of rolling EXACTLY each number?"*

### What is PMF?

The **Probability Mass Function** gives the probability of each **exact, countable outcome**.

For a fair die:

| Outcome (x) | 1 | 2 | 3 | 4 | 5 | 6 |
|-------------|---|---|---|---|---|---|
| P(X = x) | 1/6 | 1/6 | 1/6 | 1/6 | 1/6 | 1/6 |

### Visualizing the PMF

```
Probability
    │
1/6 ┤    ●     ●     ●     ●     ●     ●
    │    │     │     │     │     │     │
    │    │     │     │     │     │     │
  0 ┼────┴─────┴─────┴─────┴─────┴─────┴────
         1     2     3     4     5     6
                    Outcome (x)

Each dot represents the EXACT probability of that outcome.
The "mass" of probability sits at specific points.
```

### Key Properties of PMF

1. **Each probability is between 0 and 1:** `0 ≤ P(X = x) ≤ 1`
2. **All probabilities sum to 1:** `ΣP(X = x) = 1`
3. **Only for discrete (countable) variables**

---

## 📖 Story 2: The Coffee Shop Customers

Tasnim owns a small coffee shop. She counted customers per hour over many days:

| Customers (x) | 0 | 1 | 2 | 3 | 4 | 5+ |
|---------------|---|---|---|---|---|-----|
| Probability | 0.05 | 0.15 | 0.30 | 0.25 | 0.15 | 0.10 |

This is a PMF! Tasnim can answer:
- *"What's the probability of EXACTLY 2 customers?"* → **P(X = 2) = 0.30**
- *"What's the probability of EXACTLY 0 customers?"* → **P(X = 0) = 0.05**

### PMF Answers: "What's the probability of EXACTLY x?"

```
P(X = x) = ?
        ↑
    Specific value
```

---

## Real-Life PMF Examples

| Scenario | Random Variable | Possible Values |
|----------|-----------------|-----------------|
| Coin flips until heads | Number of flips | 1, 2, 3, 4, ... |
| Students absent today | Count of absences | 0, 1, 2, ..., class size |
| Goals in a match | Number of goals | 0, 1, 2, 3, ... |
| Defective items in batch | Count of defects | 0, 1, 2, ..., batch size |

---

# Part 2: PDF — Probability Density Function
## *For things you MEASURE*

---

## 📖 Story 3: The Height Mystery

Dr. Sultana is studying adult heights in Bangladesh. She measures thousands of people.

Here's the problem: *What's the probability someone is EXACTLY 170.0000000... cm tall?*

**Answer: Essentially ZERO!** 😱

Why? Because height is **continuous** — there are infinite possible values. The chance of hitting any exact value is practically zero.

### Enter the PDF

For continuous variables, we don't ask about exact values. Instead, we ask about **ranges**.

The **Probability Density Function** describes how probability is "spread" across a range of values.

### Visualizing the PDF (Normal Distribution for Heights)

```
Density
    │
    │           ╭───────╮
    │         ╭─╯       ╰─╮
    │       ╭─╯           ╰─╮
    │     ╭─╯               ╰─╮
    │   ╭─╯                   ╰─╮
    │ ╭─╯                       ╰─╮
    ┼─╯─────────────────────────────╰──────
        150   160   170   180   190
                  Height (cm)

The AREA under the curve between two points = Probability
```

### Key Insight: Area = Probability

For PDF, we find probability by calculating the **area under the curve**.

**Example:** What's the probability someone is between 165 cm and 175 cm?

```
P(165 < X < 175) = Area under curve from 165 to 175
```

```
Density
    │
    │           ╭───────╮
    │         ╭─╯███████╰─╮
    │       ╭─╯███████████╰─╮
    │     ╭─╯███████████████╰─╮
    │   ╭─╯   ███████████████  ╰─╮
    │ ╭─╯     ███████████████    ╰─╮
    ┼─╯───────███████████████──────────
        150   165   170   175   190
              ↑           ↑
            Start        End
            
Shaded area = P(165 < X < 175)
```

---

## 📖 Story 4: The Waiting Time

Anika is waiting for a bus that arrives randomly between 0-10 minutes. The wait time follows a **uniform distribution**.

### Uniform PDF

```
Density
    │
0.1 ┤    ┌─────────────────────┐
    │    │█████████████████████│
    │    │█████████████████████│
    │    │█████████████████████│
  0 ┼────┴─────────────────────┴────
         0    2    4    6    8   10
                Wait Time (minutes)

Height = 1/10 = 0.1 (so total area = 1)
```

**Question:** What's the probability Anika waits between 2-5 minutes?

```
P(2 < X < 5) = Base × Height
P(2 < X < 5) = 3 × 0.1
P(2 < X < 5) = 0.30 or 30%
```

---

## PMF vs PDF: The Key Difference

| Aspect | PMF (Discrete) | PDF (Continuous) |
|--------|----------------|------------------|
| **Variable Type** | Countable (integers) | Measurable (real numbers) |
| **P(X = exact value)** | Can be > 0 | Always = 0 |
| **How to find probability** | Read directly from function | Calculate area under curve |
| **Height of graph** | = Probability | = Density (NOT probability!) |
| **Sum/Integral** | Σ P(X=x) = 1 | ∫ f(x)dx = 1 |

### Visual Comparison

```
PMF (Discrete)                    PDF (Continuous)
                                  
Probability                       Density
    │                                 │
    │  ●                              │        ╭──╮
    │  │     ●                        │      ╭─╯  ╰─╮
    │  │     │  ●                     │    ╭─╯      ╰─╮
    │  │     │  │  ●                  │  ╭─╯          ╰─╮
    ┼──┴─────┴──┴──┴──                ┼──╯──────────────╰──
       1  2  3  4  5                     Values (continuous)

• Height = Probability             • Height = Density
• Read P(X=3) directly             • Must calculate AREA
```

---

# Part 3: CDF — Cumulative Distribution Function
## *"What's the probability of getting this value OR LESS?"*

---

## 📖 Story 5: The Exam Scores

Professor Rahman has graded 100 exams. He wants to know how students performed.

Instead of asking "How many got exactly 75?", he asks:

> "What percentage of students scored 75 OR BELOW?"

This is exactly what **CDF** answers!

### What is CDF?

The **Cumulative Distribution Function** gives the probability that a random variable is **less than or equal to** a specific value.

```
F(x) = P(X ≤ x)
```

### CDF Works for BOTH Discrete and Continuous!

This is the beauty of CDF — it bridges both worlds.

---

## 📖 Story 6: Back to Rafiq's Dice

Remember the dice game? Let's build its CDF.

### PMF (What we had):

| x | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|
| P(X = x) | 1/6 | 1/6 | 1/6 | 1/6 | 1/6 | 1/6 |

### CDF (Cumulating the probabilities):

| x | P(X ≤ x) | Calculation |
|---|----------|-------------|
| 1 | 1/6 ≈ 0.167 | P(X=1) |
| 2 | 2/6 ≈ 0.333 | P(X=1) + P(X=2) |
| 3 | 3/6 = 0.500 | P(X=1) + P(X=2) + P(X=3) |
| 4 | 4/6 ≈ 0.667 | P(X=1) + ... + P(X=4) |
| 5 | 5/6 ≈ 0.833 | P(X=1) + ... + P(X=5) |
| 6 | 6/6 = 1.000 | P(X=1) + ... + P(X=6) |

### Visualizing Discrete CDF (Step Function)

```
P(X ≤ x)
    │
  1 ┤                              ●────────
    │                         ●────╯
5/6 ┤                    ●────╯
    │               ●────╯
4/6 ┤          ●────╯
    │     ●────╯
2/6 ┤●────╯
    │
  0 ┼────┬────┬────┬────┬────┬────┬────
         1    2    3    4    5    6
                 Outcome (x)

Notice: Steps jump at each discrete value!
```

---

## 📖 Story 7: CDF for Continuous Variables

Back to Anika's bus wait (uniform 0-10 minutes).

### PDF was:
```
f(x) = 0.1  for 0 ≤ x ≤ 10
```

### CDF is:
```
F(x) = P(X ≤ x) = x/10  for 0 ≤ x ≤ 10
```

| Wait Time (x) | P(X ≤ x) |
|---------------|----------|
| 0 minutes | 0% |
| 2 minutes | 20% |
| 5 minutes | 50% |
| 8 minutes | 80% |
| 10 minutes | 100% |

### Visualizing Continuous CDF (Smooth Curve)

```
P(X ≤ x)
    │
  1 ┤                              ●
    │                          ╱
0.8 ┤                      ╱
    │                  ╱
0.6 ┤              ╱
    │          ╱
0.4 ┤      ╱
    │  ╱
0.2 ┤╱
    │
  0 ●────┬────┬────┬────┬────┬────
         0    2    4    6    8   10
              Wait Time (minutes)

Notice: Smooth line (no jumps) for continuous variables!
```

---

## The Magic Relationship: How They Connect

### 🔗 Connection 1: PMF → CDF (Discrete)

**CDF is the CUMULATIVE SUM of PMF**

```
F(x) = Σ P(X = k)  for all k ≤ x
```

```
        PMF                          CDF
                                     
   P(X=x)                        P(X≤x)
     │                              │
     │  ●                         1 ┤              ●───
     │  │  ●                        │         ●────╯
     │  │  │  ●         ═══►        │    ●────╯
     │  │  │  │  ●                  │●───╯
     ┼──┴──┴──┴──┴──              0 ┼────┴────┴────┴────
        1  2  3  4                     1    2    3    4

   "Exact probability"          "Running total"
```

### 🔗 Connection 2: PDF → CDF (Continuous)

**CDF is the INTEGRAL (area under curve) of PDF**

```
F(x) = ∫ f(t) dt  from -∞ to x
```

```
        PDF                          CDF
                                     
   Density                       P(X≤x)
     │    ╭─╮                        │
     │  ╭─╯ ╰─╮                    1 ┤            ╭────
     │╭─╯     ╰─╮       ═══►        │         ╭──╯
     ┼╯─────────╰──              0.5┤     ╭───╯
                                    │ ╭───╯
                                  0 ┼─╯────┬────┬────
   "Probability density"          "Accumulated area"
```

### 🔗 Connection 3: CDF → PMF/PDF (Going Backwards!)

| From CDF to... | Method |
|----------------|--------|
| **PMF** (Discrete) | P(X = x) = F(x) - F(x-1) |
| **PDF** (Continuous) | f(x) = dF(x)/dx (derivative) |

---

## Practical Examples: Using All Three

### 📖 Example 1: Student Grades (Discrete)

A class has the following grade distribution:

| Grade | A | B | C | D | F |
|-------|---|---|---|---|---|
| PMF: P(X=x) | 0.15 | 0.30 | 0.35 | 0.15 | 0.05 |

**Build the CDF:**

| Grade | CDF: P(X≤x) |
|-------|-------------|
| F | 0.05 |
| D | 0.05 + 0.15 = 0.20 |
| C | 0.20 + 0.35 = 0.55 |
| B | 0.55 + 0.30 = 0.85 |
| A | 0.85 + 0.15 = 1.00 |

**Questions:**

1. *"What's the probability of getting exactly a B?"*
   - Use PMF: **P(X = B) = 0.30**

2. *"What's the probability of getting C or worse?"*
   - Use CDF: **P(X ≤ C) = 0.55**

3. *"What's the probability of getting better than C?"*
   - Use CDF complement: **P(X > C) = 1 - 0.55 = 0.45**

---

### 📖 Example 2: Battery Life (Continuous)

A phone battery lasts according to a distribution with:

- PDF: Higher density around 8-10 hours
- Mean: 9 hours

**Questions we can answer:**

| Question | Use | Formula |
|----------|-----|---------|
| "Probability battery lasts exactly 9 hours?" | PDF concept | P(X = 9) = 0 (always for continuous!) |
| "Probability battery lasts 8-10 hours?" | PDF area | P(8 < X < 10) = ∫ f(x)dx from 8 to 10 |
| "Probability battery lasts less than 6 hours?" | CDF | P(X ≤ 6) = F(6) |
| "Probability battery lasts more than 10 hours?" | CDF | P(X > 10) = 1 - F(10) |

---

## The Relationship Summary

```
┌──────────────────────────────────────────────────────────────────┐
│                    THE COMPLETE PICTURE                          │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│   DISCRETE WORLD                    CONTINUOUS WORLD             │
│   ───────────────                   ────────────────             │
│                                                                  │
│   ┌─────────┐                       ┌─────────┐                  │
│   │   PMF   │                       │   PDF   │                  │
│   │ P(X=x)  │                       │  f(x)   │                  │
│   └────┬────┘                       └────┬────┘                  │
│        │                                 │                       │
│        │ Sum                             │ Integrate             │
│        ↓                                 ↓                       │
│   ┌─────────────────────────────────────────────┐               │
│   │                   CDF                        │               │
│   │               F(x) = P(X ≤ x)                │               │
│   │                                              │               │
│   │  • Always between 0 and 1                    │               │
│   │  • Never decreases (non-decreasing)          │               │
│   │  • F(-∞) = 0, F(+∞) = 1                      │               │
│   └─────────────────────────────────────────────┘               │
│        ↑                                 ↑                       │
│        │ Difference                      │ Derivative            │
│        │                                 │                       │
│   ┌────┴────┐                       ┌────┴────┐                  │
│   │   PMF   │                       │   PDF   │                  │
│   └─────────┘                       └─────────┘                  │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Table

| Property | PMF | PDF | CDF |
|----------|-----|-----|-----|
| **For** | Discrete | Continuous | Both |
| **Symbol** | P(X = x) or p(x) | f(x) | F(x) |
| **Height means** | Probability | Density | Cumulative probability |
| **P(X = x)** | Read directly | Always 0 | F(x) - F(x⁻) |
| **P(X ≤ x)** | Sum all P(X ≤ x) | Integrate | Read directly |
| **P(a < X < b)** | Sum from a to b | ∫f(x)dx from a to b | F(b) - F(a) |
| **Total** | Σ p(x) = 1 | ∫f(x)dx = 1 | Ends at 1 |

---

## Useful CDF Tricks

### Finding Probabilities with CDF

```
P(X ≤ a)     = F(a)                    ← Direct read
P(X > a)     = 1 - F(a)                ← Complement
P(X < a)     = F(a) - P(X = a)         ← Subtract point (discrete)
             = F(a)                     ← Same thing (continuous)
P(a < X ≤ b) = F(b) - F(a)             ← Difference
P(a ≤ X ≤ b) = F(b) - F(a) + P(X = a)  ← Discrete adjustment
```

---

## Practice Problems 📝

### Problem 1: From PMF to CDF
A random variable X has PMF:

| x | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| P(X=x) | 0.1 | 0.3 | 0.4 | 0.2 |

Find: (a) F(2) (b) P(X > 2) (c) P(1 < X ≤ 3)

<details>
<summary>Click for Answer</summary>

**Build CDF first:**
| x | F(x) = P(X ≤ x) |
|---|-----------------|
| 1 | 0.1 |
| 2 | 0.1 + 0.3 = 0.4 |
| 3 | 0.4 + 0.4 = 0.8 |
| 4 | 0.8 + 0.2 = 1.0 |

**(a) F(2) = 0.4**

**(b) P(X > 2) = 1 - F(2) = 1 - 0.4 = 0.6**

**(c) P(1 < X ≤ 3) = F(3) - F(1) = 0.8 - 0.1 = 0.7**

</details>

### Problem 2: From CDF to PMF
A discrete random variable has CDF:

| x | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| F(x) | 0.2 | 0.5 | 0.8 | 1.0 |

Find the PMF.

<details>
<summary>Click for Answer</summary>

**Use: P(X = x) = F(x) - F(x-1)**

| x | P(X = x) | Calculation |
|---|----------|-------------|
| 0 | 0.2 | F(0) - 0 |
| 1 | 0.3 | F(1) - F(0) = 0.5 - 0.2 |
| 2 | 0.3 | F(2) - F(1) = 0.8 - 0.5 |
| 3 | 0.2 | F(3) - F(2) = 1.0 - 0.8 |

</details>

### Problem 3: Continuous CDF
A continuous random variable has CDF:
```
F(x) = 0           for x < 0
F(x) = x²/4        for 0 ≤ x ≤ 2
F(x) = 1           for x > 2
```

Find: (a) P(X ≤ 1) (b) P(0.5 < X < 1.5) (c) The PDF f(x)

<details>
<summary>Click for Answer</summary>

**(a) P(X ≤ 1) = F(1) = 1²/4 = 0.25**

**(b) P(0.5 < X < 1.5) = F(1.5) - F(0.5)**
```
= (1.5)²/4 - (0.5)²/4
= 2.25/4 - 0.25/4
= 2/4 = 0.5
```

**(c) PDF = derivative of CDF:**
```
f(x) = dF(x)/dx = d(x²/4)/dx = 2x/4 = x/2  for 0 ≤ x ≤ 2
f(x) = 0  otherwise
```

</details>

---

## Final Analogy: The Water Tank 🚰

Think of probability like water in a tank:

| Concept | Water Analogy |
|---------|---------------|
| **PMF** | Individual drops of water (countable) |
| **PDF** | Water flow rate at each point (continuous) |
| **CDF** | Total water collected up to this point |

- PMF/PDF tells you **how fast** probability accumulates
- CDF tells you **how much** probability has accumulated

---

## Key Takeaways 🎯

1. **PMF** is for **discrete** variables — gives exact probabilities
2. **PDF** is for **continuous** variables — gives density (probability = area)
3. **CDF** works for **both** — gives cumulative probability P(X ≤ x)
4. **PMF/PDF → CDF:** Sum (discrete) or Integrate (continuous)
5. **CDF → PMF/PDF:** Difference (discrete) or Derivative (continuous)

> **Remember:** CDF is the universal translator between the discrete and continuous worlds!

---

*Master these three, and you've unlocked the foundation of probability theory! 🔓*
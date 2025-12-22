# Type I and Type II Errors
## The Two Ways Hypothesis Testing Can Go Wrong ⚠️

---

## The Unavoidable Truth

In hypothesis testing, we make decisions based on sample data. Since we're working with incomplete information, **we can make mistakes**. There are exactly two types of errors we can make:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE TWO ERRORS IN HYPOTHESIS TESTING                       │
│                                                             │
│   TYPE I ERROR (α - Alpha)                                  │
│   ─────────────────────────                                 │
│   Rejecting H₀ when H₀ is actually TRUE                    │
│   "False Positive" — "False Alarm"                         │
│   Seeing an effect that doesn't exist                      │
│                                                             │
│   TYPE II ERROR (β - Beta)                                  │
│   ──────────────────────────                                │
│   Failing to reject H₀ when H₀ is actually FALSE           │
│   "False Negative" — "Missed Detection"                    │
│   Missing an effect that does exist                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 Story: The Smoke Detector

Imagine a smoke detector in your kitchen:

### Type I Error: False Alarm 🚨
You're cooking dinner, and steam from your pot triggers the smoke detector. There's **no fire**, but the alarm goes off anyway.

- **Reality:** No fire (H₀ is true)
- **Detector says:** FIRE! (Rejects H₀)
- **Result:** False alarm, annoying but safe

### Type II Error: Missed Detection 😱
There's an actual fire in your kitchen, but the smoke detector's battery is low and it **fails to sound**.

- **Reality:** There IS a fire (H₀ is false)
- **Detector says:** All clear (Fails to reject H₀)
- **Result:** Missed danger, potentially catastrophic!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SMOKE DETECTOR ANALOGY                                     │
│                                                             │
│   H₀: There is NO fire                                      │
│   H₁: There IS a fire                                       │
│                                                             │
│   Type I Error:  Alarm sounds when there's NO fire         │
│                  (Annoying, but you're safe)               │
│                                                             │
│   Type II Error: Alarm DOESN'T sound when there IS fire    │
│                  (Dangerous! You could be harmed)          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Decision Matrix

### All Possible Outcomes

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│                           REALITY                                   │
│                    ┌─────────────┬─────────────┐                   │
│                    │  H₀ TRUE    │  H₀ FALSE   │                   │
│                    │ (No effect) │(Effect exists)│                  │
│   ┌────────────────┼─────────────┼─────────────┤                   │
│   │                │             │             │                   │
│ D │ REJECT H₀      │  TYPE I     │  CORRECT    │                   │
│ E │                │   ERROR     │  DECISION   │                   │
│ C │ (Conclude      │    (α)      │             │                   │
│ I │  effect exists)│ False       │   TRUE      │                   │
│ S │                │ Positive    │  POSITIVE   │                   │
│ I │                │    ⚠️       │     ✓       │                   │
│ O ├────────────────┼─────────────┼─────────────┤                   │
│ N │                │             │             │                   │
│   │ FAIL TO        │  CORRECT    │  TYPE II    │                   │
│   │ REJECT H₀      │  DECISION   │   ERROR     │                   │
│   │                │             │    (β)      │                   │
│   │ (Conclude no   │   TRUE      │  False      │                   │
│   │  evidence)     │  NEGATIVE   │  Negative   │                   │
│   │                │     ✓       │    ⚠️       │                   │
│   └────────────────┴─────────────┴─────────────┘                   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Summary of Outcomes

| | H₀ True (No Effect) | H₀ False (Effect Exists) |
|---|---|---|
| **Reject H₀** | ❌ Type I Error (α) | ✅ Correct (Power = 1-β) |
| **Fail to Reject H₀** | ✅ Correct (1-α) | ❌ Type II Error (β) |

---

## Type I Error (α) — The False Positive

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TYPE I ERROR (α)                                           │
│                                                             │
│   Definition:                                               │
│   Rejecting H₀ when H₀ is actually TRUE                    │
│                                                             │
│   In symbols:                                               │
│   α = P(Reject H₀ | H₀ is true)                            │
│                                                             │
│   Also called:                                              │
│   • False Positive                                          │
│   • False Alarm                                             │
│   • "Seeing something that isn't there"                    │
│                                                             │
│   Common values:                                            │
│   α = 0.05 (5%)  — Standard                                │
│   α = 0.01 (1%)  — Stringent                               │
│   α = 0.10 (10%) — Lenient                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### The Significance Level IS the Type I Error Rate

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   KEY INSIGHT:                                               │
│                                                             │
│   The significance level α that YOU CHOOSE is exactly      │
│   the probability of making a Type I error!                │
│                                                             │
│   If you set α = 0.05:                                     │
│   • 5% chance of rejecting H₀ when H₀ is true             │
│   • 5% chance of a false positive                          │
│   • 1 in 20 chance of a false alarm                        │
│                                                             │
│   YOU control the Type I error rate by choosing α!         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Real-World Type I Error Examples

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TYPE I ERROR EXAMPLES                                      │
│                                                             │
│   1. MEDICAL TESTING                                        │
│      H₀: Patient does NOT have the disease                 │
│      Type I: Diagnosing disease when patient is healthy    │
│      Consequence: Unnecessary treatment, anxiety, costs     │
│                                                             │
│   2. CRIMINAL JUSTICE                                       │
│      H₀: Defendant is innocent                             │
│      Type I: Convicting an innocent person                 │
│      Consequence: Innocent person goes to prison!          │
│                                                             │
│   3. DRUG TESTING                                           │
│      H₀: Drug has no effect                                │
│      Type I: Approving an ineffective drug                 │
│      Consequence: Patients get useless treatment           │
│                                                             │
│   4. SPAM FILTER                                            │
│      H₀: Email is NOT spam                                 │
│      Type I: Marking legitimate email as spam              │
│      Consequence: Missing important messages               │
│                                                             │
│   5. QUALITY CONTROL                                        │
│      H₀: Product meets specifications                      │
│      Type I: Rejecting a good product                      │
│      Consequence: Wasted product, increased costs          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Type II Error (β) — The False Negative

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TYPE II ERROR (β)                                          │
│                                                             │
│   Definition:                                               │
│   Failing to reject H₀ when H₀ is actually FALSE           │
│                                                             │
│   In symbols:                                               │
│   β = P(Fail to reject H₀ | H₀ is false)                   │
│                                                             │
│   Also called:                                              │
│   • False Negative                                          │
│   • Missed Detection                                        │
│   • "Missing something that IS there"                      │
│                                                             │
│   Related to POWER:                                         │
│   Power = 1 - β = P(Reject H₀ | H₀ is false)               │
│   Power = Probability of detecting a real effect           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Why β is Harder to Control

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   WHY TYPE II ERROR IS TRICKIER                              │
│                                                             │
│   Unlike α, you DON'T directly choose β!                   │
│                                                             │
│   β depends on:                                             │
│   • Sample size (n) — larger n → smaller β                 │
│   • Effect size — larger effect → smaller β                │
│   • Significance level (α) — larger α → smaller β          │
│   • Population variance (σ²) — smaller σ → smaller β       │
│                                                             │
│   To reduce Type II error, you need to:                    │
│   • Increase sample size                                    │
│   • Accept larger α (but increases Type I error!)          │
│   • Study effects that are actually large                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Real-World Type II Error Examples

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   TYPE II ERROR EXAMPLES                                     │
│                                                             │
│   1. MEDICAL TESTING                                        │
│      H₀: Patient does NOT have the disease                 │
│      Type II: Failing to detect disease in sick patient    │
│      Consequence: Untreated illness, disease spreads!      │
│                                                             │
│   2. CRIMINAL JUSTICE                                       │
│      H₀: Defendant is innocent                             │
│      Type II: Acquitting a guilty person                   │
│      Consequence: Criminal goes free                       │
│                                                             │
│   3. DRUG TESTING                                           │
│      H₀: Drug has no effect                                │
│      Type II: Failing to approve an effective drug         │
│      Consequence: Patients miss beneficial treatment       │
│                                                             │
│   4. SPAM FILTER                                            │
│      H₀: Email is NOT spam                                 │
│      Type II: Letting spam through to inbox                │
│      Consequence: Inbox cluttered with junk                │
│                                                             │
│   5. QUALITY CONTROL                                        │
│      H₀: Product meets specifications                      │
│      Type II: Accepting a defective product                │
│      Consequence: Customer receives faulty product         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## The Classic Analogy: The Courtroom

### The Legal System as Hypothesis Testing

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE COURTROOM ANALOGY                                      │
│                                                             │
│   H₀: The defendant is INNOCENT (presumption of innocence) │
│   H₁: The defendant is GUILTY                               │
│                                                             │
│   The jury examines evidence and makes a decision...       │
│                                                             │
└─────────────────────────────────────────────────────────────┘

                        REALITY
                 ┌──────────┬──────────┐
                 │ INNOCENT │  GUILTY  │
    ┌────────────┼──────────┼──────────┤
    │            │          │          │
  V │ CONVICT    │ TYPE I   │ CORRECT  │
  E │            │  ERROR   │          │
  R │ (Guilty)   │          │  Justice │
  D │            │ Innocent │  served! │
  I │            │ person   │    ✓     │
  C │            │ in jail! │          │
  T │            │   ⚠️     │          │
    ├────────────┼──────────┼──────────┤
    │            │          │          │
    │ ACQUIT     │ CORRECT  │ TYPE II  │
    │            │          │  ERROR   │
    │ (Not       │ Justice  │          │
    │  Guilty)   │ served!  │ Criminal │
    │            │    ✓     │ goes     │
    │            │          │ free!    │
    │            │          │   ⚠️     │
    └────────────┴──────────┴──────────┘
```

### Why Courts Are Conservative

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   "Better that ten guilty persons escape than that one     │
│    innocent suffer." — William Blackstone                   │
│                                                             │
│   This is why courts use "beyond reasonable doubt":        │
│   • Set α very LOW (avoid convicting innocent people)      │
│   • Accept higher β (some guilty people go free)           │
│   • Type I error (false conviction) is considered WORSE    │
│                                                             │
│   In statistics terms:                                      │
│   α << β  (prioritize avoiding Type I error)               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Visual: The Two Distributions

### Understanding Errors Graphically

```
              H₀ Distribution          H₁ Distribution
              (If H₀ is true)          (If H₁ is true)
              
                   ╭───╮                     ╭───╮
                 ╭─╯   ╰─╮                 ╭─╯   ╰─╮
                ╭╯       ╰╮               ╭╯       ╰╮
               ╭╯         ╰╮             ╭╯         ╰╮
              ╭╯           ╰████████████╭╯           ╰╮
             ╭╯             │╰██████████╯             ╰╮
            ╭╯              │  ████████│               ╰╮
           ╭╯               │    ██████│                ╰╮
          ╯                 │      ████│                 ╰
    ──────────────────────────┼─────────────────────────────
              μ₀            │ Critical     μ₁
                            │  Value
                            │
          ◄─────────────────┼──────────────────►
           Fail to Reject   │      Reject H₀
                 H₀         │


    TYPE I ERROR (α):                TYPE II ERROR (β):
    ████ Area under H₀               ████ Area under H₁
         to the RIGHT                     to the LEFT
         of critical value                of critical value
```

### Labeled Diagram

```
                    If H₀ is TRUE              If H₁ is TRUE
                    
                         ╭───╮                      ╭───╮
                       ╭─╯   ╰─╮                  ╭─╯   ╰─╮
                      ╭╯       ╰╮                ╭╯       ╰╮
                     ╭╯    A    ╰╮          ████╭╯    C    ╰╮
                    ╭╯           ╰████     █████╯           ╰╮
                   ╭╯             │╰███   ██████             ╰╮
                  ╭╯       B      │ ████ ███│ D               ╰╮
                 ╭╯               │  ███████│                  ╰╮
                ╯                 │    █████│                   ╰
          ────────────────────────┼─────────────────────────────────
                                  │
                            Critical Value


    A = Correct: Fail to reject H₀ when H₀ true (1 - α)
    B = TYPE I ERROR: Reject H₀ when H₀ true (α)
    C = TYPE II ERROR: Fail to reject H₀ when H₁ true (β)
    D = Correct: Reject H₀ when H₁ true (Power = 1 - β)
```

---

## The Trade-Off: α vs β

### The Fundamental Tension

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE α-β TRADE-OFF                                          │
│                                                             │
│   You CANNOT minimize both errors simultaneously!           │
│                                                             │
│   If you decrease α (fewer false positives):               │
│   • Critical value moves further from μ₀                   │
│   • Harder to reject H₀                                    │
│   • β INCREASES (more false negatives)                     │
│                                                             │
│   If you decrease β (fewer false negatives):               │
│   • Critical value moves closer to μ₀                      │
│   • Easier to reject H₀                                    │
│   • α INCREASES (more false positives)                     │
│                                                             │
│   It's like a seesaw:                                       │
│                                                             │
│        α ↓                           β ↓                    │
│         ↘                           ↙                       │
│          ╲         ┌───┐          ╱                         │
│           ╲        │   │         ╱                          │
│            ╲───────┴───┴────────╱                           │
│                     ▲                                       │
│                  Fulcrum                                    │
│                                                             │
│   Push one down, the other goes up!                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Moving the Critical Value

```
LOWER α (more conservative): Move critical value RIGHT

              H₀                        H₁
           ╭───╮                     ╭───╮
         ╭─╯   ╰─╮                 ╭─╯   ╰─╮
        ╭╯       ╰╮               ╭╯       ╰╮
       ╭╯         ╰█             ╭╯         ╰╮
      ╭╯           │█       █████╯           ╰╮
     ╭╯            │ █     ██████             ╰╮
    ╯              │  █   ███████              ╰
   ─────────────────────┼────────────────────────
                        │
                   Critical value moved RIGHT
                        
   α = tiny (good!)     β = LARGE (bad!)


HIGHER α (less conservative): Move critical value LEFT

              H₀                        H₁
           ╭───╮                     ╭───╮
         ╭─╯   ╰─╮                 ╭─╯   ╰─╮
        ╭╯       ╰╮               ╭╯       ╰╮
       ╭╯         ╰████          █╯         ╰╮
      ╭╯           │╰████       ██           ╰╮
     ╭╯            │  ████    ███             ╰╮
    ╯              │    ███  ████              ╰
   ────────────────┼─────────────────────────────
                   │
              Critical value moved LEFT
                        
   α = LARGE (bad!)     β = small (good!)
```

---

## The Only Way to Reduce BOTH Errors

### Increase Sample Size!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   THE SOLUTION: INCREASE SAMPLE SIZE                         │
│                                                             │
│   Larger n makes BOTH distributions NARROWER                │
│   (because SE = σ/√n decreases)                             │
│                                                             │
│   With narrower distributions:                              │
│   • Less overlap between H₀ and H₁ distributions           │
│   • Can maintain low α AND low β                           │
│   • More POWER to detect real effects                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Visual: Effect of Sample Size

```
SMALL n: Wide distributions, lots of overlap

           H₀                       H₁
        ╭──────╮               ╭──────╮
      ╭─╯      ╰─╮           ╭─╯      ╰─╮
    ╭─╯          ╰─────────────╯        ╰─╮
   ╭╯                                      ╰╮
  ─────────────────────────────────────────────
              │           │
           Large β    Large α if threshold here
           
           LOTS OF OVERLAP = HIGH ERROR RATES


LARGE n: Narrow distributions, less overlap

                H₀                 H₁
              ╭────╮             ╭────╮
             ╭╯    ╰╮           ╭╯    ╰╮
            ╭╯      ╰╮         ╭╯      ╰╮
           ╭╯        ╰╮       ╭╯        ╰╮
          ╭╯          ╰╮     ╭╯          ╰╮
  ─────────────────────┼─────────────────────
                       │
                  Clear separation!
                  
           LESS OVERLAP = LOWER ERROR RATES
```

---

## Power: The Complement of Type II Error

### Definition

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   STATISTICAL POWER                                          │
│                                                             │
│   Power = 1 - β                                             │
│         = P(Reject H₀ | H₀ is false)                       │
│         = P(Correctly detecting a real effect)             │
│                                                             │
│   If β = 0.20 (20% chance of missing effect)               │
│   Then Power = 0.80 (80% chance of detecting effect)       │
│                                                             │
│   CONVENTION:                                               │
│   • Minimum acceptable power: 0.80 (80%)                   │
│   • Ideal power: 0.90 (90%) or higher                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### What Affects Power?

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   FACTORS THAT INCREASE POWER (decrease β):                 │
│                                                             │
│   1. LARGER SAMPLE SIZE (n ↑)                               │
│      • Narrower distributions                               │
│      • Most direct way to increase power                   │
│                                                             │
│   2. LARGER EFFECT SIZE                                     │
│      • Bigger difference between μ₀ and μ₁                 │
│      • Distributions are further apart                      │
│                                                             │
│   3. LARGER α (higher significance level)                   │
│      • Critical value moves toward μ₀                      │
│      • Easier to reject H₀                                 │
│      • But increases Type I error!                         │
│                                                             │
│   4. SMALLER VARIANCE (σ² ↓)                               │
│      • Narrower distributions                               │
│      • Less overlap                                         │
│                                                             │
│   5. ONE-TAILED vs TWO-TAILED                              │
│      • One-tailed test has more power                      │
│      • But only detects effects in one direction           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Calculating Type I and Type II Errors

### Example: Testing a Mean

A machine fills bottles with μ₀ = 500ml. We want to detect if μ ≠ 500ml.
- σ = 10ml (known)
- n = 25
- α = 0.05 (two-tailed)
- True mean (if different): μ₁ = 504ml

### Step 1: Find Critical Values

```
For α = 0.05 (two-tailed):
Z_critical = ±1.96

Convert to X̄ scale:
SE = σ/√n = 10/√25 = 2

Critical X̄ values:
X̄_lower = μ₀ - 1.96 × SE = 500 - 1.96(2) = 496.08
X̄_upper = μ₀ + 1.96 × SE = 500 + 1.96(2) = 503.92

Reject H₀ if X̄ < 496.08 or X̄ > 503.92
```

### Step 2: Type I Error (α)

```
Type I Error = P(Reject H₀ | H₀ is true)
             = P(X̄ < 496.08 or X̄ > 503.92 | μ = 500)
             = 0.05  (by design!)

We SET α = 0.05, so Type I error rate IS 0.05.
```

### Step 3: Type II Error (β)

```
Type II Error = P(Fail to reject H₀ | H₁ is true)
              = P(496.08 ≤ X̄ ≤ 503.92 | μ = 504)

If true μ = 504:
X̄ ~ N(504, SE² = 4)

P(X̄ ≤ 503.92 | μ = 504) = P(Z ≤ (503.92-504)/2) = P(Z ≤ -0.04) = 0.484
P(X̄ ≤ 496.08 | μ = 504) = P(Z ≤ (496.08-504)/2) = P(Z ≤ -3.96) ≈ 0

β = 0.484 - 0 = 0.484

Type II Error = 48.4%
Power = 1 - β = 1 - 0.484 = 0.516 = 51.6%
```

### Step 4: Visualize

```
        H₀: μ = 500              H₁: μ = 504
        
           ╭───╮                    ╭───╮
         ╭─╯   ╰─╮                ╭─╯   ╰─╮
        ╭╯       ╰╮              ╭╯       ╰╮
       ╭╯         ╰╮            ╭╯         ╰╮
      ╭╯           ╰███████████╭╯           ╰╮
     ╭╯   ▓▓▓▓      │╰█████████╯  █████████  ╰╮
    ╭╯    ▓▓▓▓      │  ████████│  █████████   ╰╮
   ╭╯     ▓▓▓▓      │    ██████│  █████████    ╰╮
   ─────────────────┼─────────────────────────────
       496.08      500       503.92   504

   ▓▓▓ = α/2 (Type I, left tail)
   ███ = β (Type II error) — area under H₁ between critical values
   █████ = Power (1-β) — area under H₁ beyond upper critical value
```

### Interpretation

```
With n = 25, α = 0.05, and true μ = 504:

• If H₀ is true (μ = 500): 5% chance of false positive
• If H₁ is true (μ = 504): 48.4% chance of missing it!

Power of only 51.6% is TOO LOW!
We need larger n to reliably detect a 4ml difference.
```

---

## Reducing Type II Error: Sample Size Calculation

### How Large n Do We Need?

```
For 80% power (β = 0.20):

Required n formula:
n = [(Z_α/2 + Z_β)² × σ²] / (μ₁ - μ₀)²

For α = 0.05 (Z_0.025 = 1.96)
For β = 0.20 (Z_0.20 = 0.84)
σ = 10, μ₁ - μ₀ = 4

n = [(1.96 + 0.84)² × 100] / 16
  = [7.84 × 100] / 16
  = 784 / 16
  = 49

We need n = 49 for 80% power!
```

---

## Which Error is Worse?

### It Depends on Context!

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   WHEN TYPE I ERROR IS WORSE:                                │
│   ────────────────────────────                              │
│                                                             │
│   • Criminal justice (convicting innocent)                 │
│   • Approving a harmful drug                               │
│   • Launching a product that doesn't work                  │
│   • Publishing false scientific findings                   │
│                                                             │
│   → Set α very LOW (0.01 or 0.001)                         │
│   → Accept higher β                                        │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   WHEN TYPE II ERROR IS WORSE:                               │
│   ─────────────────────────────                             │
│                                                             │
│   • Failing to detect a deadly disease                     │
│   • Missing a terrorist threat                             │
│   • Not detecting a structural defect                      │
│   • Failing to identify a beneficial drug                  │
│                                                             │
│   → Accept higher α (0.10)                                 │
│   → Minimize β (maximize power)                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### The Medical Testing Dilemma

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   SCREENING TEST vs CONFIRMATORY TEST                        │
│                                                             │
│   SCREENING (Initial test):                                 │
│   • Priority: Don't miss sick people (low Type II)        │
│   • Accept more false positives (higher Type I)            │
│   • High SENSITIVITY                                        │
│   • "Better safe than sorry"                               │
│                                                             │
│   CONFIRMATORY (Follow-up test):                           │
│   • Priority: Don't falsely diagnose (low Type I)          │
│   • OK to miss some cases (higher Type II)                 │
│   • High SPECIFICITY                                        │
│   • "Be sure before treating"                              │
│                                                             │
│   This is why medical diagnosis uses MULTIPLE tests!       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Summary Table: Type I vs Type II

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│   CHARACTERISTIC      │  TYPE I ERROR (α)  │  TYPE II ERROR (β)   │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Definition          │ Reject true H₀     │ Fail to reject       │
│                       │                    │ false H₀             │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Also called         │ False Positive     │ False Negative       │
│                       │ False Alarm        │ Missed Detection     │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Symbol              │ α (alpha)          │ β (beta)             │
│   ────────────────────┼────────────────────┼────────────────────  │
│   You control it?     │ YES (you choose α) │ INDIRECTLY           │
│                       │                    │ (via n, α, effect)   │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Complement          │ Specificity (1-α)  │ Power (1-β)          │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Typical value       │ 0.05 (5%)          │ 0.20 (20%)           │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Court analogy       │ Convict innocent   │ Acquit guilty        │
│   ────────────────────┼────────────────────┼────────────────────  │
│   Medical analogy     │ Diagnose healthy   │ Miss sick patient    │
│                       │ as sick            │                      │
│   ────────────────────┼────────────────────┼────────────────────  │
│   To decrease         │ Lower α (be more   │ Increase n, α,       │
│                       │ conservative)      │ or effect size       │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

## Python Implementation

### Calculating and Visualizing Errors

```python
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt

def calculate_errors(mu_0, mu_1, sigma, n, alpha=0.05):
    """
    Calculate Type I error, Type II error, and Power
    for a two-tailed Z-test
    """
    # Standard error
    se = sigma / np.sqrt(n)
    
    # Critical values (two-tailed)
    z_crit = stats.norm.ppf(1 - alpha/2)
    x_crit_upper = mu_0 + z_crit * se
    x_crit_lower = mu_0 - z_crit * se
    
    # Type I Error (by design)
    type_1_error = alpha
    
    # Type II Error (probability of not rejecting when H1 is true)
    # P(x_crit_lower < X̄ < x_crit_upper | μ = μ₁)
    z_upper = (x_crit_upper - mu_1) / se
    z_lower = (x_crit_lower - mu_1) / se
    
    type_2_error = stats.norm.cdf(z_upper) - stats.norm.cdf(z_lower)
    
    power = 1 - type_2_error
    
    return {
        'alpha': alpha,
        'type_1_error': type_1_error,
        'type_2_error': type_2_error,
        'beta': type_2_error,
        'power': power,
        'critical_lower': x_crit_lower,
        'critical_upper': x_crit_upper,
        'se': se
    }

# Example
result = calculate_errors(mu_0=500, mu_1=504, sigma=10, n=25, alpha=0.05)

print("=" * 50)
print("TYPE I AND TYPE II ERROR ANALYSIS")
print("=" * 50)
print(f"\nParameters:")
print(f"  H₀: μ = 500")
print(f"  H₁: μ = 504")
print(f"  σ = 10")
print(f"  n = 25")
print(f"  α = {result['alpha']}")
print(f"\nResults:")
print(f"  Standard Error: {result['se']:.4f}")
print(f"  Critical Values: [{result['critical_lower']:.2f}, {result['critical_upper']:.2f}]")
print(f"  Type I Error (α): {result['type_1_error']:.4f} ({result['type_1_error']*100:.2f}%)")
print(f"  Type II Error (β): {result['type_2_error']:.4f} ({result['type_2_error']*100:.2f}%)")
print(f"  Power (1-β): {result['power']:.4f} ({result['power']*100:.2f}%)")
```

### Visualization Function

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def visualize_errors(mu_0, mu_1, sigma, n, alpha=0.05):
    """
    Visualize Type I and Type II errors
    """
    se = sigma / np.sqrt(n)
    z_crit = stats.norm.ppf(1 - alpha/2)
    x_crit_upper = mu_0 + z_crit * se
    x_crit_lower = mu_0 - z_crit * se
    
    # Create figure
    fig, ax = plt.subplots(figsize=(14, 7))
    
    # X range
    x_min = min(mu_0, mu_1) - 4*se
    x_max = max(mu_0, mu_1) + 4*se
    x = np.linspace(x_min, x_max, 1000)
    
    # H0 distribution
    y_h0 = stats.norm.pdf(x, mu_0, se)
    ax.plot(x, y_h0, 'b-', linewidth=2, label=f'H₀: μ = {mu_0}')
    ax.fill_between(x, y_h0, alpha=0.1, color='blue')
    
    # H1 distribution
    y_h1 = stats.norm.pdf(x, mu_1, se)
    ax.plot(x, y_h1, 'r-', linewidth=2, label=f'H₁: μ = {mu_1}')
    ax.fill_between(x, y_h1, alpha=0.1, color='red')
    
    # Type I Error (α) - tails of H0 beyond critical values
    x_alpha_left = x[x <= x_crit_lower]
    x_alpha_right = x[x >= x_crit_upper]
    ax.fill_between(x_alpha_left, stats.norm.pdf(x_alpha_left, mu_0, se), 
                    color='blue', alpha=0.5, label=f'Type I Error (α = {alpha})')
    ax.fill_between(x_alpha_right, stats.norm.pdf(x_alpha_right, mu_0, se), 
                    color='blue', alpha=0.5)
    
    # Type II Error (β) - H1 between critical values
    x_beta = x[(x >= x_crit_lower) & (x <= x_crit_upper)]
    y_beta = stats.norm.pdf(x_beta, mu_1, se)
    beta = stats.norm.cdf(x_crit_upper, mu_1, se) - stats.norm.cdf(x_crit_lower, mu_1, se)
    ax.fill_between(x_beta, y_beta, color='red', alpha=0.5, 
                    label=f'Type II Error (β = {beta:.3f})')
    
    # Power - H1 beyond critical values
    x_power = x[x >= x_crit_upper]
    y_power = stats.norm.pdf(x_power, mu_1, se)
    power = 1 - beta
    ax.fill_between(x_power, y_power, color='green', alpha=0.5,
                    label=f'Power (1-β = {power:.3f})')
    
    # Critical values
    ax.axvline(x_crit_lower, color='black', linestyle='--', linewidth=1.5)
    ax.axvline(x_crit_upper, color='black', linestyle='--', linewidth=1.5)
    ax.text(x_crit_lower, ax.get_ylim()[1]*0.95, f'{x_crit_lower:.2f}', 
            ha='center', fontsize=10)
    ax.text(x_crit_upper, ax.get_ylim()[1]*0.95, f'{x_crit_upper:.2f}', 
            ha='center', fontsize=10)
    
    ax.set_xlabel('Sample Mean (X̄)', fontsize=12)
    ax.set_ylabel('Probability Density', fontsize=12)
    ax.set_title(f'Type I and Type II Errors\nn = {n}, α = {alpha}, Effect = {mu_1 - mu_0}', 
                fontsize=14)
    ax.legend(loc='upper right')
    ax.grid(True, alpha=0.3)
    
    plt.tight_layout()
    plt.show()
    
    return {'alpha': alpha, 'beta': beta, 'power': power}

# Visualize
result = visualize_errors(mu_0=500, mu_1=504, sigma=10, n=25, alpha=0.05)
```

### Sample Size for Desired Power

```python
import numpy as np
from scipy import stats

def required_sample_size(mu_0, mu_1, sigma, alpha=0.05, power=0.80):
    """
    Calculate required sample size for desired power (two-tailed test)
    """
    beta = 1 - power
    z_alpha = stats.norm.ppf(1 - alpha/2)
    z_beta = stats.norm.ppf(1 - beta)
    
    effect = abs(mu_1 - mu_0)
    
    n = ((z_alpha + z_beta) ** 2 * sigma ** 2) / (effect ** 2)
    
    return int(np.ceil(n))

# Calculate required n for various power levels
print("Required Sample Sizes for Different Power Levels")
print("=" * 50)
print(f"H₀: μ = 500, H₁: μ = 504, σ = 10, α = 0.05")
print("-" * 50)

for power in [0.70, 0.80, 0.90, 0.95, 0.99]:
    n = required_sample_size(500, 504, 10, alpha=0.05, power=power)
    print(f"Power = {power:.0%}: n = {n}")
```

### Interactive Error Analysis

```python
import numpy as np
from scipy import stats

def error_analysis_table(mu_0, mu_1, sigma, alpha=0.05):
    """
    Show how errors change with sample size
    """
    print("\nEffect of Sample Size on Type II Error and Power")
    print("=" * 60)
    print(f"H₀: μ = {mu_0}, H₁: μ = {mu_1}, σ = {sigma}, α = {alpha}")
    print("-" * 60)
    print(f"{'n':>6} | {'SE':>8} | {'Type I (α)':>12} | {'Type II (β)':>12} | {'Power':>8}")
    print("-" * 60)
    
    for n in [10, 20, 30, 50, 75, 100, 150, 200]:
        result = calculate_errors(mu_0, mu_1, sigma, n, alpha)
        print(f"{n:>6} | {result['se']:>8.4f} | {result['type_1_error']:>12.4f} | "
              f"{result['type_2_error']:>12.4f} | {result['power']:>8.4f}")

error_analysis_table(500, 504, 10, 0.05)
```

---

## Practice Problems 📝

### Problem 1: Identifying Errors
A COVID test gives a positive result for someone who doesn't have COVID. What type of error is this?

<details>
<summary>Click for Answer</summary>

```
H₀: Person does NOT have COVID
H₁: Person HAS COVID

Test result: Positive (Claims person has COVID)
Reality: Person is healthy

This is a TYPE I ERROR (False Positive)

The test rejected H₀ (said "has COVID")
when H₀ was actually true (person is healthy).

Consequence: Unnecessary quarantine, anxiety, 
follow-up tests, but person is actually safe.
```

</details>

---

### Problem 2: Consequences
A drug that actually works is rejected by the FDA because trials didn't show significant effect. What type of error? What's the consequence?

<details>
<summary>Click for Answer</summary>

```
H₀: Drug has NO effect
H₁: Drug HAS effect

Decision: Failed to reject H₀ (drug not approved)
Reality: Drug actually works (H₁ is true)

This is a TYPE II ERROR (False Negative)

Consequences:
• Effective drug not available to patients
• Patients continue suffering
• Company loses investment
• Public health impact

This often happens when:
• Sample size is too small
• Effect size is modest
• Trial is underpowered
```

</details>

---

### Problem 3: Calculating β
For α = 0.05 (one-tailed, right), n = 36, μ₀ = 100, σ = 12, and true μ = 105, find β and power.

<details>
<summary>Click for Answer</summary>

```
Step 1: Find critical value
SE = σ/√n = 12/√36 = 2
Z_crit = 1.645 (one-tailed, α = 0.05)
X̄_crit = μ₀ + Z_crit × SE = 100 + 1.645(2) = 103.29

Step 2: Calculate β
β = P(X̄ < 103.29 | μ = 105)
  = P(Z < (103.29 - 105)/2)
  = P(Z < -0.855)
  = 0.196

Step 3: Calculate Power
Power = 1 - β = 1 - 0.196 = 0.804

Results:
• Type II Error (β) = 19.6%
• Power = 80.4%

This is adequate power (≥ 80%)!
```

</details>

---

### Problem 4: Reducing Errors
Given: α = 0.05, β = 0.30. How can you reduce β to 0.10 without changing α?

<details>
<summary>Click for Answer</summary>

```
To reduce β from 0.30 to 0.10 while keeping α = 0.05:

Option 1: INCREASE SAMPLE SIZE
• Most common and direct approach
• Narrower distributions → less overlap
• Typically need 2-3x more samples

Option 2: REDUCE VARIANCE
• Better measurement techniques
• More controlled environment
• More homogeneous sample

Option 3: STUDY A LARGER EFFECT
• Not always possible (effect is what it is)
• Choose populations where effect is larger

Option 4: USE ONE-TAILED TEST
• Only if scientifically justified
• Concentrates α in one tail
• More power in that direction

You CANNOT just "choose" a lower β!
You must change something about the study design.
```

</details>

---

### Problem 5: Which Error is Worse?
A factory tests products before shipping. Defective products harm customers. Which error is worse: shipping a defective product, or discarding a good product?

<details>
<summary>Click for Answer</summary>

```
H₀: Product is GOOD (meets specifications)
H₁: Product is DEFECTIVE

Type I Error: Discarding a good product
• Cost: Lost product, reduced efficiency
• Harm: Economic only

Type II Error: Shipping a defective product
• Cost: Customer harm, lawsuits, reputation damage
• Harm: Safety, trust, potentially severe

TYPE II ERROR IS WORSE in this context!

The factory should:
• Accept higher α (discard more products, even good ones)
• Minimize β (catch as many defects as possible)
• Use sensitive quality control (high power)
• Perhaps use multi-stage testing

"Better to throw away 10 good products than ship 
1 defective product that harms a customer."
```

</details>

---

## Summary: The Two Errors

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│               TYPE I AND TYPE II ERRORS                          │
│               ═════════════════════════                          │
│                                                                  │
│   TYPE I ERROR (α)           TYPE II ERROR (β)                   │
│   ────────────────           ─────────────────                   │
│   Reject true H₀             Fail to reject false H₀            │
│   FALSE POSITIVE             FALSE NEGATIVE                      │
│   "Seeing what isn't there"  "Missing what IS there"            │
│                                                                  │
│   THE TRADE-OFF:                                                 │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  ↓ α → ↑ β    (more conservative = more misses)         │   │
│   │  ↓ β → ↑ α    (more sensitive = more false alarms)      │   │
│   │                                                          │   │
│   │  Only way to reduce BOTH: INCREASE SAMPLE SIZE          │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   POWER = 1 - β                                                  │
│   ────────────────                                              │
│   Probability of detecting a real effect                        │
│   Goal: Power ≥ 0.80 (80%)                                      │
│                                                                  │
│   WHICH IS WORSE? DEPENDS ON CONTEXT!                           │
│   • Court: Type I worse (convicting innocent)                   │
│   • Screening: Type II worse (missing disease)                  │
│   • Always consider: What's the cost of each error?            │
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
│   TYPE I (α)                   TYPE II (β)                       │
│   ──────────                   ───────────                       │
│   False Positive               False Negative                    │
│   Reject true H₀               Miss false H₀                    │
│   You choose α                 β depends on n, effect, α        │
│   Typically 0.05               Typically 0.20                   │
│   "False alarm"                "Missed detection"               │
│                                                                  │
│   POWER = 1 - β = P(Reject H₀ | H₀ false)                       │
│   Target: Power ≥ 80%                                           │
│                                                                  │
│   TO INCREASE POWER:                                            │
│   • ↑ Sample size (n)                                           │
│   • ↑ Effect size                                               │
│   • ↑ α (trade-off!)                                           │
│   • ↓ Variance (σ²)                                             │
│   • Use one-tailed test (if justified)                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

> **"In hypothesis testing, we can't eliminate errors — we can only choose which error we're more willing to accept. The art of statistics is balancing these risks based on the real-world consequences of each mistake."**

Understanding Type I and Type II errors is essential for making informed decisions based on data. Now you know! ⚠️

---

*From false alarms to missed detections, from α to β — that's the unavoidable reality of inference!* 📊
# 📊 Correlation and Covariance

*"How do two variables move together?"*

---

## What Do They Measure?

Both measure the **relationship** between two variables.

- Do they move in the same direction?
- Do they move in opposite directions?
- Or no relationship at all?

---

## Covariance

*"Do two variables change together?"*

| Value | Meaning |
|-------|---------|
| **Positive** | Both increase together |
| **Negative** | One increases, other decreases |
| **Zero** | No relationship |

**Problem:** Value has no limit, hard to interpret.

```
Example:
Height & Weight → Covariance = 250 (positive)

But is 250 strong or weak? Hard to tell!
```

---

## Correlation

*"How strongly are two variables related?"*

Correlation fixes covariance by giving a value between **-1 and +1**.

| Value | Meaning |
|-------|---------|
| **+1** | Perfect positive (both increase together) |
| **0** | No relationship |
| **-1** | Perfect negative (one up, other down) |

---

## Correlation Scale

```
-1        -0.5         0         +0.5        +1
 │          │          │          │          │
 ├──────────┼──────────┼──────────┼──────────┤
 Strong    Weak       None      Weak      Strong
Negative  Negative            Positive  Positive
```

---

## Visual Examples

```
Positive (+1)      Negative (-1)      No Correlation (0)

    •  •               •                  •    •
   •  •                 •  •            •   •
  •  •                   •  •         •  •    •
 •  •                     •  •          •  •
                           •              •    •

(Both rise)         (One rises,        (Random scatter)
                    other falls)
```

---

## Quick Comparison

| Feature | Covariance | Correlation |
|---------|------------|-------------|
| Range | -∞ to +∞ | -1 to +1 |
| Easy to interpret? | No | Yes |
| Shows strength? | No | Yes |
| Shows direction? | Yes | Yes |

---

## Real Examples

| Variables | Correlation | Meaning |
|-----------|-------------|---------|
| Study hours & Grades | +0.85 | Strong positive |
| Exercise & Weight | -0.70 | Strong negative |
| Shoe size & Intelligence | 0.02 | No relationship |

---

## Important Note

> **Correlation ≠ Causation**

```
Ice cream sales ↑  and  Drowning ↑  → Correlation = +0.8

Does ice cream cause drowning? NO!

Hidden factor: Hot weather causes both.
```

---

> *"Covariance shows direction. Correlation shows direction AND strength."* 🚀
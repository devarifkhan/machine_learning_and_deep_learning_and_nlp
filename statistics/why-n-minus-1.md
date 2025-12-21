# 📊 Why Sample Variance Uses (n-1)?

*"The mystery of n-1 explained simply"*

---

## The Problem

When we calculate variance from a **sample**, we tend to **underestimate** the true population variance.

Why? Because sample data is usually closer to its own mean than to the population mean.

---

## Two Formulas

### Population Variance (divide by n)
```
σ² = Σ(x - μ)² / n
```
Use when you have **all** the data.

### Sample Variance (divide by n-1)
```
s² = Σ(x - x̄)² / (n-1)
```
Use when you have **part** of the data.

---

## Simple Explanation

| Reason | Explanation |
|--------|-------------|
| **Bias Correction** | Dividing by n gives a value that's too small. (n-1) fixes this. |
| **Degrees of Freedom** | Once you know the mean, only (n-1) values are free to vary. The last one is fixed. |
| **Better Estimate** | (n-1) gives a more accurate estimate of population variance. |

---

## Example

```
Sample: 10, 20, 30  (n = 3, mean = 20)

With n:    [(10-20)² + (20-20)² + (30-20)²] / 3 = 66.67
With n-1:  [(10-20)² + (20-20)² + (30-20)²] / 2 = 100

(n-1) gives a slightly larger, more accurate estimate.
```

---

## Degrees of Freedom — Simple Analogy

```
You have 3 numbers that must average 20.

Pick first number:  10  ✅ (free choice)
Pick second number: 20  ✅ (free choice)
Pick third number:  ?   ❌ (must be 30 to make average 20)

Only 2 numbers were "free" → Degrees of freedom = n-1 = 2
```

---

## Quick Summary

| Data Type | Divide By | Why |
|-----------|-----------|-----|
| **Population** | n | You have all data, no correction needed |
| **Sample** | n-1 | Corrects underestimation, more accurate |

---

> *"n-1 makes sample variance an unbiased estimator of population variance."* 🚀
# 📊 Measures of Dispersion

*"How spread out is your data?"*

---

## What is it?

Tells you how **scattered** or **spread** the data is from the center.

---

## Four Types

### 1. Range
*Difference between highest and lowest*

```
Data: 10, 20, 30, 40, 50

Range = 50 - 10 = 40
```

**Simple but affected by outliers**

---

### 2. Variance
*Average of squared differences from mean*

```
Data: 10, 20, 30

Mean = 20

Variance = [(10-20)² + (20-20)² + (30-20)²] / 3
         = [100 + 0 + 100] / 3
         = 66.67
```

**Higher variance = more spread**

---

### 3. Standard Deviation
*Square root of variance*

```
Variance = 66.67

Standard Deviation = √66.67 = 8.16
```

**Most commonly used — same unit as data**

---

### 4. Interquartile Range (IQR)
*Range of the middle 50% of data*

```
Data: 10, 20, 30, 40, 50, 60, 70

Q1 (25%) = 20
Q3 (75%) = 60

IQR = 60 - 20 = 40
```

**Good when outliers exist**

---

## Quick Comparison

| Measure | What it shows | Best for |
|---------|---------------|----------|
| **Range** | Total spread | Quick overview |
| **Variance** | Average spread | Calculations |
| **Std Deviation** | Typical spread | Most common use |
| **IQR** | Middle spread | Data with outliers |

---

## Example: Test Scores

```
Class A: 70, 72, 74, 76, 78  →  Std Dev = 2.8 (consistent)
Class B: 50, 60, 75, 90, 95  →  Std Dev = 17.7 (varied)

Both have Mean = 74, but Class B is more spread out.
```

---

> *"Central tendency shows the center. Dispersion shows the spread."* 🚀
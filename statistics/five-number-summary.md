# 📊 Five Number Summary

*"Describe your data in 5 numbers"*

---

## What is it?

The **Five Number Summary** gives a quick overview of your data using just 5 values.

---

## The 5 Numbers

| Number | Meaning |
|--------|---------|
| **Minimum** | Smallest value |
| **Q1** | 25th percentile |
| **Median (Q2)** | Middle value (50th percentile) |
| **Q3** | 75th percentile |
| **Maximum** | Largest value |

---

## Simple Example

```
Data: 12, 18, 24, 30, 36, 42, 48, 54, 60

1. Minimum = 12
2. Q1 = 21       (25% mark)
3. Median = 36   (middle value)
4. Q3 = 51       (75% mark)
5. Maximum = 60

Five Number Summary: [12, 21, 36, 51, 60]
```

---

## Visual: Box Plot

The 5 numbers create a **Box Plot**:

```
        Min   Q1    Median   Q3    Max
         │    │       │      │      │
         ├────┼───────┼──────┼──────┤
         12   21      36     51     60
              └───────────────┘
                   Box (IQR)
```

---

## What It Tells You

| Part | Shows |
|------|-------|
| Min to Max | Total range of data |
| Q1 to Q3 (Box) | Where middle 50% lives |
| Median line | Center of data |
| Whiskers | Spread on both sides |

---

## Real Example: Test Scores

```
Scores: 45, 52, 58, 62, 68, 72, 78, 85, 92

Five Number Summary:
• Min = 45     (lowest score)
• Q1 = 55      (bottom 25%)
• Median = 68  (middle score)
• Q3 = 81.5    (top 25% starts here)
• Max = 92     (highest score)

Insight: Most students scored between 55-81.5
```

---

> *"Five numbers tell the whole story of your data."* 🚀
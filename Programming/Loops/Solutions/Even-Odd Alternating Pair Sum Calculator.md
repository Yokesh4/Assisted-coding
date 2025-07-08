# 🔄 Alternative Pair Difference Sum Calculator

## 🧠 Problem Statement

You are given two integers, `s` (start) and `e` (end). Your task is to compute a special alternating pair difference sum from `s` to `e` using the following rules:

- If either `s` or `e` are negative, convert them to positive.
- Iterate from `s` to `e` in steps of 2.
- For each value `i`:
  - If `i == e` and `i + 1 > e`, just add `e` to the sum.
  - If `i` is even: add `(i - (i + 1))` to the sum.
  - If `i` is odd: add `((i + 1) - i)` to the sum.
- Return the final sum after completing the loop.

---

## 📝 Algorithm Steps

1. **Input Normalization**:
   - If both `s` and `e` are negative:
     - Convert both to their absolute values.
   - If only `s` is negative:
     - Convert `s` to positive.
   - If only `e` is negative:
     - Convert `e` to positive.

2. **Loop from `s` to `e` (inclusive)** with step size 2:
   - If `i == e` and `i + 1 > e`, add `e` to the sum and continue.
   - If `i` is even, perform `sum += (i - (i + 1))`
   - If `i` is odd, perform `sum += ((i + 1) - i)`

3. **Return the result**.

---

## 💻 Pseudocode

```pseudo
FUNCTION alternativePairSum(s, e):
    IF s < 0 AND e < 0:
        s = -s
        e = -e
    ELSE IF s < 0:
        s = -s
    ELSE IF e < 0:
        e = -e

    sum = 0

    FOR i FROM s TO e STEP 2:
        IF i == e AND i + 1 > e:
            sum += e
            CONTINUE

        IF i % 2 == 0:
            sum += (i - (i + 1))
        ELSE:
            sum += ((i + 1) - i)

    RETURN sum

```
💡 Complexity Analysis

| Metric           | Value                           |
| ---------------- | ------------------------------- |
| Time Complexity  | O(n) — Iterates from `s` to `e` |
| Space Complexity | O(1) — Constant extra space     |

---
🚀 Challenge
Try implementing this algorithm in your preferred language:

Java

Python

C++

JavaScript

---
✅ What to Do Next?
📂 Create a folder in your repo:
Questions/Math/

📄 Create file:
alternative-pair-sum.md

📝 Paste this content into the file

📌 Commit with a message:
Added alternative pair sum problem with solution and pseudocode


---

Let me know if you want:
- This exported as `.md` or `.pdf`
- Boilerplate code for Java, Python, C++
- Another problem documented in the same format



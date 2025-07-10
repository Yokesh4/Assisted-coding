# 🔁 Forward-Forward Even Sum Calculator

## 📝 Problem Statement  
You're developing a **smart street lighting system** for a city. The lights on each road are uniquely numbered. The city wants to calculate the **total energy consumption** for a subset of lights based on specific street sections. Here's how it works:

- Each street has **two sections**:
  - One where lights are checked in **forward direction** (`s1` to `e1`)
  - Another in the **backward direction** (`s2` to `e2`)
- Only **even-numbered lights** are considered for energy reporting.
- The system runs this analysis **only when both section starts** (`s1` and `s2`) are either **both even** or **both odd**.

## 🔍 Task  
Write a function that:
1. Accepts four integers:  
   - `s1`, `e1` → Start and end of the **forward** range.  
   - `s2`, `e2` → Start and end of the **backward** range.  
2. Takes absolute values of all inputs (in case of sensor errors).
3. If `s1` and `s2` do not match parity (i.e., one is even, one is odd), return **0**.

### 🟢 Real-World Conditions:
- Negative input values from faulty sensors must be treated as positive.
- Only even-numbered lights are summed.

## 📊 Sample Test Cases

| Test Case | Inputs (`s1`, `e1`, `s2`, `e2`) | Expected Output | Explanation |
|-----------|-------------------------------|-----------------|-------------|
| TC-1      | 1, 6, 3, 8                     | 30              | Odd + Odd → Sum of evens in [1–6] and [3–8] = 2+4+6+4+6+8 |
| TC-2      | 2, 4, 6, 8                     | 20              | Even + Even → 2+4+6+8 = 20 |
| TC-3      | 1, 3, 2, 4                     | 0               | Odd + Even → Mismatch → 0 |
| TC-4      | -1, 4, -3, 6                   | 16              | Inputs are negated to (1,4) and (3,6); Odd+Odd → 2+4+4+6 |
| TC-5      | 2, 5, 3, 7                     | 0               | Even + Odd → 0 |

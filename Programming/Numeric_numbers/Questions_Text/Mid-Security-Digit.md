# 🔐 Mid Security Digit

## 📝 Problem Statement

You are working on a **digital lock system**. Each lock's code is a **positive integer**. To generate a **security verification digit**, your system must extract the **middle digit** of the number:

- If the code has an **odd number of digits**, return the **middle digit**.
  - Example: For a 5-digit code `96356`, the middle digit is `3`.
  
- If the code has an **even number of digits**, return the **left-middle digit**.
  - Example: For a 4-digit code `1234`, the left-middle digit is `2`.

Write a function `int findMidNumber(int num)` that performs this operation.

---

## 📊 Sample Test Cases

| Test Case | Input  | Output | Explanation                                             |
|-----------|--------|--------|---------------------------------------------------------|
| TC-1      | `96356`| `3`    | Middle digit for 5-digit number `96356` is `3`.         |
| TC-2      | `1234` | `2`    | Left-middle digit for 4-digit number `1234` is `2`.     |

---

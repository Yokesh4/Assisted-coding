# 🔢 Count All Zeros in a String

## 📝 Problem Statement

You're building a system for a **secure transaction logger**. Each transaction is assigned a **reference number** as a **string**. These reference numbers may include leading, middle, or trailing zeros, which must be preserved exactly as entered.

### 🔍 Task

- Write a function that:
  - Counts how many times the digit `0` appears in the reference number (string).
  - Do not convert the string to an integer, and do not skip any zeros, regardless of their position.

---

## 🎯 Problem Explanation

Given a reference number as a string, you need to count how many times the digit `0` appears.

### ✔ Valid Example:
- Reference Number: `"500"`
- Zeros: Two `0` digits → Output: `2`

### ❌ Invalid Example:
- Reference Number: `"123"`
- Zeros: No zeros → Output: `0`

---

## 📊 Sample Test Cases

| Test Case | Input    | Output | Explanation                                         |
|-----------|----------|--------|-----------------------------------------------------|
| TC-1      | `"045"`  | `1`    | One `0` present → Output: `1`                      |
| TC-2      | `"540"`  | `1`    | One `0` present → Output: `1`                      |
| TC-3      | `"500"`  | `2`    | Two `0` present → Output: `2`                      |
| TC-4      | `"000"`  | `3`    | Three `0` present → Output: `3`                    |
| TC-5      | `"005"`  | `2`    | Two `0` present → Output: `2`                      |
| TC-6      | `"0"`    | `1`    | One `0` present → Output: `1`                      |
| TC-7      | `"123"`  | `0`    | No `0` present → Output: `0`                       |

---

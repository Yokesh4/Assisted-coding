# 🔢 Find First Zero Position in a Number

## 📝 Problem Statement

You are working on a system that processes **transaction reference numbers**. Each reference number is a **positive integer**, and sometimes includes zeros in between digits. 

### 🔍 Task

- Write a function that:
  - Identifies the position (starting from the **right**, starting at `1`) of the **first zero** in the given reference number.
  - If the number contains no zero, return the position after the **last digit** (i.e., length of the number + 1).
  - If the number starts with zero (e.g., `000` or `050`), handle the input as valid and ensure no confusion with octal representations.

---

## 🎯 Problem Explanation

Given a **transaction reference number**, you need to identify where the first zero occurs when read from **right to left**. 

### ✔ Valid Example:
- Reference Number: `504`
- Right to Left Check: First zero occurs at **position 2** → ✅ Valid

### ❌ Invalid Example:
- Reference Number: `123`
- No zero is present → Position after the last digit → ❌ Valid → Position is `4`.

---

## 📊 Sample Test Cases

| Test Case | Input    | Output | Explanation                                         |
|-----------|----------|--------|-----------------------------------------------------|
| TC-1      | `504`    | `2`    | First zero is at position `2` from the right.       |
| TC-2      | `540`    | `1`    | First zero is at position `1` from the right.       |
| TC-3      | `13400`  | `1`    | First zero is at position `1` from the right.       |
| TC-4      | `123`    | `4`    | No zero is present, position after last digit is `4`|

---

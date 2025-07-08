# 🧮 Even-Odd Alternating Pair Sum Calculator

## 📝 Problem Statement
You are building a number processor that computes a special **alternating pair difference sum** between two integers `s` and `e` based on their parity (even/odd) positions.

The logic needs to:
- Convert any negative values of `s` and `e` to positive.
- Iterate from `s` to `e`, skipping every second number (`i = i + 2`).
- Calculate:
  - If `i` is **even**: `i - (i + 1)`
  - If `i` is **odd**: `(i + 1) - i`
  - If the loop ends exactly at `i == e` and `i + 1 > e`, just add `e` to the sum.

## 🔍 Task
Write a function that:
1. Accepts two integers: `s` (start) and `e` (end).
2. Converts any negative `s` or `e` to their absolute values.
3. Loops from `s` to `e` in steps of 2.
4. Computes the alternating sum as described.
5. Returns the final result.

### 🟡 Special Conditions:
- If both `s` and `e` are negative, convert both to positive.
- If `i == e` and `i+1 > e`, just add `e` to sum.
- Result varies based on whether `s` and `e` are odd or even.

---

## 📊 Sample Test Cases

| Test Case | Input (`s`, `e`) | Expected Output | Explanation |
|-----------|------------------|-----------------|-------------|
| TC-1      | 1, 4             | 2               | (2-1) + (4-3) = 1 + 1 = 2 |
| TC-2      | 2, 4             | 3               | (2-3) + 4 = -1 + 4 = 3 |
| TC-3      | 2, 5             | -2              | (2-3) + (5-4) = -1 + (-1) = -2 |
| TC-4      | -3, -5           | -2              | Converted to (3,5) → (3-4) + (5-6) = -1 + (-1) = -2 |
| TC-5      | -2, 3            | 2               | Converted to (2,3) → (2-3) + 3 = -1 + 3 = 2 |
| TC-6      | 3, 3             | 3               | Only one value, `i == e`, i+1 > e → sum = 3 |
| TC-7      | 0, 1             | 1               | (0-1) + 1 = -1 + 1 = 0 |
| TC-8      | 4, 4             | 4               | i==e and i+1>e → sum = 4 |
| TC-9      | 0, 0             | 0               | Only `i==e`, `i+1 > e` → sum = 0 |
| TC-10     | -1, 2            | 2               | Converted: (1,2) → (1-2) + 2 = -1 + 2 = 1 |
| TC-11     | 1, 1             | 1               | Only `i==e`, i+1 > e → sum = 1 |
| TC-12     | 100, 100         | 100             | Boundary: Single even number, sum = 100 |
| TC-13     | -100, -98        | 0               | Converted to (100,98), invalid loop range, sum = 0 |

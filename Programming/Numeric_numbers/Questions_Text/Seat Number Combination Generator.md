# 🚉 Seat Number Combination Generator

## 📝 Problem Statement
You are working on a railway seat reservation system where seat numbers are displayed in a special combined format to help passengers easily locate adjacent seats.

Each seat has a unique number called the **"mid seat"**, and the system needs to generate a combination code that includes:
- Two seats before the given seat.
- The current seat.
- Two seats after the given seat.
- Special merging rules apply when adjacent seats cross into two-digit numbers.

## 🔍 Task
Write a function that:
1. Accepts an integer `midNum` representing the middle seat number.
2. Calculates:
   - The seat numbers of the **two seats before** (`prev`).
   - The seat numbers of the **two seats after** (`after`).
3. Merges them into a unique combination number:
   - Merge order: **prev → midNum → after**.
   - If `prev` becomes negative, skip it and return only after.
4. Rejects invalid inputs (`midNum` outside 0-9) by returning `-1`.

### 🟡 Special Conditions:
- If `prev` is negative, it is ignored in the final combination.
- Inputs outside the range 0-9 return `-1` as invalid.

## 📊 Sample Test Cases

| Test Case | Input (`midNum`) | Expected Output | Explanation |
|-----------|------------------|-----------------|-------------|
| TC-1      | 8                | 678910          | prev = 67, after = 910 → Result = 67 + 8 + 910 |
| TC-2      | 9                | 7891011         | prev = 78, after = 1011 → Result = 78 + 9 + 1011 |
| TC-3      | 7                | 56789           | prev = 56, after = 89 → Result = 56 + 7 + 89 |
| TC-4      | 0                | 12              | prev = -21 (ignored), after = 12 → Result = 12 |
| TC-5      | 10               | -1              | Invalid input, outside 0-9 range |
| TC-6      | 5                | 34567           | prev = 34, after = 67 → Result = 34 + 5 + 67 |
| TC-7      | -1               | -1              | Invalid input, negative value |
| TC-8      | 1                | 23              | prev = -8 (ignored), after = 23 → Result = 23 |
| TC-9      | 6                | 45678           | prev = 45, after = 78 → Result = 45 + 6 + 78 |


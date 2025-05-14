# 📚 Catalog Number Sorting Check

## 📝 Problem Statement

You are helping a librarian organize books in a **special locker** that stores books based on their **catalog number**.

Each **catalog number** consists of digits, and it must follow this **sorting rule**:
> ✅ The digits must be arranged in **non-decreasing order from right to left**  
> (i.e., each digit from right to left should be less than or equal to the one before it).

### 🔍 Task

- Write a method that:
  - Takes the **catalog number** as an **integer**.
  - Returns `true` if the digits are sorted according to the rule.
  - Returns `false` otherwise.

---

## 🎯 Problem Explanation

Given a catalog number, check if the digits are sorted in non-decreasing order from **right to left**.

### ✔ Valid Example:
- Catalog Number: `54321`
- Right to Left Check: `1 <= 2 <= 3 <= 4 <= 5` → ✅ Valid

### ❌ Invalid Example:
- Catalog Number: `54021`
- Right to Left Check: `1 <= 2` (OK), but `2 > 0` → ❌ Invalid

---

## 📊 Sample Test Cases

| Test Case | Input    | Output | Explanation                                         |
|-----------|----------|--------|----------------------------------------------------|
| TC-1      | `54321`  | true   | Right to left: `1 <= 2 <= 3 <= 4 <= 5` → Valid     |
| TC-2      | `54021`  | false  | `2 > 0` → Sorting breaks here → Invalid             |
| TC-3      | `0321`   | false  | `3 > 0` → Sorting breaks → Invalid                  |
| TC-4      | `4021`   | false  | `2 > 0` → Sorting breaks → Invalid                  |

---

## 🧠 Solution Approach (Algorithm)

This logic can be implemented in any programming language.

### ✅ Steps:
1. Convert the **catalog number** to a **string** to access each digit.
2. Traverse from the **rightmost digit** to the left.
3. For each digit, compare it with the digit before it.
4. If the current digit is **greater than the previous digit**, the rule is broken → return `false`.
5. If no violations occur, return `true`.

---

## 📝 Pseudocode

```pseudo
FUNCTION isSortedRightToLeft(number):
    Convert number to string representation → numStr
    FOR i FROM len(numStr) - 1 DOWNTO 1:
        IF numStr[i] > numStr[i - 1]:
            RETURN false
    RETURN true

# 🔄 Rearranging a Character Based on String Middle

## 📝 Problem Statement

You are developing a system that transforms an input string by swapping its **first character** with the **middle character**. The conditions are as follows:

- If the first character is **not a digit**, swap it with the **middle character**.
- If the **middle character** is a **digit**, swap the **first character** with the **character before the middle**.

### 🧩 Task

- Write a function `placeFirstAtMid` that performs this transformation.
- Your function should return the transformed string without modifying the original string.

### 🔒 Constraints:
- The string will have at least 1 character.
- Only basic libraries like `<string.h>` are allowed.

---

## 🎯 Problem Explanation

Given an input string, follow these rules to rearrange the characters:

1. If the first character is **not a digit**, swap it with the middle character.
2. If the middle character is a **digit**, swap the first character with the character before the middle.

---

## 📊 Sample Test Cases

| Input   | Output   | Explanation                                        |
|---------|----------|----------------------------------------------------|
| "abbcd" | "bbacd"  | Swapped first character `a` with middle `b`.      |
| "0bbcd" | "0bbcd"  | No swap, because the first character is a digit. |
| "ab0cd" | "0a0cd"  | Swapped first character `a` with the character before the middle, which is `0`. |
| "abbc"  | "bbac"   | Swapped first character `a` with middle `b`.      |

---

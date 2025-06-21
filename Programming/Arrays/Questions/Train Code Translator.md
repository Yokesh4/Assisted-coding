# 🚉 Train Code Translator

## 📝 Problem Statement
You are working for the **Railway Control Software Unit**. A special translation system encodes short station control codes based on incoming numeric patterns.

Each station code is provided as an **array of up to 3 integers**. Your task is to implement the logic for converting this control code into a single integer that represents the **encoded station number**.

## 🔍 Task
Write a function that:
1. Accepts an **integer array** `nums` of size up to 3.
2. Performs the following:
   - If length of the array is **greater than 3**, return `-1`.
   - If **only one unique value is negative**, convert that **one negative** to its **absolute value**.
   - If there are **multiple negative values** or **repeating negatives**, **retain them**.
   - Treat **zeros** as valid digits.
3. Combines the values to form a single number by **concatenating digits from left to right**.
   - Example: `[3, 4, 5]` → `345`
   - Example: `[-3, -4, -5]` → `-345`

### 🟡 Special Conditions:
- If there is **only one negative value**, convert that to **positive**.
- If there are **multiple** (different or same) **negative values**, retain as-is.
- Inputs with **more than 3 digits** are **invalid**, return `-1`.
- Zeros must **not be ignored**, they are part of the number.

## 📊 Sample Test Cases

| Test Case | Input Array        | Expected Output | Explanation                                                   |
|-----------|--------------------|-----------------|---------------------------------------------------------------|
| TC-1      | [3, 4, 5]          | 345             | All positive → Result = 3 + 4 + 5 = 345                       |
| TC-2      | [-3, -4, -5]       | -345            | All negative → Combined as -345                              |
| TC-3      | [0, 0, 0]          | 0               | All zeros remain                                              |
| TC-4      | [3, 5, 0]          | 350             | Last digit is 0 → Combined                                   |
| TC-5      | [0, 0, 4]          | 4               | Leading 0s → Final is 4                                      |
| TC-6      | [0, 0, -4]         | 4               | One negative → Convert to 4                                   |
| TC-7      | [-4, 0, -4]        | -404            | Multiple same negatives → Retain                             |
| TC-8      | [0, -4, -4]        | -44             | Multiple negatives → Retain                                  |
| TC-9      | [-4, 0, 0]         | 400             | One negative → 4, then 0, 0 → 400                             |
| TC-10     | [4, 0, 0]          | 400             | Normal case with trailing 0s                                 |
| TC-11     | [0, 4, 0]          | 40              | Middle digit is the only non-zero                            |
| TC-12     | [2, 3, 4, 5]       | -1              | Invalid: length > 3                                          |

## 💻 Function Signature

```java
public static int convertArraysToNumbers(int[] nums)

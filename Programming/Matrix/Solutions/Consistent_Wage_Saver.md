# Solution Explanation and Approach

## Problem Recap
We are given:
- A **wages matrix**, where each row represents one person’s daily wages for the week.
- The **base wage** is the first element (Day 1).
- A person is **Consistent Wage Saver** if:
  1. Every 2nd, 4th, … wage is **exactly double the base wage**.
  2. These doubled wages are **non-zero** and equal to each other.

We must return:
- `[person, savings]`  
   - **person** → 1-indexed row number of the consistent saver with the **highest doubled wage**.  
   - **savings** → the doubled wage amount.  
- If none are valid → `[-1, -1]`.

---

## Approach
1. Initialize:
   - `person = -1`  
   - `wage = -1`
2. Loop over each person:
   - Take `base = wages[i][0]`.
   - Check every **even index (2, 4, …)**:
     - If any wage ≠ `base * 2`, mark inconsistent → stop checking this row.
   - If all checks pass:
     - Ensure doubled wages are equal (`wages[i][2] == wages[i][4]`) and non-zero.
     - If this doubled wage is higher than the current best, update:
       - `person = i + 1` (since rows are 1-indexed in output).
       - `wage = base * 2`.
3. Return `[person, wage]`.

---

## Pseudo-code

```pseudo
FUNCTION ConsistentWageSaver(wages[][]):

    person ← -1
    wage ← -1

    FOR i FROM 0 TO wages.length-1:
        base ← wages[i][0]
        consistent ← TRUE

        FOR j FROM 2 TO wages[i].length-1 STEP 2:
            IF wages[i][j] ≠ base * 2:
                consistent ← FALSE
                BREAK

        IF consistent AND wages[i][2] == wages[i][4] AND wages[i][2] ≠ 0:
            IF base * 2 > wage:
                person ← i + 1
                wage ← base * 2

    RETURN [person, wage]

```

Example Walkthrough

Input:

```
wages = [
 {200, 50, 400, 50, 400, 100},
 {200, 50, 400, 50, 400, 100},
 {300, 50, 600, 50, 600, 100}
]

```

Execution:

Person 1 → base = 200 → doubled = 400 → valid.

Person 2 → same as Person 1.

Person 3 → base = 300 → doubled = 600 → valid and highest.

Output:

```
{3, 600}

```
---

Time Complexity

Outer loop → O(P) (where P = number of persons).

Inner loop → up to 3 checks (since at most 7 days per row).

Overall: O(P).

Space Complexity

O(1) → only a few variables are used.

---

Notes

This implementation assumes each row has ≥ 5 elements so that indices [2] and [4] exist.

If the input is shorter, boundary checks should be added.

The algorithm is efficient because it only checks fixed positions (2 and 4) in addition to the doubling rule.

---
## Test Case 1
```
int wages[][] = {
    {200, 50, 400, 50, 400, 100},
    {200, 50, 400, 50, 400, 100},
    {60,  50, 120, 50, 120, 100}
};

```

## Output:
```
[1, 400]
```
(Person 1 and 2 both valid with doubled wage 400, but Person 1 comes first.)

## Test Case 2
```
int wages[][] = {
    {200, 50, 400, 50, 400, 100},
    {200, 50, 400, 50, 400, 100},
    {60,  50, 120, 50, 120, 100},
    {250, 50, 500, 50, 500, 100}
};
```

## Output:
```
[4, 500]
```
## Test Case 3

```
int wages[][] = {
    {200, 50, 0, 50, 0, 100},
    {200, 50, 0, 50, 0, 100},
    {60,  50, 0, 50, 0, 100},
    {250, 50, 0, 50, 0, 100}
};
```
## Output:
```
[-1, -1]
```
## Test Case 4

```
int wages[][] = {
    {0, 50, 0, 50, 0, 100}
};
```
## Output:

```
[-1, -1]

```
(Base wage is zero, so no valid consistent doubling.)

---
👉 These are **all hidden test cases** (apart from the two sample inputs).

# Consistent Wage Saver

You are given a **wages matrix**, where each row represents the daily wages of a person over the week.  
The first element in each row is the **base wage (Day 1)**.  

Every 2nd day from the start (i.e., indices 2, 4, … ) should be exactly **double the base wage** if the person saves consistently.  
If the pattern breaks for a person, they are not considered consistent.

A person is considered a **Consistent Wage Saver** if:
1. Every alternating wage (2nd, 4th, …) is exactly double the base wage.  
2. These doubled wages are non-zero and equal to each other.

Among all consistent savers, return the person with the **highest doubled wage**.

---
## Task
Return an array of two integers:

person → 1-indexed row number of the consistent saver with the highest doubled wage.

savings → the doubled wage amount.

If no person satisfies the condition, return {-1, -1}.

---

## Sample Input 1
```

wages = [
 {200, 50, 400, 50, 400, 100},
 {200, 50, 400, 50, 400, 100},
 {300, 50, 600, 50, 600, 100}
]

```
## Output:
```

{3, 600}

```
Explanation:

Person 3 has base = 300.

Doubled wages = {600, 600} (valid and highest).

Thus, answer = {3, 600}.

---

## Sample Input 2

```
wages = [
 {200, 50, 0, 50, 1, 100},
 {200, 50, 0, 50, 1, 100},
 {60,  50, 0, 50, 1, 100},
 {250, 50, 0, 50, 1, 100}
]
```
## Output:

```
{-1, -1}
```
Explanation:

None of the rows have valid consistent doubling.

---

Constraints

1 ≤ wages.length ≤ 100

1 ≤ wages[i].length ≤ 7 (week up to 6 days)

0 ≤ wages[i][j] ≤ 10^4

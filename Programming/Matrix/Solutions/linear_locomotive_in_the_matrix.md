# Solution Explanation and Approach

## Problem Recap
We are given:
- An **n × n grid matrix** representing a train track system:
  - `0` → unbroken track (passable)  
  - `-1` → broken track (impassable unless repaired)  
- The train starts at `(Ye, 0)` and moves **row by row (left to right)** until it reaches `(Xe, Ye)`.  
- The train can **repair a broken track** only if one of these holds:
  1. There is a valid (already passed or unbroken) track directly above `(i-1, j)`.  
  2. There is a valid track at the **end of the previous row** `(i-1, n-1)`.  
  3. There is a valid track **two steps to the left** `(i, j-2)`.  
- If the starting cell `(Ye, 0)` is broken, the journey fails immediately.  
- Return **true** if the train can reach `(Xe, Ye)`, otherwise **false**.

---

## Approach
1. Iterate row by row from the starting row `Ye` until the last row `n-1`.
2. For each cell `(i, j)`:
   - If this cell is the **destination `(Xe, Ye)`**:
     - If broken (`-1`), attempt repair using `checkFixing`.
       - If repair successful → mark as passed and return true.
       - Else return false.
     - If not broken, mark as passed and return true.
   - If this cell is broken (`-1`):
     - Call `checkFixing` to see if it can be repaired.
       - If repair possible → mark as passed.
       - Else → return false immediately.
   - Otherwise, mark cell as passed.
3. If the loop completes without blockage, return true.

---

## Helper Function: `checkFixing`
```pseudo
FUNCTION checkFixing(matrix, n, i, j):
    // condition 1: track above
    IF i > 0 AND matrix[i-1][j] == 1:
        matrix[i-1][j] ← -1
        RETURN true

    // condition 2: last track of previous row
    IF i > 0 AND matrix[i-1][n-1] == 1:
        matrix[i-1][n-1] ← -1
        RETURN true

    // condition 3: two steps left in same row
    IF j > 1 AND matrix[i][j-2] == 1:
        matrix[i][j-1] ← -1
        RETURN true

    RETURN false
```
## Main Simulation: trainMakeDest

```
FUNCTION trainMakeDest(matrix, n, Xe, Ye):

    FOR i FROM Ye TO n-1:
        FOR j FROM 0 TO n-1:

            // destination reached
            IF i == Xe AND j == Ye:
                IF matrix[i][j] == -1:
                    IF checkFixing(matrix, n, i, j):
                        matrix[i][j] ← 1
                        RETURN true
                    ELSE:
                        RETURN false
                ELSE:
                    matrix[i][j] ← 1
                    RETURN true

            // handling broken cell
            IF matrix[i][j] == -1:
                IF checkFixing(matrix, n, i, j):
                    matrix[i][j] ← 1
                ELSE:
                    RETURN false

            // mark passed track
            matrix[i][j] ← 1

    RETURN true
```
## Example Walkthrough

## Example 1

Input:
```
n = 3
Xe = 2, Ye = 0
matrix =
[
 {0, 0, -1},
 {0, 0, 0},
 {0, 0, 0}
]
```

Execution:

Start at (0,0) → valid.

(0,1) valid, (0,2) broken but avoided since path drops at end of row.

Next rows all valid.

## Output:
```
true
```
## Example 2

Input:
```
n = 3
Xe = 2, Ye = 1
matrix =
[
 {0, 0, 0},
 {0, -1, -1},
 {-1, 0, 0}
]
```
Execution:

Start at (1,0) valid.

Next cell (1,1) broken. Cannot be repaired since none of the 3 repair rules apply.

Path blocked.

## Output:
```
false
```
---
## Time Complexity

Outer loop over rows → O(n)

Inner loop over columns → O(n)

checkFixing runs in O(1) per broken cell.

Overall: O(n²)

## Space Complexity

Only the input matrix is modified.

O(1) extra space.

---

## Notes
This algorithm is simulation-based (traces path cell by cell).
Early exit on blockage improves performance.
For very large grids, logic remains efficient since each cell is processed once.

---

# Additional Test Case Explanations – Train Path Problem
These cases extend beyond the sample inputs to ensure the correctness and robustness of the `trainMakeDest` method.

```
int arr1[][]={
    {0, 0, 0},
    {0, -1, -1},
    {-1, 0, 0}
};
```
---
## Test Case 1
```
trainMakeDest(arr1, 3, 1, 1)
```
Explanation:
Destination (1,1) itself is an obstacle -1.
The train can never stop on a blocked cell.

✔ Expected: 
```
false
```
## Test Case 2
```
trainMakeDest(arr1, 3, 0, 0)
```
Explanation:
Destination (0,0) is the starting point.
Since the train is already at this location, it is trivially reachable.

✔ Expected: 
```
true
```
## Test Case 3
```
trainMakeDest(arr1, 3, 1, 0)
```
Explanation:
Path (0,0) → (1,0) is valid since (1,0) is free.
No obstacles encountered.

✔ Expected: 
```
true
```
## Test Case 4
```
trainMakeDest(arr1, 3, 2, 0)
```
Explanation:
Path (0,0) → (1,0) → (2,0) is valid since both (1,0) and (2,0) are free.

✔ Expected: 
```
true
```
## Test Case 5
```
int arr2[][]={
    {0, -1, 0},
    {0, -1, -1},
    {-1, 0, 0}
};
```
---
```
trainMakeDest(arr2, 3, 1, 0)
```
Explanation:
Destination (1,0) looks reachable at first.
But from (0,0) → (1,0), the path is blocked further due to -1s on the right, making it an isolated cell.
Since continuation is impossible, the algorithm treats this as not reachable.

✔ Expected: 
```
false
```

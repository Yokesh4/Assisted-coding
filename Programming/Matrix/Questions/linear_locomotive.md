# Linear **Locomotive** in the Matrix

You are given an `n x n` grid matrix representing a train track system:

- `0` → unbroken track (passable)  
- `-1` → broken track (impassable unless repaired)  

The train starts at `(Ye, 0)` and needs to reach `(Xe, Ye)`, **moving row by row from top to bottom**.

The train moves **left to right in each row**, then drops to the next row, continuing until the destination is reached.

---

## Repair Rule

If the train encounters a broken track (`-1`), it can repair it **only if** at least one of the following conditions holds:

1. There is an unbroken or already-passed track **directly above** `(i-1, j)`.  
2. There is an unbroken or already-passed track **at the end of the previous row** `(i-1, n-1)`.  
3. There is an unbroken or already-passed track **two steps to the left** `(i, j-2)` in the same row.  

Once repaired, the broken track becomes a `0` (passed track).

Repairable track (can be used once, but after being used it becomes broken).

The starting cell `(Ye, 0)` **cannot** be repaired if broken — if it’s broken, return `false` immediately.

Return `true` if the train can reach `(Xe, Ye)`, else `false`.

---

## Sample Input 1
```psuedo
n = 3
s = 2
e = 0
matrix =
[
    [0,  0, -1],
    [0,  0,  0],
    [0,  0,  0]
]

```
Output
```psuedo

true

```
## Explanation
The train starts at (0,0) and passes (0,1).

The broken track at (0,2) is avoided by replacing the track that it passed before standing (j-2), since the path moves downward at the end of the row.

All tracks in rows 1 and 2 are unbroken, so the train reaches (2,0) successfully.

## Sample Input 1
```psuedo
n = 3
s = 2
e = 1
matrix =
[
    [0,  0,  0],
    [0, -1, -1],
    [-1, 0,  0]
]

```
Output
```psuedo

false

```
## Explanation
The train starts at (1,0), but this cell (1,1) is broken (-1).

According to the rules, the cell (1,1) cannot be repaired by (i-1, n-1), so the train is immediately blocked and cannot proceed to (2,1).

---

If you want, you can **also checkout the matching `solution.md`** under `solution/matrix`  in the same repo.



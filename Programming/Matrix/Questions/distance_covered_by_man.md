# Distance Covered by a Man

A man is walking through a rectangular grid of size **M × N**.  
The grid cells are numbered from **(0,0)** at the top-left to **(M-1, N-1)** at the bottom-right.

The man’s movement is as follows:  
- He starts at the **first cell of the row `Yc`**, i.e., coordinates **(Yc, 0)**.  
- He moves **row by row** from left to right, starting at column 0, and proceeds downwards.  
- The man stops immediately upon reaching the destination cell `(Xc, Yc)`.

You are given:
- The **distance `K`** the man covers when moving from one cell to an adjacent cell.
- The **destination coordinates `(Xc, Yc)`**.

Your task is to calculate the **total distance** the man covers from the starting position to the destination.

---

## Input Format
M N
K
Xc Yc

- `M` = Number of rows in the grid (1 ≤ M ≤ 1000)  
- `N` = Number of columns in the grid (1 ≤ N ≤ 1000)  
- `K` = Distance covered per move (1 ≤ K ≤ 10^6)  
- `Xc`, `Yc` = Destination cell coordinates (0 ≤ Xc < M, 0 ≤ Yc < N)

---

## Sample Input 1
5 3
3
3 1

**Output**

21

**Explanation**  
The man starts at `(1, 0)` (since `Yc = 1`) and moves left to right in each row until he reaches `(3, 1)`.  
He covers **7 moves** in total, and each move is 3 units long:  
`7 × 3 = 21`

## Sample Input 1
4 4
2
2 1

**Output**

10

**Explanation**  
The man starts at `(1, 0)` (since `Yc = 1`) and moves left to right in each row until he reaches `(2, 1)`.  
He covers **5 moves** in total, and each move is 2 units long:  
`5 × 2 = 10`





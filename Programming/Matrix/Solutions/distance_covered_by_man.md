# Solution Explanation and Approach

## Problem Recap
We are given:
- Grid size **M × N**.
- **K** distance covered per move.
- Destination cell coordinates `(destRow, destCol)`.

The man:
- Starts at `(destCol, 0)` (row = `destCol`, column = 0).
- Moves row-by-row, left to right, until he reaches `(destRow, destCol)`.
- We must calculate the **total distance** covered before stopping.

---

## Approach
1. Start `distance = 0`.
2. From the starting row (`destCol`) to the last row:
   - From column `0` to `n-1`:
     - If the current cell is the destination cell `(destRow, destCol)`:
       - Stop and return the current distance.
     - Else:
       - Add `K` to `distance`.
3. Output the total `distance` when destination is reached.

---

## Pseudo-code

FOR row FROM destCol TO m-1:
    FOR col FROM 0 TO n-1:
        IF row == destRow AND col == destCol:
            RETURN distance
        distance ← distance + k

RETURN distance


---

## Example Walkthrough
**Input:**

m = 5, n = 3, k = 3
destRow = 3, destCol = 1

**Execution:**
- Start at `(1, 0)`  
- Move across `(1, 1)`, `(1, 2)` → go to `(2, 0)`, `(2, 1)`, `(2, 2)` → `(3, 0)`, `(3, 1)` → stop.

**Moves Count:** 7 moves  
**Distance:** `7 × 3 = 21`

---

## Time Complexity
- **O(M × N)** in the worst case (destination at the bottom-right).

## Space Complexity
- **O(1)** → Only `distance` variable is used.

---

## Notes
- The pseudo-code is language-agnostic; you can translate it into Java, Python, C++, or any language.
- For very large grids, this method may be slow — consider using a formula-based O(1) approach to count moves without iterating.



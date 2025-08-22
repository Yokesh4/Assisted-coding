# 🛡️ Grid Guardian I

A watchman is patrolling a square apartment block represented as an `n × n` grid.  

Each cell in the grid can be one of the following:  
- `'V'` → Already visited apartment  
- `'O'` → Open apartment (can be directly marked visited by the watchman)  
- `'C'` → Closed apartment (requires a spare key from a neighbor to open)  
- `'G'` → Goal apartment (treated like an open apartment)  

---

## 🔑 Rules

1. If a cell is `'O'`, the watchman marks it as `'V'` (visited).  
2. If a cell is `'C'`, the watchman tries to unlock it using a spare key from one of its neighbors:  
   - Right neighbor `(i, j+1)` if it exists and is `'O'`.  
   - Bottom-left diagonal neighbor `(i+1, j-1)` if it exists and is `'O'`.  
3. If a spare key is found, he unlocks the `'C'` apartment, marks it as `'V'`, and increments the **spares used counter**.  
4. If no spare is available for a `'C'`, the watchman fails and the process stops immediately (return `-1`).  

---

## 📝 Task
The function processes the entire grid row by row, marking visited apartments and counting the number of spares used.

Return the total number of spares used if the watchman successfully visits all required apartments.

Return 1 if at any point a 'C' apartment cannot be unlocked.

---

## Sample Input 1
```
apartment = [
 ['V','O','V'],
 ['O','O','C'],
 ['O','V','G']
]
```
Output:
```
1
```
Explanation:

All 'O' are marked visited.

The 'C' at (1,2) borrows a spare from its left neighbor (1,1) which is 'O'.

Total spares used = 1.

## Sample Input 2
```
apartment = [
 ['C','O','V'],
 ['V','C','C'],
 ['V','V','G']
]
```
Output:
```
-1
```
Explanation:

The closed apartment (1,1) has no spare available in neighbors.

The process fails.

## Sample Input 3
```
apartment = [
 ['V','C','O'],
 ['O','O','O'],
 ['C','O','G']
]
```
Output:
```
2
```
Explanation:

Two 'C' apartments successfully unlock with spare keys.

Total spares used = 2.

## ⚙️ Constraints

1 ≤ n ≤ 50

Each cell ∈ { 'V', 'O', 'C', 'G' }

Grid is always square (n × n)

---


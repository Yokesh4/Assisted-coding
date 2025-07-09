## 🧠 Solution Approach (Algorithm)

### ✅ Steps:

1. **Input Normalization**:
   - Convert all four inputs `s1`, `e1`, `s2`, and `e2` to their absolute values to eliminate any impact of negative ranges due to faulty sensors or input errors.

2. **Check Starting Point Parity**:
   - Only proceed if:
     - Both `s1` and `s2` are **odd** **OR**
     - Both `s1` and `s2` are **even**.
   - If the parity doesn't match (e.g., one is odd, the other even), return `0`.

3. **Calculate Even Sum**:
   - For both ranges `[s1, e1]` and `[s2, e2]`, iterate through each number.
   - Add the number to a counter `evenc` **only if it is even**.

4. **Return Result**:
   - Return the total sum of even numbers from both ranges when parity condition is satisfied.

---

## 📝 Pseudocode

```pseudo
FUNCTION forwardBackwardEvenSum(s1, e1, s2, e2):
    SET s1 = ABS(s1)
    SET e1 = ABS(e1)
    SET s2 = ABS(s2)
    SET e2 = ABS(e2)
    
    SET evenc = 0

    IF (s1 MOD 2 == 1 AND s2 MOD 2 == 1) OR (s1 MOD 2 == 0 AND s2 MOD 2 == 0):
        FOR i FROM s1 TO e1:
            IF i MOD 2 == 0:
                evenc = evenc + i

        FOR j FROM s2 TO e2:
            IF j MOD 2 == 0:
                evenc = evenc + j
    ELSE:
        RETURN 0

    RETURN evenc
```
---
💡 Complexity Analysis
| Metric           | Value                                          |
| ---------------- | ---------------------------------------------- |
| Time Complexity  | O(n) — where n = (e1 - s1 + 1) + (e2 - s2 + 1) |
| Space Complexity | O(1) — Constant space for counters             |

---
🚀 Challenge
Try implementing this logic in your preferred language:

Python
Java
C++
JavaScript

---
✅ What to Do Next?
📁 Create a folder in your repo:
Questions/Math/

📄 Create file:
forward-backward-even-sum.md

📌 Paste this entire content into the file.

💬 Commit Message:
```
Added forward-backward even sum problem with algorithm, pseudocode, and analysis.
```

Let me know if you want the **Java implementation code block** or a **real-world scenario section** to go along with this!


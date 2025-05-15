## 🧠 Solution Approach (Algorithm)

### ✅ Steps:

1. **Input validation**:
   - If `midNum < 0` or `midNum > 9`, return `-1`.
2. **Calculate Previous Seats (`prev`)**:
   - `prev = (midNum - 2) * 10 + (midNum - 1)`
3. **Calculate After Seats (`after`)**:
   - If `midNum + 1` and `midNum + 2` are single digits:
     - `after = (midNum + 1) * 10 + (midNum + 2)`
   - If they are double digits, adjust by multiplying accordingly (100, 1000, etc.) to maintain correct digit placement.
4. **Merge `prev` and `midNum`**:
   - If `prev` is positive, `result = (prev * 10) + midNum`
   - Otherwise, start from 0.
5. **Merge `after` into the `result`**:
   - Multiply `result` by `100`, `1000`, or `10000` based on the number of digits in `after`.
   - Add `after` to `result`.
6. **Return the final combined seat number**.

---

## 📝 Pseudocode

```pseudo
FUNCTION CombinationGenerator(midNum):
    IF midNum < 0 OR midNum > 9:
        RETURN -1  // Invalid input

    prev = (midNum - 2) * 10 + (midNum - 1)

    IF (midNum + 1) > 0 AND (midNum + 1) < 9:
        after = (midNum + 1) * 10 + (midNum + 2)
    ELSE IF (midNum + 1) > 9 AND (midNum + 1) < 100:
        after = (midNum + 1) * 100 + (midNum + 2)
    ELSE IF (midNum + 2) > 9 AND (midNum + 2) < 100:
        after = (midNum + 1) * 100 + (midNum + 2)

    IF prev > 0:
        result = (prev * 10) + midNum
    ELSE:
        result = 0

    IF after HAS 3 DIGITS:
        result = (result * 1000) + after
    ELSE IF after HAS 4 DIGITS:
        result = (result * 10000) + after
    ELSE:
        result = (result * 100) + after

    RETURN result

```

💡 Complexity Analysis

| Metric           | Value                             |
| ---------------- | --------------------------------- |
| Time Complexity  | O(1) — Constant time calculations |
| Space Complexity | O(1) — Constant extra space       |

🚀 Challenge

Try implementing this algorithm in your preferred language:
Python
Java
C++
JavaScript

✅ What to Do Next?
Create a folder in your repo: Questions/Math/

Create file: seat-number-combination.md

Paste this content into the file.

Commit with a message:

Added seat number combination problem with solution and pseudocode


---

Let me know if you want me to generate example code snippets in any language or a ready-to-use repo folder structure!

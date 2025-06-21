## 🧠 Solution Approach (Algorithm)

### ✅ Steps:

1. **Input validation**:
   - If the length of the array `nums` is greater than 3, return `-1`.

2. **Count negative numbers**:
   - Traverse the array and count how many negative numbers exist.
   - If **only one** negative number exists, **convert it to positive** using absolute value.
   - If **more than one** negative (even if they are the same value), retain them all.

3. **Combine digits**:
   - Concatenate digits from left to right to form a single number.
   - Multiplying the result by 10 and adding the current digit simulates concatenation.

4. **Return final number**:
   - The final result is the single integer representing the station code.

---

## 📝 Pseudocode

```pseudo
FUNCTION convertArraysToNumbers(nums):
    IF length(nums) > 3:
        RETURN -1

    count = 0
    index = -1

    FOR i FROM 0 TO length(nums) - 1:
        IF nums[i] < 0:
            count += 1
            index = i

    FOR i FROM 0 TO length(nums) - 1:
        IF i == index AND count == 1:
            nums[i] = ABS(nums[i])

    result = 0
    FOR i FROM 0 TO length(nums) - 1:
        result = result * 10 + nums[i]

    RETURN result
```
💡 Complexity Analysis
| Metric           | Value                                 |
| ---------------- | ------------------------------------- |
| Time Complexity  | O(1) — Constant time (max 3 elements) |
| Space Complexity | O(1) — Constant extra space           |



🚀 Challenge

Try implementing this algorithm in your preferred language:

Python

Java

JavaScript

C++

---

Let me know if you want me to generate example code snippets in any language or a ready-to-use repo folder structure!



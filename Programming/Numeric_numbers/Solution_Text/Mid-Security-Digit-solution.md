## 🧠 Solution Approach (Algorithm)

The approach involves finding the middle digit of the given integer by following these steps:

1. **Count the number of digits** in the number.
2. **Find the middle index** (or left-middle for even number of digits).
3. **Traverse the number** until you reach the middle digit and extract it.
4. Return the extracted digit.

### Solution Steps:
1. Start with the **input number**.
2. Use a **while loop** to count the number of digits by repeatedly dividing the number by 10.
3. Once the count is known, calculate the **middle index** of the number.
4. Use another **while loop** to divide the number until you reach the middle position.
5. Return the **middle digit** by using the modulus operator (`%`).

---

## 📝 Pseudocode

```pseudo
FUNCTION findMidNumber(num):
    countVar = num
    resVar = num
    c = 0
    WHILE countVar > 0:
        countVar /= 10
        c++
    i = c / 2
    WHILE i > 0:
        resVar /= 10
        i--
    RETURN resVar % 10

```
💡 Complexity Analysis

| Metric           | Value                            |
| ---------------- | -------------------------------- |
| Time Complexity  | O(N), where N = number of digits |
| Space Complexity | O(1), constant extra space used  |

🚀 Challenge

Try implementing this in:
Python
Java
C++
JavaScript

✅ What to Do Next?
Create folder in your repo: Questions/Text/

Create file: mid-security-digit.md

Paste this content into it.

Commit the changes with a message:

Added Mid Security Digit problem with solutions and test cases


---

### 📌 **What you can do next**:
1. Add this file to your repository in the folder structure (`Questions/Text/`).
2. Commit with a message: `Added Mid Security Digit question`.

---

Let me know if you would like further assistance with this or anything else!

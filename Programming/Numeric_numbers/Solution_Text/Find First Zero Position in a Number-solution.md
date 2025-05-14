## 🧠 Solution Approach (Algorithm)

To find the first zero position, you can follow this approach:

1. Start with `i = 1`, representing the first position from the right.
2. Traverse the number from right to left using modulo (`%`) and division (`/`).
3. If a zero is encountered, return the current position `i`.
4. If no zero is found, return `i + 1` (position after the last digit).

5. ## 📝 Pseudocode

```pseudo

FUNCTION zeroPosition(num):
    SET i = 1  // Start from the first position from the right
    
    WHILE num > -1:
        SET digit = num % 10  // Get the rightmost digit
        
        IF digit == 0:
            RETURN i  // Return the current position of the first zero
        
        num = num / 10  // Remove the rightmost digit
        
        IF num == 0:
            RETURN i + 1  // If no zero is found, return the position after the last digit
        
        INCREMENT i  // Move to the next position from the right
    
    RETURN i + 1  // If no zero, return the position after the last digit

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

Create file: find-zero-position.md

Paste this content into it.

Commit the changes with a message:

Added Find First Zero Position problem with solutions and test cases


---

### 📌 **What you can do next**:
1. Add this file to your repository in the folder structure (`Questions/Text/`).
2. Commit with a message: `Added Find First Zero Position question`.

This format is similar to the one for the **Catalog Number Sorting Check** problem, making it easy to maintain a professional and organized repo. Let me know if you need any further adjustments!



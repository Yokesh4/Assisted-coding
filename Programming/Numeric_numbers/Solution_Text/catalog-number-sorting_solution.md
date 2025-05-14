## 🧠 Solution Approach (Algorithm)

This logic can be implemented in any programming language.

### ✅ Steps:
1. Convert the **catalog number** to a **string** to access each digit.
2. Traverse from the **rightmost digit** to the left.
3. For each digit, compare it with the digit before it.
4. If the current digit is **greater than the previous digit**, the rule is broken → return `false`.
5. If no violations occur, return `true`.

---

## 📝 Pseudocode

```pseudo
FUNCTION isSortedRightToLeft(number):
    Convert number to string representation → numStr
    FOR i FROM len(numStr) - 1 DOWNTO 1:
        IF numStr[i] > numStr[i - 1]:
            RETURN false
    RETURN true

💡 Complexity Analysis

Metric	Value
Time Complexity	O(N), where N = number of digits
Space Complexity	O(1), constant extra space used

🚀 Challenge
Try implementing this in:

Python

Java

C++

JavaScript


---

## ✅ **What to Do Next?**
1. **Create folder in your repo**: `Questions/Text/`
2. **Create file**: `catalog-number-sorting.md`
3. **Paste this content into it**.
4. **Commit the changes** with a message:  
   > `Added catalog number sorting problem with solutions and test cases`

---

Do you want me to give you a **ready-made GitHub folder structure with files + sample README.md content as a ZIP** for your entire Question Bank repo?  
Reply **"Yes, give me ready-made repo structure"** if you'd like it. 🔥

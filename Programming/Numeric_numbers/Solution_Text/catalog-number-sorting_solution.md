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


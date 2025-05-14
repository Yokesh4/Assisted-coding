## 🧠 Solution Approach (Algorithm)

### ✅ Steps:
1. **Find the length** of the string.
2. **Check the first character**:
   - If the first character is a **digit**, return the string as is.
3. **Find the middle character** by calculating `len / 2`.
4. **Check if the middle character is a digit**:
   - If yes, swap the first character with the character before the middle.
   - If no, swap the first character with the middle character.
5. **Return the modified string**.

### 📝 Pseudocode:

```pseudo

FUNCTION placeFirstAtMid(input):
    SET len = LENGTH(input)   // Find length of the string
    SET result = DUPLICATE(input)  // Create a copy of the input string
    
    IF result[0] IS A DIGIT:  // If first character is a digit
        RETURN result  // No swap needed
    
    SET mid_index = len / 2    // Find the middle index
    SET first_char = result[0]  // Store the first character
    SET mid_char = result[mid_index]  // Store the middle character

    IF mid_char IS A DIGIT:   // If middle character is a digit
        mid_index = mid_index - 1  // Shift to the character before middle
    
    // Swap the first character and the target character
    result[0] = result[mid_index]
    result[mid_index] = first_char

    RETURN result  // Return the modified string

```

💡 Complexity Analysis

| Metric           | Value                                |
| ---------------- | ------------------------------------ |
| Time Complexity  | O(N), where N = length of the string |
| Space Complexity | O(N), for the duplicate string       |



🚀 Challenge
Try implementing this in:

Python
Java
C++
JavaScript

✅ What to Do Next?
Create folder in your repo: Questions/Text/

Create file: rearrange-char-mid.md

Paste this content into it.

Commit the changes with a message:

Added Rearranging a Character Based on String Middle problem with solutions and test cases


---

### 📌 **Explanation of Steps**:
1. **Duplicate the string** to avoid modifying the original.
2. **Check if the first character is a digit**. If it is, simply return the original string.
3. **Calculate the middle index** using the formula `len / 2`.
4. **Check if the middle character is a digit**. If it is, adjust the index to point to the character before the middle.
5. **Swap the first character** with the appropriate character (middle or before middle).
6. **Return the modified string**.

---

### 📌 **What you can do next**:
1. Add this file to your repository in the folder structure (`Questions/Text/`).
2. Commit with a message: `Added Rearranging a Character Based on String Middle problem`.

This markdown format provides a comprehensive explanation, solution approach, and test cases in a way that can be easily implemented in any programming language. Let me know if you need further modifications or more examples!

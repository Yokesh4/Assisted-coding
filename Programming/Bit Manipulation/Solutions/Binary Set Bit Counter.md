# 🔢 Binary Set Bit Counter

## 🧠 Solution Approach (Algorithm)

This algorithm counts the **number of 1s (set bits)** in the **64-bit binary representation** of a given `long` integer in Java. The logic works even for **negative numbers** by using **unsigned right shift (`>>>`)**, ensuring proper bit traversal regardless of sign.

---

### ✅ Steps:

1. **Accept a long number** (`num`) as input.
2. **Initialize** a `count = 0` to keep track of the set bits.
3. **Loop** through the number until it becomes 0:
   - Use bitwise AND `num & 1` to check if the **least significant bit (LSB)** is set (`1`).
   - If so, increment the count.
   - Use **`num >>>= 1`** (unsigned right shift) to move to the next bit, avoiding sign extension.
4. After the loop ends, print the total `count` of set bits.

---

## 📝 Pseudocode

```pseudo
FUNCTION countBit(num):
    count ← 0
    WHILE num ≠ 0:
        IF (num AND 1) == 1:
            count ← count + 1
        num ← num >>> 1
    PRINT "Set bit count: " + count
```

---

💡 **Complexity Analysis**

| Metric           | Value                             |
|------------------|-----------------------------------|
| Time Complexity  | O(1) — Max 64 iterations (fixed)  |
| Space Complexity | O(1) — Constant space usage       |

---

## 🧪 Sample Input/Output & Explanation

| Input Value           | Binary Representation (Truncated)           | Set Bits | Explanation                                                                 |
|------------------------|---------------------------------------------|----------|-----------------------------------------------------------------------------|
| `-8`                   | `111...11111000`                            | 61       | Two's complement of `-8` has 61 set bits in 64-bit form                     |
| `Short.MAX_VALUE`      | `00000000 00000000 01111111 11111111`       | 15       | 15 bits set (`32767` = all lower 15 bits set)                              |
| `8`                    | `00000000 00000000 00000000 00001000`       | 1        | Only the 4th bit is set                                                    |
| `Short.MIN_VALUE`      | `11111111 11111111 10000000 00000000`       | 49       | Two's complement of `-32768` in 64-bit has 49 ones                         |
| `Long.MIN_VALUE`       | `10000000...0000` (only MSB is 1)           | 1        | Only the highest bit (bit 63) is set                                       |
| `Long.MAX_VALUE`       | `01111111...1111` (all but MSB are 1)       | 63       | All 63 lower bits are 1                                                    |
| `Integer.MAX_VALUE`    | `00000000 01111111 11111111 11111111`       | 31       | Highest 31 bits set                                                        |
| `Integer.MIN_VALUE`    | `11111111 10000000 00000000 00000000`       | 33       | Only MSB is 1 + 32 extension bits                                          |
| `Byte.MAX_VALUE`       | `01111111`                                  | 7        | Highest positive 8-bit signed value (7 bits set)                           |
| `Byte.MIN_VALUE`       | `10000000`                                  | 57       | Only MSB set + sign extended to 64 bits in two’s complement                |
| `16`                   | `00000000 00000000 00000000 00010000`       | 1        | Only 5th bit is set                                                        |
| `0`                    | `00000000...0000`                           | 0        | No bits set                                                                |
| `-1`                   | `11111111...1111`                           | 64       | All bits are set in two’s complement of -1                                 |
| `32`                   | `00000000 00000000 00000000 00100000`       | 1        | Only 6th bit is set                                                        |

---

## ✅ Example Java Code

```java

  public static void countBit(long num) {
    int count = 0;

    while (num != 0) {
      if ((num & 1) == 1) {
        count++;
      }
      num >>>= 1; // unsigned right shift
    }

    System.out.println("Set bit count: " + count);
  }

```

---

🚀 **Challenge**

Try modifying this logic to:
- Count bits using `Brian Kernighan’s Algorithm` for faster performance.
- Return the result instead of printing it (for unit testing).
- Count **unset bits (0s)** instead.

---

✅ **What to Do Next?**

- Create a folder in your repo: `Questions/Binary/`
- Create file: `count-set-bits.md`
- Paste this content into the file.
- Commit with message:  
  ```
  Added set bit counting problem with algorithm, analysis, and test cases
  ```

---

Let me know if you want this in a downloadable `.md` file or need C++/Python versions of the implementation!

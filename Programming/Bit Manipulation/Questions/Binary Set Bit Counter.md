# 🧮 Binary Set Bit Counter

## 📝 Problem Statement
You are developing a utility for analyzing the **number of set bits** (`1`s) in the binary representation of various numeric types in Java. This tool helps developers and testers evaluate the bit-level structure of values across types like `byte`, `short`, `int`, and `long`.

You need to create a function that counts how many bits are set (`1`) in the **64-bit binary representation** of a given `long` value.

---

## 🔍 Task

Implement a method that:
1. Accepts a **`long` number** as input.
2. Treats the number as a **64-bit two's complement binary**.
3. Counts and prints the number of `1`s (set bits) in the binary form.
4. Shifts bits **unsigned** (`>>>`) to ensure all 64 bits are evaluated (even for negative numbers).

---

### ⚙️ Method Signature

```java
public static void countBit(long num)
```

> Output Format:
```
Set bit count: <count>
```

---

## 🟡 Special Conditions

- Negative numbers are stored in **two's complement** form in Java.
- Use the **unsigned right shift operator (`>>>`)** to avoid infinite loops with negative numbers.
- Java treats all smaller types (`byte`, `short`, `int`) as `int`, so you must handle promotion to `long` properly when analyzing bits.
  
---

## 📊 Sample Test Cases

| Test Case | Input (`num`)             | Expected Output             | Explanation                                                        |
|-----------|---------------------------|-----------------------------|--------------------------------------------------------------------|
| TC-1      | -8                        | `Set bit count: 61`         | `-8L` = `111...1000` → 61 ones in 64-bit 2’s complement            |
| TC-2      | `Short.MAX_VALUE` (32767) | `Set bit count: 15`         | Binary: `00000000...011111111111111` (15 ones)                     |
| TC-3      | 8                         | `Set bit count: 1`          | Binary: `1000` has 1 set bit                                       |
| TC-4      | `Short.MIN_VALUE` (-32768)| `Set bit count: 49`         | 2’s complement of `short` -32768 has 49 ones in 64-bit long        |
| TC-5      | `Long.MIN_VALUE`          | `Set bit count: 1`          | Only MSB is set in 64-bit: `100...0`                               |
| TC-6      | `Long.MAX_VALUE`          | `Set bit count: 63`         | All bits except MSB are 1                                          |
| TC-7      | `Integer.MAX_VALUE`       | `Set bit count: 31`         | Binary of `2^31 - 1` → 31 ones                                     |
| TC-8      | `Integer.MIN_VALUE`       | `Set bit count: 33`         | MSB set, rest 0; promoted to long → 33 ones (32 + sign bits)       |
| TC-9      | `Byte.MAX_VALUE` (127)    | `Set bit count: 7`          | 01111111 → 7 set bits                                              |
| TC-10     | `Byte.MIN_VALUE` (-128)   | `Set bit count: 57`         | 2’s complement long of -128 has 57 ones                            |
| TC-11     | 16                        | `Set bit count: 1`          | 2⁴ = 16 → only one bit set                                         |
| TC-12     | 0                         | `Set bit count: 0`          | All bits are 0                                                     |
| TC-13     | -1                        | `Set bit count: 64`         | All 64 bits are set to 1                                           |
| TC-14     | 32                        | `Set bit count: 1`          | Only one set bit in 6th position                                   |

---




## LINKS
[leetcode](https://leetcode.com/problems/reverse-string)

---
## PROBLEM
<pre>
def reverse_string(self, s: List[str]) -> None:

    # initialize two pointers: 
    # `start` will point to the beginning of the string
    # `end` will point to the end of the string

    start = 0 
    end = len(s) - 1 

    # iterate as long as start is less than end

    while start < end:

        # swap characters at the start and end positions

        s[start], s[end] = s[end], s[start]

        # move the `start` pointer rightwards and the `end` pointer leftwards

        start += 1
        end -= 1 

    # no return value is necessary, as the modification is done in-place
    return s
</pre>
---

## LOGIC 

### **Observation**:
To reverse a string, we need to swap characters from both ends of the string toward the center. The process stops when the two pointers meet or cross each other.

---

### **Step 1 – Initialize Two Pointers**:
- Start with two pointers:
  - `start` at the **beginning** of the string (index 0).
  - `end` at the **end** of the string (index `n-1`, where `n` is the length of the string).

### **Step 2 – Swap Characters**:
- While `start < end`, swap the characters at positions `start` and `end`.
- Move the `start` pointer **right** (increment) and the `end` pointer **left** (decrement) after each swap.

### **Step 3 – Continue Until Pointers Meet**:
- Continue the swapping process until the `start` pointer is no longer less than the `end` pointer (i.e., the two pointers meet in the middle or cross each other).
- Since each swap happens in-place, no additional memory is used, making this approach efficient.

### **Step 4 – End of Process**:
- Once the pointers meet or cross, the string has been reversed.

---

## COMPLEXITY

![Time Complexity](https://img.shields.io/badge/Time-O(n)-blue)
![Space Complexity](https://img.shields.io/badge/Space-O(1)-green)

---

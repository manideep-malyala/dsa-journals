## LINKS

[leetcode](https://leetcode.com/problems/largest-odd-number-in-string)

---

## PROBLEM
<pre>
def largest_odd_number(num: str) -> str:

    # step 1 – scan from the end:
    # find the rightmost index where the digit is odd

    ind = -1
    for i in range(len(num) - 1, -1, -1):
        if int(num[i]) % 2 != 0:
            ind = i
            break

    # step 2 – skip leading zeros:
    # find the first non-zero digit from the left

    j = 0
    while j < ind and num[j] == '0':
        j += 1

    # step 3 – return the largest odd substring:
    # return the substring from j to ind (inclusive)

    return num[j:ind + 1]
</pre>

---

## LOGIC

### Observation:
For a substring to represent an **odd number**, it must **end with an odd digit** (`1, 3, 5, 7, 9`).


### Step 1 – Scan from the End:
Traverse the string from the **end towards the beginning** to find the **first occurrence of an odd digit**.  
Let this index be **`i`**.  
This means the substring from the start of the string **up to `i`** could be the **largest odd number**.


### Step 2 – Skip Leading Zeros:
To ensure the number is valid and doesn't include leading zeros,  
scan from the **start of the string** to find the **first non-zero digit index**, say **`j`**.


### Step 3 – Return the Largest Odd Substring:
If an odd digit was found (i.e., `i != -1`),  
return the substring from index **`j` to `i`** (inclusive).  
This is the **longest valid odd-valued substring** possible.

---
## COMPLEXITY

![Time Complexity](https://img.shields.io/badge/Time-O(n)-blue)
![Space Complexity](https://img.shields.io/badge/Space-O(1)-green)


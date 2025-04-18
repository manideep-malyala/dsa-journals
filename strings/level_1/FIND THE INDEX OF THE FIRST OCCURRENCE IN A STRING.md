## LINKS

[leetcode](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string?envType=problem-list-v2&envId=string)

---
## PROBLEM

<pre> 
def needle_in_haystack(haystack: str, needle: str) -> int:
    # Length of needle and haystack
    n, m = len(needle), len(haystack)

    # loop through the haystack from 0 to (m - n + 1)
    # this ensures we check for a substring of length n starting from each index i

    for i in range(m - n + 1):

        # if the substring of length n starting at index i matches the needle

        if haystack[i:i + n] == needle:
            return i  # return the index of the first occurrence
    
    # if no match was found, return -1
    return -1  

    # ALTERNATE APPROACH
    # built-in find method to simplify this:
    # return haystack.find(needle)
</pre>
---
## LOGIC


### Initialize Lengths:
- `n` is the length of the **needle**.
- `m` is the length of the **haystack**.

### Loop Through the Haystack:
- We need to check whether the needle can fit within the remaining characters of the haystack, so we loop from `0` to `(m - n + 1)`.
- `m - n + 1` ensures we only check up to the last possible starting point where the full needle can fit. This is because the remaining length in the haystack should be at least as long as the needle.

### Check Substring Match:
- At each index `i`, we extract the substring of length `n` from **haystack** and compare it with **needle**.
- If the substring matches the needle, we return the current index `i` as the first occurrence.

### Return `-1` if Not Found:
- If no match is found by the time the loop ends, return `-1` indicating the needle is not in the haystack.

---
## COMPLEXITY

![Time Complexity](https://img.shields.io/badge/Time-O(m%20*%20n)-blue)
![Space Complexity](https://img.shields.io/badge/Space-O(n)-green)

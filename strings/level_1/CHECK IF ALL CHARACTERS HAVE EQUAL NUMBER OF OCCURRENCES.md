## LINKS
[leetcode](https://leetcode.com/problems/check-if-all-characters-have-equal-number-of-occurrences?envType=problem-list-v2&envId=string)

---
## PROBLEM

<pre>

from collections import Counter

def are_occurances_equal(s: str) -> bool:

    # count the frequency of each character using counter

    model = Counter(s)

    # ALTERNATE APPROACH (without using Counter)
    # Initialize frequency dictionary with 0 for each character
    # model = { character: 0 for character in s }
    # for c in s:
    #     model[c] += 1

    # convert the frequency values to a set
    # if all characters have the same frequency, set size will be 1

    return len(set(model.values())) == 1

</pre>


---
## LOGIC 

### Observation  
If every character appears the same number of times, then the frequency values stored in a dictionary will all be equal. So, converting those values into a set will give a set of size 1.

### Step-by-Step Approach

**Step 1 – Initialize an Empty Dictionary**  
Create an empty dictionary `freq_map` to store character frequencies.

**Step 2 – Loop Through the String**  
For each character `c` in the string:
- If `c` is already in `freq_map`, increment its value by 1.
- If not, initialize `freq_map[c] = 1`.

**Step 3 – Extract Frequency Values**  
Once the loop is done, get all values from the dictionary using `freq_map.values()`.

**Step 4 – Convert to Set**  
Convert the values to a set. If all characters have the same frequency, the set will contain only one element.

**Step 5 – Return Result**  
Check if the length of the set is 1:
- If yes, return `True`.
- Otherwise, return `False`.

---

## COMPLEXITY

![Time Complexity](https://img.shields.io/badge/Time-O(n)-blue)
![Space Complexity](https://img.shields.io/badge/Space-O(n)-green)

# [Array Duplicate](https://github.com/skoodath/coding_challenges/blob/master/arrayduplicate.js)

Source [Leetcode](https://leetcode.com/problems/contains-duplicate/)

## Problem

> Easy

Given an integer array num, return true if any value appears twice in the array and return false if every element is distint.

### Example 1

```
Input: `num = [1, 2, 3, 1]`
Output: `true`
```

### Example 2

```
Input: `num = [1, 2, 3, 4]`
Output: `false`
```

---

### Solution

1. Create a new set from the array which removes duplicates.
2. Compare the length of the array to the size of the set.
   - If the comparison returns true, it means there were no duplicates since the nothing was removed from the array while creating the set.
   - If it returns false, it means, there were duplicate values which were removed while creating the set.

```JavaScript
const arrayDuplicate = (arr) => {
  let unique = new Set(arr);
  return arr.length === unique.size;
};
```

---

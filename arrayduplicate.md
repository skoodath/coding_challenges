# [Array Duplicate](https://github.com/skoodath/coding_challenges/blob/master/arrayduplicate.js)

Source [Leetcode]()

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

Create a new set from the array which removes duplicates. Compare the length of the array to the size of the set.

```JavaScript
const arrayDuplicate = (arr) => {
  let unique = new Set(arr);
  return arr.length === unique.size;
};
```

---

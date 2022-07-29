# Array Duplicate

> Source [Leetcode](https://leetcode.com/problems/contains-duplicate/)

## Problem

**Easy**

Given an integer array num, return true if any value appears twice in the array and return false if every element is distinct.

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

### Solution1

```JavaScript
const arrayDuplicate = (arr) => {
  let unique = new Set(arr); // create a new Set from input array which removes duplicates and retains unique values
  return arr.length === unique.size; // compare the length of original array to the size of the set. If different, original array had duplicates;
};
```

### Solution2

```JavaScript
const checkDuplicate = (arr) => {
  arr.sort(); // sort the input array
  let len = arr.length;
  for(let i = 0; i < len; i++){ // run a for loop to iterate through the array
    if(arr[i] === a[i+1]){ // compare each element to its immediate neighbor to the right and return true if match found
      return true;
    }
  }
  return false; // else return false after completing the loop
};
```

### Solution3

```JavaScript
const findDuplicate = a => {
    for(let i = 0; i < a.length; i++)
        for (let j = i + 1; j < a.length; j++)
            if(a[i] === a[j])
                return true;
    return false;
}
```

---

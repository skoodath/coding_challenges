# Intersection of Two Arrays

> Source [Leetcode](https://leetcode.com/problems/contains-duplicate/)

**Easy**

Given two integer arrays `nums1` and `nums2`, return an _array_ of their _intersection_. Each element in the result must be **unique** and you may return the result in **any order**.

## Example 1

```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2]
```

## Example 2

```
Input: nums1 = [4,9,5], nums2 = [9,4,9,8,4]
Output: [9,4]
Explanation: [4,9] is also accepted.
```

### Constraints

- 1 <= nums1.length, nums2.length <= 1000
- 0 <= nums1[i], nums2[i] <= 1000

---

## Solution

```JavaScript
var intersection = function(nums1, nums2) {

  const uniqueArray = Array.from(new Set([...nums1, ...nums2])); // Create a array of unique values using set method
  const results = []; // initiate an empty array for storing results
  for (let currentVal of uniqueArray) { // loop through the unique array
    if (nums1.includes(currentVal) && nums2.includes(currentVal)) { // check if values in unique array is present in both input arrays
      results.push(currentVal); // If present, push it to the
    }
  }
return results; // return results
}
```

---

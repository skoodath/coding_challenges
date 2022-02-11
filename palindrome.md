# Palindrome Number

> Source [Leetcode](https://leetcode.com/problems/palindrome-number/)

**Easy**

Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward.

    For example, 121 is a palindrome while 123 is not.

## Example 1:

```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

## Example 2:

```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

## Example 3:

```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

### Constraints:

```
-231 <= x <= 231 - 1
```

---

## Solution

```JavaScript
var isPalindrome = function(x) {

    if(x < 0 || (x !== 0 && x % 10 == 0)) // Ignore negative numbers, 0 and numbers ending with 0
        return false;

    let reverse = 0; // initiate a variable to store number reversed

    while (x > reverse) {
        reverse = reverse * 10 + x % 10; // extract the last number and store in the reverse variable
        x = Math.floor(x/10); // remove the last digit extracted from original number
        //repeat until reverse is <= original number
    }

    return x === reverse || x === Math.floor(reverse/10); // return if original number is equal to reversed number
};
```

---

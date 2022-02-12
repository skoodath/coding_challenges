# Test Primality

**Easy**

Given an integer `nums1` check if the integer is a prime number. Result should return true or false.

## Example 1

```
Input: nums1 = 1
Output: `false`
```

## Example 2

```
Input: nums1 = 2
Output: `true`
Explanation: [4,9] is also accepted.
```

---

## Solution

```JavaScript
function isPrimeNum(n){
    let sqrt = Math.sqrt(n);
    if(n <= 1) return false; // Check if the number is 1. 1 is not prime so returns false
    if(n <= 3) return true;  // Check if the number is 2 or 3. if true, returns true as 2 and 3 are prime numbers

    if(n % 2 === 0 || n % 3 === 0) return false; // Rules out any number that is divisible by 2 or 3

    for (let i = 5; i <= sqrt; i += 6){
        if(n % i === 0 || n % (i + 2) === 0) return false; // considering any prime number is of the pattern 6k +/- 1, test numbers in increments of 6 until the squart root of given number

    }
    return true;
}

```

---

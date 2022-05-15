# Array.prototype.concat implementation

## Problem

Implement a custom Array.prototype.concat method

```
input: arr1 = ["orange","apple","chickoo"]
arr2 = ["banana","strawberry","peach"]
```

> Create a function that takes two arrays as parameters and concat them

### Solution 1

```JavaScript
const myConcat = (arr1, arr2) => {
    let result = Array.from(arr1); // Make a copy so that original array is not mutated

    for(let i = 0; i < arr2.length; i++){ // loop through second array and push items to the copy
        result.push(arr2[i])
    }
    return result; // return output which is ["orange","apple","chickoo","banana","strawberry","peach"]
}
```

### Solution 2

```JavaScript
Array.prototype.myOwnConcat = function(arr){
    let result = Array.from(this);

    for (let i = 0; i < arr.length; i++){
        result.push(arr[i])
    }
    return result;
}
```

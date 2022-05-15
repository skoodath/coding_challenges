# Array.prototype.filter implementation

## Problem

Implement a custom Array.prototype.filter method

```
input: `array = [1,2,3,4]`
```

### Solution 1

```JavaScript
const myFilter = (arr, func) => { // takes an array and callback function as arguments
    let result = []; // initiate an empty array to return result
    for (let i = 0; i < arr.length; i++) { // loop through the array
        let resultFunc = func(arr[i], i, arr); // for each value in the array run the callback function and store it in a variable
        if(resultFunc){ // if callback function returns true, push the value to result array
            result.push(arr[i])
        }
    }
    return result;
}

```

#### Example output

> Return an array with values greater than 2;

```JavaScript
  myFilter(array, function(val){ // array and callback function as arguments
   return val > 2;           // callback function returns an array of values greater than 2;
})
```

### Solution 2 (Prototype implementation)

```JavaScript
Array.prototype.myOwnFilter = function(func){
    let result = [];
    const {length} = this;
    for (let i=0; i<length; i++){
        let resultFunc = func(this[i], i, this);
        if(resultFunc) result.push(this[i])
    }
    return result;
}
```

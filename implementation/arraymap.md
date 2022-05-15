# Array.prototype.map implementation

## Problem

Implement a custom Array.prototype.map method

### Solution 1

```
input: `array = [1,2,3,4]`
```

```JavaScript
  const myMap = (arr, func) => {  // input array and callback function as arguments
    let result = []; // initiate an empty array for results
    for (let i = 0; i < arr.length; i++) { // loop through each item in the input array
        result.push(func(arr[i], i, arr)) // callback functions supplied to the map method is pushed into the result array. This function takes value, index and array as its arguments and performs any user defined calculations
    }
    return result; // map function returns the final array
}
```

#### Example output

> Return an array of squared value of given array

```JavaScript
  myMap(array, function(val){ // array and callback function as arguments
   return val ** 2;           // callback function returns an array of squared values of input array
})
```

### Solution 2 (Prototype implementation)

```JavaScript
  Array.prototype.myOwnMap = function(func){ // prototype implementation takes only the callback function as argument
   let output = [];
   const {length} = this; // this points to the Array object
   for (let i = 0; i < length; i++){
      output.push(func(this[i], i, this))
   }
   return output;
}
```

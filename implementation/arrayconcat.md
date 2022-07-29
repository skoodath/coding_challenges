# Array.prototype.concat implementation

## Problem

Implement a custom Array.prototype.concat method

```
input: arr1 = ["orange","apple","chickoo"]
arr2 = ["banana","strawberry","peach"]
string = "john"
object = {name: "john"}
```

> Create a function that takes two arrays as parameters and concat them

### Solution 1

```JavaScript
const myConcat = (...args) => {
    let result = []; // Initiate an empty array

    for(let arg of args){ // loop through arguments and push items to the copy
        /*if the argument is an array, use spread operator to add just he values by flattening the array;*/
        if(Array.isArray(arg)) result.push(...arg);
        else result.push(arg); // Else push as is
    }
    return result; // return output
}
```

### Solution 2

```JavaScript
Array.prototype.myConcat = function(){
    let result = Array.from(this);

    for (let arg of arguments){
        if(Array.isArray(arg)) result.push(...arg);
        else result.push(arg)
    }
    return result;
}
```

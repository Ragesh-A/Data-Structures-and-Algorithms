
## Questions


### Create a function that looks through an array arr and returns the first element in it that passes a 'truth test'. This means that given an element x, the 'truth test' is passed if `func(x)` is `true`. If no element passes the test, return `undefined`.

```
function findElement(arr, func){
  return arr.find(num=> func(num))
}


const result = findElement([1, 3, 5, 8, 9, 10], num => num % 2 === 0 )
console.log(result)
```

### Remove all the falsy value from an array

```
function bouncer(arr) {
  return arr.filter(ele=> {
    if(ele){
      return ele
    }
  });
}

bouncer([7, "ate", "", false, 9]);
```

### Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

```
function getIndexToIns(arr, num) {
  arr.push(num);
  arr.sort(function(a, b) {
    return a - b;
  });
  return arr.indexOf(num);
}
```
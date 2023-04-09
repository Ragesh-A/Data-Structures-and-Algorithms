# String

Sting is sequence of character that represent text. In another word string is collection of character enclosed with single quotes ('') or double quotes ("").

```
const str = "Hello, world!";
```

## Questions

### Create a function that looks through an array arr and returns the first element in it that passes a 'truth test'. This means that given an element x, the 'truth test' is passed if `func(x)` is `true`. If no element passes the test, return `undefined`.

```
function findElement(arr, func){
  return arr.find(num=> func(num))
}


const result = findElement([1, 3, 5, 8, 9, 10], num => num % 2 === 0 )
console.log(result)
```

###  function to check value is classified as a boolean primitive. Return true or false

```
function isBoolean(value){
  return typeof value === 'boolean;
}

let result = isBoolean(false)
console.log(result)
result = isBoolean(true)
console.log(result)
result = isBoolean("Hi")
console.log(result)
```

### Function that return the provided string with the first letter of each word capitalized and the rest of the word is in lower case.

```
function titleCase(str) {
  const arr = str.toLowerCase().split(' ')
  let newStr = arr.map(word=> word[0].toUpperCase() + word.slice(1)).join('')
  return newStr;
}

titleCase("I'm a little tea pot");
```
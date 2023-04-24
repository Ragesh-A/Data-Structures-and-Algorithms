## Questions

###  function to check value is classified as a boolean primitive. Return `true` or `false`

```js
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

```js
function titleCase(str) {
  const arr = str.toLowerCase().split(' ')
  let newStr = arr.map(word=> word[0].toUpperCase() + word.slice(1)).join('')
  return newStr;
}

titleCase("I'm a little tea pot");
```

### check the string palindrome or not

```js
function palindrome(str) {

    var len = str.length;
    var mid = Math.floor(len/2);

    for ( var i = 0; i < mid; i++ ) {
        if (str[i] !== str[len - 1 - i]) {
            return false;
        }
    }

    return true;
}
```
# Recursion

Function call itself directly or indirectly, called recursion.

## Questions

### Basic

##### Q1 : Print the nature number up to `n` ascending order as well as descending order

```js
function ascending(n){
  if( n === 0 ){
    return n
  }
  ascending( n-1 )
  console.log(n)
}

ascending(5);

function descending(n){
  if( n === 0 ){
    return n
  }
  console.log(n)
  descending( n-1 )
}

descending(5);


```

##### Q2 : Print the sum of `n` nature number.

```js
function sum(n){
  if( n === 1 ){
    return n
  }
  return n + sum( n-1 )
}

console.log(sum(5))
```

##### Q3 : Print the factorial of number `n`.

```js
function calcFact(n){
  if(n===1){
    return n
  }

  return n * calcFact( n - 1)
}
 
console.log(calcFact(5))
```

##### Q4 : Print the fibonacci sequence till nth term

```js
function calcFact(n,f=0,s=1){
  if(n=== 0){
    return;
  }
  let sum = f +s
  f = s
  s = sum
  console.log(sum)
  calcFact( n - 1,f,s)
}


console.log(0)
let n = 5
calcFact(n - 1)
```

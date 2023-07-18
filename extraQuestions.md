## Power of 2
function to check the given integer is power of 2 or not

```js
function isPowerOfTwo(n){
  if(n<1) return false;
  return (n & (n-1)) === 0
}
```

# Leetcode Questions

### 118 Pascal's Triangle

```js
const numRows = 5;
const result = [];
for (let i =0; i < numRows; i++) {
  result.push([1])
  for (let j = 0; j < i; j++) {
    const prev = result[i - 1]
    result[i][j+1] = prev[j] + (prev[j + 1] || 0)
  }
}

console.log(result);
```
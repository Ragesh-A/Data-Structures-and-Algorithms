## Power of 2
function to check the given integer is power of 2 or not

```
function isPowerOfTwo(n){
  if(n<1) return false;
  return (n & (n-1)) === 0

}
```
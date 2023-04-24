### How to reverse a stack

```js
// this method is should be inside the stack class 
reverse() {
  if (this.isEmpty()) return false;
  let reversed = [];
  while (!this.isEmpty()) {
    reversed.push(this.pop());
  }
  return (this.items = reversed);
}
```
# Questions

### Q1 find the middle value of a linked list

```js

middleValue() {
  let fastPointer = this.head;
  let slowPointer = this.head;

  while(fastPointer != null && fastPointer.next !== null) {
    fastPointer = fastPointer.next.next
    slowPointer = slowPointer.next;
  }
  return slowPointer.value
}

```

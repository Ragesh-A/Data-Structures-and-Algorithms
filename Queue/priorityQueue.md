# Implementation of priority queue using linked list

```js
class Node {
  constructor(value, priority) {
    this.value = value;
    this.priority = priority;
    this.next = null;
  }
}

class PriorityQueue {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insert(value, priority) {
    const newNode = new Node(value, priority);
    let current = this.head;

    if (!current) {
      this.head = newNode;
      this.tail = newNode;
    } else {

      while (current.next !== null && current.next.priority < priority) {
        current = current.next;
      }

      if (current.priority > priority) {
        newNode.next = current;
        this.head = newNode;
      } else {
        newNode.next = current.next;
        current.next = newNode;
      }
    }
  }

  print() {
    let current = this.head;
    while (current) {
      console.log(current.value);
      current = current.next;
    }
  }
}
```

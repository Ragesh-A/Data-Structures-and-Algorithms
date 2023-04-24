# Queue

A queue is a linear data structure that is open at both ends and the operations are  performed in first in first out (FIFO) order.
In other word, 'A queue to be a list one end and all the additions to the list are made at one end and all the deletions from the list are made at other end. The element which is first push will delete first.'

## Operations 

enQueue : add value to the queue. <br>
deQueue : remove value from the queue. <br>
*Other common are the operations are : <br>
peek <br>
isEmpty <br>
size  <br>
print  <br>

## Implementation of Queue

```js
class Queue {
  constructor(){
    this.items = {}
    this.rear = 0
    this.front = 0 
  }

  // adding the element to queue

  enQueue(element){
    this.items[this.rear] = element
    this.rear++
  }

  // removing element from the queue

  deQueue(){
    const value = this.items[this.front]
    delete this.items[this.front]
    this.front++
    return value
  }

  // the last element of queue

  peek(){
    return this.items[this.front]
  }

  // return the size of queue

  size(){
    return this.rear - this.front
  }

  // return the queue is empty or not 

  isEmpty(){
    return this.rear - this.front === 0
  }

  // print all the element in queue

  print(){
    return Object.values(this.items)
  }
}
```

## usage of queue 

```
const queue = new Queue()

queue.enQueue(10)
queue.enQueue(20)
queue.enQueue(30)
console.log(queue.deQueue())
console.log(queue.isEmpty())
console.log(queue.size())
console.log(queue.print())
```

### implementation of Queue using array

```js
class Queue{
  constructor(){
    this.items = []
  }

  enQueue(value){
    this.items.push(value)
  }
  deQueue(){
    return this.items.shift()
  }
  isEmpty(){
    return this.items.length === 0
  }
  size(){
    return this.items.length
  }
  print(){
    for(let i = 0; i < this.items.length; i++){
      console.log(this.items[i])
    }
  }
}
```

### implementation using linked list
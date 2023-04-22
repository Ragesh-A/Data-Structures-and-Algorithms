# Stack

A stack is a linear data structure in which the insertion of new element and removal of an existing element takes place at the same end represented as the top of stack.

## Basic operation in stack

-> push() complexity of push is O(1).</br>
-> pop() complexity pop is O(1).</br>
-> top() complexity of top is O(1.)</br>
-> isEmpty() complexity of isEmpty is O(1).</br>
-> size() complexity of size is O(1).</br>

## Type of stacks

<dl>
  <dt>Fixed size stack</dt>
  <dd>
    <ul>
      <li>Cannot grow or shrink dynamically.</li>
      <li>When the stack is full push operation cannot be done when it done it will leads to stack overflow error.</li>
      <li>When the stack is empty pop operation cannot be done when it done it will leads to stack underflow error.</li>
    </ul>
  </dd>
  <dt>Dynamic size stack</dt>
  <dd>
    <ul>
      <li>Stack will grow or shrink dynamically.</li>
      <li>This dynamic stack can implemented through linked list.</li>
    </ul>
  </dd>
  <br>
  *These two are the main type of stack however there are variation od stack is also there. like :
  <dt>Infix to postfix stack</dt>
  <dd>Used to convert infix expression to postfix expression.</dd>
  <dt>Expression evaluation stack</dt>
  <dd>This type of stack used to evaluate postfix expression.</dd>
  <dt>Recursion Stack</dt>
  <dd>This type of stack is used to track a function call in computer program to return to current function after execution.</dd>
  <dt>undo redo stack</dt>
  <dd>To enable undo redo operation.</dd>
  <dt>Memory Management Stack</dt>
  <dd>This kind of stack is used to sore the values of program. This allow program return to actual state after the function returns.</dd>
  <dt>Balanced parenthesis stack</dt>
  <dd>This stack is used to check or to ensure the parenthesis are written currently. </dd>
</dl>

## Implementation of stack

```
// Creation of stack
class Stack{
    constructor(){
        this.items = []
    }
    // adding values into the stack.

    push(element){
        this.items.push(element)
    }

    //removing value from the stack

    pop(){
        if(!this.isEmpty()){
            return this.items.pop()
        }
        console.warn("stack is empty")
        return;
    }

    //checking the stack is empty or not

    isEmpty(){
        return this.items.length === 0
    }

    // return the size of stack

    size(){
        return this.items.length
    }

    // top element of the stack

    peek(){
        if(!this.isEmpty()){
        return this.items[this.size() - 1]
        }
    }

    //return all the element in a stack

    print(){
        console.log(...this.items)
    }
}
```

## how to use the stack ?

```
// create of stack
const stack = new Stack()

// adding elements into stack
stack.push(10)

// stack is empty or not
console.log(stack.isEmpty())

// length is stack
console.log(stack.size())

// the top element in the stack
console.log(stack.peek())

// all the element in a stack
console.log(stack.print())

// remove element from the stack
console.log(stack.pop())
```

##  implementation of stack using linked list 

```
class Node{
  constructor(value){
    this.value = value;
    this.next = null;
  }
}

class Stack{
  constructor(){
    this.top = null
    this.size = 0
  }

  push(value){
    if(!value) return false;
    const newNode = new Node(value);
    newNode.next = this.top
    this.top = newNode
    this.size++
  }
  pop(){
    if (!this.top) return null;
    const poppedNode = this.top;
    this.top = poppedNode.next;
    poppedNode.next = null;
    this.size--;
    return poppedNode.value;
  }
  peek(){
    return this.top;
  }
  isEmpty(){
    return this.size === 0
  }
  getSize(){
    return this.size
  }

}
```
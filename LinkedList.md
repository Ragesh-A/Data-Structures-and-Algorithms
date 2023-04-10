# Linked list

Linked list is a linear data structure similar to array. But the memory allocated to non-contiguous memory locations. There is no particular index or something to get an particular value. So traversal is necessary to access value. Best choice when the size are dynamically change. The memory is like value with pointer, these called node. The first node is called `head` and end node is called `tail`

## complexity 


<dl>
  <dt>Initialization</dt>
  <dd>The initialization is very easy because we only create one node then all other are appending. Son complexity is O(1)ST
  </dd>
  <dt>Set and Get</dt>
  <dd>The complexity of set is `O(n)T`. Because to set any value in a it needed to traverse through entire node and update, it don't have any index like array to set value.</dd>
  <dd>The complexity of get also same it needed to traverse to each node so `O(n)T`</dd>
  <dd>but these problem can solve through saving the position of each node then it will `O(1)T`</dd>
  <dt>Traverse</dt>
  <dd>`O(n)T`</dd>
  <dt>Insert</dt>
  <dd>
    Head : `O(1)T`<br/>
    Tail : These have another sub case like while we stored the position the complexity will become `O(1)T` otherwise `O(n)T`<br/>
  </dd>
  <dt>Delete</dt>
  <dd>
    The complexity od deletion have some case like <br />
    -> deletion of head `O(1)T`<br />
    -> deletion of tail : These have another sub case like while we stored the position the complexity will become `O(1)T` otherwise `O(n)T`<br />
    -> deletion of other than head and tail : These have another sub case like while we stored the position the complexity will become `O(1)T` otherwise `O(n)T`<br />
  </dd>
</dl>


## Types of Linked Lists
There are three types of linked lists:
<ul>
  <li> Singly Linked Lists: Each node contains only one pointer to the next node. This is what we have been talking about so far.</li>
  <li>Doubly Linked Lists: Each node contains two pointers, a pointer to the next node and a pointer to the previous node.</li>
  <li>Circular Linked Lists: Circular linked lists are a variation of a linked list in which the last node points to the first node or any other node before it, thereby forming a loop.</li>
</ul>


## creation of linked list in javaScript
```
class LinkedList {
  constructor(head =null){
    this.head = head
  }
}
````

## creation of  node in javaScript

```
class Node {
  constructor(data){
    this.data = data,
    this.next = null
  }
}
```


## Putting all together 

```
// creation of node
let node1 = new Node(5)
let node2 = new Node(6)

//creating connection of node
node1.next = node2

//creating linkedList 

let list = new LinkedList(node1);

```

## To access the value in aa Node
```
console.log(list.head.next.data) // return 6
```
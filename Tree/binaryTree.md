# Binary Tree

A tree data structure is hierarchical structure that is used to represent and organize data in a way that easy to navigate and search.
It is a collection of nodes that are connected by edge (edge is the line that represent connection of nodes) and has hierarchical relationship between the nodes. <br />


## Implementation of Binary search tree

### Tree node

```
// tree node class
class Node{
  constructor(value){
    this.value = value
    this.left = null
    this.right = null
  }
}
```

### Binary Tree 

```

// construction of binary search tree class

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  isEmpty() {
    return this.root === null;
  }

  // insert the node

  insert(value) {
    if (!value) return false;
    const node = new Node(value);
    if (this.root === null) {
      return (this.root = node);
    }
    this._insertNode(this.root, node);
  }

  // function to search the position and inset the node

  _insertNode(head, node) {
    if (!node || !head) {
      return false;
    }

    if (head.value > node.value) {
      if (head.left === null) return (head.left = node);
      this._insertNode(head.left, node);
    } else {
      if (head.right === null) return (head.right = node);
      this._insertNode(head.right, node);
    }
  }
}

```

lets test 

```
const BST = new BinarySearchTree()
BST.insert(10)
BST.insert(5)
BST.insert(7)
BST.insert(3)
BST.insert(11)
BST.insert(10)
BST.insert(12)
console.log(BST)
```
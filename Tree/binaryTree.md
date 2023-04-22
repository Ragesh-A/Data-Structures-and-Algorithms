# Binary Tree

 <br />


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

  // search the value is exist or not in the binary search tree

  search(root, value){
    if(!root) return false
    if(!value) throw "value is missing"
    if(root.value === value) return true
    if(root.value < value) return this.search(root.right, value)
    else return this.search(root.left, value)
  }

  // Pre-order traversal format like (root, left , right)

  preOrder(node = this.root){
      if(!node) return;
      console.log(node.value)
      this.preOrder(node.left)
      this.preOrder(node.right)
  }

  //in-order traversal format like (left , root, right)

  inOrder(node = this.node){
      if(!node) return;
      this.inOrder(node.left)
      console.log(node.value)
      this.inOrder(node.right)
  }

  //post-order traversal format like (left , right, root)

  inOrder(node = this.node){
      if(!node) return;
      this.inOrder(node.left)
      console.log(node.value)
      this.inOrder(node.right)
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
console.log(BST.search(BST.root,11))
BST.preOrder(BST.root)
BST.inOrder(BST.root)
```
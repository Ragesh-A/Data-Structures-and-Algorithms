# Binary Search Tree

Binary Search tree is a tree data structure, Which has it on property like the left child node has a value less than the parent value and the right child node value is greater then the parent value. This property make efficient search and insert and delete .
<br />

## Implementation of Binary search tree

### Tree node

```js
// tree node class
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}
```

### Binary Tree

```js
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

  contain(root, value) {
    if (!root) return false;
    if (root.value === value) return true;
    if (root.value < value) return this.contain(root.right, value);
    else return this.contain(root.left, value);
  }

  // Pre-order traversal format like (root, left , right)

  preOrder(node = this.root) {
    if (!node) return;
    console.log(node.value);
    this.preOrder(node.left);
    this.preOrder(node.right);
  }

  //in-order traversal format like (left , root, right)

  inOrder(node = this.node) {
    if (!node) return;
    this.inOrder(node.left);
    console.log(node.value);
    this.inOrder(node.right);
  }

  //post-order traversal format like (left , right, root)

  postOrder(node = this.node) {
    if (!node) return;
    this.inOrder(node.left);
    this.inOrder(node.right);
    console.log(node.value);
  }

  min(root = this.root) {
    if (head.left === null) {
      return head.value;
    }
    return this.min(root.left);
  }
  max(root = this.root) {
    if (root.right === null) {
      return root.value;
    }
    return this.max(root.right);
  }
  delete(value) {
    let root = this._deleteNode(this.root, value);
    console.log(root);
  }
  _deleteNode(root, value) {
    if (!root) return root;
    if (value < root.value) {
      root.left = this._deleteNode(root.left, value);
    } else if (value > root.value) {
      root.right = this._deleteNode(root.right, value);
    } else {
      // if the node is leaf node
      if (!root.left && !root.right) {
        return null;
      }

      if (!root.left) {
        // if there is no left node return right node
        return root.right;
      } else if (!root.right) {
        // if there is no right child return left node
        return root.left;
      }
      // it means the node has two child node
      root.value = this.min(root.right);
      root.right = this._deleteNode(root.right, root.value);
    }
    return root;
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
console.log(BST.contain(BST.root,11))
BST.preOrder(BST.root)
BST.inOrder(BST.root)
```

### type of binary tree on the basis of completion of completion of level

# Heap

Heap is a tree based data structure which the tree is a complete binary tree. Basically heap denoted as array. Heap can be classified into two <br />

<dl>
  <dt>Max-heap</dt>
  <dd>The value of root must be greater than all child. And same thing done for its subtree.</dd>
  <dt>Min-heap</dt>
  <dd>The value of root must be less then all child. And rhe same thing done for its subtree.</dd>
</dl>


<pre>
node : i
left child = i * 2 + 1
right child = i * 2 + 2 
parent = (i - 1) / 2
</pre>

<pre>you can only delete the root node</pre>


### Implementation of Heap

```js
class MaxHeap {
  constructor() {
    this.heap = [];
  }
  // return there is parent for node
  hasParent(i) {
    return i !== 0;
  }
  // return the parent index
  parentIndex(i) {
    return Math.floor((i - 1) / 2);
  }
  // return the node has left child
  hasLeftChild(i) {
    return this.leftChildIndex(i) < this.heap.length;
  }
  // return the left child index
  leftChildIndex(i) {
    return i * 2 + 1;
  }
  // return the node has right child
  hasRightChild(i) {
    return this.rightChildIndex(i) < this.heap.length;
  }
  // return the right child index
  rightChildIndex(i) {
    return i * 2 + 2;
  }

  // return the size of array
  isEmpty() {
    return this.heap.length === 0;
  }

  // insertion of value
  insert(value) {
    this.heap.push(value); // value inserted
    this._bubbleUp(this.heap.length - 1); // to maintain the heap structure
  }

  _bubbleUp(i) {
    if (i === 0) return;
    const parent = this.parentIndex(i);
    if (this.heap[i] > this.heap[parent]) {
      [this.heap[i], this.heap[parent]] = [this.heap[parent], this.heap[i]];
      this._bubbleUp(parent);
    }
  }

  // we can only remove the root node
  removeRoot() {
    const removedValue = this.heap[0];
    this.heap[0] = this.heap[this.heap.length - 1]; // root element change with last element
    this.heap.pop(); // removed the last element
    this._bubbleDown(0); // start from the root
    return removedValue;
  }

  _bubbleDown(i) {
    const left = this.leftChildIndex(i);
    const right = this.rightChildIndex(i);
    let highest = left;
    if (this.heap[right] > this.heap[left]) {
      highest = right;
    }
    // compare the highest value child with parent
    if (this.heap[highest] > this.heap[i]) {
      [this.heap[i], this.heap[highest]] = [this.heap[highest], this.heap[i]]; // swap
      return this._bubbleDown(highest);
    }
  }
}

```
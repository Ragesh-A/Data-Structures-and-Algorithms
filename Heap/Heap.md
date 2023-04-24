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

you can only delete the root node
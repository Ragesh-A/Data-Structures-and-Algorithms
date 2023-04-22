# Tree data structure

A tree data structure is hierarchical structure that is used to represent and organize data in a way that easy to navigate and search.
It is a collection of nodes that are connected by edge (edge is the line that represent connection of nodes) and has hierarchical relationship between the nodes. <br />


## Terminologies

<ol>
  <li>Root node : The top most node is known as root node.</li>
  <li>Parent node : The node which iis predecessor of a node.</li>
  <li>Child node : Node which is successor of a node.</li>
  <li>Siblings : Children of same parent.</li>
  <li>Ancestor : Predecessor of a node to root.</li>
  <li>Descendant : >successor of a node.</li>
  <li>Internal node : The node which have at least one node.</li>
  <li>Leafs / External node : The node which do not have any child node.</li>
  <li>Level of node : count of edge from root to that node.</li>
  <li>Subtree : Any node along with descendant.</li>
</ol>

### Properties of tree

<ul>
  <li>Number of edge : A tree has 'n' number of node then edge will 'n-1'.</li>
  <li>Depth of a node : The length of path from root to that node.</li>
  <li>Height of a node : The length of longest path from leaf node to that node.</li>
  <li>Degree of node : Total count of subtree to that node.</li>
  <li>Height of a tree : The longest path from leaf node to root node.</li>
</ul>

### Application of tree 

<ul>
  <li>Spanning tree : Shortest path routes to direct the packets to the destination.</li>
  <li>Binary search tree : Maintain sorted stream of data.</li>
  <li>Heap : Tree data structure helps to represent the data in the form of array to implement priority queue.</li>
  <li>AI : Decision trees and other tree-based models are commonly used in machine learning and artificial intelligence to make predictions and classify data.</li>
  <li>Database :  Some databases use trees to organize data for efficient searching and sorting.</li>
</ul>

### Types of tree

<ul>
  <li>General tree : A general tree data structure has no restriction on the number of nodes. It means that a parent node can have any number of child nodes.</li>
  <li>Binary search tree : A node of a binary tree can have a maximum of two child nodes.</li>
  <li>Balanced tree  : If the height of the left sub-tree and the right sub-tree is equal or differs at most by 1, the tree is known as a balanced tree.</li>
</ul>
# Tree data structure

A tree data structure is hierarchical structure that is used to represent and organize data in a way that easy to navigate and search.
It is a collection of nodes that are connected by edge (edge is the line that represent connection of nodes) and has hierarchical relationship between the nodes. <br />


## Terminologies

<ol>
  <li>Root node : The top most node is known as root node.</li>
  <li>Parent node : The node which is predecessor of a node.</li>
  <li>Child node : Node which is successor of a node.</li>
  <li>Siblings : Children of same parent.</li>
  <li>Ancestor : Predecessor of a node to root.</li>
  <li>Descendant : successor of a node.</li>
  <li>Internal node : The node which have at least one node.</li>
  <li>Leaf / External node : The node which do not have any child node.</li>
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

<li>General Tree:  A general tree data structure has no restriction on the number of nodes. It means that a parent node can have any number of child nodes.</li>
<li>Binary Tree: A node of a binary tree can have a maximum of two child nodes.</li>
<li>Ternary Tree: A Ternary Tree is a tree data structure in which each node has at most three child nodes, usually distinguished as “left”, “mid” and “right”.
</li>

### Tree traversal technique

<ol start="1">
  <li>Depth first search</li>
  Depth-First Search explores a graph by visiting the deepest nodes first and then backtracking. 
  <ul>
    <li>Pre-order traversal: root -> left -> right. O(n)</li>
    <li>In-order traversal: left -> root -> right. O(n)</li>
    <li>post-order traversal: left -> right -> root. O(n)</li>
  </ul>
  <li>Breath first search</li>
  Breadth-First Search explores a graph level by level.
  <ul>
    <li>Boundary traversal</li>
    <li>Diagonal traversal</li>
  </ul>
</ol>
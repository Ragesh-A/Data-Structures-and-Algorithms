# Graph

Graph is a non-linear data structure consist of infinite number od vertex (which is also called as node) connected by edge.

### Type of Graph

<ul>
  <li>Null graph : When there is no edge is there.</li>
  <li>Trivial graph : When graph have only one node.</li>
  <li>Undirected graph : Bi-direction of edge.</li>
  <li>Directed graph : Edges have the directions</li>
  <li>Cycle graph : Degree of each vertex us two.</li>
  <li>Cyclic graph : Graph contain at least on cycle</li>
  <li>Weighted graph : graph which has cost of travel to another vertex.</li>
  <li>Connected graph</li>
  <li>Disconnected graph</li>
</ul>

### implementation of graph

The graph can be implemented in two ways
-> Adjacency matrix <br />
-> Adjacency list <br />

## Adjacency matrix 

It is 2D array of size v * v where v is the number of vertex. Each column and row represent the vertex.

|   | A | B | C |
|---|---|---|---|
| A | 0 | 1 | 0 |
| B | 1 | 0 | 1 |
| C | 0 | 1 | 0 |

This means the `A` vertex has a connection with `B`. `B` vertex has a connection with `A` and  `c`. And `C` has a connection with `B`.

## Adjacency list 

This graph is represented as collection of lined list.
<pre>
list = {
  A : [B],
  B : [A, B],
  C : [B]
}
</pre>

This also telling the same thing that  `A` vertex has a connection with `B`. `B` vertex has a connection with `A` and  `c`. And `C` has a connection with `B`.


### Implementation using Adjacency list

```js
class Graph{
  constructor(){
    this.adjacencyList = {}
  }

  // create new vertex only if not there

  addVertex(vertex){
    if(!this.adjacencyList[vertex]){
      this.adjacencyList[vertex] = new Set()
      return true 
    }
    return false
  }

  // creation edge between two vertex if vertex no there create new vertex

  addEdge(vertex1, vertex2){
    if(!this.adjacencyList[vertex1]){
      this.addVertex(vertex1)
    }
    if(!this.adjacencyList[vertex2]){
      this.addVertex(vertex2)
    }
    this.adjacencyList[vertex1].add(vertex2)
    this.adjacencyList[vertex2].add(vertex1)
  }

  // return

  hasEdge(vertex1, vertex2){
    return this.adjacencyList[vertex1].has(vertex2)
  }

  // delete the edge between vertex

  deleteEdge(vertex1, vertex2){
    if(this.hasEdge(vertex1, vertex2)){
      this.adjacencyList[vertex1].delete(vertex2)
      this.adjacencyList[vertex2].delete(vertex1)
      return true
    }
    return false
  }

  // to delete the vertex remove all the edge and delete 

  deleteVertex(vertex){
    for (const item of this.adjacencyList[vertex]) {
      this.deleteEdge(item, vertex)
    }
    return delete this.adjacencyList[vertex]
  }

  display(){
    for (const vertex in this.adjacencyList) {
      console.log(`${vertex} -> ${[...this.adjacencyList[vertex]]}`)
    }
  }
}

```
# Graph
Graph is a data structure which is reprseneted by finite set of nodes and edges.
These nodes are called vertices and edges are used to connect vertices.<br>
Applications :- <br>
1.Google Maps<br>
2.Social Networks like Facebook,Quora,Linkedin.Friend suggestion and recommendation
is done due to this.<br>
3.Routing Algorithms

## Components of Graph
i.Adjacent vertices<br>
Two Vertices which are directly connected by an edge.<br>
ii.Degree<br>
No of edges connected to a vertices.<br>
iii.Path<br>
Set of edges from source node to destination node.<br>
iv.Connected Graph<br>
A connected graph is a graph in which it's possible to get from every vertex 
in the graph to every other vertex through a series of edges, called a path.<br>
v.Tree<br>
A tree is acyclic graph<br>
vi.Forest<br>
A collection of tree is called forest<br>
vii.Minimum Spanning Tree<br>
A subgraph of a graph containing all the vertices and subset of edges and weight along
the edges are minimum.<br>

## Types Of Graph 
1.Unweighted Graph<br>
Edges donot have weight associated with them or edges have equal weights.<br>
![](unweighted.png)<br>
2.Weighted Graph<br>
Edges have weight associated with them .<br>
![](weighted.png)<br>

## Types of edges
1.Undirected Weighted Edges<br>
-A simple network of friends,bi-directional roads.
2.Directed Weighted Edges<br>
-One way Distance from one end to another end.
3.Bi-Directional Weighted Edges
-Flight cost from mumbai to delhi and delhi to mumbai.

## No of edges in Graph
1.Complete Graph<br>
Every node is connected to every other node.<br>
![](complete.png)<br>

## Implementing Graph
1.Edge List<br>
We make a list of vertex.We take edges connection list.<br>
2.Adjacency Matrix<br>
If we have 5 vertices,we make 5*5 matrix and mark true is there is edges between those
two vertices.In case of weighted graph we store the edge weight instead of true or false.
It is not efficient to find out adjacent vertices of particular node.We need to traverse
that row and see for it. Complexity :- O(V).Takes alot of memory. For 1000 vertices we will
waste memory 10^6. Takes memory O(v^2).<br>
3.Adjacency List 
We can make a hashmap of key-value pairs or array of linked list. To see the neighbors
we can simply traverse the linked list which complexity will be less than O(V) and it is
also memory efficient.<br>


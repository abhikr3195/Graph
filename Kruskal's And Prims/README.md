# Kruskal's Algorithm
It is used to find minimum spanning tree in a graph.It is based on greedy technique.                      The graph given must be undirected and weighted.Prim's and Kruskal's algorithm works only for undirected graphs.

 ### A graph is called a tree if there is no cycles present
 
     Steps Involved :-
     1.First find the edge with minimum weight.
     2.Select this edge in minimum spanning tree if and only if after                                          inserting this edge there is no cycle formed.
     - Cycle formed can be checked by either DFS,BFS or Union Find By Rank
     

# Prim's Algorithm
It is used to find minimum spanning tree in a graph.It is based on greedy technique.                      The graph given must be undirected and weighted.Prim's and Kruskal's algorithm works only for undirected graphs.

     Steps Involved
     1.We will create an array/map for visited vertices.
     2.Mapping of vertex with their weight.
     3.Choose any vertex and then choose any minimum weight vertex connected with it.
     4.If any neighbour is already visited then donot include it.

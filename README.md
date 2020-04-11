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
-A simple network of friends,bi-directional roads.<br>
2.Directed Weighted Edges<br>
-One way Distance from one end to another end.<br>
3.Bi-Directional Weighted Edges<br>
-Flight cost from mumbai to delhi and delhi to mumbai.<br>

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
See adjacentlist.cpp for code related information.<br>


## Graph Traversal
1. Breadth First Search<br>
2. Depth First Search<br>

# Breadth First Search
i. It is an graph traversal method.<br>
ii. It is an iterative approach.<br>
iii. It uses a Queue to maintain FIFO ordering and another data structure is used to maintain the list of vertices visited so far.<br>
iv. It is like level-order traversal in binary tree.<br>
For a better understanding check the above bfs ppt.
PseudoCode
    
    void BFS(int G[][7],int start,int n){
     int i=start,j;
     //Visited vertex array
     int visited[7]={0};
     //Source Vertex
     printf("%d ",i);
     //Mark visited
     visited[i]=1;
     //Push the element in Queue
      enqueue(i);
      while(!isEmpty()){
         //Pop An ELement
           i=dequeue();
           //Check for the adjacent vertex of the poped element.
           //If present and not visited then push it.
            for(j=1;j<n;j++){
                if(G[i][j]==1 && visited[j]==0){
                    printf("%d ",j);
                    visited[j]=1;
                    enqueue(j);
                }
            }
        }
        //If the queue becomes empty then BFS is over.
    }

## Application
### Single Source Shortest Path
Use a queue and a distance array.
Initialise all the distance to infinity.
Make the distance of starting node a zero.<br>
        
        distance[child]=distance[parent]+1.

So push the source in the queue.And then i pop out this node .
And push the neighbours which arent visited.Neighbours will be at distance 1.
Subsequently neighbours are assigned distance.And you can check if a weight is 
assigned once you dont need to push it.Check singleSourceShortestpath.cpp

#### Snakes And Ladder Problem
You are given a board where it contain snakes and ladder.If you climb a stair you
reach a higher point and if bitten by snake then you reach lower point.You are given a dice
and you can throw your choice of number.Minimum number of dice moves to win the game.Each dice can have any number from 1 to 6.
<br>
![](snakes.png)
<br>
Sample Output
Min Moves :- 4<br>
One Possible Shortest Path : 1 ->15->29->30->36<br>
<br>
The whole thing can be represented as a graph.So there are 37 vertices.Each Node has
some neighbour.<br>
<br>
So initially we are at zero.If we throw a dice from zero you can reach 1,15,3,4,7,6.
We reach 15,7 because there is ladder at 2,5 which act as transient point.<br>
So if we are at one.If we throw a dice from zero you can reach 15,3,4,7,6,8.
We reach 15,7 because there is ladder at 2,5 which act as transient point.<br>
From every node v there are some edges which are going to v+1,v+2,v+3...v+6 vertices.<br>
Since the cost is same for every dice throw and you can only climb up from stair cant
come back or only move forward so it is unweighted directed graph.<br>
I am going to make a board array and initialise it zero.And add some exception.<br>
On reaching 2 we move to 15.On reaching 2 we get a jump of 13.On reaching 5 we move to 7.
On reaching 5 we get a jump of 2.<br>
board[2]=13,board[5]=2.<br>
In case of snake.If we reach 17 then we are bitten by snake and we go to 4.<br>
board[17]=-13;

## DEPTH FIRST SEARCH

    It traverses graph ‘Depth-first’ starting from source , then picks one of the unvisited neighbours     and visit it.
    It is an recursive algorithm for the traversal of graph.
    Recursion goes deeper into branch until it cant go further.   
    Multiple ordering are possible.

    For DFS we require two thing:-
    Recursive Call on the univisted node.
    Array and map to know which node is visited or not

See the ppt Depth First Search.

## Topological Sorting Using DFS/*Complexity :- linear 0(V+E)*/

This algorithm output of linear ordering of vertices.<br>
Such that for every edge u-->v vertex u comes before vertex v in the 
ordering.It works on only Directed Acyclic Graph
![](topo.png)<br>

    Applications
    1.Finding out possible sequence to finish task
    2.Installing of packages in a Linux System,all dependencies are installed first
    in the order generated by topological sort*/

## Topological Sort Using BFS - KAHN'S ALgorithm
    
    -Uses a modified BFS
    -A queue and array/map for storing indegree of each vertex is used 
    -Algorithm starts from finding vertices with 0 indegree
  
<br>

![](topobfs.png)<br>

Steps:<br>
- I push all the vertices in queue with 0 indegree.<br>
- Then i pop out a node from queue.<br>
- So the adjacent vertices of the node degree will decrease by 1.<br>
- So i push the node whose indegree turns out to be zero and repeat until queue 
  becomes empty.<br>

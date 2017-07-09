# Path-Planning-Explanation
In this document, multiple path planning algorithms will be explained and compared. I will make use of grid maps, environments that are discretized to be represented in squares of the same costs. The examples used in this document will be square grids of 21x21 squares, where grey squares are obstacles. The green and red square represent the goal and end node respectively. The yellow line is the shortest path calculated by the algorithm. The blue and light green squares are nodes that are discovered and the frontier.


## Breadth-First Search
This algorithm will explore equally in all directions. This algorithm doesn't use any heuristic method of going towards the goal and treats all nodes equally. After calculating every node's value or distance from the goal, it calculates the shortest path towards it.
This causes the algorithm to calculate a path to the goal lcoation as well as all other locations. This is only applicable if this algorithm does not get stopped when it discovered the goal node.
The BFS Algorithm will always check all of the posibilities before going into the different branches of a map. It can be illustrated by the following image. It first checks all the 'side' nodes before going deeper. 

![Breadth-First Search](http://www3.cs.stonybrook.edu/~skiena/combinatorica/animations/anim/bfs.gif)

## Dijkstra’s Algorithm
This algorithm starts from the initial node where the path should start, the algorithm marks all direct neighbours of the initial node with the cost to get there. It then proceeds from the node with the lowest cost to all of its adjacent vertices and marks them with the cost to get to them via itself if this cost is lower. Once all neighbours of a node have been checked, the algorithm proceeds to the node with the next lowest cost.

![Dijkstra's Algorithm](https://upload.wikimedia.org/wikipedia/commons/2/23/Dijkstras_progress_animation.gif)

## A* Algorithm
This algorithm will calculate the cost of each node around the starting node and pick the node with the lowest cost. After it calculated the node with the lowest cost, it predicts the node which appears to be closer to the goal node and calculates these first. This results in the most direct path towards the goal node. This 

![A* Algorithm](https://upload.wikimedia.org/wikipedia/commons/8/85/Weighted_A_star_with_eps_5.gif)

## The Mathematics
All of the algorithms follow steps that I will explain using this example, where R is the starting node and G is the goal node:
![Grid one](https://github.com/RobertDelmaar/Path-Planning-Explanation/blob/master/Sheets.png?raw=true)
### Breadth-First Search
We start with the nodes adjacent to R. Node 1 and 7 are 1 step away from the starting node. Next are nodes 2 and 10 with 2 steps away from the start. This repeats itself until the node G has been reached:

Steps  -  Nodes

1    -    1,7

2    -    2,10

3    -    3,14

4    -    5,15

5    -    8,16

6    -    9,11

7    -    G,12

### Dijkstra's
In this example, Dijkstra's algorithm will behave exactly the same as BFS. This is due to the size of the grid and due to the fact that we're using a grid instead of a graph with weights attached to the paths.

### A*
The A* algorithm works with two parameters: f(n) = g(n)+h(n) Here, g(n) is the distance between the starting position and the node n, h(n) is the distance between the node n and the endpoint. h(n) is calculated by using Pythagoras and g(n) is the number of steps you have taken between the starting position and the node.

From R we can go to 1 and to 7. 
 f(1)=g(1)-h(1)
The steps between R and 1 is 1 so g(1)=1. The distance between the node 1 and the endpoint is h(1)= sqrt{2²+4²}.
So f(1)=1+sqrt{20} = 5.47
Same goes for f(7) = g(7)+h(7)*g(7)=1 and h(1)=sqrt{0²+4²} so   f(7)=1+4=5
So here we see that f(7) is a smaller value than f(1) so in the next step f(1) will remain and will continue calculating the path of f(7) and then compare the values again.

f(1)=5.47
For f(10)=g(10)+h(10)*g(10)=2 because now we are two steps away from R. h(10)=sqrt{1²+4²}. So f(10)=2+sqrt{17}=6.12.
Now we can see that f(1) is less than f(10) so in the next step we’ll calculate the next step for path f(1).

We’ll have to keep repeating these steps until we reach the endpoint. There will be a moment where we can go 3 ways instead of 2. This works the same as 2 but now you compare 3 values with each other and take the lowest value for the next step. 

## Comparison
All of the path planners described above are efficient in their own 

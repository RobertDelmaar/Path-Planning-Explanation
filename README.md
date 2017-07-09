# Path-Planning-Explanation
In this document, multiple path planning algorithms will be explained and compared. I will make use of grid maps, environments that are discretized to be represented in squares of the same costs. The examples used in this document will be square grids of 21x21 squares, where grey squares are obstacles. The green and red square represent the goal and end node respectively. The yellow line is the shortest path calculated by the algorithm. The blue and light green squares are nodes that are discovered and the frontier.


## Breadth-First Search
This algorithm will explore equally in all directions. This algorithm doesn't use any heuristic method of going towards the goal and treats all nodes equally. After calculating every node's value or distance from the goal, it calculates the shortest path towards it.
This causes the algorithm to calculate a path to the goal lcoation as well as all other locations. This is only applicable if this algorithm does not get stopped when it discovered the goal node.
![Breadth-First Search](http://www3.cs.stonybrook.edu/~skiena/combinatorica/animations/anim/bfs.gif)

## Dijkstra’s Algorithm
This algorithm starts from the initial node where the path should start, the algorithm marks all direct neighbours of the initial node with the cost to get there. It then proceeds from the node with the lowest cost to all of its adjacent vertices and marks them with the cost to get to them via itself if this cost is lower. Once all neighbours of a node have been checked, the algorithm proceeds to the node with the next lowest cost.
![Dijkstra's Algorithm](https://upload.wikimedia.org/wikipedia/commons/2/23/Dijkstras_progress_animation.gif)

## A* Algorithm
This algorithm will calculate the cost of each node around the starting node and pick the node with the lowest cost. After it calculated the node with the lowest cost, it predicts the node which appears to be closer to the goal node and calculates these first. This 

![A* Algorithm](https://upload.wikimedia.org/wikipedia/commons/8/85/Weighted_A_star_with_eps_5.gif)








## Comparison

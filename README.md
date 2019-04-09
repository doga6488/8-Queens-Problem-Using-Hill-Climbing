# 8 Queens Problem Using Hill Climbing
Definition of the problem:
The eight queens puzzle is the problem of placing eight queens on an 8×8 chessboard in a way that not a single two queens threaten each other.
The eight queens puzzle has 92 distinct solutions.In fact the puzzle has only 12 solutions other solutions are just symmety of themselves.

Hill Climbing Approach
Hill Climbing is heuristic search that used for mathematical optimization problems in the field of Artificial Intelligence .
Given a large set of inputs and a good heuristic function, it tries to find a sufficiently good solution to the problem.
This solution may not be the global optimal maximum which means the algorithm itself might stick on some particular states called local maxima hence it might not be able to find the best solution whatsoever.

In this solution queens are represented as an array. The array consists of the queens' row number which represented by elements of array 
and indexes of array represent the coloumn number of the queens.
The movement of queens are assumed as they can be moved only on their own coloumns in order to constrain the movements so that calculate collapses simply and more structural.

Q=[4, 1, 7, 5, 3, 7, 4, 1]

For instance given array Q may be considered as the chess board below

    0     1     2     3     4     5     6     7     

0   *     *     *     *     *     *     *     *   

1   *     Q     *     *     *     *     *     Q   

2   *     *     *     *     *     *     *     *   

3   *     *     *     *     Q     *     *     *   

4   Q     *     *     *     *     *     Q     *   

5   *     *     *     Q     *     *     *     *   

6   *     *     *     *     *     *     *     *   

7   *     *     Q     *     *     Q     *     *   

Algorithm  
1 Calculate all collapses for every piece if a queen  move to another piece which shares the same coloumn with the queen
2 Evaluate the collapsses by finding minimum 
	2.1 if(There are equal collapses pick one randomly)
3 Perform movement by changing reagarding queens row number on the array
4 Assess the movement by examining whether there is a decrease on number of collapses
	4.1 if it equals then examine by counting this particular situation (in order to avoid shoulders)
	4.2 if it increase, on the other hand, start over by generating new queen positions
5 Do again until encounter 0 collapse movement
	
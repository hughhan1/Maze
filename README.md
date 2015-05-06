# Maze
This is a command-line Java application to generate random mazes.

### How Does It Work?
1. An *n* x *m* matrix is generated, which contains *n* x *m* cells. Initially, each cell is generated with four walls surrounding it.
2. All of the cells are dumped into a union-find data structure. Cells are disjoint when there are no paths connecting them. In other words, exist walls that them off from each other.
3. Random walls are then processed. 
  * If there exists a path from the cell on one side of the wall to the cell on the other side of the wall, do nothing.
  * Otherwise, remove the wall between those two cells and union the cells in the union-find data structure.
4. Repeat Step 3 until there are no disjoint sets in the union-find data structure. At that point, every cell will be reachable from any other cell in the maze.

### Usage
To use this application:

1. Clone this repository using ```git clone https://github.com/hughhan1/Maze.git```.
3. Compile the source code using ```javac *.java```.
2. Run ```java MazeDriver <rows> <cols>```, where <rows> and <cols> are the number of rows and columns of your maze.

Example: 

```
$ cd ~/Desktop
$ git clone https://github.com/hughhan1/Maze.git
$ javac *.java
$ java MazeDriver 15 20
```

This will generate a random 15 x 20 maze, with 15 rows and 20 columns.

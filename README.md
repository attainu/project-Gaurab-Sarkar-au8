###Maze Solver####

The aim of the project is to build a python program that run as a command line tool. It should take the input and output file name as command line arguments. Using the square matrix present in the input file and it should generate a path to reach from source to a destination point of the maze and put it in the output file. If the maze is unsolvable, it should return -1 as the only value in the output file.

In the maze matrix, 0 means the wall and 1 means the block can be used in the path from source to destination.


HOW TO SOLVE THE PROBLEM:
Read the input matrix from the inputFile.txt and form a 2-D matrix from it.
. In the given 2-D matrix consider the position of the element as the node where 1 is present and make a graph from it.
Now check whether it is possible to reach from source to destination in the 2-D matrix with the help of 1’s.
If yes find the position of all the 1’s present in 2-D array and store them in a list say “resultArray”.
Create another 2-D array say outputList and each position which is present in the resultArray as 1 and the reset of the position as 0
. write the outputList in the outputFile.txt


CONCEPT USED TO IMPLEMENT THE SOLUTION
	File handling
	Graph
	BFS
	Library of python(Collection, argparse, copy)  

Description 
Folder mainly contain Four files:
1.	Maze solver.py
2.	InputFile.txt
3.	OutputFIle.txt
4.	write .py
write .py
	It will request for an input which will be the order of the matrix say N
	It will open the inputFile .txt in write mode.
It will request for input n time  and user needs to give the space separated input with 0 or 1
It  will write the each input in inputfile.txt and then close the file.

InputFile.txt
InputFile .txt will contain an n x n matrix with 0 and 1 as element

OutputFIle.txt
OutputFile .txt will contain an nxn matrix with 0 and 1 as element but 1 will be present at source to destination path only or -1(for edge case “If doesn’t exist any path”)

MazeSolver.py
	Import three modules
Argparse modules
collection modules
copy modules

	Argparse module: This module is used for creating command-line.
	The collection module: provide different types of Container use for storing 
    Different object, some of build-in containers are (Tuple, List, Dictionary)
	Copy module: Copy module is just for keep the copy of visited Array.


AddEdge:
This function required two arguments u and v.
As undirected graph is getting creating it will add u as key to the graph which is define in constructor and append  v in list as value of u and vice versa for v and u.

PathExist:
This function required two argument u and v 
Where u is source and v is destination
This function working on the principle of BFS

Breadth First Search(BFS):
	BFS is a traversing algorithm it work in the following manner:

Let’s say we have a graph as shown in the figure and we need to find out whether a path exist between 0 and 8.
As we know BFS is a  non-linear data structure. Its principal are:
•	Visit / travel all node from source node 
•	It visit all node  in the level order.
•	It avoid all the duplicate visited node.
It will create a queue say Q = []
 It will create a dictionary say visited ={} add each node as key with their value as false so visited become visited node.
Initially Node ={0:false,1:false,2:false,3:false,4:false,5:false,6:false,7:false}  

It will enque the starting node to queue and mark the starting node as true in visited List now the Q and visited will become Q=[0]
Visited={0: true,1:false,2:false,3:false,4:false,5:false,6:false,7:false}

 Now it will deque the Q and enque the node which are connected to node 0 and mark those node as visited
Now the Q =[1,7] and
Visited={0:true,1:true,2: false,3:false,4:false,5:false,6:true,7 :false} 
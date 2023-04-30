Download Link: https://assignmentchef.com/product/solved-cs251-project-06-graph-algorithms
<br>
In lab and HW you’ve been building and working with graphs.  Our graph class is limited to 26 vertices ‘A’ – ‘Z’, but it’s enough to allow the investigation of various graph algorithms.  In this assignment you’re going to write a program to perform the following three algorithms:  BFS, DFS, and Dijkstra’s shortest weighted path.  Much of the code has already been developed, and you are free to use any code from lab and HW.

<h1>Program Overview</h1>

The program will input a graph from a text file, exactly as we have been doing in the lab and HW.  The graph is then output, and the user is prompted for a starting vertex.  Based on that starting vertex, the program outputs the neighbors, and then the results from traversing via BFS, DFS, and Dijkstra’s algorithm.  This is repeated until the user enters ‘#’ for the starting vertex.  Screenshot:

<h1>File input</h1>

The input to the program will come from a text file that contains N &gt; 0 lines.  The file format is exactly the same as from earlier lab and HW:  one vertex per line, following by #, then one edge per line, followed by #.  Assume all weights are positive, and that multi-edges will not occur (i.e. there is at most one edge between any two vertices).  Here’s the “graph1.txt” input file:




<strong>A </strong>

<strong>B </strong>

<strong>D </strong>

<strong>C </strong>

<strong>F </strong>

<strong>E </strong>

<strong># </strong>

<ul>

 <li><strong>B 100 </strong></li>

 <li><strong>A 80 </strong></li>

 <li><strong>D 115 </strong></li>

 <li><strong>D 12 </strong></li>

 <li><strong>C 20 </strong></li>

 <li><strong>E 29 </strong></li>

</ul>

<strong>E C 29 </strong>

<strong>D C 7 </strong>

<strong>#</strong>




Four sample input files are provided on the course web site under Projects, <a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">project06</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">–</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">files</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">:</a>  “graph1.txt”, “graph2.txt”, “graph3.txt”, and “graph4.txt”.  Visual drawings of graphs 1 – 3 are given in this <a href="https://www.dropbox.com/s/kbnhbdn0rkw0ofj/graphs-1-3.pdf?dl=0">PDF</a><a href="https://www.dropbox.com/s/kbnhbdn0rkw0ofj/graphs-1-3.pdf?dl=0">.</a>




The code to read the text file and build the graph has been provided in lab and HW; see the function <strong>buildGraph()</strong>.  This function should be in the same C++ file (util.cpp?) as your BFS and DFS solutions.  Feel free to reuse this function exactly as provided.  If you decide to write your own function, note that since we are not inputting strings that may contain spaces, you can use the <strong>&gt;&gt;</strong> input operator instead of getline().

<h1>Provided files and implementation details</h1>

Besides sample input files, we are providing a <strong>graph</strong> class (similar to what has been used in lab and HW), and a <strong>minqueue</strong> class needed by Dijkstra’s algorithm.  Note that a main.cpp file is *not* provided; that is intentional.  If you prefer to work on Codio, the project “<strong>cs251-project06-graphs</strong>” is provided with these files + a makefile.  If you prefer to work outside Codio, the files are provided in both Linux and Mac-Windows formats:  download from course web page under Projects, <a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">project06</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">–</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">files</a><a href="https://www.dropbox.com/sh/hog8aot9x591gjh/AADwIkOHYA23jRUcqePETDGqa?dl=0">.</a>




When it comes time to implement Dijkstra’s algorithm, take a look at the provided <strong>minqueue</strong> class.  This provides the “PopMin” function shown in the zybooks algorithm.  Note that clarifications to Dijkstra’s algorithm will be given in class, so you should check the lecture notes starting from Friday Nov 22 (<a href="https://www.dropbox.com/sh/cgsrga893jw0gl3/AAD2tHXI9NKeHjS4nOXCkDfHa?dl=0">Day </a><a href="https://www.dropbox.com/sh/cgsrga893jw0gl3/AAD2tHXI9NKeHjS4nOXCkDfHa?dl=0">37</a><a href="https://www.dropbox.com/sh/cgsrga893jw0gl3/AAD2tHXI9NKeHjS4nOXCkDfHa?dl=0">)</a>, and beyond.  Your implementation of Dijkstra’s algorithm should compute the set of vertices that are visited, in the order they are visited, must like BFS and DFS.  In addition, your implementation also needs to compute the minimum distance to each of these vertices, and the predecessors back to the starting vertex.

<h1>Program behavior</h1>

The program starts by inputting a filename.  The program should check to make sure the file exists, and halt with an error message if not.  If the file exists, open the file, build the graph, and then output to the screen; note that the provided <strong>graph</strong> class now contains an <strong>output()</strong> function to output the graph for you.  The program then prompts for a starting vertex, and outputs the results of neighbors, BFS, DFS, and Dijkstra’s algorithm.  This is repeated until the user enters the sentinel ‘#’.  Here’s another screenshot:
















Note that if the user enters a vertex that doesn’t exist, e.g. ‘F’ as shown above or illegal chars such as ‘7’ or ‘a’, then the program should output an error message.  With regards to the output shown for Dijkstra’s algorithm, the first output is the set of visited vertices, in order they are visited — much like BFS and DFS.  Then, for each visited vertex, the minimum distance is output, along with the path that achieves this minimum distance.

<h1>Requirements</h1>

<ol>

 <li>You must use the provided “graph.h” class as your graph.</li>

 <li>You may not change the provided “graph.h” class — we will grade your submission using our graph.h.</li>

 <li>You must have functions that implement BFS, DFS, and Dijkstra’s alg. Those functions, and any functions they call, may *not* output to a file or the console.  You must pass all data in via parameters, and return all results via parameters / return value.  If your function breaks this requirement, we will mark it as incorrect and score this aspect of the assignment as 0.</li>

</ol>




<ol start="4">

 <li>The max nesting of loops is 2 — i.e. any function that contains more than two levels of loop nesting will be deleted. Any functionality that depends on the deleted function will not be graded and scored as 0.  Use functions.  Here’s an example of code that would violate this requirement:</li>

</ol>




while (…) {

.   .   for (…)   {

for (…)

{ }

}   .

.

}

The code has 3 levels of explicit loop nesting.  The solution is to turn one of the loops into a function, and call it, that’s fine.  The goal is to encourage more use of functions.






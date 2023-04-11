# GraphColoring
<h2>
  This problem asks, given a graph, how many colors are needed to color each vertex where no two adjacent vertices are the same color.
</h2>

This project takes in files where the first line has two numbers: the number of vertices in the graph and the number of edges in the graph. 
It is then followed by sets of numbers describing the pairs of vertices connected by each edge.
The solution output has a number which is the smallest number of colors needed to color the graph followed by a list of color values for each vertex.
I used a constraint satisfaction approach. I started by finding the greedy solution k colors then tried k-1 colors continuously until finding that no answer was possible. Then my minimal answer was the last value that returned a solution, which I then put in my solution file. 
To find the solution, I started with the vertex that had the most edges and assigned it a legal color. Each vertex has a domain of legal colors, so after each assignment, that domain gets reduced.
Then, I picked my next vertex by which one had the smallest domain and therefore the fewest options for legal colors.
If ever a vertex had no legal color, I backtracked. The vertex would choose a new different color and try again.
This would keep going until a solution is found (every vertex has a color) or solution is impossible (there is a vertex where no color is legal).

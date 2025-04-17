# Depth-First Search (DFS) Traversal in Python

##  Aim
To implement a Python utility function for performing Depth-First Search (DFS) traversal from a given source vertex.

## Procedure
1. Use recursion to explore as far as possible along each branch before backtracking.
2. Maintain a `visited` set or list to avoid revisiting nodes.
3. Start from the source vertex and recursively visit all unvisited adjacent vertices.

##  Program
```python
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v, end=' ')

		# Recur for all the vertices
		# adjacent to this vertex
		for neighbour in self.graph[v]:
			if neighbour not in visited:
				self.DFSUtil(neighbour, visited)

	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)


```

## Output:

![image](https://github.com/user-attachments/assets/c6ce2e1b-dba4-431b-bd9a-0cbc9c586f26)

## Result:
The function performs a recursive DFS traversal and prints the nodes in the order they are visited starting from the given source vertex.



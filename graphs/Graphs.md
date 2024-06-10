

### Graph Terminology

**Graph** - Nodes(n)+ Edges(m)
 A path is a **cycle** if its first and last node are the same. **Simple Path** - Each node appears atmost once in it.
**Connected Graph** - A path exists between any two nodes.

**Components** - Connected parts of a graph

#### Tree
Connected graph with **n nodes** and **n - 1 edges**.
**Unique path** between any two nodes of a tree => **Acylic**

**Connected Acylic Graph**


Edge weights often interpreted as edge lengths.


**Neighbors/Adjacent** - Two nodes with an edge between them.
**Degree**  of a node - Number of its neighbors

**Sum of degrees** in a graph - **Always 2m**  (each edge increases the degree of exactly two nodes by one)  => Sum of degrees is **always even**



**Regular Graph** - Degree of every node is a **constant d**.

**Complete Graph** - Degree of every node is **n - 1** - graph contains all possible edges between the nodes.


#### Coloring
No adjacent nodes have the same color.

**Bipartite Graph** - Can be colored using only two colors.
A graph is bipartite **exactly** when it **does not contain a cycle with an odd number of edges**.
                     a   -----   b 
                      \\          /
					    c
		If a is colored red, and b is colored green, then c must be colored comething else, so not bipartite.


**Simple Graph** - No Self Edges, and no multiple edges between nodes.

### Graph Representation



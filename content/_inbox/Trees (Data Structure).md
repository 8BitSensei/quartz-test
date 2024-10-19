2024-01-17
Tags: #dataStructure #CompSci 

Type of [[Graph Data Structure]] composed of nodes and edges; a node is an element, and an edge is a directional connection from one node to another. It's main properties are:
1. Acyclic, meaning there are no loops between nodes
2. There is a path from the root to any node
3. Has `n - 1` edges where `n` is the number of nodes
4. Each node has only one parent

Here are some important terms to memorise:
- **Internal node**: every node in a tree that has at least one child node.
- **Leaf node**: every node in a tree that has no child nodes.
- **Ancestor**: all the nodes that are between the path from the root to the current node are the ancestors of the current node. An ancestor node of the current node is either the parent of the current node or the parent of another ancestor of the node.
- **Descendent**: all the nodes that are reachable from the current node when moving down the tree are the descendants of the current node. A descendant of the current node is either a child of the node or a child of another descendant of the node.
- **Level**: the number of ancestors from the node to the root nodes.


---
# References

https://algo.monster/problems/tree_intro
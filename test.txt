import matplotlib.pyplot as plt
import networkx as nx

# Define the adjacency matrix from the image
adjacency_matrix = [
    [0, 1, 0, 1, 0],
    [1, 1, 1, 0, 0],
    [0, 0, 1, 1, 1],
    [1, 1, 0, 1, 1],
    [1, 0, 1, 0, 1]
]

# Create the graph
G = nx.Graph()

# Add nodes
G.add_nodes_from(range(1, 6))  # Nodes are 1 to 5

# Add edges based on the adjacency matrix
for i in range(len(adjacency_matrix)):
    for j in range(len(adjacency_matrix[i])):
        if adjacency_matrix[i][j] == 1:
            G.add_edge(i + 1, j + 1)  # Nodes are 1-indexed

# Draw the graph
plt.figure(figsize=(8, 6))
nx.draw(G, with_labels=True, node_color='lightblue', node_size=500, font_size=12, font_weight='bold', edge_color='gray')
plt.title("Graph Representation of the Adjacency Matrix", fontsize=14)
plt.show()
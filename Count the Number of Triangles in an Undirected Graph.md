# Ex. No: 18E - Count the Number of Triangles in an Undirected Graph

## AIM:
To write a Python program to **count the number of triangles** present in an **undirected graph** using matrix operations.

## ALGORITHM:

**Step 1**: Initialize a matrix `aux2` to store the square of the adjacency matrix (i.e., `graph²`).  
Also, initialize a matrix `aux3` to store the cube of the adjacency matrix (i.e., `graph³`).

**Step 2**: Multiply the adjacency matrix with itself to compute `aux2 = graph × graph`.

**Step 3**: Multiply `aux2` with the adjacency matrix again to compute `aux3 = aux2 × graph`.

**Step 4**: Compute the **trace** of the matrix `aux3` (i.e., the sum of diagonal elements of the matrix).

**Step 5**: Divide the trace by **6** to get the number of triangles in the graph.  
*(Each triangle is counted six times in the trace — twice per vertex and once per direction.)*

**Step 6**: Return the result.

## PYTHON PROGRAM

```
import numpy as np

def count_triangles(adj_matrix):
    # Convert the adjacency matrix to numpy array for matrix operations
    A = np.array(adj_matrix)

    # Compute A^3 (i.e., A cubed)
    A3 = np.linalg.matrix_power(A, 3)

    # Calculate the trace of A^3
    trace = np.trace(A3)

    # Each triangle is counted 6 times in an undirected graph
    return trace // 6

# Sample input: adjacency matrix for a graph with 4 vertices
adj_matrix = [
    [0, 1, 1, 0],  # Connections for node 0
    [1, 0, 1, 1],  # Connections for node 1
    [1, 1, 0, 1],  # Connections for node 2
    [0, 1, 1, 0]   # Connections for node 3
]

print("Total number of Triangle in Graph :", count_triangles(adj_matrix))

```

## OUTPUT
<img width="1258" height="231" alt="image" src="https://github.com/user-attachments/assets/baac92bd-b29e-4f7a-8907-99246b2ad06c" />

```

## RESULT
Thus the Python program to **count the number of triangles** present in an **undirected graph** using matrix operations is executed successfully.

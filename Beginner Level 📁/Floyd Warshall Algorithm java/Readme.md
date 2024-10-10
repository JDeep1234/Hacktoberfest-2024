## Explanation

**Floyd's algorithm**, often referred to as the **Floyd-Warshall algorithm**, is a classic algorithm used to find the shortest paths between all pairs of vertices in a weighted graph. It works for both directed and undirected graphs and can handle negative weights (but not negative cycles).

1. **Input**: 
   - The input is an adjacency matrix `graph`, where `graph[i][j]` represents the weight of the edge from vertex `i` to vertex `j`. If there is no edge, it can be represented by `Integer.MAX_VALUE` (or a very large number).
  
2. **Distance Initialization**: 
   - We initialize a distance matrix `dist` to store the shortest paths. Initially, `dist[i][j]` is set to `graph[i][j]`.

3. **Algorithm**:
   - The three nested loops iterate through all pairs of vertices `(i, j)` and check if the path from `i` to `j` through an intermediate vertex `k` offers a shorter path than the currently known shortest path.
   - The condition `dist[i][k] != Integer.MAX_VALUE && dist[k][j] != Integer.MAX_VALUE` ensures we only consider valid paths.

4. **Output**: 
   - The final `dist` matrix contains the shortest path lengths between all pairs of vertices.

## Complexity Analysis

- **Time Complexity**: O(V^3), where V is the number of vertices in the graph. This is because we iterate through three nested loops.
- **Space Complexity**: O(V^2) due to the storage of the distance matrix.

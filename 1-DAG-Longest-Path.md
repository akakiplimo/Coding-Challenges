# Master DAG Longest Path - First Principles Breakdown

## Core Concepts You Need

### 1. **Graph Fundamentals**
- What is a graph? (nodes + edges)
- Directed vs undirected
- Cyclic vs acyclic (DAG)
- Graph representations (adjacency list, adjacency matrix, edge list)

### 2. **Topological Sort**
- Why it works only on DAGs
- Kahn's algorithm (BFS-based)
- DFS-based approach
- In-degree concept

### 3. **Dynamic Programming on Graphs**
- Dependency-based computation
- Memoization patterns
- Bottom-up vs top-down

### 4. **JavaScript Data Structures**
- Map operations (set, get, has)
- Set operations (add, has, iteration)
- Array as queue (push, shift)

---

## 7-Day Learning Schedule

### **Day 1: Graph Basics**

**Morning (1 hour):**
- Draw graphs on paper: 5 directed graphs, 5 undirected
- Practice converting edge list to adjacency list manually
- Identify cycles by hand

**Exercises:**
```javascript
// 1. Build adjacency list from edges
function buildGraph(edges) {
    // [[1,2], [2,3], [1,3]]
    // Return: Map { 1: [2,3], 2: [3], 3: [] }
}

// 2. Count nodes in graph
function countNodes(edges) {
    // Use Set to track unique nodes
}

// 3. Find all neighbors of a node
function getNeighbors(graph, node) {
    // Return array of neighbors
}
```

**Evening (30 min):**
- Implement the 3 exercises above
- Test with 3 different graphs

---

### **Day 2: In-Degree & Out-Degree**

**Morning (1 hour):**
- Draw 3 graphs and manually calculate in-degree for each node
- Understand: in-degree = number of incoming edges

**Exercises:**
```javascript
// 1. Calculate in-degrees for all nodes
function calculateInDegrees(edges) {
    // edges: [[1,2], [1,3], [2,3]]
    // Return: Map { 1: 0, 2: 1, 3: 2 }
}

// 2. Find source nodes (in-degree = 0)
function findSources(edges) {
    // Return array of nodes with no incoming edges
}

// 3. Find sink nodes (out-degree = 0)
function findSinks(edges) {
    // Return array of nodes with no outgoing edges
}
```

**Evening (30 min):**
- Code all 3 functions
- Draw graphs and verify your code matches manual calculations

---

### **Day 3: Topological Sort (Kahn's Algorithm)**

**Morning (1.5 hours):**
- Watch: Understand Kahn's algorithm conceptually
- Steps: Start with in-degree=0 → Process → Reduce neighbors' in-degree → Repeat

**Exercises:**
```javascript
// 1. Basic topological sort (return order)
function topologicalSort(edges) {
    // Return one valid topological ordering
    // Example: [[1,2], [2,3]] → [1, 2, 3]
}

// 2. Check if graph is DAG
function isDAG(edges) {
    // Use topological sort
    // If you can't process all nodes → cycle exists
}

// 3. Topological sort with BFS tracking
function topoSortWithLevels(edges) {
    // Track which "level" each node is processed at
}
```

**Evening (1 hour):**
- Implement topological sort from scratch 3 times without looking
- Test on 5 different graphs

---

### **Day 4: Distance Tracking**

**Morning (1 hour):**
- Understand: Distance = number of edges from source
- Practice manually tracking max distance to each node

**Exercises:**
```javascript
// 1. Calculate distance from single source
function distanceFromSource(edges, source) {
    // Return Map of node → distance from source
    // Use BFS
}

// 2. Find farthest node from source
function farthestNode(edges, source) {
    // Return {node, distance}
}

// 3. Track max distance during topological sort
function maxDistanceInTopoSort(edges) {
    // Combine Day 3 knowledge
    // Update distances as you process nodes
}
```

**Evening (1 hour):**
- Draw 3 graphs
- Manually calculate distances
- Verify with your code

---

### **Day 5: Combining Everything**

**Morning (2 hours):**
- Implement `findLongestPath` from scratch without looking
- Break it into steps:
  1. Build graph + calculate in-degrees
  2. Find sources
  3. Topological sort
  4. Track distances
  5. Return max

**Exercises:**
```javascript
// 1. Longest path (your main problem)
function findLongestPath(edges) {
    // Implement completely from memory
}

// 2. Find the actual path (not just length)
function findLongestPathWithNodes(edges) {
    // Return: {length: 3, path: [1, 2, 3, 4]}
}

// 3. All longest paths (if multiple exist)
function findAllLongestPaths(edges) {
    // Return array of all paths with max length
}
```

**Evening (1 hour):**
- Test with edge cases:
  - Single node
  - Disconnected components
  - Multiple sources
  - Linear chain

---

### **Day 6: Pattern Recognition**

**Morning (1.5 hours):**

Study variations of the same pattern:
```javascript
// 1. Shortest path in DAG (weighted)
function shortestPathDAG(edges, weights, start, end) {
    // Same structure, different update rule
}

// 2. Number of paths in DAG
function countPaths(edges, start, end) {
    // dp[node] = sum of dp[previous nodes]
}

// 3. Longest increasing subsequence (using DAG)
function longestIncreasingSubsequence(arr) {
    // Build implicit DAG
}
```

**Evening (1 hour):**
- Identify the common pattern:
  1. Build graph structure
  2. Topological order
  3. DP on that order
  4. Return result

---

### **Day 7: Speed Practice**

**Morning (2 hours):**

Set timer challenges:

**Round 1 (30 min):**
- Implement `findLongestPath` from scratch
- No looking at notes

**Round 2 (20 min):**
- Implement again, faster

**Round 3 (15 min):**
- Implement again, even faster

**Round 4 (10 min):**
- Final attempt

**Evening (1 hour):**

Solve these without any reference:
1. Course Schedule II (LeetCode 210)
2. Longest Path in DAG
3. Minimum Height Trees (LeetCode 310)

---

## Memory Aids

### The Pattern (Memorize This):
```
1. Initialize: graph, inDegree, Set of nodes
2. Build: For each edge [a,b]:
   - Add to graph[a]
   - Increment inDegree[b]
3. Queue: All nodes with inDegree = 0
4. Process: While queue not empty:
   - Pop node
   - For each neighbor:
     - Update DP value
     - Decrement inDegree
     - If inDegree = 0, add to queue
5. Return: Max DP value
```

### Whiteboard Practice

Every day, draw and solve on paper before coding:
- Forces you to think through logic
- Reveals gaps in understanding
- Builds muscle memory

### Success Metrics

By Day 7, you should:
- ✅ Write `findLongestPath` in under 10 minutes
- ✅ Explain each line's purpose
- ✅ Identify and fix bugs quickly
- ✅ Adapt pattern to similar problems

---

## Final Notes

The key is **repetition with understanding**, not just memorization. Each time you implement it, try to understand *why* each step works.

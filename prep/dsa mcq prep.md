
---

# 🔍 SEARCHING – MCQ SHORTCUTS

- **Binary Search works ONLY on** → **Sorted array**
    
- **Fastest searching in sorted array** → **Binary Search (O log n)**
    
- **Binary Search worst case** → **O(log n)**
    
- **Interpolation Search best when** → **Uniformly distributed data**
    
- **Linear search best case** → **O(1)**
    
- **Exponential Search** → Binary Search + range finding
    

📌 **MCQ Trick**

> If array is **unsorted**, answer is almost always **Linear Search**

---

# 🔄 SORTING – MCQ SHORTCUTS

### ⏱️ TIME COMPLEXITY QUICK RULES

- **Bubble / Selection / Insertion** → O(n²)
    
- **Merge / Heap / Quick (avg)** → O(n log n)
    
- **Counting / Radix / Bucket** → **NOT comparison-based**
    

---

### 🧠 STABILITY TRICK

**Stable Sorts** (order preserved):

- Bubble
    
- Insertion
    
- Merge
    
- Counting
    
- Radix
    

**Unstable Sorts**:

- Selection
    
- Quick
    
- Heap
    

📌 MCQ Rule:

> **If question says "stable" → eliminate Quick & Heap immediately**

---

### 💾 IN-PLACE SORTS

- **In-place** → Bubble, Selection, Insertion, Quick, Heap
    
- **Not in-place** → Merge, Counting, Radix, Bucket
    

---

### 🥇 FASTEST SORT (MCQ ANSWERS)

- **General purpose** → **Quick Sort**
    
- **Guaranteed performance** → **Merge Sort**
    
- **Memory constrained** → **Heap Sort**
    

---

# 🌳 TREES – MCQ SHORTCUTS

- **Inorder traversal of BST** → **Sorted output**
    
- **Min value in BST** → **Leftmost node**
    
- **Max value in BST** → **Rightmost node**
    
- **Balanced BST height** → **O(log n)**
    
- **Skewed tree height** → **O(n)**
    

📌 MCQ Rule:

> If BST + sorted → **Inorder**

---

# 📊 GRAPHS – MCQ SHORTCUTS

- **BFS uses** → Queue
    
- **DFS uses** → Stack / Recursion
    
- **Cycle detection (undirected)** → DFS / Union-Find
    
- **Cycle detection (directed)** → DFS + recursion stack
    
- **Topological sort works only on** → **DAG**
    

---

### 🚦 SHORTEST PATH TRICKS

|Condition|Algorithm|
|---|---|
|No negative edges|Dijkstra|
|Negative edges|Bellman-Ford|
|All pairs shortest path|Floyd-Warshall|

📌 MCQ Rule:

> Negative edge present → **Never Dijkstra**

---

### 🌉 MST SHORTCUT

- **Prim’s** → Vertex-based
    
- **Kruskal’s** → Edge-based
    
- **Dense graph** → Prim’s
    
- **Sparse graph** → Kruskal’s
    

---

# 📈 DYNAMIC PROGRAMMING – MCQ SHORTCUTS

- **Overlapping subproblems + optimal substructure** → DP
    
- **DP vs Recursion** → DP avoids recomputation
    
- **0/1 Knapsack** → DP (not greedy)
    
- **Fractional Knapsack** → Greedy
    

📌 MCQ Rule:

> If choices are **take / not take** → DP

---

# 🧮 COMPLEXITY MCQ TRICKS

### 🔥 ORDER (FAST → SLOW)

```
O(1)
O(log n)
O(n)
O(n log n)
O(n²)
O(2ⁿ)
O(n!)
```

📌 If options include **n!** → it’s **worst**

---

### ⏳ RECURSION SHORTCUT

- **T(n) = 2T(n/2) + n** → **O(n log n)**
    
- **T(n) = T(n-1) + n** → **O(n²)**
    

---

# 🔤 STRING ALGORITHMS – MCQ SHORTCUTS

- **Naive pattern matching** → O(nm)
    
- **KMP** → O(n + m)
    
- **Rabin-Karp uses** → Hashing
    
- **Z algorithm uses** → Z-array
    

📌 MCQ Rule:

> Pattern matching + linear time → **KMP**

---

# ⚙️ BIT MANIPULATION – MCQ SHORTCUTS

- **XOR of same numbers** → 0
    
- **XOR with 0** → Same number
    
- **n & (n−1)** → Removes lowest set bit
    
- **Check power of 2** → n & (n−1) == 0
    

---

# 🔁 BACKTRACKING – MCQ SHORTCUTS

- **Exponential time** problems:
    
    - N-Queens
        
    - Sudoku
        
    - Permutations
        
- **Uses recursion + undo choice**
    

📌 MCQ Rule:

> All possibilities → Backtracking

---

# 🎯 MOST COMMON MCQ CONFUSIONS

|Question|Correct Answer|
|---|---|
|Fastest sorting average|Quick Sort|
|Fastest worst-case sort|Merge Sort|
|Sorted BST traversal|Inorder|
|Shortest path negative edges|Bellman-Ford|
|Cycle in directed graph|DFS|
|Stable + n log n|Merge Sort|

---


###### **master list of DSA algorithms**

---

# 🔢 1. Searching Algorithms

|Algorithm|One-line Definition|Time Complexity|Space|
|---|---|---|---|
|**Linear Search**|Checks each element sequentially until found|O(n)|O(1)|
|**Binary Search**|Repeatedly divides sorted array to find element|O(log n)|O(1)|
|**Jump Search**|Jumps fixed steps then linear search|O(√n)|O(1)|
|**Interpolation Search**|Estimates position based on value distribution|O(log log n) avg, O(n) worst|O(1)|
|**Exponential Search**|Finds range then applies binary search|O(log n)|O(1)|

---

# 🔄 2. Sorting Algorithms

|Algorithm|One-line Definition|Time Complexity (Best / Avg / Worst)|Space|
|---|---|---|---|
|**Bubble Sort**|Swaps adjacent elements repeatedly|O(n) / O(n²) / O(n²)|O(1)|
|**Selection Sort**|Selects minimum and places it correctly|O(n²)|O(1)|
|**Insertion Sort**|Inserts elements into sorted portion|O(n) / O(n²) / O(n²)|O(1)|
|**Merge Sort**|Divides array and merges sorted halves|O(n log n)|O(n)|
|**Quick Sort**|Partitions around pivot recursively|O(n log n) avg, O(n²) worst|O(log n)|
|**Heap Sort**|Uses heap data structure to sort|O(n log n)|O(1)|
|**Counting Sort**|Counts occurrences of values|O(n + k)|O(k)|
|**Radix Sort**|Sorts digit by digit|O(nk)|O(n + k)|
|**Bucket Sort**|Distributes elements into buckets|O(n + k)|O(n)|

---

# 🌳 3. Tree Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**Preorder Traversal**|Root → Left → Right|O(n)|O(h)|
|**Inorder Traversal**|Left → Root → Right|O(n)|O(h)|
|**Postorder Traversal**|Left → Right → Root|O(n)|O(h)|
|**Level Order Traversal**|Traverses tree level by level|O(n)|O(n)|
|**BST Search**|Searches element in BST|O(log n) avg, O(n) worst|O(1)|
|**BST Insert/Delete**|Inserts or deletes maintaining BST|O(log n) avg|O(1)|

(h = height of tree)

---

# 📈 4. Graph Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**BFS**|Traverses graph level-wise|O(V + E)|O(V)|
|**DFS**|Traverses graph depth-wise|O(V + E)|O(V)|
|**Dijkstra**|Finds shortest path from source|O(E log V)|O(V)|
|**Bellman-Ford**|Shortest path allowing negative edges|O(VE)|O(V)|
|**Floyd-Warshall**|All-pairs shortest path|O(V³)|O(V²)|
|**Prim’s Algorithm**|Finds minimum spanning tree|O(E log V)|O(V)|
|**Kruskal’s Algorithm**|MST using edge sorting|O(E log E)|O(V)|
|**Topological Sort**|Linear ordering of DAG|O(V + E)|O(V)|

---

# 🧮 5. Dynamic Programming Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**Fibonacci (DP)**|Uses memoization/tabulation|O(n)|O(n)|
|**0/1 Knapsack**|Maximizes value with weight constraint|O(nW)|O(nW)|
|**LCS**|Finds longest common subsequence|O(nm)|O(nm)|
|**LIS**|Finds longest increasing subsequence|O(n log n)|O(n)|
|**Matrix Chain Multiplication**|Optimal matrix multiplication order|O(n³)|O(n²)|
|**Coin Change**|Minimum coins for amount|O(n × amount)|O(amount)|

---

# 🔁 6. Greedy Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**Activity Selection**|Selects max non-overlapping activities|O(n log n)|O(1)|
|**Huffman Coding**|Optimal prefix codes for compression|O(n log n)|O(n)|
|**Fractional Knapsack**|Maximizes value with fractions allowed|O(n log n)|O(1)|
|**Job Sequencing**|Maximizes profit before deadlines|O(n log n)|O(n)|

---

# 🔐 7. Backtracking Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**N-Queens**|Places queens without conflicts|O(n!)|O(n)|
|**Sudoku Solver**|Solves grid using recursion|O(9^(n²))|O(n²)|
|**Rat in a Maze**|Finds all possible paths|Exponential|O(n²)|
|**Permutations**|Generates all permutations|O(n!)|O(n)|

---

# 🔗 8. String Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**Naive Pattern Search**|Checks pattern at every index|O(nm)|O(1)|
|**KMP Algorithm**|Uses LPS array to skip comparisons|O(n + m)|O(m)|
|**Rabin-Karp**|Uses hashing for pattern search|O(n + m) avg|O(1)|
|**Z Algorithm**|Uses Z-array for pattern matching|O(n + m)|O(n)|

---

# ⚙️ 9. Bit Manipulation Algorithms

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**XOR Technique**|Finds unique element|O(n)|O(1)|
|**Brian Kernighan’s Algo**|Counts set bits|O(k)|O(1)|
|**Bit Masking**|Represents subsets using bits|O(2ⁿ)|O(1)|

---

# 🧠 10. Divide and Conquer

|Algorithm|One-line Definition|Time|Space|
|---|---|---|---|
|**Merge Sort**|Divide, sort, merge|O(n log n)|O(n)|
|**Quick Sort**|Partition around pivot|O(n log n) avg|O(log n)|
|**Binary Search**|Divide sorted array|O(log n)|O(1)|
|**Strassen’s Matrix Mult.**|Faster matrix multiplication|O(n^2.81)|O(n²)|

---


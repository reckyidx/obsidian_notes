
## 1️⃣ Brute Force

**Idea:** Try all possibilities

**Use when:**

- Constraints are small
    
- As a baseline / correctness check
    

**TC:** Usually `O(n²)` or worse

**Examples:**

- All subarrays
    
- All substrings
    
- All pairs
    

---

## 2️⃣ Two Pointers

**Idea:** Use two indices moving toward/away from each other

**Use when:**

- Array / string
    
- Sorted data or window-like problems
    

**Examples:**

- Two Sum (sorted)
    
- Remove duplicates
    
- Valid palindrome
    

---

## 3️⃣ Sliding Window (Fixed / Variable)

**Idea:** Maintain a moving window over the array

**Use when:**

- Subarrays / substrings
    
- Continuous segments
    

**Examples:**

- Max sum subarray of size k
    
- Longest substring without repeats
    
- Minimum window substring
    

---

## 4️⃣ Prefix Sum

**Idea:** Precompute cumulative sums

**Use when:**

- Range sum queries
    
- Subarray sum problems
    

**Examples:**

- Subarray sum equals k
    
- Range sum queries
    

---

## 5️⃣ Prefix Sum + Hash Map

**Idea:** Store frequency of prefix sums

**Use when:**

- Count subarrays
    
- Negative numbers exist
    

**Examples:**

- Subarray sum equals k
    
- Binary subarrays with sum
    

---

## 6️⃣ Difference Array

**Idea:** Efficient range updates

**Use when:**

- Multiple range increments
    

**Examples:**

- Range addition
    
- Corporate flight bookings
    

---

## 7️⃣ Hashing / Frequency Map

**Idea:** Store counts / existence

**Use when:**

- Counting
    
- Fast lookup
    

**Examples:**

- Anagrams
    
- Majority element
    
- First unique character
    

---

## 8️⃣ Sorting Based Techniques

**Idea:** Sort first, then solve

**Use when:**

- Order matters
    
- Greedy pairing
    

**Examples:**

- Merge intervals
    
- 3Sum
    
- Meeting rooms
    

---

## 9️⃣ Greedy

**Idea:** Take best local decision

**Use when:**

- Optimal substructure exists
    
- Choices don’t affect future badly
    

**Examples:**

- Jump Game
    
- Activity selection
    
- Gas station
    

---

## 🔟 Binary Search

**Idea:** Divide search space by half

**Use when:**

- Sorted or monotonic property
    
- “Minimum / Maximum feasible”
    

**Examples:**

- Search in rotated array
    
- Capacity to ship packages
    

---

## 1️⃣1️⃣ Binary Search on Answer

**Idea:** Search the solution space, not array

**Examples:**

- Min eating speed
    
- Allocate books
    
- Aggressive cows
    

---

## 1️⃣2️⃣ Stack (Monotonic Stack)

**Idea:** Maintain increasing/decreasing order

**Use when:**

- Nearest greater/smaller element
    

**Examples:**

- Next greater element
    
- Largest rectangle in histogram
    
- Daily temperatures
    

---

## 1️⃣3️⃣ Queue / Deque

**Idea:** FIFO or sliding window max/min

**Examples:**

- Sliding window maximum
    
- BFS traversal
    

---

## 1️⃣4️⃣ Recursion

**Idea:** Function calls itself

**Use when:**

- Tree / divide problems
    

**Examples:**

- Tree traversal
    
- Permutations
    

---

## 1️⃣5️⃣ Backtracking

**Idea:** Try → undo → try next

**Use when:**

- All combinations / permutations
    

**Examples:**

- N-Queens
    
- Subsets
    
- Sudoku solver
    

---

## 1️⃣6️⃣ Dynamic Programming (DP)

**Idea:** Overlapping subproblems + memoization

**Types:**

- 1D DP
    
- 2D DP
    
- DP on trees
    
- DP on grids
    

**Examples:**

- Fibonacci
    
- Coin change
    
- LCS
    
- Knapsack
    

---

## 1️⃣7️⃣ Greedy + DP Hybrid

**Examples:**

- Job scheduling
    
- Weighted intervals
    

---

## 1️⃣8️⃣ Graph Traversal (BFS / DFS)

**Idea:** Explore nodes & edges

**Examples:**

- Number of islands
    
- Shortest path in grid
    

---

## 1️⃣9️⃣ Topological Sort

**Idea:** Order tasks with dependencies

**Examples:**

- Course schedule
    
- Alien dictionary
    

---

## 2️⃣0️⃣ Union Find (Disjoint Set)

**Idea:** Group connected components

**Examples:**

- Detect cycle
    
- Number of provinces
    

---

## 2️⃣1️⃣ Heap / Priority Queue

**Idea:** Always extract min/max

**Examples:**

- K largest elements
    
- Median from data stream
    

---

## 2️⃣2️⃣ Bit Manipulation

**Idea:** Use bits for optimization

**Examples:**

- Single number
    
- Subsets
    
- XOR tricks
    

---

## 2️⃣3️⃣ Math / Number Theory

**Examples:**

- GCD / LCM
    
- Sieve of Eratosthenes
    
- Modulo arithmetic
    

---

## 2️⃣4️⃣ String Algorithms

**Examples:**

- KMP
- Rabin-Karp
- Z-Algorithm
- Trie
    

---

## 2️⃣5️⃣ Trie (Prefix Tree)

**Use when:**

- Prefix / dictionary problems

**Examples:**

- Word search
- Autocomplete
    

---

## 2️⃣6️⃣ Segment Tree / Fenwick Tree

**Use when:**

- Range queries + updates
    

**Examples:**

- Range sum query
    
- Inversion count
    

---

## 2️⃣7️⃣ Sweep Line

**Idea:** Process events in order

**Examples:**

- Skyline problem
    
- Meeting rooms II
    

---

## 2️⃣8️⃣ Two Heaps

**Examples:**

- Median in stream
    

---

## 2️⃣9️⃣ State Compression

**Idea:** Use bitmask DP

**Examples:**

- Traveling salesman
    
- DP with subsets
    

---

## 3️⃣0️⃣ Meet in the Middle

**Idea:** Split problem in half

**Examples:**

- Subset sum large constraints
    

---

# 🧠 How interviewers expect you to think

1. Start brute force
    
2. Optimize using:
    
    - Sliding window
        
    - Hashing
        
    - DP
        
    - Binary search
        
3. Explain trade-offs
    

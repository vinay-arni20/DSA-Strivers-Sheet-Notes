# Amazon 2026 SDE Internship - Complete LeetCode Problem List by Round

## ROUND 1: WRITTEN TEST (Online Assessment) - November 3-4, 2025

### Problem Categories and LeetCode Links

---

## EASY PROBLEMS - Foundation (Must Master All)

### Arrays & Hashing

1. **Two Sum**
   - LeetCode: https://leetcode.com/problems/two-sum/
   - Difficulty: Easy
   - Time: O(n), Space: O(n)
   - Pattern: Hashing
   - 
   ```cpp
   class Solution {
   public:
       vector<int> twoSum(vector<int>& nums, int target) {
           unordered_map<int, int> ump;
   
           for(int i = 0; i < nums.size(); ++i){
               
               if(ump.find(target - nums[i]) != ump.end()){
                   return {ump[target - nums[i]], i};
               }
               
               ump[nums[i]] = i;
   
           }
           return {};
       }
           
   };
   ```
   
   - Why: Foundation for all array problems

2. **Majority Element**
   - LeetCode: https://leetcode.com/problems/majority-element/
   - Difficulty: Easy
   - Time: O(n), Space: O(1)
   - Pattern: Array Manipulation
   - Why: Voting algorithm

3. **Best Time to Buy and Sell Stock**
   - LeetCode: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/
   - Difficulty: Easy
   - Time: O(n), Space: O(1)
   - Pattern: Single Pass
   - Why: Greedy approach foundation

4. **Merge Sorted Array**
   - LeetCode: https://leetcode.com/problems/merge-sorted-array/
   - Difficulty: Easy
   - Time: O(n+m), Space: O(1)
   - Pattern: Two Pointers
   - Why: Merging logic

5. **First Unique Character in a String**
   - LeetCode: https://leetcode.com/problems/first-unique-character-in-a-string/
   - Difficulty: Easy
   - Time: O(n), Space: O(1)
   - Pattern: Hashing
   - Why: Character frequency counting

6. **Valid Palindrome**
   - LeetCode: https://leetcode.com/problems/valid-palindrome/
   - Difficulty: Easy
   - Time: O(n), Space: O(1)
   - Pattern: Two Pointers
   - Why: String validation

### Trees

7. **Maximum Depth of Binary Tree**
   - LeetCode: https://leetcode.com/problems/maximum-depth-of-binary-tree/
   - Difficulty: Easy
   - Time: O(n), Space: O(h)
   - Pattern: DFS
   - Why: Basic tree recursion

8. **Same Tree**
   - LeetCode: https://leetcode.com/problems/same-tree/
   - Difficulty: Easy
   - Time: O(n), Space: O(h)
   - Pattern: Tree Comparison
   - Why: Tree structure comparison

9. **Symmetric Tree**
   - LeetCode: https://leetcode.com/problems/symmetric-tree/
   - Difficulty: Easy
   - Time: O(n), Space: O(h)
   - Pattern: Tree Symmetry
   - Why: Mirror tree check

10. **Diameter of Binary Tree**
    - LeetCode: https://leetcode.com/problems/diameter-of-binary-tree/
    - Difficulty: Easy
    - Time: O(n), Space: O(h)
    - Pattern: DFS
    - Why: Tree path finding

### Linked Lists

11. **Reverse Linked List**
    - LeetCode: https://leetcode.com/problems/reverse-linked-list/
    - Difficulty: Easy
    - Time: O(n), Space: O(1)
    - Pattern: Pointer Manipulation
    - Why: Linked list foundation

12. **Merge Two Sorted Lists**
    - LeetCode: https://leetcode.com/problems/merge-two-sorted-lists/
    - Difficulty: Easy
    - Time: O(n+m), Space: O(1)
    - Pattern: List Merging
    - Why: Merge operations

13. **Palindrome Linked List**
    - LeetCode: https://leetcode.com/problems/palindrome-linked-list/
    - Difficulty: Easy
    - Time: O(n), Space: O(1)
    - Pattern: Fast/Slow Pointers
    - Why: Linked list traversal

### Stack & Queue

14. **Valid Parentheses**
    - LeetCode: https://leetcode.com/problems/valid-parentheses/
    - Difficulty: Easy
    - Time: O(n), Space: O(n)
    - Pattern: Stack
    - Why: Stack foundation

15. **Min Stack**
    - LeetCode: https://leetcode.com/problems/min-stack/
    - Difficulty: Easy
    - Time: O(1), Space: O(n)
    - Pattern: Stack Design
    - Why: Auxiliary data structure

### Dynamic Programming

16. **Climbing Stairs**
    - LeetCode: https://leetcode.com/problems/climbing-stairs/
    - Difficulty: Easy
    - Time: O(n), Space: O(n)
    - Pattern: DP
    - Why: DP foundation

17. **House Robber**
    - LeetCode: https://leetcode.com/problems/house-robber/
    - Difficulty: Easy
    - Time: O(n), Space: O(1)
    - Pattern: DP
    - Why: DP optimization

### Graphs

18. **Flood Fill**
    - LeetCode: https://leetcode.com/problems/flood-fill/
    - Difficulty: Easy
    - Time: O(n*m), Space: O(n*m)
    - Pattern: DFS/BFS on Grid
    - Why: 2D grid traversal

---

## MEDIUM PROBLEMS - Core Focus (Must Solve All 30)

### Priority 1 - Very High Frequency (Solve First)

1. **Number of Islands** ⭐⭐⭐
   - LeetCode: https://leetcode.com/problems/number-of-islands/
   - Difficulty: Medium
   - Time: O(m*n), Space: O(m*n)
   - Pattern: Graph DFS/BFS
   - Frequency: Very High

2. **LRU Cache** ⭐⭐⭐
   - LeetCode: https://leetcode.com/problems/lru-cache/
   - Difficulty: Medium
   - Time: O(1), Space: O(capacity)
   - Pattern: Design + Data Structure
   - Frequency: Very High

3. **Merge Intervals** ⭐⭐⭐
   - LeetCode: https://leetcode.com/problems/merge-intervals/
   - Difficulty: Medium
   - Time: O(n log n), Space: O(1)
   - Pattern: Sorting + Greedy
   - Frequency: Very High

4. **Longest Substring Without Repeating Characters** ⭐⭐⭐
   - LeetCode: https://leetcode.com/problems/longest-substring-without-repeating-characters/
   - Difficulty: Medium
   - Time: O(n), Space: O(min(n, charset))
   - Pattern: Sliding Window
   - Frequency: Very High

5. **Subarray Sum Equals K** ⭐⭐⭐
   - LeetCode: https://leetcode.com/problems/subarray-sum-equals-k/
   - Difficulty: Medium
   - Time: O(n), Space: O(n)
   - Pattern: Prefix Sum + Hashing
   - Frequency: Very High

### Priority 2 - High Frequency (Solve Next)

6. **Group Anagrams** ⭐⭐
   - LeetCode: https://leetcode.com/problems/group-anagrams/
   - Difficulty: Medium
   - Time: O(n*k log k), Space: O(n*k)
   - Pattern: Hashing + Sorting
   - Frequency: High

7. **Top K Frequent Elements** ⭐⭐
   - LeetCode: https://leetcode.com/problems/top-k-frequent-elements/
   - Difficulty: Medium
   - Time: O(n log k), Space: O(n)
   - Pattern: Heap
   - Frequency: High

8. **Course Schedule** ⭐⭐
   - LeetCode: https://leetcode.com/problems/course-schedule/
   - Difficulty: Medium
   - Time: O(V+E), Space: O(V+E)
   - Pattern: Topological Sort + Cycle Detection
   - Frequency: High

9. **3Sum** ⭐⭐
   - LeetCode: https://leetcode.com/problems/3sum/
   - Difficulty: Medium
   - Time: O(n²), Space: O(1)
   - Pattern: Two Pointers
   - Frequency: High

10. **Product of Array Except Self** ⭐⭐
    - LeetCode: https://leetcode.com/problems/product-of-array-except-self/
    - Difficulty: Medium
    - Time: O(n), Space: O(n)
    - Pattern: Prefix/Suffix
    - Frequency: High

11. **Binary Tree Level Order Traversal** ⭐⭐
    - LeetCode: https://leetcode.com/problems/binary-tree-level-order-traversal/
    - Difficulty: Medium
    - Time: O(n), Space: O(w)
    - Pattern: BFS/Queue
    - Frequency: High

12. **Rotting Oranges** ⭐⭐
    - LeetCode: https://leetcode.com/problems/rotting-oranges/
    - Difficulty: Medium
    - Time: O(m*n), Space: O(m*n)
    - Pattern: Multi-source BFS
    - Frequency: High

13. **Validate Binary Search Tree**
    - LeetCode: https://leetcode.com/problems/validate-binary-search-tree/
    - Difficulty: Medium
    - Time: O(n), Space: O(h)
    - Pattern: Tree Validation
    - Frequency: Medium

14. **Lowest Common Ancestor of Binary Tree**
    - LeetCode: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/
    - Difficulty: Medium
    - Time: O(n), Space: O(h)
    - Pattern: Tree Recursion
    - Frequency: Medium

15. **Coin Change**
    - LeetCode: https://leetcode.com/problems/coin-change/
    - Difficulty: Medium
    - Time: O(n*amount), Space: O(amount)
    - Pattern: DP/BFS
    - Frequency: Medium-High

16. **Word Break**
    - LeetCode: https://leetcode.com/problems/word-break/
    - Difficulty: Medium
    - Time: O(n²), Space: O(n)
    - Pattern: DP + String
    - Frequency: Medium

17. **Course Schedule II** (Topological Sort)
    - LeetCode: https://leetcode.com/problems/course-schedule-ii/
    - Difficulty: Medium
    - Time: O(V+E), Space: O(V+E)
    - Pattern: Topological Sort
    - Frequency: Medium

18. **Copy List with Random Pointer**
    - LeetCode: https://leetcode.com/problems/copy-list-with-random-pointer/
    - Difficulty: Medium
    - Time: O(n), Space: O(n)
    - Pattern: Linked List + HashMap
    - Frequency: Medium

19. **Trapping Rain Water**
    - LeetCode: https://leetcode.com/problems/trapping-rain-water/
    - Difficulty: Hard
    - Time: O(n), Space: O(1)
    - Pattern: Two Pointers/Stack
    - Frequency: Medium

20. **Merge K Sorted Lists**
    - LeetCode: https://leetcode.com/problems/merge-k-sorted-lists/
    - Difficulty: Hard
    - Time: O(n log k), Space: O(k)
    - Pattern: Heap + Linked List
    - Frequency: Medium

21. **Binary Tree Right Side View**
    - LeetCode: https://leetcode.com/problems/binary-tree-right-side-view/
    - Difficulty: Medium
    - Time: O(n), Space: O(w)
    - Pattern: BFS/DFS
    - Frequency: Medium

22. **Task Scheduler**
    - LeetCode: https://leetcode.com/problems/task-scheduler/
    - Difficulty: Medium
    - Time: O(n), Space: O(1)
    - Pattern: Greedy + Simulation
    - Frequency: Medium

23. **Kth Largest Element in Array**
    - LeetCode: https://leetcode.com/problems/kth-largest-element-in-an-array/
    - Difficulty: Medium
    - Time: O(n log k), Space: O(k)
    - Pattern: Heap/QuickSelect
    - Frequency: Medium

24. **Letter Combinations of Phone Number**
    - LeetCode: https://leetcode.com/problems/letter-combinations-of-a-phone-number/
    - Difficulty: Medium
    - Time: O(4ⁿ), Space: O(4ⁿ)
    - Pattern: Backtracking
    - Frequency: Low-Medium

25. **Best Time to Buy and Sell Stock II**
    - LeetCode: https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/
    - Difficulty: Medium
    - Time: O(n), Space: O(1)
    - Pattern: Greedy
    - Frequency: Medium

26. **Reorganize String**
    - LeetCode: https://leetcode.com/problems/reorganize-string/
    - Difficulty: Medium
    - Time: O(n log n), Space: O(n)
    - Pattern: Greedy + Heap
    - Frequency: Low-Medium

27. **K Closest Points to Origin**
    - LeetCode: https://leetcode.com/problems/k-closest-points-to-origin/
    - Difficulty: Medium
    - Time: O(n log k), Space: O(k)
    - Pattern: Heap
    - Frequency: Medium

28. **Remove Nth Node from End of List**
    - LeetCode: https://leetcode.com/problems/remove-nth-node-from-end-of-list/
    - Difficulty: Medium
    - Time: O(n), Space: O(1)
    - Pattern: Linked List + Two Pointers
    - Frequency: Medium

29. **3Sum Closest**
    - LeetCode: https://leetcode.com/problems/3sum-closest/
    - Difficulty: Medium
    - Time: O(n²), Space: O(1)
    - Pattern: Two Pointers + Sorting
    - Frequency: Low-Medium

30. **Surrounded Regions**
    - LeetCode: https://leetcode.com/problems/surrounded-regions/
    - Difficulty: Medium
    - Time: O(m*n), Space: O(m*n)
    - Pattern: DFS/BFS
    - Frequency: Low-Medium

---

## HARD PROBLEMS - Practice If Time Permits

### Hard Level Problems for Extra Preparation

1. **Median of Two Sorted Arrays**
   - LeetCode: https://leetcode.com/problems/median-of-two-sorted-arrays/
   - Difficulty: Hard
   - Time: O(log(min(n,m))), Space: O(1)
   - Pattern: Binary Search

2. **Minimum Window Substring**
   - LeetCode: https://leetcode.com/problems/minimum-window-substring/
   - Difficulty: Hard
   - Time: O(n), Space: O(charset)
   - Pattern: Sliding Window + Hashing

3. **LFU Cache**
   - LeetCode: https://leetcode.com/problems/lfu-cache/
   - Difficulty: Hard
   - Time: O(1), Space: O(capacity)
   - Pattern: Design + Data Structure

4. **Largest Rectangle in Histogram**
   - LeetCode: https://leetcode.com/problems/largest-rectangle-in-histogram/
   - Difficulty: Hard
   - Time: O(n), Space: O(n)
   - Pattern: Stack

5. **Sliding Window Maximum**
   - LeetCode: https://leetcode.com/problems/sliding-window-maximum/
   - Difficulty: Hard
   - Time: O(n), Space: O(k)
   - Pattern: Deque

6. **Word Ladder**
   - LeetCode: https://leetcode.com/problems/word-ladder/
   - Difficulty: Hard
   - Time: O(n*L²), Space: O(n*L)
   - Pattern: BFS

7. **Alien Dictionary**
   - LeetCode: https://leetcode.com/problems/alien-dictionary/
   - Difficulty: Hard
   - Time: O(V+E), Space: O(1)
   - Pattern: Topological Sort

8. **Regular Expression Matching**
   - LeetCode: https://leetcode.com/problems/regular-expression-matching/
   - Difficulty: Hard
   - Time: O(n*m), Space: O(n*m)
   - Pattern: DP

---

# ROUND 2: TECHNICAL INTERVIEWS - 2-3 Rounds

## Round 2 consists of 2-3 technical interview rounds, each with 2 coding problems

### Technical Round 2.1 - Focus: Arrays, Trees, Graphs

**Problems to Review (All from Round 1 Medium List):**

1. Number of Islands
2. Merge Intervals
3. Group Anagrams
4. 3Sum
5. Product of Array Except Self
6. Binary Tree Level Order Traversal
7. Validate Binary Search Tree
8. Lowest Common Ancestor of Binary Tree
9. Binary Tree Right Side View
10. Course Schedule
11. Rotting Oranges
12. Trapping Rain Water

**New Additional Problems for Round 2:**

13. **Reconstruct Itinerary**
    - LeetCode: https://leetcode.com/problems/reconstruct-itinerary/
    - Difficulty: Hard
    - Time: O(E log E), Space: O(V+E)
    - Pattern: DFS + Graph

14. **Number of Connected Components in Undirected Graph**
    - LeetCode: https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/
    - Difficulty: Medium
    - Time: O(V+E), Space: O(V)
    - Pattern: Union-Find/DFS

15. **Graph Valid Tree**
    - LeetCode: https://leetcode.com/problems/graph-valid-tree/
    - Difficulty: Medium
    - Time: O(V+E), Space: O(V)
    - Pattern: DFS/Union-Find

16. **Pacific Atlantic Water Flow**
    - LeetCode: https://leetcode.com/problems/pacific-atlantic-water-flow/
    - Difficulty: Medium
    - Time: O(m*n), Space: O(m*n)
    - Pattern: DFS/BFS on Grid

17. **Walls and Gates**
    - LeetCode: https://leetcode.com/problems/walls-and-gates/
    - Difficulty: Medium
    - Time: O(m*n), Space: O(m*n)
    - Pattern: Multi-source BFS

18. **Invert Binary Tree**
    - LeetCode: https://leetcode.com/problems/invert-binary-tree/
    - Difficulty: Easy
    - Time: O(n), Space: O(h)
    - Pattern: Tree Recursion

19. **Path Sum**
    - LeetCode: https://leetcode.com/problems/path-sum/
    - Difficulty: Easy
    - Time: O(n), Space: O(h)
    - Pattern: Tree DFS

20. **Binary Tree Maximum Path Sum**
    - LeetCode: https://leetcode.com/problems/binary-tree-maximum-path-sum/
    - Difficulty: Hard
    - Time: O(n), Space: O(h)
    - Pattern: Tree DFS

### Technical Round 2.2 - Focus: String, DP, Hashing

**Problems to Review:**

1. Longest Substring Without Repeating Characters
2. Subarray Sum Equals K
3. Coin Change
4. Word Break
5. Top K Frequent Elements
6. Task Scheduler
7. Reorganize String

**New Additional Problems:**

8. **Longest Increasing Subsequence**
   - LeetCode: https://leetcode.com/problems/longest-increasing-subsequence/
   - Difficulty: Medium
   - Time: O(n log n), Space: O(n)
   - Pattern: DP/Binary Search

9. **Longest Palindromic Substring**
   - LeetCode: https://leetcode.com/problems/longest-palindromic-substring/
   - Difficulty: Medium
   - Time: O(n²), Space: O(1)
   - Pattern: DP/Expand Around

10. **Edit Distance**
    - LeetCode: https://leetcode.com/problems/edit-distance/
    - Difficulty: Hard
    - Time: O(n*m), Space: O(n*m)
    - Pattern: DP

11. **Distinct Subsequences**
    - LeetCode: https://leetcode.com/problems/distinct-subsequences/
    - Difficulty: Hard
    - Time: O(n*m), Space: O(n*m)
    - Pattern: DP

12. **Maximum Subarray**
    - LeetCode: https://leetcode.com/problems/maximum-subarray/
    - Difficulty: Easy
    - Time: O(n), Space: O(1)
    - Pattern: Kadane's Algorithm

13. **Contains Duplicate**
    - LeetCode: https://leetcode.com/problems/contains-duplicate/
    - Difficulty: Easy
    - Time: O(n), Space: O(n)
    - Pattern: Hashing

14. **Contains Duplicate II**
    - LeetCode: https://leetcode.com/problems/contains-duplicate-ii/
    - Difficulty: Easy
    - Time: O(n), Space: O(min(n, k))
    - Pattern: Sliding Window + Hashing

15. **Valid Anagram**
    - LeetCode: https://leetcode.com/problems/valid-anagram/
    - Difficulty: Easy
    - Time: O(n), Space: O(1)
    - Pattern: Hashing

### Technical Round 2.3 (if applicable) - Focus: Advanced & Mixed

**Problems to Review (All from Round 1):**

1. LRU Cache
2. Merge K Sorted Lists
3. Trapping Rain Water
4. Minimum Window Substring
5. Course Schedule

**New Additional Problems:**

6. **4Sum**
   - LeetCode: https://leetcode.com/problems/4sum/
   - Difficulty: Medium
   - Time: O(n³), Space: O(1)
   - Pattern: Two Pointers

7. **Sort List**
   - LeetCode: https://leetcode.com/problems/sort-list/
   - Difficulty: Medium
   - Time: O(n log n), Space: O(log n)
   - Pattern: Merge Sort on Linked List

8. **Reorder List**
   - LeetCode: https://leetcode.com/problems/reorder-list/
   - Difficulty: Medium
   - Time: O(n), Space: O(1)
   - Pattern: Linked List

9. **Spiral Matrix**
   - LeetCode: https://leetcode.com/problems/spiral-matrix/
   - Difficulty: Medium
   - Time: O(m*n), Space: O(1)
   - Pattern: 2D Array Traversal

10. **Rotate Matrix**
    - LeetCode: https://leetcode.com/problems/rotate-image/
    - Difficulty: Medium
    - Time: O(m*n), Space: O(1)
    - Pattern: 2D Array Manipulation

11. **Search in Rotated Sorted Array**
    - LeetCode: https://leetcode.com/problems/search-in-rotated-sorted-array/
    - Difficulty: Medium
    - Time: O(log n), Space: O(1)
    - Pattern: Binary Search

12. **Find Minimum in Rotated Sorted Array**
    - LeetCode: https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/
    - Difficulty: Medium
    - Time: O(log n), Space: O(1)
    - Pattern: Binary Search

13. **Search a 2D Matrix**
    - LeetCode: https://leetcode.com/problems/search-a-2d-matrix/
    - Difficulty: Medium
    - Time: O(log(m*n)), Space: O(1)
    - Pattern: Binary Search

14. **Longest Common Subsequence**
    - LeetCode: https://leetcode.com/problems/longest-common-subsequence/
    - Difficulty: Medium
    - Time: O(n*m), Space: O(n*m)
    - Pattern: DP

15. **Maximum Subarray Sum with One Deletion**
    - LeetCode: https://leetcode.com/problems/maximum-subarray-sum-with-one-deletion/
    - Difficulty: Medium
    - Time: O(n), Space: O(1)
    - Pattern: DP

---

# ROUND 3: FINAL TECHNICAL INTERVIEW (if applicable) - Advanced Topics

## Round 3 focuses on harder problems, system design basics, and advanced data structures

### Advanced DP Problems

1. **Unique Paths**
   - LeetCode: https://leetcode.com/problems/unique-paths/
   - Difficulty: Medium
   - Time: O(m*n), Space: O(m*n)
   - Pattern: DP

2. **Unique Paths II**
   - LeetCode: https://leetcode.com/problems/unique-paths-ii/
   - Difficulty: Medium
   - Time: O(m*n), Space: O(m*n)
   - Pattern: DP

3. **Minimum Path Sum**
   - LeetCode: https://leetcode.com/problems/minimum-path-sum/
   - Difficulty: Medium
   - Time: O(m*n), Space: O(m*n)
   - Pattern: DP

4. **Jump Game**
   - LeetCode: https://leetcode.com/problems/jump-game/
   - Difficulty: Medium
   - Time: O(n), Space: O(1)
   - Pattern: Greedy/DP

5. **Jump Game II**
   - LeetCode: https://leetcode.com/problems/jump-game-ii/
   - Difficulty: Hard
   - Time: O(n), Space: O(1)
   - Pattern: Greedy

6. **Decode Ways**
   - LeetCode: https://leetcode.com/problems/decode-ways/
   - Difficulty: Medium
   - Time: O(n), Space: O(n)
   - Pattern: DP

7. **Palindrome Partitioning**
   - LeetCode: https://leetcode.com/problems/palindrome-partitioning/
   - Difficulty: Medium
   - Time: O(2ⁿ), Space: O(2ⁿ)
   - Pattern: Backtracking

8. **Word Ladder II**
   - LeetCode: https://leetcode.com/problems/word-ladder-ii/
   - Difficulty: Hard
   - Time: O(n*L*2ⁿ), Space: O(n*L*2ⁿ)
   - Pattern: BFS + Backtracking

### Advanced Graph Problems

9. **Topological Sort (Kahn's Algorithm)**
   - LeetCode: https://leetcode.com/problems/course-schedule/
   - Difficulty: Medium
   - Time: O(V+E), Space: O(V)
   - Pattern: Topological Sort

10. **Network Delay Time**
    - LeetCode: https://leetcode.com/problems/network-delay-time/
    - Difficulty: Medium
    - Time: O((V+E) log V), Space: O(V+E)
    - Pattern: Dijkstra's Algorithm

11. **Accounts Merge**
    - LeetCode: https://leetcode.com/problems/accounts-merge/
    - Difficulty: Hard
    - Time: O(n log n), Space: O(n)
    - Pattern: Union-Find/DFS

12. **Number of Islands II**
    - LeetCode: https://leetcode.com/problems/number-of-islands-ii/
    - Difficulty: Hard
    - Time: O(m*n*α), Space: O(m*n)
    - Pattern: Union-Find

13. **Redundant Connection**
    - LeetCode: https://leetcode.com/problems/redundant-connection/
    - Difficulty: Medium
    - Time: O(n*α), Space: O(n)
    - Pattern: Union-Find

14. **Implement Trie (Prefix Tree)**
    - LeetCode: https://leetcode.com/problems/implement-trie-prefix-tree/
    - Difficulty: Medium
    - Time: O(m), Space: O(alphabet_size * n)
    - Pattern: Trie Data Structure

15. **Word Search II**
    - LeetCode: https://leetcode.com/problems/word-search-ii/
    - Difficulty: Hard
    - Time: O(n*m*4ⁿ), Space: O(n)
    - Pattern: Trie + DFS

### Advanced Linked List Problems

16. **LRU Cache (Already in Round 1)**
    - Reference for Round 3 testing

17. **Reverse Nodes in K-Group**
    - LeetCode: https://leetcode.com/problems/reverse-nodes-in-k-group/
    - Difficulty: Hard
    - Time: O(n), Space: O(1)
    - Pattern: Linked List Manipulation

18. **Add Two Numbers**
    - LeetCode: https://leetcode.com/problems/add-two-numbers/
    - Difficulty: Medium
    - Time: O(max(m,n)), Space: O(1)
    - Pattern: Linked List

19. **Add Two Numbers II**
    - LeetCode: https://leetcode.com/problems/add-two-numbers-ii/
    - Difficulty: Medium
    - Time: O(max(m,n)), Space: O(max(m,n))
    - Pattern: Linked List + Stack

### Advanced Array Problems

20. **Trapping Rain Water** (Already in Round 1)
    - Reference for more advanced follow-ups

21. **Largest Rectangle in Histogram** (Already mentioned)
    - Reference for advanced testing

22. **Maximal Rectangle**
    - LeetCode: https://leetcode.com/problems/maximal-rectangle/
    - Difficulty: Hard
    - Time: O(m*n), Space: O(n)
    - Pattern: DP + Histogram

23. **The Skyline Problem**
    - LeetCode: https://leetcode.com/problems/the-skyline-problem/
    - Difficulty: Hard
    - Time: O(n log n), Space: O(n)
    - Pattern: Sweep Line Algorithm

24. **Meeting Rooms**
    - LeetCode: https://leetcode.com/problems/meeting-rooms/
    - Difficulty: Easy
    - Time: O(n log n), Space: O(1)
    - Pattern: Sorting

25. **Meeting Rooms II**
    - LeetCode: https://leetcode.com/problems/meeting-rooms-ii/
    - Difficulty: Medium
    - Time: O(n log n), Space: O(n)
    - Pattern: Heap

### Advanced Backtracking Problems

26. **Permutations**
    - LeetCode: https://leetcode.com/problems/permutations/
    - Difficulty: Medium
    - Time: O(n!), Space: O(n!)
    - Pattern: Backtracking

27. **Permutations II**
    - LeetCode: https://leetcode.com/problems/permutations-ii/
    - Difficulty: Medium
    - Time: O(n!), Space: O(n!)
    - Pattern: Backtracking

28. **Combinations**
    - LeetCode: https://leetcode.com/problems/combinations/
    - Difficulty: Medium
    - Time: O(C(n,k)), Space: O(C(n,k))
    - Pattern: Backtracking

29. **N-Queens**
    - LeetCode: https://leetcode.com/problems/n-queens/
    - Difficulty: Hard
    - Time: O(n!), Space: O(n²)
    - Pattern: Backtracking

30. **Sudoku Solver**
    - LeetCode: https://leetcode.com/problems/sudoku-solver/
    - Difficulty: Hard
    - Time: O(9^(n*n)), Space: O(n²)
    - Pattern: Backtracking

---

## SUMMARY - STUDY SEQUENCE

### Phase 1: ROUND 1 Preparation (Oct 31 - Nov 2)
**Total Problems to Solve: 48 (18 Easy + 30 Medium)**

1. Master all 18 easy problems
2. Solve all 30 medium priority 1 and 2 problems
3. Do 2-3 timed mock tests

### Phase 2: ROUND 2 Preparation (If Shortlisted)
**Total Additional Problems: 35**

1. Solve 12-15 problems per technical round (3 rounds total)
2. Deep understanding of all patterns
3. Focus on communication and optimization

### Phase 3: ROUND 3 Preparation (If Progressed)
**Total Additional Problems: 30**

1. Advanced DP problems (8)
2. Advanced Graph problems (7)
3. Advanced Linked List problems (4)
4. Advanced Array problems (6)
5. Advanced Backtracking problems (5)

---

## TIPS FOR EFFECTIVE PRACTICE

1. **Solve in Order:** Start with easy, progress to medium, then hard
2. **Understand Pattern:** Learn 10 patterns deeply rather than 100 problems superficially
3. **Code Multiple Times:** Solve same problem 3-4 times on different days
4. **Explain Out Loud:** Practice explaining solution while coding
5. **Time Yourself:** Always practice under time pressure
6. **Review Mistakes:** Spend time understanding why you failed
7. **Group by Pattern:** Practice similar problems back-to-back

---

## Quick Reference: Most Important 15 Problems

1. Two Sum (https://leetcode.com/problems/two-sum/)
2. Valid Parentheses (https://leetcode.com/problems/valid-parentheses/)
3. Number of Islands (https://leetcode.com/problems/number-of-islands/)
4. LRU Cache (https://leetcode.com/problems/lru-cache/)
5. Merge Intervals (https://leetcode.com/problems/merge-intervals/)
6. Group Anagrams (https://leetcode.com/problems/group-anagrams/)
7. Top K Frequent Elements (https://leetcode.com/problems/top-k-frequent-elements/)
8. Course Schedule (https://leetcode.com/problems/course-schedule/)
9. Subarray Sum Equals K (https://leetcode.com/problems/subarray-sum-equals-k/)
10. Longest Substring Without Repeating (https://leetcode.com/problems/longest-substring-without-repeating-characters/)
11. 3Sum (https://leetcode.com/problems/3sum/)
12. Product of Array Except Self (https://leetcode.com/problems/product-of-array-except-self/)
13. Merge K Sorted Lists (https://leetcode.com/problems/merge-k-sorted-lists/)
14. Rotting Oranges (https://leetcode.com/problems/rotting-oranges/)
15. Coin Change (https://leetcode.com/problems/coin-change/)

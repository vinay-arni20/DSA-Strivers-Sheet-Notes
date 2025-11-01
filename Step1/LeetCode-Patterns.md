# 🚀 **LeetCode Patterns & Problem-Solving Guide**

## 📌 **Complete DSA Patterns to Crack Any Coding Interview**

---

## **Table of Contents**

1. [Two Pointers](#1-two-pointers)
2. [Sliding Window](#2-sliding-window)
3. [Fast & Slow Pointers](#3-fast--slow-pointers)
4. [Merge Intervals](#4-merge-intervals)
5. [Cyclic Sort](#5-cyclic-sort)
6. [In-place Reversal of LinkedList](#6-in-place-reversal-of-linkedlist)
7. [Binary Search](#7-binary-search)
8. [Top K Elements (Heap)](#8-top-k-elements-heap)
9. [K-way Merge](#9-k-way-merge)
10. [Dynamic Programming Patterns](#10-dynamic-programming-patterns)
11. [Backtracking](#11-backtracking)
12. [Graph Patterns (BFS/DFS)](#12-graph-patterns-bfsdfs)
13. [Tree Patterns](#13-tree-patterns)
14. [Trie](#14-trie)
15. [Monotonic Stack/Queue](#15-monotonic-stackqueue)
16. [Bit Manipulation](#16-bit-manipulation)
17. [Math & Number Theory](#17-math--number-theory)
18. [Greedy Algorithms](#18-greedy-algorithms)
19. [Union Find (Disjoint Set)](#19-union-find-disjoint-set)
20. [Advanced Patterns](#20-advanced-patterns)

---

## **1. Two Pointers**

### **Pattern Recognition:**
- Sorted array/list
- Need to find pairs/triplets
- Remove duplicates
- Compare elements from both ends

### **Template:**

```cpp
int left = 0, right = n - 1;
while (left < right) {
    if (condition) {
        // Process
        left++;
        right--;
    } else if (sum < target) {
        left++;
    } else {
        right--;
    }
}
```

### **Problems:**

| # | Problem | Difficulty | Pattern |
|---|---------|------------|---------|
| 1 | Two Sum II (LeetCode #167) | Easy | Opposite Direction |
| 2 | 3Sum (LeetCode #15) | Medium | Fixed + Two Pointers |
| 3 | Container With Most Water (LeetCode #11) | Medium | Opposite Direction |
| 4 | Remove Duplicates (LeetCode #26) | Easy | Same Direction |
| 5 | Valid Palindrome (LeetCode #125) | Easy | Opposite Direction |
| 6 | Trapping Rain Water (LeetCode #42) | Hard | Two Pass |

### **Example: Two Sum II**

```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    
    while (left < right) {
        int sum = nums[left] + nums[right];
        if (sum == target) {
            return {left + 1, right + 1};
        } else if (sum < target) {
            left++;
        } else {
            right--;
        }
    }
    return {};
}
```

---

## **2. Sliding Window**

### **Pattern Recognition:**
- Contiguous subarray/substring
- Maximum/minimum/longest/shortest
- Fixed or variable window size

### **Template (Variable Window):**

```cpp
int left = 0, result = 0;
unordered_map<char, int> freq;

for (int right = 0; right < n; right++) {
    // Expand window
    freq[s[right]]++;
    
    // Shrink window if invalid
    while (window_invalid) {
        freq[s[left]]--;
        left++;
    }
    
    // Update result
    result = max(result, right - left + 1);
}
```

### **Problems:**

| # | Problem | Difficulty | Window Type |
|---|---------|------------|-------------|
| 1 | Max Consecutive Ones III (LeetCode #1004) | Medium | Variable |
| 2 | Longest Substring Without Repeating (LeetCode #3) | Medium | Variable |
| 3 | Minimum Window Substring (LeetCode #76) | Hard | Variable |
| 4 | Max Sum Subarray of Size K | Easy | Fixed |
| 5 | Longest Repeating Character Replacement (LeetCode #424) | Medium | Variable |
| 6 | Permutation in String (LeetCode #567) | Medium | Fixed |
| 7 | Sliding Window Maximum (LeetCode #239) | Hard | Fixed + Deque |

### **Example: Longest Substring Without Repeating Characters**

```cpp
int lengthOfLongestSubstring(string s) {
    unordered_map<char, int> freq;
    int left = 0, maxLen = 0;
    
    for (int right = 0; right < s.size(); right++) {
        freq[s[right]]++;
        
        while (freq[s[right]] > 1) {
            freq[s[left]]--;
            left++;
        }
        
        maxLen = max(maxLen, right - left + 1);
    }
    return maxLen;
}
```

---

## **3. Fast & Slow Pointers**

### **Pattern Recognition:**
- Cycle detection in LinkedList
- Middle of LinkedList
- Palindrome LinkedList
- Happy Number

### **Template:**

```cpp
ListNode* slow = head;
ListNode* fast = head;

while (fast && fast->next) {
    slow = slow->next;
    fast = fast->next->next;
    
    if (slow == fast) {
        // Cycle detected
        break;
    }
}
```

### **Problems:**

| # | Problem | Difficulty | Use Case |
|---|---------|------------|----------|
| 1 | Linked List Cycle (LeetCode #141) | Easy | Cycle Detection |
| 2 | Find Cycle Start (LeetCode #142) | Medium | Cycle Start |
| 3 | Happy Number (LeetCode #202) | Easy | Cycle Detection |
| 4 | Middle of LinkedList (LeetCode #876) | Easy | Find Middle |
| 5 | Palindrome LinkedList (LeetCode #234) | Easy | Reverse + Compare |
| 6 | Reorder List (LeetCode #143) | Medium | Find Middle + Reverse |

### **Example: Linked List Cycle**

```cpp
bool hasCycle(ListNode *head) {
    ListNode* slow = head;
    ListNode* fast = head;
    
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
        if (slow == fast) return true;
    }
    return false;
}
```

---

## **4. Merge Intervals**

### **Pattern Recognition:**
- Overlapping intervals
- Insert/merge/remove intervals
- Find conflicts

### **Template:**

```cpp
sort(intervals.begin(), intervals.end());
vector<vector<int>> result;

for (auto& interval : intervals) {
    if (result.empty() || result.back()[1] < interval[0]) {
        result.push_back(interval);
    } else {
        result.back()[1] = max(result.back()[1], interval[1]);
    }
}
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Merge Intervals (LeetCode #56) | Medium |
| 2 | Insert Interval (LeetCode #57) | Medium |
| 3 | Interval List Intersections (LeetCode #986) | Medium |
| 4 | Meeting Rooms (LeetCode #252) | Easy |
| 5 | Meeting Rooms II (LeetCode #253) | Medium |
| 6 | Non-overlapping Intervals (LeetCode #435) | Medium |

---

## **5. Cyclic Sort**

### **Pattern Recognition:**
- Array contains numbers in range [1, n]
- Find missing/duplicate numbers
- Numbers should be at index = number - 1

### **Template:**

```cpp
for (int i = 0; i < nums.size(); i++) {
    while (nums[i] != i + 1 && nums[i] != nums[nums[i] - 1]) {
        swap(nums[i], nums[nums[i] - 1]);
    }
}
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Missing Number (LeetCode #268) | Easy |
| 2 | Find All Duplicates (LeetCode #442) | Medium |
| 3 | Find Duplicate Number (LeetCode #287) | Medium |
| 4 | First Missing Positive (LeetCode #41) | Hard |
| 5 | Find All Missing Numbers (LeetCode #448) | Medium |

---

## **6. In-place Reversal of LinkedList**

### **Pattern Recognition:**
- Reverse entire or part of LinkedList
- No extra space

### **Template:**

```cpp
ListNode* reverse(ListNode* head) {
    ListNode* prev = nullptr;
    ListNode* curr = head;
    
    while (curr) {
        ListNode* next = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next;
    }
    return prev;
}
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Reverse Linked List (LeetCode #206) | Easy |
| 2 | Reverse Linked List II (LeetCode #92) | Medium |
| 3 | Reverse Nodes in k-Group (LeetCode #25) | Hard |
| 4 | Swap Nodes in Pairs (LeetCode #24) | Medium |
| 5 | Palindrome Linked List (LeetCode #234) | Easy |

---

## **7. Binary Search**

### **Pattern Recognition:**
- Sorted array/search space
- Find target/boundary
- Minimize/maximize something

### **Template:**

```cpp
int binarySearch(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;
        
        if (nums[mid] == target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1;
}
```

### **Binary Search Variants:**

#### **1. Find Exact Target**
```cpp
while (left <= right) {
    int mid = left + (right - left) / 2;
    if (nums[mid] == target) return mid;
    else if (nums[mid] < target) left = mid + 1;
    else right = mid - 1;
}
```

#### **2. Find Left Boundary (First Occurrence)**
```cpp
while (left < right) {
    int mid = left + (right - left) / 2;
    if (nums[mid] < target) left = mid + 1;
    else right = mid;
}
```

#### **3. Find Right Boundary (Last Occurrence)**
```cpp
while (left < right) {
    int mid = left + (right - left) / 2 + 1;
    if (nums[mid] > target) right = mid - 1;
    else left = mid;
}
```

### **Problems:**

| # | Problem | Difficulty | Type |
|---|---------|------------|------|
| 1 | Binary Search (LeetCode #704) | Easy | Basic |
| 2 | Search in Rotated Sorted Array (LeetCode #33) | Medium | Modified |
| 3 | Find Peak Element (LeetCode #162) | Medium | Peak Finding |
| 4 | Search 2D Matrix (LeetCode #74) | Medium | 2D Search |
| 5 | Koko Eating Bananas (LeetCode #875) | Medium | Answer Space |
| 6 | Median of Two Sorted Arrays (LeetCode #4) | Hard | Two Arrays |
| 7 | Split Array Largest Sum (LeetCode #410) | Hard | Answer Space |

---

## **8. Top K Elements (Heap)**

### **Pattern Recognition:**
- Find top/smallest/most frequent K elements
- Kth largest/smallest

### **Template:**

```cpp
priority_queue<int, vector<int>, greater<int>> minHeap;  // Min heap

for (int num : nums) {
    minHeap.push(num);
    if (minHeap.size() > k) {
        minHeap.pop();
    }
}
return minHeap.top();  // Kth largest
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Kth Largest Element (LeetCode #215) | Medium |
| 2 | Top K Frequent Elements (LeetCode #347) | Medium |
| 3 | K Closest Points to Origin (LeetCode #973) | Medium |
| 4 | Kth Smallest in Sorted Matrix (LeetCode #378) | Medium |
| 5 | Find Median from Data Stream (LeetCode #295) | Hard |
| 6 | Reorganize String (LeetCode #767) | Medium |

---

## **9. K-way Merge**

### **Pattern Recognition:**
- Merge K sorted lists/arrays
- Find smallest range in K lists

### **Template:**

```cpp
priority_queue<pair<int, pair<int, int>>, 
               vector<pair<int, pair<int, int>>>, 
               greater<>> minHeap;

// Push first element of each list
for (int i = 0; i < k; i++) {
    minHeap.push({lists[i][0], {i, 0}});
}

while (!minHeap.empty()) {
    auto [val, pos] = minHeap.top();
    minHeap.pop();
    // Process
}
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Merge K Sorted Lists (LeetCode #23) | Hard |
| 2 | Kth Smallest in Sorted Matrix (LeetCode #378) | Medium |
| 3 | Smallest Range from K Lists (LeetCode #632) | Hard |
| 4 | Find K Pairs with Smallest Sums (LeetCode #373) | Medium |

---

## **10. Dynamic Programming Patterns**

### **10.1 Linear DP (1D)**

#### **Pattern Recognition:**
- Single sequence/array
- Decision at each step

#### **Template:**
```cpp
vector<int> dp(n + 1);
dp[0] = base_case;

for (int i = 1; i <= n; i++) {
    dp[i] = // recurrence relation
}
```

#### **Problems:**

| # | Problem | Difficulty | Subpattern |
|---|---------|------------|------------|
| 1 | Climbing Stairs (LeetCode #70) | Easy | Fibonacci |
| 2 | House Robber (LeetCode #198) | Medium | Skip Pattern |
| 3 | Coin Change (LeetCode #322) | Medium | Unbounded Knapsack |
| 4 | Longest Increasing Subsequence (LeetCode #300) | Medium | LIS |
| 5 | Word Break (LeetCode #139) | Medium | String DP |
| 6 | Decode Ways (LeetCode #91) | Medium | Partition |

---

### **10.2 Grid DP (2D)**

#### **Pattern Recognition:**
- 2D grid/matrix
- Path counting/optimization

#### **Template:**
```cpp
vector<vector<int>> dp(m, vector<int>(n));
dp[0][0] = base_case;

for (int i = 0; i < m; i++) {
    for (int j = 0; j < n; j++) {
        dp[i][j] = // relation with dp[i-1][j], dp[i][j-1]
    }
}
```

#### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Unique Paths (LeetCode #62) | Medium |
| 2 | Minimum Path Sum (LeetCode #64) | Medium |
| 3 | Maximal Square (LeetCode #221) | Medium |
| 4 | Edit Distance (LeetCode #72) | Hard |
| 5 | Longest Common Subsequence (LeetCode #1143) | Medium |

---

### **10.3 Knapsack Pattern**

#### **0/1 Knapsack Template:**
```cpp
vector<vector<int>> dp(n + 1, vector<int>(capacity + 1, 0));

for (int i = 1; i <= n; i++) {
    for (int w = 0; w <= capacity; w++) {
        if (weight[i-1] <= w) {
            dp[i][w] = max(dp[i-1][w], 
                          value[i-1] + dp[i-1][w - weight[i-1]]);
        } else {
            dp[i][w] = dp[i-1][w];
        }
    }
}
```

#### **Problems:**

| # | Problem | Difficulty | Type |
|---|---------|------------|------|
| 1 | Partition Equal Subset Sum (LeetCode #416) | Medium | 0/1 |
| 2 | Target Sum (LeetCode #494) | Medium | Count |
| 3 | Coin Change II (LeetCode #518) | Medium | Unbounded |
| 4 | Ones and Zeroes (LeetCode #474) | Medium | 2D Knapsack |

---

### **10.4 State Machine DP**

#### **Pattern:** Buy/Sell Stock Problems

```cpp
// Hold stock, don't hold stock
int hold = -prices[0], notHold = 0;

for (int i = 1; i < n; i++) {
    int newHold = max(hold, notHold - prices[i]);
    int newNotHold = max(notHold, hold + prices[i]);
    hold = newHold;
    notHold = newNotHold;
}
```

#### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Best Time to Buy/Sell Stock (LeetCode #121) | Easy |
| 2 | Best Time with Cooldown (LeetCode #309) | Medium |
| 3 | Best Time with Transaction Fee (LeetCode #714) | Medium |
| 4 | Best Time with K Transactions (LeetCode #188) | Hard |

---

### **10.5 Interval DP**

#### **Pattern:** Split array/string into parts

```cpp
vector<vector<int>> dp(n, vector<int>(n, 0));

for (int len = 2; len <= n; len++) {
    for (int i = 0; i <= n - len; i++) {
        int j = i + len - 1;
        dp[i][j] = INT_MAX;
        for (int k = i; k < j; k++) {
            dp[i][j] = min(dp[i][j], dp[i][k] + dp[k+1][j] + cost);
        }
    }
}
```

#### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Burst Balloons (LeetCode #312) | Hard |
| 2 | Minimum Cost to Merge Stones (LeetCode #1000) | Hard |
| 3 | Palindrome Partitioning II (LeetCode #132) | Hard |

---

## **11. Backtracking**

### **Pattern Recognition:**
- Generate all combinations/permutations
- Explore all possibilities
- Decision tree

### **Template:**

```cpp
void backtrack(vector<int>& path, /* other params */) {
    if (base_condition) {
        result.push_back(path);
        return;
    }
    
    for (int i = start; i < n; i++) {
        // Choose
        path.push_back(nums[i]);
        
        // Explore
        backtrack(path, i + 1);
        
        // Unchoose (backtrack)
        path.pop_back();
    }
}
```

### **Problems:**

| # | Problem | Difficulty | Type |
|---|---------|------------|------|
| 1 | Permutations (LeetCode #46) | Medium | Permutation |
| 2 | Combinations (LeetCode #77) | Medium | Combination |
| 3 | Subsets (LeetCode #78) | Medium | Subset |
| 4 | Palindrome Partitioning (LeetCode #131) | Medium | Partition |
| 5 | N-Queens (LeetCode #51) | Hard | Constraint |
| 6 | Sudoku Solver (LeetCode #37) | Hard | Constraint |
| 7 | Word Search (LeetCode #79) | Medium | Grid |
| 8 | Letter Combinations (LeetCode #17) | Medium | Mapping |

---

## **12. Graph Patterns (BFS/DFS)**

### **12.1 BFS Template**

```cpp
queue<int> q;
vector<bool> visited(n, false);
q.push(start);
visited[start] = true;

while (!q.empty()) {
    int node = q.front();
    q.pop();
    
    for (int neighbor : graph[node]) {
        if (!visited[neighbor]) {
            visited[neighbor] = true;
            q.push(neighbor);
        }
    }
}
```

### **12.2 DFS Template**

```cpp
void dfs(int node, vector<vector<int>>& graph, vector<bool>& visited) {
    visited[node] = true;
    
    for (int neighbor : graph[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, graph, visited);
        }
    }
}
```

### **Problems:**

| # | Problem | Difficulty | Algorithm |
|---|---------|------------|-----------|
| 1 | Number of Islands (LeetCode #200) | Medium | DFS/BFS |
| 2 | Clone Graph (LeetCode #133) | Medium | DFS/BFS |
| 3 | Course Schedule (LeetCode #207) | Medium | Topological Sort |
| 4 | Pacific Atlantic Water Flow (LeetCode #417) | Medium | DFS |
| 5 | Word Ladder (LeetCode #127) | Hard | BFS |
| 6 | Shortest Path in Binary Matrix (LeetCode #1091) | Medium | BFS |
| 7 | Network Delay Time (LeetCode #743) | Medium | Dijkstra |
| 8 | Cheapest Flights K Stops (LeetCode #787) | Medium | BFS/Bellman-Ford |

---

## **13. Tree Patterns**

### **13.1 Tree Traversal**

#### **Inorder (Left-Root-Right)**
```cpp
void inorder(TreeNode* root) {
    if (!root) return;
    inorder(root->left);
    visit(root);
    inorder(root->right);
}
```

#### **Preorder (Root-Left-Right)**
```cpp
void preorder(TreeNode* root) {
    if (!root) return;
    visit(root);
    preorder(root->left);
    preorder(root->right);
}
```

#### **Postorder (Left-Right-Root)**
```cpp
void postorder(TreeNode* root) {
    if (!root) return;
    postorder(root->left);
    postorder(root->right);
    visit(root);
}
```

#### **Level Order (BFS)**
```cpp
void levelOrder(TreeNode* root) {
    queue<TreeNode*> q;
    q.push(root);
    
    while (!q.empty()) {
        int size = q.size();
        for (int i = 0; i < size; i++) {
            TreeNode* node = q.front();
            q.pop();
            visit(node);
            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);
        }
    }
}
```

### **Problems:**

| # | Problem | Difficulty | Pattern |
|---|---------|------------|---------|
| 1 | Maximum Depth (LeetCode #104) | Easy | DFS |
| 2 | Same Tree (LeetCode #100) | Easy | DFS |
| 3 | Invert Binary Tree (LeetCode #226) | Easy | DFS |
| 4 | Diameter of Binary Tree (LeetCode #543) | Easy | DFS |
| 5 | Path Sum (LeetCode #112) | Easy | DFS |
| 6 | Lowest Common Ancestor (LeetCode #236) | Medium | DFS |
| 7 | Binary Tree Right Side View (LeetCode #199) | Medium | BFS |
| 8 | Serialize/Deserialize (LeetCode #297) | Hard | BFS/DFS |
| 9 | Binary Tree Maximum Path Sum (LeetCode #124) | Hard | DFS |

---

## **14. Trie**

### **Pattern Recognition:**
- Prefix matching
- Word search
- Autocomplete

### **Template:**

```cpp
class TrieNode {
public:
    unordered_map<char, TrieNode*> children;
    bool isEnd = false;
};

class Trie {
    TrieNode* root;
public:
    Trie() { root = new TrieNode(); }
    
    void insert(string word) {
        TrieNode* node = root;
        for (char c : word) {
            if (!node->children[c]) {
                node->children[c] = new TrieNode();
            }
            node = node->children[c];
        }
        node->isEnd = true;
    }
    
    bool search(string word) {
        TrieNode* node = root;
        for (char c : word) {
            if (!node->children[c]) return false;
            node = node->children[c];
        }
        return node->isEnd;
    }
};
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Implement Trie (LeetCode #208) | Medium |
| 2 | Add and Search Word (LeetCode #211) | Medium |
| 3 | Word Search II (LeetCode #212) | Hard |
| 4 | Replace Words (LeetCode #648) | Medium |

---

## **15. Monotonic Stack/Queue**

### **Pattern Recognition:**
- Next greater/smaller element
- Sliding window maximum
- Maintain increasing/decreasing order

### **Monotonic Stack Template:**

```cpp
vector<int> nextGreater(vector<int>& nums) {
    int n = nums.size();
    vector<int> result(n, -1);
    stack<int> st;  // Store indices
    
    for (int i = 0; i < n; i++) {
        while (!st.empty() && nums[st.top()] < nums[i]) {
            result[st.top()] = nums[i];
            st.pop();
        }
        st.push(i);
    }
    return result;
}
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Next Greater Element (LeetCode #496) | Easy |
| 2 | Daily Temperatures (LeetCode #739) | Medium |
| 3 | Largest Rectangle in Histogram (LeetCode #84) | Hard |
| 4 | Trapping Rain Water (LeetCode #42) | Hard |
| 5 | Sliding Window Maximum (LeetCode #239) | Hard |

---

## **16. Bit Manipulation**

### **Common Operations:**

```cpp
// Check if kth bit is set
bool isSet = (num & (1 << k)) != 0;

// Set kth bit
num |= (1 << k);

// Clear kth bit
num &= ~(1 << k);

// Toggle kth bit
num ^= (1 << k);

// Count set bits
int countBits = __builtin_popcount(num);

// Check if power of 2
bool isPowerOf2 = (num > 0) && (num & (num - 1)) == 0;

// Get rightmost set bit
int rightmost = num & -num;
```

### **Problems:**

| # | Problem | Difficulty | Trick |
|---|---------|------------|-------|
| 1 | Single Number (LeetCode #136) | Easy | XOR |
| 2 | Number of 1 Bits (LeetCode #191) | Easy | Counting |
| 3 | Counting Bits (LeetCode #338) | Easy | DP + Bits |
| 4 | Single Number II (LeetCode #137) | Medium | Bit Manipulation |
| 5 | Bitwise AND of Range (LeetCode #201) | Medium | Common Prefix |
| 6 | Maximum XOR (LeetCode #421) | Medium | Trie |

---

## **17. Math & Number Theory**

### **Problems:**

| # | Problem | Difficulty | Concept |
|---|---------|------------|---------|
| 1 | Pow(x, n) (LeetCode #50) | Medium | Fast Power |
| 2 | Sqrt(x) (LeetCode #69) | Easy | Binary Search |
| 3 | Happy Number (LeetCode #202) | Easy | Cycle Detection |
| 4 | Factorial Trailing Zeroes (LeetCode #172) | Medium | Math |
| 5 | Excel Sheet Column Number (LeetCode #171) | Easy | Base Conversion |
| 6 | Nth Digit (LeetCode #400) | Medium | Math |

---

## **18. Greedy Algorithms**

### **Pattern Recognition:**
- Local optimal leads to global optimal
- Sorting helps
- Activity selection

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Jump Game (LeetCode #55) | Medium |
| 2 | Jump Game II (LeetCode #45) | Medium |
| 3 | Gas Station (LeetCode #134) | Medium |
| 4 | Partition Labels (LeetCode #763) | Medium |
| 5 | Task Scheduler (LeetCode #621) | Medium |
| 6 | Non-overlapping Intervals (LeetCode #435) | Medium |

---

## **19. Union Find (Disjoint Set)**

### **Template:**

```cpp
class UnionFind {
    vector<int> parent, rank;
public:
    UnionFind(int n) {
        parent.resize(n);
        rank.resize(n, 0);
        for (int i = 0; i < n; i++) {
            parent[i] = i;
        }
    }
    
    int find(int x) {
        if (parent[x] != x) {
            parent[x] = find(parent[x]);  // Path compression
        }
        return parent[x];
    }
    
    bool unite(int x, int y) {
        int px = find(x), py = find(y);
        if (px == py) return false;
        
        // Union by rank
        if (rank[px] < rank[py]) swap(px, py);
        parent[py] = px;
        if (rank[px] == rank[py]) rank[px]++;
        return true;
    }
};
```

### **Problems:**

| # | Problem | Difficulty |
|---|---------|------------|
| 1 | Number of Connected Components (LeetCode #323) | Medium |
| 2 | Graph Valid Tree (LeetCode #261) | Medium |
| 3 | Redundant Connection (LeetCode #684) | Medium |
| 4 | Accounts Merge (LeetCode #721) | Medium |
| 5 | Most Stones Removed (LeetCode #947) | Medium |

---

## **20. Advanced Patterns**

### **20.1 Segment Tree**
- Range queries
- Point updates
- **Problems:** Range Sum Query (LeetCode #307)

### **20.2 Binary Indexed Tree (Fenwick Tree)**
- Prefix sum queries
- Range updates
- **Problems:** Range Sum Query (LeetCode #307)

### **20.3 KMP Algorithm**
- Pattern matching
- **Problems:** Implement strStr() (LeetCode #28)

### **20.4 Rabin-Karp**
- Rolling hash
- **Problems:** Repeated DNA Sequences (LeetCode #187)

---

## 📊 **Pattern Frequency in Interviews**

| Pattern | Frequency | Must Practice |
|---------|-----------|---------------|
| Two Pointers | ⭐⭐⭐⭐⭐ | ✅ |
| Sliding Window | ⭐⭐⭐⭐⭐ | ✅ |
| Binary Search | ⭐⭐⭐⭐⭐ | ✅ |
| DFS/BFS | ⭐⭐⭐⭐⭐ | ✅ |
| Dynamic Programming | ⭐⭐⭐⭐⭐ | ✅ |
| Backtracking | ⭐⭐⭐⭐ | ✅ |
| Heap | ⭐⭐⭐⭐ | ✅ |
| Fast & Slow Pointers | ⭐⭐⭐ | ✅ |
| Monotonic Stack | ⭐⭐⭐ | ✅ |
| Greedy | ⭐⭐⭐⭐ | ✅ |
| Trie | ⭐⭐⭐ | ✅ |
| Union Find | ⭐⭐⭐ | ✅ |
| Bit Manipulation | ⭐⭐⭐ | ✅ |

---

## 🎯 **Study Plan**

### **Week 1-2: Foundation**
- Arrays & Strings
- Two Pointers
- Sliding Window
- Hashing

### **Week 3-4: Searching & Sorting**
- Binary Search (all variants)
- Sorting algorithms
- Merge Intervals

### **Week 5-6: Linked Lists & Trees**
- Fast & Slow Pointers
- Tree Traversals
- Binary Search Trees

### **Week 7-8: Graphs**
- DFS/BFS
- Topological Sort
- Dijkstra

### **Week 9-10: Dynamic Programming**
- 1D DP
- 2D DP
- Knapsack

### **Week 11-12: Advanced**
- Backtracking
- Greedy
- Bit Manipulation
- Trie

---

## 🔥 **Must-Do Problems (Top 75)**

### **Easy (15 problems)**
1. Two Sum
2. Valid Parentheses
3. Merge Two Sorted Lists
4. Best Time to Buy and Sell Stock
5. Valid Palindrome
6. Invert Binary Tree
7. Binary Search
8. Climbing Stairs
9. Linked List Cycle
10. Maximum Depth of Binary Tree
11. Single Number
12. Happy Number
13. Remove Duplicates from Sorted Array
14. Move Zeroes
15. Majority Element

### **Medium (45 problems)**
1. Add Two Numbers
2. Longest Substring Without Repeating Characters
3. Container With Most Water
4. 3Sum
5. Letter Combinations of a Phone Number
6. Remove Nth Node From End of List
7. Generate Parentheses
8. Merge Intervals
9. Rotate Image
10. Group Anagrams
11. Maximum Subarray
12. Jump Game
13. Unique Paths
14. Minimum Path Sum
15. Word Search
16. Search in Rotated Sorted Array
17. Find Minimum in Rotated Sorted Array
18. Maximum Product Subarray
19. Number of Islands
20. Course Schedule
21. House Robber II
22. Kth Largest Element
23. Product of Array Except Self
24. Lowest Common Ancestor of BST
25. Binary Tree Level Order Traversal
26. Validate Binary Search Tree
27. Kth Smallest Element in BST
28. Implement Trie
29. Design Add and Search Words
30. Longest Increasing Subsequence
31. Coin Change
32. Palindrome Partitioning
33. Word Break
34. Combination Sum
35. Permutations
36. Subsets
37. Merge K Sorted Lists
38. Top K Frequent Elements
39. Find Median from Data Stream
40. Sliding Window Maximum
41. Longest Palindromic Substring
42. Decode Ways
43. Unique Binary Search Trees
44. Clone Graph
45. Pacific Atlantic Water Flow

### **Hard (15 problems)**
1. Median of Two Sorted Arrays
2. Merge K Sorted Lists
3. Trapping Rain Water
4. First Missing Positive
5. Wildcard Matching
6. Jump Game II
7. N-Queens
8. Minimum Window Substring
9. Largest Rectangle in Histogram
10. Word Ladder
11. Binary Tree Maximum Path Sum
12. Word Search II
13. Serialize and Deserialize Binary Tree
14. Alien Dictionary
15. Palindrome Pairs

---

## 💡 **Tips for Success**

### **1. Pattern Recognition**
- Don't memorize solutions
- Understand the pattern
- Practice identifying patterns

### **2. Time Management**
- Easy: 10-15 min
- Medium: 20-30 min
- Hard: 40-50 min

### **3. Problem-Solving Approach**
1. **Understand** - Read carefully, ask clarifying questions
2. **Examples** - Work through examples manually
3. **Approach** - Identify pattern, discuss brute force
4. **Code** - Write clean, modular code
5. **Test** - Test with edge cases
6. **Optimize** - Discuss time/space complexity

### **4. Edge Cases**
- Empty input
- Single element
- All same elements
- Negative numbers
- Overflow
- Null pointers

### **5. Complexity Analysis**
Always analyze:
- **Time Complexity:** O(?)
- **Space Complexity:** O(?)

---

## 🚀 **Company-Specific Patterns**

### **FAANG Companies:**

| Company | Focus Areas |
|---------|-------------|
| **Google** | Graphs, DP, System Design |
| **Amazon** | Arrays, Trees, OOP Design |
| **Facebook/Meta** | Graphs, DFS/BFS, Trees |
| **Apple** | Arrays, Strings, Design |
| **Netflix** | Algorithms, Scalability |
| **Microsoft** | DP, Graphs, Design |

---

## 📚 **Additional Resources**

1. **LeetCode** - Main practice platform
2. **Blind 75** - Curated list
3. **NeetCode** - Video explanations
4. **AlgoExpert** - Structured course
5. **Cracking the Coding Interview** - Book
6. **Elements of Programming Interviews** - Book

---

## ✅ **Progress Tracker**

Create a spreadsheet with:
- Problem Name
- Pattern
- Difficulty
- First Attempt Date
- Solved (Yes/No)
- Time Taken
- Review Date

---

**Good luck with your DSA journey! 🎉**

Remember: **Consistency > Intensity**. Practice daily, even if it's just one problem!


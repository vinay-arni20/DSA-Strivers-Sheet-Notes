# STL Quick notes

## 🧩 **1. STL `pair` — Complete Notes**

### 📘 **Concept Summary**

- `pair` is a simple container that holds **two values of possibly different types**.
- Defined in `<utility>` header (also included in `<bits/stdc++.h>`).
- Commonly used for storing key-value pairs or coordinate data (like `(x, y)` points).
- Supports:
    - `.first` and `.second` for element access.
    - `make_pair()` for creation.
    - Comparison operators (`==`, `<`, `>`, etc.) — lexicographical comparison.
    - `swap()` to interchange pairs.
    - Nested pairs and arrays of pairs.

### ⚙️ **Key Operations**

| Operation | Syntax | Description |
| --- | --- | --- |
| Create a pair | `pair<int, int> p = {1, 2};` | Initializes with values |
| Access elements | `p.first`, `p.second` | Returns first/second element |
| Create with helper | `auto p = make_pair(10, 20);` | Infers data types automatically |
| Swap two pairs | `swap(p1, p2);` | Swaps both elements |
| Nested pair | `pair<int, pair<int,int>> np = {1,{2,3}};` | Pair inside another pair |
| Array of pairs | `pair<int,int> arr[] = {{1,2},{3,4}};` | Useful in sorting & mapping |

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    pair<int, int> p1 = {10, 20};
    pair<int, int> p2 = {30, 40};

    cout << "Before swap: (" << p1.first << ", " << p1.second << ")\n";
    swap(p1, p2);
    cout << "After swap: (" << p1.first << ", " << p1.second << ")\n";

    pair<int, pair<int, int>> nested = {1, {2, 3}};
    cout << "Nested: (" << nested.first << ", ("
         << nested.second.first << ", "
         << nested.second.second << "))\n";

    pair<int,int> arr[] = {{1,2}, {3,4}, {5,6}};
    for(auto &p : arr) // we are using reference here so we can directly pass value not copying it will save lot of space 
        cout << "(" << p.first << "," << p.second << ") ";
}

```

**🧾 Output:**

```
Before swap: (10, 20)
After swap: (30, 40)
Nested: (1, (2, 3))
(1,2) (3,4) (5,6)

```

---

---

## 🧩 **2. STL `vector` — Complete Notes**

### 📘 **Concept Summary**

- `vector` is a **dynamic array** — it automatically grows or shrinks in size during runtime.
- Comes from the header `<vector>`.
- **Stores elements in contiguous memory** (like arrays).
- Provides **random access** (O(1) time for `v[i]`).
- Automatically handles memory reallocation when capacity increases.
- Adding/removing at the **end is fast (O(1) amortized)**; inserting/deleting in the middle is slower (O(n)).
- Fully compatible with STL algorithms (`sort()`, `find()`, etc.).

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create empty vector | `vector<int> v;` | Creates an empty vector | O(1) |
| Initialize with size | `vector<int> v(5, 10);` | 5 elements, all = 10 | O(n) |
| Initialize list | `vector<int> v = {1,2,3};` | Initializes with values | O(n) |
| Copy constructor | `vector<int> v2(v1);` | Clones another vector | O(n) |
| Add element | `v.push_back(x);` | Adds element at end | Amortized O(1) |
| Emplace element | `v.emplace_back(x);` | Faster than `push_back` | Amortized O(1) |
| Remove last | `v.pop_back();` | Deletes last element | O(1) |
| Access element | `v[i]`, `v.at(i)` | Random access | O(1) |
| Size / Empty | `v.size()`, `v.empty()` | Info about vector | O(1) |
| Insert | `v.insert(v.begin()+i, val);` | Insert at position | O(n) |
| Erase | `v.erase(v.begin()+i);` | Delete at position | O(n) |
| Clear | `v.clear();` | Removes all elements | O(n) |
| Resize | `v.resize(newSize);` | Change size | O(n) |
| Sort | `sort(v.begin(), v.end());` | Sorts ascending | O(n log n) |
| Reverse | `reverse(v.begin(), v.end());` | Reverses order | O(n) |
| Find | `find(v.begin(), v.end(), x);` | Returns iterator | O(n) |
| Unique | `v.erase(unique(v.begin(), v.end()), v.end());` | Removes duplicates | O(n) |
| Sum | `accumulate(v.begin(), v.end(), 0);` | Sums elements | O(n) |

---

### 🧠 **LeetCode Problems Using `vector`**

*(All levels — beginner → advanced)*

### 🔹 **Beginner**

1. [#1920 — Build Array from Permutation](https://leetcode.com/problems/build-array-from-permutation/)
2. [#1480 — Running Sum of 1D Array](https://leetcode.com/problems/running-sum-of-1d-array/)
3. [#1672 — Richest Customer Wealth](https://leetcode.com/problems/richest-customer-wealth/)
4. [#283 — Move Zeroes](https://leetcode.com/problems/move-zeroes/)
5. [#977 — Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)
6. [#1089 — Duplicate Zeros](https://leetcode.com/problems/duplicate-zeros/)
7. [#905 — Sort Array by Parity](https://leetcode.com/problems/sort-array-by-parity/)
8. [#136 — Single Number](https://leetcode.com/problems/single-number/)
9. [#350 — Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
10. [#66 — Plus One](https://leetcode.com/problems/plus-one/)

### 🔸 **Intermediate**

1. [#15 — 3Sum](https://leetcode.com/problems/3sum/)
2. [#56 — Merge Intervals](https://leetcode.com/problems/merge-intervals/)
3. [#238 — Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)
4. [#560 — Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
5. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
6. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
7. [#42 — Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)
8. [#31 — Next Permutation](https://leetcode.com/problems/next-permutation/)
9. [#240 — Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii/)
10. [#48 — Rotate Image](https://leetcode.com/problems/rotate-image/)

### 🔺 **Advanced**

1. [#4 — Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/)
2. [#41 — First Missing Positive](https://leetcode.com/problems/first-missing-positive/)
3. [#84 — Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/)
4. [#239 — Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)
5. [#1289 — Minimum Falling Path Sum II](https://leetcode.com/problems/minimum-falling-path-sum-ii/)
6. [#120 — Triangle](https://leetcode.com/problems/triangle/)
7. [#200 — Number of Islands](https://leetcode.com/problems/number-of-islands/)
8. [#695 — Max Area of Island](https://leetcode.com/problems/max-area-of-island/)
9. [#130 — Surrounded Regions](https://leetcode.com/problems/surrounded-regions/)
10. [#417 — Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    vector<int> v1;
    vector<int> v2(5, 10);      // {10,10,10,10,10}
    vector<int> v3 = {1, 2, 3}; // list initialization

    // 2. Adding elements
    v1.push_back(5);
    v1.emplace_back(10); // faster version

    // 3. Accessing
    cout << v3[0] << " " << v3.at(1) << "\n";
    cout << v3.front() << " " << v3.back() << "\n";

    // 4. Iteration
    for (auto it = v3.begin(); it != v3.end(); ++it)
        cout << *it << " ";

    // 5. Insertion & Deletion
    v3.insert(v3.begin()+1, 9); // {1,9,2,3}
    v3.erase(v3.begin()+2);     // remove 2

    // 6. Sorting
    sort(v3.begin(), v3.end()); // {1,3,9}
    reverse(v3.begin(), v3.end());

    // 7. Unique elements
    v3 = {1,1,2,2,3};
    v3.erase(unique(v3.begin(), v3.end()), v3.end()); // {1,2,3}

    // 8. 2D Vector
    vector<vector<int>> mat = {{1,2,3}, {4,5,6}};
    for (auto &row : mat) {
        for (int val : row) cout << val << " ";
        cout << "\n";
    }

    return 0;
}

```

**🧾 Output (Simplified):**

```
1 2
1 3
1 2 3
4 5 6

```

---

---

## 🧩 **3. STL `list` — Complete Notes**

### 📘 **Concept Summary**

- `list` is a **doubly linked list** — each node stores data + pointers to both previous and next nodes.
- Defined in `<list>` header.
- Efficient for **insertions and deletions anywhere** in O(1) (if iterator is known).
- No **random access** (you can’t use `l[i]`).
- Maintains **insertion order**.
- Supports bidirectional iterators.
- Slightly **more memory overhead** than `vector` due to pointers.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create empty list | `list<int> l;` | Creates an empty list | O(1) |
| Initialize with size | `list<int> l(5, 10);` | 5 elements, all = 10 | O(n) |
| Initialize list | `list<int> l = {1,2,3,4};` | Creates from values | O(n) |
| Copy list | `list<int> l2(l1);` | Duplicates contents | O(n) |
| Push front/back | `l.push_front(x);`, `l.push_back(x);` | Insert at ends | O(1) |
| Emplace | `l.emplace_front(x);`, `l.emplace_back(x);` | Faster insertion | O(1) |
| Pop front/back | `l.pop_front();`, `l.pop_back();` | Remove from ends | O(1) |
| Front/Back | `l.front();`, `l.back();` | Access first/last | O(1) |
| Insert | `l.insert(it, val);` | Insert before iterator | O(1) |
| Erase | `l.erase(it);` | Remove element by iterator | O(1) |
| Clear | `l.clear();` | Remove all elements | O(n) |
| Remove value | `l.remove(x);` | Removes all `x` | O(n) |
| Unique | `l.unique();` | Removes consecutive duplicates | O(n) |
| Sort | `l.sort();` | Sorts ascending | O(n log n) |
| Reverse | `l.reverse();` | Reverses order | O(n) |
| Merge | `l1.merge(l2);` | Merges sorted lists | O(n+m) |
| Splice | `l1.splice(pos, l2);` | Moves nodes from one list to another | O(1) |

---

### 🧠 **LeetCode Problems Using `list`**

*(Covers all levels — practical linked list mastery)*

### 🔹 **Beginner**

1. [#876 — Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
2. [#206 — Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)
3. [#141 — Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
4. [#21 — Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
5. [#83 — Remove Duplicates from Sorted List](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)
6. [#203 — Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)
7. [#237 — Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/)
8. [#2 — Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)
9. [#19 — Remove Nth Node From End](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
10. [#234 — Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)

### 🔸 **Intermediate**

1. [#61 — Rotate List](https://leetcode.com/problems/rotate-list/)
2. [#24 — Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/)
3. [#143 — Reorder List](https://leetcode.com/problems/reorder-list/)
4. [#147 — Insertion Sort List](https://leetcode.com/problems/insertion-sort-list/)
5. [#148 — Sort List](https://leetcode.com/problems/sort-list/)
6. [#82 — Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)
7. [#92 — Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)
8. [#328 — Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/)
9. [#445 — Add Two Numbers II](https://leetcode.com/problems/add-two-numbers-ii/)
10. [#707 — Design Linked List](https://leetcode.com/problems/design-linked-list/)

### 🔺 **Advanced**

1. [#23 — Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)
2. [#25 — Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/)
3. [#138 — Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/)
4. [#142 — Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
5. [#1171 — Remove Zero Sum Consecutive Nodes from Linked List](https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/)
6. [#725 — Split Linked List in Parts](https://leetcode.com/problems/split-linked-list-in-parts/)
7. [#1474 — Delete N Nodes After M Nodes](https://leetcode.com/problems/delete-n-nodes-after-m-nodes-of-a-linked-list/)
8. [#1721 — Swapping Nodes in a Linked List](https://leetcode.com/problems/swapping-nodes-in-a-linked-list/)
9. [#2807 — Insert Greatest Common Divisors in Linked List](https://leetcode.com/problems/insert-greatest-common-divisors-in-linked-list/)
10. [#2816 — Double a Number Represented as a Linked List](https://leetcode.com/problems/double-a-number-represented-as-a-linked-list/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    list<int> l1 = {1, 2, 3};
    list<int> l2(5, 10); // {10,10,10,10,10}

    // 2. Adding elements
    l1.push_back(4);
    l1.push_front(0);
    l1.emplace_back(5);
    l1.emplace_front(-1);

    // 3. Iteration
    cout << "List: ";
    for (auto x : l1) cout << x << " ";
    cout << "\n";

    // 4. Insert and Erase
    auto it = l1.begin();
    advance(it, 2);        // move iterator to 2nd index
    l1.insert(it, 99);     // insert 99 before that
    l1.erase(next(l1.begin(), 3)); // erase 3rd element

    // 5. Sort and Reverse
    l1.sort();
    l1.reverse();

    // 6. Remove duplicates
    l1.unique();

    // 7. Merge
    list<int> l3 = {7, 8};
    l1.merge(l3);

    // 8. Splice
    list<int> l4 = {100, 200};
    l1.splice(l1.begin(), l4); // move all of l4 to front

    cout << "Modified List: ";
    for (auto x : l1) cout << x << " ";
}

```

**🧾 Output (Simplified):**

```
List: -1 0 1 2 3 4 5
Modified List: 100 200 -1 0 1 2 3 4 5 7 8

```

---

---

## 🧩 **4. STL `deque` — Complete Notes**

### 📘 **Concept Summary**

- `deque` (pronounced “deck”) stands for **Double-Ended Queue**.
- Defined in `<deque>` header.
- Similar to `vector`, but allows **fast insertions and deletions at both ends**.
- Internally implemented as **segmented blocks** (not contiguous like vectors).
- Supports **random access** (`O(1)`), but slightly slower than vector due to non-contiguous layout.
- Preferred when you need **frequent push/pop operations from both front and back**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create empty deque | `deque<int> d;` | Creates an empty deque | O(1) |
| Initialize with size | `deque<int> d(5, 10);` | 5 elements, all = 10 | O(n) |
| Initialize list | `deque<int> d = {1,2,3};` | Initializes with values | O(n) |
| Copy constructor | `deque<int> d2(d1);` | Copies existing deque | O(n) |
| Push front/back | `d.push_front(x);`, `d.push_back(x);` | Insert at both ends | O(1) |
| Emplace front/back | `d.emplace_front(x);`, `d.emplace_back(x);` | Faster version of push | O(1) |
| Pop front/back | `d.pop_front();`, `d.pop_back();` | Remove from both ends | O(1) |
| Access front/back | `d.front();`, `d.back();` | First/last element | O(1) |
| Access index | `d[i];`, `d.at(i);` | Random access | O(1) |
| Insert | `d.insert(d.begin()+i, val);` | Insert at position | O(n) |
| Erase | `d.erase(d.begin()+i);` | Erase at position | O(n) |
| Clear | `d.clear();` | Remove all elements | O(n) |
| Resize | `d.resize(newSize);` | Change number of elements | O(n) |
| Sort | `sort(d.begin(), d.end());` | Sort ascending | O(n log n) |
| Reverse | `reverse(d.begin(), d.end());` | Reverse elements | O(n) |
| Count | `count(d.begin(), d.end(), val);` | Count occurrences | O(n) |

---

### 🧠 **LeetCode Problems Using `deque`**

*(All levels — excellent for mastering sliding windows, queues, and optimization)*

### 🔹 **Beginner**

1. [#232 — Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/)
2. [#933 — Number of Recent Calls](https://leetcode.com/problems/number-of-recent-calls/)
3. [#1700 — Number of Students Unable to Eat Lunch](https://leetcode.com/problems/number-of-students-unable-to-eat-lunch/)
4. [#2390 — Removing Stars From a String](https://leetcode.com/problems/removing-stars-from-a-string/)
5. [#682 — Baseball Game](https://leetcode.com/problems/baseball-game/)
6. [#225 — Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)
7. [#2073 — Time Needed to Buy Tickets](https://leetcode.com/problems/time-needed-to-buy-tickets/)
8. [#346 — Moving Average from Data Stream](https://leetcode.com/problems/moving-average-from-data-stream/)
9. [#2326 — Spiral Matrix IV](https://leetcode.com/problems/spiral-matrix-iv/)
10. [#2810 — Faulty Keyboard](https://leetcode.com/problems/faulty-keyboard/)

### 🔸 **Intermediate**

1. [#239 — Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)
2. [#862 — Shortest Subarray with Sum at Least K](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/)
3. [#1696 — Jump Game VI](https://leetcode.com/problems/jump-game-vi/)
4. [#862 — Shortest Subarray with Sum ≥ K](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/)
5. [#918 — Maximum Sum Circular Subarray](https://leetcode.com/problems/maximum-sum-circular-subarray/)
6. [#503 — Next Greater Element II](https://leetcode.com/problems/next-greater-element-ii/)
7. [#1438 — Longest Continuous Subarray With Absolute Diff ≤ Limit](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)
8. [#2391 — Minimum Amount of Time to Collect Garbage](https://leetcode.com/problems/minimum-amount-of-time-to-collect-garbage/)
9. [#2396 — Strictly Palindromic Number](https://leetcode.com/problems/strictly-palindromic-number/)
10. [#1695 — Maximum Erasure Value](https://leetcode.com/problems/maximum-erasure-value/)

### 🔺 **Advanced**

1. [#862 — Sliding Window Deque Optimization](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/)
2. [#1499 — Max Value of Equation](https://leetcode.com/problems/max-value-of-equation/)
3. [#2398 — Maximum Number of Robots Within Budget](https://leetcode.com/problems/maximum-number-of-robots-within-budget/)
4. [#1696 — Jump Game VI (Deque DP)](https://leetcode.com/problems/jump-game-vi/)
5. [#1425 — Constrained Subsequence Sum](https://leetcode.com/problems/constrained-subsequence-sum/)
6. [#862 — Prefix Sum Deque Optimization](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/)
7. [#1438 — Longest Subarray With Limit](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)
8. [#239 — Sliding Window Maximum (Hard pattern)](https://leetcode.com/problems/sliding-window-maximum/)
9. [#480 — Sliding Window Median](https://leetcode.com/problems/sliding-window-median/)
10. [#862 — Monotonic Queue Pattern Practice](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    deque<int> d1 = {1, 2, 3};
    deque<int> d2(4, 10); // {10,10,10,10}

    // 2. Adding elements
    d1.push_front(0);  // {0,1,2,3}
    d1.push_back(4);   // {0,1,2,3,4}
    d1.emplace_front(-1);
    d1.emplace_back(5);

    // 3. Access
    cout << "Front: " << d1.front() << ", Back: " << d1.back() << "\n";
    cout << "Element at index 2: " << d1[2] << "\n";

    // 4. Iteration
    cout << "Deque: ";
    for (auto x : d1) cout << x << " ";
    cout << "\n";

    // 5. Insertion and Deletion
    d1.insert(d1.begin() + 2, 99);
    d1.erase(d1.begin() + 3);

    // 6. Sorting and Reversing
    sort(d1.begin(), d1.end());
    reverse(d1.begin(), d1.end());

    // 7. Clear
    d2.clear();
    cout << "Size of d2 after clear: " << d2.size() << "\n";

    // 8. Example use — Sliding Window Maximum
    deque<int> dq;
    vector<int> nums = {1,3,-1,-3,5,3,6,7};
    int k = 3;
    vector<int> result;

    for (int i = 0; i < nums.size(); i++) {
        while (!dq.empty() && dq.front() <= i - k) dq.pop_front();
        while (!dq.empty() && nums[dq.back()] <= nums[i]) dq.pop_back();
        dq.push_back(i);
        if (i >= k - 1) result.push_back(nums[dq.front()]);
    }

    cout << "Sliding window max: ";
    for (int x : result) cout << x << " ";
}

```

**🧾 Output (Simplified):**

```
Front: -1, Back: 5
Element at index 2: 1
Deque: -1 0 1 2 3 4 5
Size of d2 after clear: 0
Sliding window max: 3 3 5 5 6 7

```

---

---

## 🧩 **5. STL `queue` — Complete Notes**

### 📘 **Concept Summary**

- `queue` is a **FIFO (First In, First Out)** container adapter — just like a real-world queue.
- Defined in `<queue>` header.
- You can **only access the front and back elements** — no random access or iterators.
- Underlying container is usually a **`deque`** (by default) but can also use `list`.
- Supports **O(1)** insertion and deletion at ends.
- Very useful for **BFS (Breadth-First Search)** and **level-order traversal** problems.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create empty queue | `queue<int> q;` | Creates an empty queue | O(1) |
| Copy queue | `queue<int> q2(q1);` | Copies another queue | O(n) |
| Push | `q.push(x);` | Insert at back | O(1) |
| Emplace | `q.emplace(x);` | Insert (faster) at back | O(1) |
| Pop | `q.pop();` | Remove element from front | O(1) |
| Front | `q.front();` | Access front element | O(1) |
| Back | `q.back();` | Access last element | O(1) |
| Size | `q.size();` | Get number of elements | O(1) |
| Empty | `q.empty();` | Check if empty | O(1) |
| Swap | `q1.swap(q2);` | Swap queues | O(1) |

---

### 🧠 **LeetCode Problems Using `queue`**

*(All levels — BFS, simulations, and level traversals)*

### 🔹 **Beginner**

1. [#933 — Number of Recent Calls](https://leetcode.com/problems/number-of-recent-calls/)
2. [#1700 — Number of Students Unable to Eat Lunch](https://leetcode.com/problems/number-of-students-unable-to-eat-lunch/)
3. [#225 — Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)
4. [#232 — Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/)
5. [#2073 — Time Needed to Buy Tickets](https://leetcode.com/problems/time-needed-to-buy-tickets/)
6. [#1823 — Find the Winner of the Circular Game](https://leetcode.com/problems/find-the-winner-of-the-circular-game/)
7. [#346 — Moving Average from Data Stream](https://leetcode.com/problems/moving-average-from-data-stream/)
8. [#387 — First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)
9. [#2259 — Remove Digit From Number to Maximize Result](https://leetcode.com/problems/remove-digit-from-number-to-maximize-result/)
10. [#170 — Two Sum III — Data structure design](https://leetcode.com/problems/two-sum-iii-data-structure-design/)

### 🔸 **Intermediate**

1. [#102 — Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
2. [#104 — Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
3. [#279 — Perfect Squares](https://leetcode.com/problems/perfect-squares/)
4. [#994 — Rotting Oranges](https://leetcode.com/problems/rotting-oranges/)
5. [#286 — Walls and Gates](https://leetcode.com/problems/walls-and-gates/)
6. [#542 — 01 Matrix](https://leetcode.com/problems/01-matrix/)
7. [#127 — Word Ladder](https://leetcode.com/problems/word-ladder/)
8. [#200 — Number of Islands (BFS variant)](https://leetcode.com/problems/number-of-islands/)
9. [#207 — Course Schedule](https://leetcode.com/problems/course-schedule/)
10. [#1091 — Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix/)

### 🔺 **Advanced**

1. [#815 — Bus Routes](https://leetcode.com/problems/bus-routes/)
2. [#1293 — Shortest Path in a Grid with Obstacles Elimination](https://leetcode.com/problems/shortest-path-in-a-grid-with-obstacles-elimination/)
3. [#505 — The Maze II](https://leetcode.com/problems/the-maze-ii/)
4. [#675 — Cut Off Trees for Golf Event](https://leetcode.com/problems/cut-off-trees-for-golf-event/)
5. [#1263 — Minimum Moves to Move a Box to Target Location](https://leetcode.com/problems/minimum-moves-to-move-a-box-to-target-location/)
6. [#815 — BFS Route Optimization](https://leetcode.com/problems/bus-routes/)
7. [#847 — Shortest Path Visiting All Nodes](https://leetcode.com/problems/shortest-path-visiting-all-nodes/)
8. [#934 — Shortest Bridge](https://leetcode.com/problems/shortest-bridge/)
9. [#310 — Minimum Height Trees](https://leetcode.com/problems/minimum-height-trees/)
10. [#1162 — As Far from Land as Possible](https://leetcode.com/problems/as-far-from-land-as-possible/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    queue<int> q;

    // 2. Add elements
    q.push(10);
    q.push(20);
    q.emplace(30);

    // 3. Access
    cout << "Front: " << q.front() << ", Back: " << q.back() << "\n";

    // 4. Remove
    q.pop();
    cout << "After pop, Front: " << q.front() << "\n";

    // 5. Size and Empty
    cout << "Size: " << q.size() << "\n";
    cout << "Empty: " << (q.empty() ? "Yes" : "No") << "\n";

    // 6. Swap example
    queue<int> q2;
    q2.push(100);
    q.swap(q2);

    cout << "After swap, Front: " << q.front() << "\n";

    // 7. Example — BFS on a graph
    int n = 5;
    vector<vector<int>> adj = {{1,2}, {0,3}, {0,3,4}, {1,2}, {2}};
    vector<int> visited(n, 0);
    queue<int> bfs;
    bfs.push(0);
    visited[0] = 1;

    cout << "BFS Order: ";
    while(!bfs.empty()) {
        int node = bfs.front();
        bfs.pop();
        cout << node << " ";
        for (auto nbr : adj[node]) {
            if (!visited[nbr]) {
                visited[nbr] = 1;
                bfs.push(nbr);
            }
        }
    }
}

```

**🧾 Output (Simplified):**

```
Front: 10, Back: 30
After pop, Front: 20
Size: 2
Empty: No
After swap, Front: 100
BFS Order: 0 1 2 3 4

```

---

---

## 🧩 **6. STL `priority_queue` — Complete Notes**

### 📘 **Concept Summary**

- `priority_queue` is a **special container adapter** that stores elements in **heap order**.
- By default, it’s a **max-heap** (top = largest element).
- Can be converted into a **min-heap** using a custom comparator.
- Defined in `<queue>` header.
- Internally implemented as a **binary heap (vector-based)**.
- Provides O(1) access to the top element and O(log n) insertion/deletion.
- Commonly used in:
    - Dijkstra’s shortest path algorithm
    - Kth largest/smallest elements
    - Scheduling, Huffman encoding, merging sorted data

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create max-heap | `priority_queue<int> pq;` | Default max-heap | O(1) |
| Create min-heap | `priority_queue<int, vector<int>, greater<int>> pq;` | Smallest on top | O(1) |
| Insert element | `pq.push(x);` | Adds element | O(log n) |
| Emplace element | `pq.emplace(x);` | Faster insertion | O(log n) |
| Access top | `pq.top();` | Returns top element | O(1) |
| Remove top | `pq.pop();` | Removes top element | O(log n) |
| Size | `pq.size();` | Number of elements | O(1) |
| Empty | `pq.empty();` | Check if empty | O(1) |
| Swap | `pq1.swap(pq2);` | Swaps two heaps | O(1) |
| Custom comparator | `priority_queue<Type, vector<Type>, Compare>` | Define custom order | O(log n) |

---

### 🧠 **LeetCode Problems Using `priority_queue`**

*(All levels — perfect for heaps, greedy, and shortest path problems)*

### 🔹 **Beginner**

1. [#215 — Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)
2. [#703 — Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/)
3. [#1046 — Last Stone Weight](https://leetcode.com/problems/last-stone-weight/)
4. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#973 — K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/)
6. [#2558 — Take Gifts From the Richest Pile](https://leetcode.com/problems/take-gifts-from-the-richest-pile/)
7. [#1337 — The K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)
8. [#506 — Relative Ranks](https://leetcode.com/problems/relative-ranks/)
9. [#2462 — Total Cost to Hire K Workers](https://leetcode.com/problems/total-cost-to-hire-k-workers/)
10. [#2208 — Minimum Operations to Halve Array Sum](https://leetcode.com/problems/minimum-operations-to-halve-array-sum/)

### 🔸 **Intermediate**

1. [#451 — Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
2. [#373 — Find K Pairs with Smallest Sums](https://leetcode.com/problems/find-k-pairs-with-smallest-sums/)
3. [#621 — Task Scheduler](https://leetcode.com/problems/task-scheduler/)
4. [#502 — IPO](https://leetcode.com/problems/ipo/)
5. [#239 — Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)
6. [#2158 — Amount of Time for Binary Tree to Be Infected](https://leetcode.com/problems/amount-of-time-for-binary-tree-to-be-infected/)
7. [#1705 — Maximum Number of Eaten Apples](https://leetcode.com/problems/maximum-number-of-eaten-apples/)
8. [#1834 — Single-Threaded CPU](https://leetcode.com/problems/single-threaded-cpu/)
9. [#621 — Task Scheduling Optimization](https://leetcode.com/problems/task-scheduler/)
10. [#2402 — Meeting Rooms III](https://leetcode.com/problems/meeting-rooms-iii/)

### 🔺 **Advanced**

1. [#787 — Cheapest Flights Within K Stops](https://leetcode.com/problems/cheapest-flights-within-k-stops/)
2. [#743 — Network Delay Time](https://leetcode.com/problems/network-delay-time/)
3. [#1631 — Path With Minimum Effort](https://leetcode.com/problems/path-with-minimum-effort/)
4. [#1976 — Number of Ways to Arrive at Destination](https://leetcode.com/problems/number-of-ways-to-arrive-at-destination/)
5. [#630 — Course Schedule III](https://leetcode.com/problems/course-schedule-iii/)
6. [#1786 — Number of Restricted Paths From First to Last Node](https://leetcode.com/problems/number-of-restricted-paths-from-first-to-last-node/)
7. [#778 — Swim in Rising Water](https://leetcode.com/problems/swim-in-rising-water/)
8. [#295 — Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)
9. [#1642 — Furthest Building You Can Reach](https://leetcode.com/problems/furthest-building-you-can-reach/)
10. [#871 — Minimum Number of Refueling Stops](https://leetcode.com/problems/minimum-number-of-refueling-stops/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Max Heap (default)
    priority_queue<int> pq;
    pq.push(10);
    pq.push(30);
    pq.push(20);
    pq.emplace(40);

    cout << "Max-Heap top: " << pq.top() << "\n"; // 40
    pq.pop();
    cout << "Next top: " << pq.top() << "\n"; // 30

    // 2. Min Heap
    priority_queue<int, vector<int>, greater<int>> minpq;
    minpq.push(10);
    minpq.push(5);
    minpq.push(15);
    cout << "Min-Heap top: " << minpq.top() << "\n"; // 5

    // 3. Pair-based heap (useful for Dijkstra)
    priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pqPair;
    pqPair.push({5, 2});
    pqPair.push({3, 1});
    pqPair.push({10, 4});

    cout << "Pair with smallest first value: ("
         << pqPair.top().first << ", " << pqPair.top().second << ")\n";

    // 4. Example — Kth Largest Element
    vector<int> nums = {3,2,1,5,6,4};
    int k = 2;
    priority_queue<int, vector<int>, greater<int>> minHeap;
    for (int n : nums) {
        minHeap.push(n);
        if (minHeap.size() > k) minHeap.pop();
    }
    cout << "Kth largest: " << minHeap.top() << "\n";
}

```

**🧾 Output (Simplified):**

```
Max-Heap top: 40
Next top: 30
Min-Heap top: 5
Pair with smallest first value: (3, 1)
Kth largest: 5

```

---

---

## 🧩 **7. STL `set` — Complete Notes**

### 📘 **Concept Summary**

- `set` is an **ordered associative container** that stores **unique elements** in **sorted order**.
- Implemented internally as a **balanced Red-Black Tree**.
- All insertions, deletions, and lookups take **O(log n)**.
- Elements **cannot be modified** after insertion (only erased/reinserted).
- Duplicates are not allowed.
- Maintains **ascending order** by default.
- Very useful for maintaining **sorted data, finding bounds, and uniqueness checks**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create set | `set<int> s;` | Empty ordered set | O(1) |
| Initialize | `set<int> s = {1,2,3};` | Initialize with values | O(n log n) |
| Insert | `s.insert(x);` | Adds element (only if not exists) | O(log n) |
| Emplace | `s.emplace(x);` | Faster insertion | O(log n) |
| Erase element | `s.erase(x);` | Remove specific element | O(log n) |
| Erase iterator | `s.erase(it);` | Remove via iterator | O(1) amortized |
| Find | `s.find(x);` | Returns iterator to element / `s.end()` | O(log n) |
| Count | `s.count(x);` | Returns 1 if exists else 0 | O(log n) |
| Size | `s.size();` | Total elements | O(1) |
| Empty | `s.empty();` | Check if empty | O(1) |
| Clear | `s.clear();` | Removes all elements | O(n) |
| Begin/End | `s.begin(), s.end()` | Iterators to traverse | O(1) |
| Lower bound | `s.lower_bound(x);` | First element ≥ x | O(log n) |
| Upper bound | `s.upper_bound(x);` | First element > x | O(log n) |
| Erase range | `s.erase(it1, it2);` | Remove elements in range | O(k log n) |
| Swap | `s1.swap(s2);` | Swaps two sets | O(1) |

---

### ⚖️ **Comparison with `unordered_set`**

| Feature | `set` | `unordered_set` |
| --- | --- | --- |
| Order | Sorted | Unordered |
| Implementation | Red-Black Tree | Hash Table |
| Duplicate elements | Not allowed | Not allowed |
| Time Complexity | O(log n) | O(1) average |
| Supports bounds | ✅ Yes | ❌ No |
| Use case | Sorted data, bounds | Fast lookups |

---

### 🧠 **LeetCode Problems Using `set`**

*(All levels — unique element maintenance, range queries, and bounds usage)*

### 🔹 **Beginner**

1. [#217 — Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
2. [#136 — Single Number](https://leetcode.com/problems/single-number/)
3. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
4. [#202 — Happy Number](https://leetcode.com/problems/happy-number/)
5. [#575 — Distribute Candies](https://leetcode.com/problems/distribute-candies/)
6. [#804 — Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/)
7. [#929 — Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses/)
8. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
9. [#219 — Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)
10. [#961 — N-Repeated Element in Size 2N Array](https://leetcode.com/problems/n-repeated-element-in-size-2n-array/)

### 🔸 **Intermediate**

1. [#220 — Contains Duplicate III](https://leetcode.com/problems/contains-duplicate-iii/)
2. [#295 — Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)
3. [#480 — Sliding Window Median](https://leetcode.com/problems/sliding-window-median/)
4. [#658 — Find K Closest Elements](https://leetcode.com/problems/find-k-closest-elements/)
5. [#846 — Hand of Straights](https://leetcode.com/problems/hand-of-straights/)
6. [#855 — Exam Room](https://leetcode.com/problems/exam-room/)
7. [#729 — My Calendar I](https://leetcode.com/problems/my-calendar-i/)
8. [#731 — My Calendar II](https://leetcode.com/problems/my-calendar-ii/)
9. [#855 — Seat Arrangement Optimization](https://leetcode.com/problems/exam-room/)
10. [#981 — Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)

### 🔺 **Advanced**

1. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
2. [#327 — Count of Range Sum](https://leetcode.com/problems/count-of-range-sum/)
3. [#220 — Sliding Window with Set](https://leetcode.com/problems/contains-duplicate-iii/)
4. [#218 — The Skyline Problem](https://leetcode.com/problems/the-skyline-problem/)
5. [#352 — Data Stream as Disjoint Intervals](https://leetcode.com/problems/data-stream-as-disjoint-intervals/)
6. [#715 — Range Module](https://leetcode.com/problems/range-module/)
7. [#855 — Exam Room (Advanced)](https://leetcode.com/problems/exam-room/)
8. [#1649 — Create Sorted Array through Instructions](https://leetcode.com/problems/create-sorted-array-through-instructions/)
9. [#493 — Reverse Pairs](https://leetcode.com/problems/reverse-pairs/)
10. [#295 — Median Maintenance with Multiset](https://leetcode.com/problems/find-median-from-data-stream/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    set<int> s = {5, 1, 4, 2, 3};

    // 2. Automatically sorted and unique
    cout << "Set elements: ";
    for (auto x : s) cout << x << " ";
    cout << "\n";

    // 3. Insert / Erase
    s.insert(6);
    s.erase(3);

    // 4. Find / Count
    if (s.find(4) != s.end()) cout << "4 found!\n";
    cout << "Count of 2: " << s.count(2) << "\n";

    // 5. Bounds
    auto it = s.lower_bound(4); // >= 4
    cout << "Lower bound of 4: " << *it << "\n";
    it = s.upper_bound(4); // > 4
    cout << "Upper bound of 4: " << *it << "\n";

    // 6. Example — Remove duplicates from array
    vector<int> arr = {1,2,2,3,4,4,5};
    set<int> uniq(arr.begin(), arr.end());
    cout << "Unique elements: ";
    for (auto x : uniq) cout << x << " ";
    cout << "\n";

    // 7. Example — Longest consecutive sequence
    int longest = 0;
    for (auto x : uniq) {
        if (!uniq.count(x - 1)) {
            int y = x;
            while (uniq.count(y)) y++;
            longest = max(longest, y - x);
        }
    }
    cout << "Longest consecutive length: " << longest << "\n";
}

```

**🧾 Output (Simplified):**

```
Set elements: 1 2 3 4 5
4 found!
Count of 2: 1
Lower bound of 4: 4
Upper bound of 4: 5
Unique elements: 1 2 3 4 5
Longest consecutive length: 5

```

---

---

## 🧩 **8. STL `multiset` — Complete Notes**

### 📘 **Concept Summary**

- `multiset` is similar to `set`, but it **allows duplicate elements**.
- Elements are stored in **sorted order (ascending by default)**.
- Implemented as a **balanced Red-Black Tree**.
- Supports **O(log n)** insertions, deletions, and searches.
- You **can’t modify** elements directly, but can erase specific instances.
- Great for problems needing **sorted collections with duplicates**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `multiset<int> ms;` | Empty multiset | O(1) |
| Initialize | `multiset<int> ms = {1,2,2,3};` | Allows duplicates | O(n log n) |
| Insert | `ms.insert(x);` | Adds element | O(log n) |
| Emplace | `ms.emplace(x);` | Faster insertion | O(log n) |
| Erase by value | `ms.erase(x);` | Removes **all** occurrences of x | O(k log n) |
| Erase by iterator | `ms.erase(it);` | Removes **one occurrence** | O(log n) |
| Count | `ms.count(x);` | Returns number of occurrences | O(log n) |
| Find | `ms.find(x);` | Iterator to first occurrence | O(log n) |
| Equal range | `auto [l, r] = ms.equal_range(x);` | Range of elements equal to x | O(log n) |
| Lower bound | `ms.lower_bound(x);` | First element ≥ x | O(log n) |
| Upper bound | `ms.upper_bound(x);` | First element > x | O(log n) |
| Size | `ms.size();` | Total elements | O(1) |
| Clear | `ms.clear();` | Remove all | O(n) |
| Empty | `ms.empty();` | Check empty | O(1) |

---

### ⚖️ **Comparison: `set` vs `multiset`**

| Feature | `set` | `multiset` |
| --- | --- | --- |
| Duplicates | ❌ Not allowed | ✅ Allowed |
| Count(x) | 0 or 1 | 0 or more |
| Erase(x) | Removes unique | Removes all x |
| Use case | Unique sorted data | Sorted data with duplicates |

---

### 🧠 **LeetCode Problems Using `multiset`**

*(Perfect for sliding windows, frequency control, and medians)*

### 🔹 **Beginner**

1. [#1046 — Last Stone Weight](https://leetcode.com/problems/last-stone-weight/)
2. [#1337 — The K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)
3. [#506 — Relative Ranks](https://leetcode.com/problems/relative-ranks/)
4. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#242 — Valid Anagram (alternate)](https://leetcode.com/problems/valid-anagram/)
6. [#2037 — Minimum Number of Moves to Seat Everyone](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/)
7. [#973 — K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/)
8. [#2161 — Partition Array According to Given Pivot](https://leetcode.com/problems/partition-array-according-to-given-pivot/)
9. [#2208 — Minimum Operations to Halve Array Sum](https://leetcode.com/problems/minimum-operations-to-halve-array-sum/)
10. [#1636 — Sort Array by Increasing Frequency](https://leetcode.com/problems/sort-array-by-increasing-frequency/)

### 🔸 **Intermediate**

1. [#480 — Sliding Window Median](https://leetcode.com/problems/sliding-window-median/)
2. [#295 — Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)
3. [#220 — Contains Duplicate III](https://leetcode.com/problems/contains-duplicate-iii/)
4. [#1438 — Longest Continuous Subarray With Absolute Diff ≤ Limit](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)
5. [#2034 — Stock Price Fluctuation](https://leetcode.com/problems/stock-price-fluctuation/)
6. [#480 — Balanced Sliding Window](https://leetcode.com/problems/sliding-window-median/)
7. [#846 — Hand of Straights](https://leetcode.com/problems/hand-of-straights/)
8. [#658 — Find K Closest Elements](https://leetcode.com/problems/find-k-closest-elements/)
9. [#1834 — Single-Threaded CPU](https://leetcode.com/problems/single-threaded-cpu/)
10. [#855 — Exam Room (duplicates allowed)](https://leetcode.com/problems/exam-room/)

### 🔺 **Advanced**

1. [#295 — Median of Data Stream (two multisets)](https://leetcode.com/problems/find-median-from-data-stream/)
2. [#480 — Sliding Window Median (dual multiset approach)](https://leetcode.com/problems/sliding-window-median/)
3. [#1438 — Monotonic Range Maintenance](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)
4. [#295 — Online Median Maintenance](https://leetcode.com/problems/find-median-from-data-stream/)
5. [#1642 — Furthest Building You Can Reach](https://leetcode.com/problems/furthest-building-you-can-reach/)
6. [#632 — Smallest Range Covering Elements from K Lists](https://leetcode.com/problems/smallest-range-covering-elements-from-k-lists/)
7. [#480 — Median Balancing Sliding Window](https://leetcode.com/problems/sliding-window-median/)
8. [#239 — Sliding Window Maximum (alternative)](https://leetcode.com/problems/sliding-window-maximum/)
9. [#220 — Duplicate Distance Check](https://leetcode.com/problems/contains-duplicate-iii/)
10. [#480 — Median Window (Advanced Implementation)](https://leetcode.com/problems/sliding-window-median/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    multiset<int> ms = {1, 2, 2, 3, 4, 4, 5};

    // 2. Display elements
    cout << "Multiset elements: ";
    for (auto x : ms) cout << x << " ";
    cout << "\n";

    // 3. Insert & Erase
    ms.insert(3);
    cout << "After inserting 3: ";
    for (auto x : ms) cout << x << " ";
    cout << "\n";

    // Erase all '2's
    ms.erase(2);
    cout << "After erasing 2s: ";
    for (auto x : ms) cout << x << " ";
    cout << "\n";

    // 4. Count & Find
    cout << "Count of 4: " << ms.count(4) << "\n";
    auto it = ms.find(4);
    if (it != ms.end()) cout << "Found: " << *it << "\n";

    // 5. Lower & Upper bounds
    cout << "Lower bound(3): " << *ms.lower_bound(3) << "\n";
    cout << "Upper bound(3): " << *ms.upper_bound(3) << "\n";

    // 6. Example — Sliding window median simulation
    vector<int> nums = {1, 3, -1, -3, 5, 3, 6, 7};
    int k = 3;
    multiset<int> window;

    for (int i = 0; i < nums.size(); i++) {
        window.insert(nums[i]);
        if (window.size() > k) window.erase(window.find(nums[i - k]));
        if (window.size() == k) {
            auto mid = next(window.begin(), k / 2);
            cout << "Median at i=" << i << ": " << *mid << "\n";
        }
    }
}

```

**🧾 Output (Simplified):**

```
Multiset elements: 1 2 2 3 4 4 5
After inserting 3: 1 2 2 3 3 4 4 5
After erasing 2s: 1 3 3 4 4 5
Count of 4: 2
Found: 4
Lower bound(3): 3
Upper bound(3): 4
Median at i=2: 1
Median at i=3: -1
...

```

---

---

## 🧩 **9. STL `map` — Complete Notes**

### 📘 **Concept Summary**

- `map` is an **ordered associative container** that stores **key–value pairs** in sorted order **by key**.
- Each **key is unique**, and every key maps to **exactly one value**.
- Implemented as a **balanced Red-Black Tree**.
- Operations like insertion, deletion, and lookup all take **O(log n)**.
- Automatically maintains keys in ascending order (custom comparators possible).
- Perfect for **frequency maps**, **coordinate compression**, **ranking**, **prefix counting**, etc.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create map | `map<int, int> mp;` | Empty map | O(1) |
| Initialize | `map<int, string> mp = {{1,"A"}, {2,"B"}};` | Initialize | O(n log n) |
| Insert | `mp.insert({key, val});` | Insert key–value | O(log n) |
| Emplace | `mp.emplace(key, val);` | Faster insertion | O(log n) |
| Access value | `mp[key];` | Returns value (inserts key if missing) | O(log n) |
| At | `mp.at(key);` | Access (throws if missing) | O(log n) |
| Erase by key | `mp.erase(key);` | Removes key | O(log n) |
| Erase by iterator | `mp.erase(it);` | Remove element | O(log n) |
| Find | `mp.find(key);` | Returns iterator to key or `end()` | O(log n) |
| Count | `mp.count(key);` | Returns 1 if exists else 0 | O(log n) |
| Size | `mp.size();` | No. of pairs | O(1) |
| Clear | `mp.clear();` | Removes all | O(n) |
| Begin/End | `mp.begin(), mp.end();` | Iterators | O(1) |
| Lower bound | `mp.lower_bound(k);` | ≥ key | O(log n) |
| Upper bound | `mp.upper_bound(k);` | > key | O(log n) |

---

### ⚖️ **Comparison: `map` vs `unordered_map`**

| Feature | `map` | `unordered_map` |
| --- | --- | --- |
| Order | Sorted | Unordered |
| Implementation | Red-Black Tree | Hash Table |
| Duplicates | ❌ Not allowed | ❌ Not allowed |
| Access time | O(log n) | O(1) average |
| Memory usage | Higher | Lower |
| Stable iteration order | ✅ Yes | ❌ No |
| Use case | Range queries, ordered data | Fast lookups |

---

### 🧠 **LeetCode Problems Using `map`**

*(All levels — key-value logic, frequency counting, and prefix/suffix handling)*

### 🔹 **Beginner**

1. [#1 — Two Sum](https://leetcode.com/problems/two-sum/)
2. [#387 — First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)
3. [#383 — Ransom Note](https://leetcode.com/problems/ransom-note/)
4. [#242 — Valid Anagram](https://leetcode.com/problems/valid-anagram/)
5. [#409 — Longest Palindrome](https://leetcode.com/problems/longest-palindrome/)
6. [#771 — Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/)
7. [#219 — Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)
8. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
9. [#290 — Word Pattern](https://leetcode.com/problems/word-pattern/)
10. [#205 — Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

### 🔸 **Intermediate**

1. [#451 — Sort Characters by Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
2. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
3. [#451 — Sort Characters by Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
4. [#890 — Find and Replace Pattern](https://leetcode.com/problems/find-and-replace-pattern/)
5. [#811 — Subdomain Visit Count](https://leetcode.com/problems/subdomain-visit-count/)
6. [#523 — Continuous Subarray Sum](https://leetcode.com/problems/continuous-subarray-sum/)
7. [#560 — Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
8. [#525 — Contiguous Array](https://leetcode.com/problems/contiguous-array/)
9. [#930 — Binary Subarrays With Sum](https://leetcode.com/problems/binary-subarrays-with-sum/)
10. [#974 — Subarray Sums Divisible by K](https://leetcode.com/problems/subarray-sums-divisible-by-k/)

### 🔺 **Advanced**

1. [#460 — LFU Cache](https://leetcode.com/problems/lfu-cache/)
2. [#146 — LRU Cache](https://leetcode.com/problems/lru-cache/)
3. [#981 — Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)
4. [#1171 — Remove Zero Sum Consecutive Nodes](https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/)
5. [#1679 — Max Number of K-Sum Pairs](https://leetcode.com/problems/max-number-of-k-sum-pairs/)
6. [#1396 — Design Underground System](https://leetcode.com/problems/design-underground-system/)
7. [#2349 — Design a Number Container System](https://leetcode.com/problems/design-a-number-container-system/)
8. [#953 — Verifying an Alien Dictionary](https://leetcode.com/problems/verifying-an-alien-dictionary/)
9. [#1152 — Analyze User Website Visit Pattern](https://leetcode.com/problems/analyze-user-website-visit-pattern/)
10. [#139 — Word Break](https://leetcode.com/problems/word-break/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    map<int, string> mp;
    mp[1] = "Apple";
    mp[2] = "Banana";
    mp[3] = "Cherry";

    // 2. Iteration
    cout << "Map contents:\n";
    for (auto &p : mp) {
        cout << p.first << " -> " << p.second << "\n";
    }

    // 3. Insert and Erase
    mp.insert({4, "Date"});
    mp.erase(2); // removes Banana

    // 4. Find and Count
    if (mp.find(3) != mp.end())
        cout << "Key 3 exists with value: " << mp[3] << "\n";
    cout << "Count of key 2: " << mp.count(2) << "\n";

    // 5. Bounds
    auto it = mp.lower_bound(2);
    if (it != mp.end()) cout << "Lower bound(2): " << it->first << "\n";

    // 6. Example — Frequency Count
    string str = "hello";
    map<char, int> freq;
    for (char c : str) freq[c]++;

    cout << "Character frequencies:\n";
    for (auto &p : freq)
        cout << p.first << " -> " << p.second << "\n";

    // 7. Example — Subarray sum equals k
    vector<int> nums = {1, 1, 1};
    int k = 2;
    map<int, int> prefix;
    prefix[0] = 1;
    int sum = 0, cnt = 0;

    for (int n : nums) {
        sum += n;
        if (prefix.count(sum - k)) cnt += prefix[sum - k];
        prefix[sum]++;
    }
    cout << "Subarrays with sum = " << k << ": " << cnt << "\n";
}

```

**🧾 Output (Simplified):**

```
Map contents:
1 -> Apple
2 -> Banana
3 -> Cherry
Key 3 exists with value: Cherry
Count of key 2: 0
Lower bound(2): 3
Character frequencies:
e -> 1
h -> 1
l -> 2
o -> 1
Subarrays with sum = 2: 2

```

---

---

## 🧩 **10. STL `multimap` — Complete Notes**

### 📘 **Concept Summary**

- `multimap` is similar to `map`, **but allows duplicate keys**.
- Stores elements in **sorted order by key** (ascending by default).
- Each key can have **multiple values**.
- Internally implemented as a **balanced Red-Black Tree**.
- Useful when one key is associated with **multiple values** — e.g.,
    - student → multiple subjects
    - word → multiple positions
    - price → multiple products

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `multimap<int, string> mm;` | Empty multimap | O(1) |
| Initialize | `multimap<int, string> mm = {{1,"A"}, {2,"B"}, {1,"C"}};` | Allows duplicate keys | O(n log n) |
| Insert | `mm.insert({key, val});` | Adds key-value | O(log n) |
| Emplace | `mm.emplace(key, val);` | Faster insert | O(log n) |
| Erase by key | `mm.erase(key);` | Removes **all pairs** with that key | O(k log n) |
| Erase by iterator | `mm.erase(it);` | Removes one element | O(log n) |
| Find | `mm.find(key);` | Returns iterator to first match | O(log n) |
| Count | `mm.count(key);` | Number of entries for key | O(log n) |
| Equal range | `auto [l, r] = mm.equal_range(key);` | Range of duplicates | O(log n) |
| Lower/Upper bound | `mm.lower_bound(k);`, `mm.upper_bound(k);` | Range lookup | O(log n) |
| Size | `mm.size();` | Number of pairs | O(1) |
| Empty | `mm.empty();` | Check empty | O(1) |
| Clear | `mm.clear();` | Removes all | O(n) |

---

### ⚖️ **Comparison: `map` vs `multimap`**

| Feature | `map` | `multimap` |
| --- | --- | --- |
| Duplicates | ❌ Not allowed | ✅ Allowed |
| Access using `[]` | ✅ Yes | ❌ No |
| Insert same key | Ignored | Accepted |
| Find returns | Unique element | First of duplicates |
| Use case | Unique mapping | One-to-many mapping |

---

### 🧠 **LeetCode Problems Using `multimap`**

*(Ideal for duplicate-key relationships, sorting by multiple attributes, and grouped storage)*

### 🔹 **Beginner**

1. [#1 — Two Sum (grouped by value)](https://leetcode.com/problems/two-sum/)
2. [#350 — Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
3. [#387 — First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)
4. [#451 — Sort Characters by Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
5. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
6. [#953 — Verifying an Alien Dictionary](https://leetcode.com/problems/verifying-an-alien-dictionary/)
7. [#179 — Largest Number](https://leetcode.com/problems/largest-number/)
8. [#1331 — Rank Transform of an Array](https://leetcode.com/problems/rank-transform-of-an-array/)
9. [#506 — Relative Ranks](https://leetcode.com/problems/relative-ranks/)
10. [#720 — Longest Word in Dictionary](https://leetcode.com/problems/longest-word-in-dictionary/)

### 🔸 **Intermediate**

1. [#692 — Top K Frequent Words](https://leetcode.com/problems/top-k-frequent-words/)
2. [#811 — Subdomain Visit Count](https://leetcode.com/problems/subdomain-visit-count/)
3. [#451 — Frequency Sort (key = freq)](https://leetcode.com/problems/sort-characters-by-frequency/)
4. [#347 — Top K Frequent Elements (value grouping)](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#721 — Accounts Merge](https://leetcode.com/problems/accounts-merge/)
6. [#981 — Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)
7. [#1337 — K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)
8. [#692 — Sort Words by Frequency](https://leetcode.com/problems/top-k-frequent-words/)
9. [#811 — Subdomain Visit Count (duplicate keys)](https://leetcode.com/problems/subdomain-visit-count/)
10. [#133 — Clone Graph (multi-mapping neighbors)](https://leetcode.com/problems/clone-graph/)

### 🔺 **Advanced**

1. [#269 — Alien Dictionary](https://leetcode.com/problems/alien-dictionary/)
2. [#987 — Vertical Order Traversal of Binary Tree](https://leetcode.com/problems/vertical-order-traversal-of-a-binary-tree/)
3. [#355 — Design Twitter](https://leetcode.com/problems/design-twitter/)
4. [#981 — Time Based Key-Value Store (multiple timestamps)](https://leetcode.com/problems/time-based-key-value-store/)
5. [#218 — The Skyline Problem](https://leetcode.com/problems/the-skyline-problem/)
6. [#588 — Design In-Memory File System](https://leetcode.com/problems/design-in-memory-file-system/)
7. [#2034 — Stock Price Fluctuation](https://leetcode.com/problems/stock-price-fluctuation/)
8. [#1268 — Search Suggestions System](https://leetcode.com/problems/search-suggestions-system/)
9. [#850 — Rectangle Area II (coordinate grouping)](https://leetcode.com/problems/rectangle-area-ii/)
10. [#981 — Time-Based Key-Value Store (multi-entries)](https://leetcode.com/problems/time-based-key-value-store/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    multimap<int, string> mm = {
        {1, "A"}, {2, "B"}, {1, "C"}, {3, "D"}, {2, "E"}
    };

    // 2. Display all elements
    cout << "Multimap contents:\n";
    for (auto &p : mm)
        cout << p.first << " -> " << p.second << "\n";

    // 3. Count and Find
    cout << "Count of key=1: " << mm.count(1) << "\n";
    auto it = mm.find(2);
    if (it != mm.end()) cout << "First element with key=2: " << it->second << "\n";

    // 4. Equal Range (get all values for a key)
    auto range = mm.equal_range(2);
    cout << "All values for key=2: ";
    for (auto i = range.first; i != range.second; ++i)
        cout << i->second << " ";
    cout << "\n";

    // 5. Erase by key
    mm.erase(1);
    cout << "After erasing key=1:\n";
    for (auto &p : mm) cout << p.first << " -> " << p.second << "\n";

    // 6. Example — Group students by marks
    multimap<int, string> marks;
    marks.insert({90, "Vinay"});
    marks.insert({85, "Kiran"});
    marks.insert({90, "Ravi"});
    marks.insert({70, "Sita"});

    cout << "\nStudents grouped by marks:\n";
    for (auto &p : marks)
        cout << p.first << " -> " << p.second << "\n";
}

```

**🧾 Output (Simplified):**

```
Multimap contents:
1 -> A
1 -> C
2 -> B
2 -> E
3 -> D
Count of key=1: 2
First element with key=2: B
All values for key=2: B E
After erasing key=1:
2 -> B
2 -> E
3 -> D

Students grouped by marks:
70 -> Sita
85 -> Kiran
90 -> Ravi
90 -> Vinay

```

---

Perfect ⚙️ Vinay — continuing your **STL Master Notes series**, here’s the **Notion-ready `multimap`** section 👇

This one’s great for grouped data, inverse lookups, and duplicate key management (commonly used in database-style mappings, reverse associations, and frequency bins).

---

## 🧩 **10. STL `multimap` — Complete Notes**

### 📘 **Concept Summary**

- `multimap` is similar to `map`, **but allows duplicate keys**.
- Stores elements in **sorted order by key** (ascending by default).
- Each key can have **multiple values**.
- Internally implemented as a **balanced Red-Black Tree**.
- Useful when one key is associated with **multiple values** — e.g.,
    - student → multiple subjects
    - word → multiple positions
    - price → multiple products

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `multimap<int, string> mm;` | Empty multimap | O(1) |
| Initialize | `multimap<int, string> mm = {{1,"A"}, {2,"B"}, {1,"C"}};` | Allows duplicate keys | O(n log n) |
| Insert | `mm.insert({key, val});` | Adds key-value | O(log n) |
| Emplace | `mm.emplace(key, val);` | Faster insert | O(log n) |
| Erase by key | `mm.erase(key);` | Removes **all pairs** with that key | O(k log n) |
| Erase by iterator | `mm.erase(it);` | Removes one element | O(log n) |
| Find | `mm.find(key);` | Returns iterator to first match | O(log n) |
| Count | `mm.count(key);` | Number of entries for key | O(log n) |
| Equal range | `auto [l, r] = mm.equal_range(key);` | Range of duplicates | O(log n) |
| Lower/Upper bound | `mm.lower_bound(k);`, `mm.upper_bound(k);` | Range lookup | O(log n) |
| Size | `mm.size();` | Number of pairs | O(1) |
| Empty | `mm.empty();` | Check empty | O(1) |
| Clear | `mm.clear();` | Removes all | O(n) |

---

### ⚖️ **Comparison: `map` vs `multimap`**

| Feature | `map` | `multimap` |
| --- | --- | --- |
| Duplicates | ❌ Not allowed | ✅ Allowed |
| Access using `[]` | ✅ Yes | ❌ No |
| Insert same key | Ignored | Accepted |
| Find returns | Unique element | First of duplicates |
| Use case | Unique mapping | One-to-many mapping |

---

### 🧠 **LeetCode Problems Using `multimap`**

*(Ideal for duplicate-key relationships, sorting by multiple attributes, and grouped storage)*

### 🔹 **Beginner**

1. [#1 — Two Sum (grouped by value)](https://leetcode.com/problems/two-sum/)
2. [#350 — Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
3. [#387 — First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)
4. [#451 — Sort Characters by Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
5. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
6. [#953 — Verifying an Alien Dictionary](https://leetcode.com/problems/verifying-an-alien-dictionary/)
7. [#179 — Largest Number](https://leetcode.com/problems/largest-number/)
8. [#1331 — Rank Transform of an Array](https://leetcode.com/problems/rank-transform-of-an-array/)
9. [#506 — Relative Ranks](https://leetcode.com/problems/relative-ranks/)
10. [#720 — Longest Word in Dictionary](https://leetcode.com/problems/longest-word-in-dictionary/)

### 🔸 **Intermediate**

1. [#692 — Top K Frequent Words](https://leetcode.com/problems/top-k-frequent-words/)
2. [#811 — Subdomain Visit Count](https://leetcode.com/problems/subdomain-visit-count/)
3. [#451 — Frequency Sort (key = freq)](https://leetcode.com/problems/sort-characters-by-frequency/)
4. [#347 — Top K Frequent Elements (value grouping)](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#721 — Accounts Merge](https://leetcode.com/problems/accounts-merge/)
6. [#981 — Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)
7. [#1337 — K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)
8. [#692 — Sort Words by Frequency](https://leetcode.com/problems/top-k-frequent-words/)
9. [#811 — Subdomain Visit Count (duplicate keys)](https://leetcode.com/problems/subdomain-visit-count/)
10. [#133 — Clone Graph (multi-mapping neighbors)](https://leetcode.com/problems/clone-graph/)

### 🔺 **Advanced**

1. [#269 — Alien Dictionary](https://leetcode.com/problems/alien-dictionary/)
2. [#987 — Vertical Order Traversal of Binary Tree](https://leetcode.com/problems/vertical-order-traversal-of-a-binary-tree/)
3. [#355 — Design Twitter](https://leetcode.com/problems/design-twitter/)
4. [#981 — Time Based Key-Value Store (multiple timestamps)](https://leetcode.com/problems/time-based-key-value-store/)
5. [#218 — The Skyline Problem](https://leetcode.com/problems/the-skyline-problem/)
6. [#588 — Design In-Memory File System](https://leetcode.com/problems/design-in-memory-file-system/)
7. [#2034 — Stock Price Fluctuation](https://leetcode.com/problems/stock-price-fluctuation/)
8. [#1268 — Search Suggestions System](https://leetcode.com/problems/search-suggestions-system/)
9. [#850 — Rectangle Area II (coordinate grouping)](https://leetcode.com/problems/rectangle-area-ii/)
10. [#981 — Time-Based Key-Value Store (multi-entries)](https://leetcode.com/problems/time-based-key-value-store/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    multimap<int, string> mm = {
        {1, "A"}, {2, "B"}, {1, "C"}, {3, "D"}, {2, "E"}
    };

    // 2. Display all elements
    cout << "Multimap contents:\n";
    for (auto &p : mm)
        cout << p.first << " -> " << p.second << "\n";

    // 3. Count and Find
    cout << "Count of key=1: " << mm.count(1) << "\n";
    auto it = mm.find(2);
    if (it != mm.end()) cout << "First element with key=2: " << it->second << "\n";

    // 4. Equal Range (get all values for a key)
    auto range = mm.equal_range(2);
    cout << "All values for key=2: ";
    for (auto i = range.first; i != range.second; ++i)
        cout << i->second << " ";
    cout << "\n";

    // 5. Erase by key
    mm.erase(1);
    cout << "After erasing key=1:\n";
    for (auto &p : mm) cout << p.first << " -> " << p.second << "\n";

    // 6. Example — Group students by marks
    multimap<int, string> marks;
    marks.insert({90, "Vinay"});
    marks.insert({85, "Kiran"});
    marks.insert({90, "Ravi"});
    marks.insert({70, "Sita"});

    cout << "\nStudents grouped by marks:\n";
    for (auto &p : marks)
        cout << p.first << " -> " << p.second << "\n";
}

```

**🧾 Output (Simplified):**

```
Multimap contents:
1 -> A
1 -> C
2 -> B
2 -> E
3 -> D
Count of key=1: 2
First element with key=2: B
All values for key=2: B E
After erasing key=1:
2 -> B
2 -> E
3 -> D

Students grouped by marks:
70 -> Sita
85 -> Kiran
90 -> Ravi
90 -> Vinay

```

---

---

## 🧩 **11. STL `unordered_map` — Complete Notes**

### 📘 **Concept Summary**

- `unordered_map` stores **key–value pairs** with **unique keys**, like `map`.
- But unlike `map`, elements are **not stored in sorted order**.
- Internally implemented as a **hash table** → average **O(1)** lookups, insertions, and deletions.
- Order of traversal is **unpredictable**.
- Allows **custom hash functions** (for pairs, strings, structs).
- Ideal when order doesn’t matter and **speed is the priority**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `unordered_map<int, string> mp;` | Empty hash map | O(1) |
| Initialize | `unordered_map<int, string> mp = {{1,"A"}, {2,"B"}};` | Initialize | O(n) |
| Insert | `mp.insert({key, val});` | Add new key–value pair | O(1) average |
| Emplace | `mp.emplace(key, val);` | Faster insertion | O(1) |
| Access | `mp[key];` | Access value (creates default if missing) | O(1) |
| At | `mp.at(key);` | Access existing key safely | O(1) |
| Erase by key | `mp.erase(key);` | Remove key | O(1) |
| Find | `mp.find(key);` | Iterator to key or `end()` | O(1) |
| Count | `mp.count(key);` | Returns 1 if key exists | O(1) |
| Size | `mp.size();` | No. of elements | O(1) |
| Empty | `mp.empty();` | Check empty | O(1) |
| Clear | `mp.clear();` | Remove all | O(n) |
| Bucket count | `mp.bucket_count();` | No. of hash buckets | O(1) |
| Load factor | `mp.load_factor();` | Density measure | O(1) |
| Rehash | `mp.rehash(n);` | Change bucket count | O(n) |

---

### ⚖️ **Comparison: `map` vs `unordered_map`**

| Feature | `map` | `unordered_map` |
| --- | --- | --- |
| Order | Sorted | Unordered |
| Implementation | Red-Black Tree | Hash Table |
| Time complexity | O(log n) | O(1) average |
| Space usage | Lower | Higher |
| Iteration order | Sorted | Random |
| Duplicate keys | ❌ Not allowed | ❌ Not allowed |
| Best for | Ordered data, range queries | Fast lookup, frequency maps |

---

### ⚡ **Key Internals**

- Uses **hashing + chaining** for collisions.
- Avoid using `unordered_map` with custom objects **without proper hash functions**.
- In rare worst cases (many collisions), operations degrade to **O(n)**.

---

### 🧠 **LeetCode Problems Using `unordered_map`**

*(All levels — frequency, prefix sums, counting, and caching)*

### 🔹 **Beginner**

1. [#1 — Two Sum](https://leetcode.com/problems/two-sum/)
2. [#242 — Valid Anagram](https://leetcode.com/problems/valid-anagram/)
3. [#383 — Ransom Note](https://leetcode.com/problems/ransom-note/)
4. [#387 — First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)
5. [#409 — Longest Palindrome](https://leetcode.com/problems/longest-palindrome/)
6. [#771 — Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/)
7. [#136 — Single Number](https://leetcode.com/problems/single-number/)
8. [#217 — Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
9. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
10. [#219 — Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)

### 🔸 **Intermediate**

1. [#560 — Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
2. [#523 — Continuous Subarray Sum](https://leetcode.com/problems/continuous-subarray-sum/)
3. [#525 — Contiguous Array](https://leetcode.com/problems/contiguous-array/)
4. [#974 — Subarray Sums Divisible by K](https://leetcode.com/problems/subarray-sums-divisible-by-k/)
5. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
6. [#290 — Word Pattern](https://leetcode.com/problems/word-pattern/)
7. [#205 — Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)
8. [#811 — Subdomain Visit Count](https://leetcode.com/problems/subdomain-visit-count/)
9. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
10. [#554 — Brick Wall](https://leetcode.com/problems/brick-wall/)

### 🔺 **Advanced**

1. [#146 — LRU Cache](https://leetcode.com/problems/lru-cache/)
2. [#460 — LFU Cache](https://leetcode.com/problems/lfu-cache/)
3. [#981 — Time-Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)
4. [#139 — Word Break](https://leetcode.com/problems/word-break/)
5. [#187 — Repeated DNA Sequences](https://leetcode.com/problems/repeated-dna-sequences/)
6. [#954 — Array of Doubled Pairs](https://leetcode.com/problems/array-of-doubled-pairs/)
7. [#2034 — Stock Price Fluctuation](https://leetcode.com/problems/stock-price-fluctuation/)
8. [#992 — Subarrays with K Different Integers](https://leetcode.com/problems/subarrays-with-k-different-integers/)
9. [#1282 — Group the People Given Group Size](https://leetcode.com/problems/group-the-people-given-the-group-size-they-belong-to/)
10. [#1152 — Analyze User Website Visit Pattern](https://leetcode.com/problems/analyze-user-website-visit-pattern/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    unordered_map<string, int> freq = {
        {"apple", 3},
        {"banana", 5},
        {"cherry", 2}
    };

    // 2. Insert / Update
    freq["apple"]++;       // increment value
    freq["mango"] = 7;     // add new key

    // 3. Iteration (unordered)
    cout << "Fruits frequency:\n";
    for (auto &p : freq)
        cout << p.first << " -> " << p.second << "\n";

    // 4. Find & Count
    if (freq.find("banana") != freq.end())
        cout << "Banana count: " << freq["banana"] << "\n";
    cout << "Contains apple? " << (freq.count("apple") ? "Yes" : "No") << "\n";

    // 5. Erase
    freq.erase("cherry");

    // 6. Example — Two Sum
    vector<int> nums = {2, 7, 11, 15};
    int target = 9;
    unordered_map<int, int> mp; // value -> index

    for (int i = 0; i < nums.size(); i++) {
        int diff = target - nums[i];
        if (mp.count(diff)) {
            cout << "Two Sum indices: " << mp[diff] << ", " << i << "\n";
            break;
        }
        mp[nums[i]] = i;
    }

    // 7. Example — Subarray Sum Equals K
    vector<int> arr = {1, 1, 1};
    int k = 2, sum = 0, cnt = 0;
    unordered_map<int, int> prefix;
    prefix[0] = 1;

    for (int n : arr) {
        sum += n;
        if (prefix.count(sum - k)) cnt += prefix[sum - k];
        prefix[sum]++;
    }
    cout << "Subarrays with sum = " << k << ": " << cnt << "\n";
}

```

**🧾 Output (Simplified):**

```
Fruits frequency:
banana -> 5
apple -> 4
mango -> 7
Contains apple? Yes
Banana count: 5
Two Sum indices: 0, 1
Subarrays with sum = 2: 2

```

---

---

## 🧩 **12. STL `unordered_set` — Complete Notes**

### 📘 **Concept Summary**

- `unordered_set` stores **unique elements** in **no particular order**.
- Internally implemented as a **hash table**, unlike `set` which uses a tree.
- Provides **average O(1)** complexity for `insert`, `find`, and `erase`.
- No duplicate elements allowed.
- No order — elements are stored based on hash values.
- Perfect for **fast lookups**, **membership tests**, and **duplicate removal**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `unordered_set<int> s;` | Empty hash set | O(1) |
| Initialize | `unordered_set<int> s = {1,2,3};` | Initialize with values | O(n) |
| Insert | `s.insert(x);` | Add element | O(1) average |
| Emplace | `s.emplace(x);` | Faster insert | O(1) |
| Erase | `s.erase(x);` | Remove element | O(1) average |
| Find | `s.find(x);` | Returns iterator or `end()` | O(1) |
| Count | `s.count(x);` | 1 if exists, else 0 | O(1) |
| Size | `s.size();` | No. of elements | O(1) |
| Empty | `s.empty();` | Check if empty | O(1) |
| Clear | `s.clear();` | Remove all elements | O(n) |
| Bucket count | `s.bucket_count();` | No. of hash buckets | O(1) |
| Load factor | `s.load_factor();` | Measure of density | O(1) |
| Rehash | `s.rehash(n);` | Reorganize hash table | O(n) |

---

### ⚖️ **Comparison: `set` vs `unordered_set`**

| Feature | `set` | `unordered_set` |
| --- | --- | --- |
| Order | Sorted | Unordered |
| Implementation | Red-Black Tree | Hash Table |
| Duplicates | ❌ Not allowed | ❌ Not allowed |
| Lookup speed | O(log n) | O(1) average |
| Supports bounds | ✅ Yes | ❌ No |
| Best for | Ordered data, bounds queries | Fast lookups and existence checks |

---

### ⚡ **Key Notes**

- Elements **cannot be modified** (only erased/reinserted).
- If many elements hash to same bucket, performance degrades to **O(n)** worst case.
- **Does not maintain insertion or sorted order.**
- Works great for:
    - Removing duplicates
    - Checking existence (e.g., seen elements)
    - Fast membership tests in large datasets

---

### 🧠 **LeetCode Problems Using `unordered_set`**

*(All levels — mostly existence, duplicates, and uniqueness problems)*

### 🔹 **Beginner**

1. [#217 — Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
2. [#136 — Single Number](https://leetcode.com/problems/single-number/)
3. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
4. [#202 — Happy Number](https://leetcode.com/problems/happy-number/)
5. [#575 — Distribute Candies](https://leetcode.com/problems/distribute-candies/)
6. [#804 — Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/)
7. [#929 — Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses/)
8. [#349 — Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
9. [#219 — Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)
10. [#2351 — First Letter to Appear Twice](https://leetcode.com/problems/first-letter-to-appear-twice/)

### 🔸 **Intermediate**

1. [#3 — Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
2. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
3. [#36 — Valid Sudoku](https://leetcode.com/problems/valid-sudoku/)
4. [#187 — Repeated DNA Sequences](https://leetcode.com/problems/repeated-dna-sequences/)
5. [#349 — Array Intersection](https://leetcode.com/problems/intersection-of-two-arrays/)
6. [#141 — Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
7. [#142 — Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
8. [#219 — Contains Duplicate II (Sliding Window)](https://leetcode.com/problems/contains-duplicate-ii/)
9. [#220 — Contains Duplicate III (Hash + Window)](https://leetcode.com/problems/contains-duplicate-iii/)
10. [#532 — K-diff Pairs in an Array](https://leetcode.com/problems/k-diff-pairs-in-an-array/)

### 🔺 **Advanced**

1. [#355 — Design Twitter](https://leetcode.com/problems/design-twitter/)
2. [#355 — Social Network Graph Storage](https://leetcode.com/problems/design-twitter/)
3. [#149 — Max Points on a Line](https://leetcode.com/problems/max-points-on-a-line/)
4. [#939 — Minimum Area Rectangle](https://leetcode.com/problems/minimum-area-rectangle/)
5. [#489 — Robot Room Cleaner](https://leetcode.com/problems/robot-room-cleaner/)
6. [#753 — Cracking the Safe](https://leetcode.com/problems/cracking-the-safe/)
7. [#403 — Frog Jump](https://leetcode.com/problems/frog-jump/)
8. [#126 — Word Ladder II](https://leetcode.com/problems/word-ladder-ii/)
9. [#980 — Unique Paths III](https://leetcode.com/problems/unique-paths-iii/)
10. [#212 — Word Search II](https://leetcode.com/problems/word-search-ii/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    unordered_set<int> s = {1, 2, 3, 2, 1};

    // 2. Unique + unordered
    cout << "Unordered set elements: ";
    for (auto x : s) cout << x << " ";
    cout << "\n";

    // 3. Insert / Erase
    s.insert(5);
    s.erase(2);

    // 4. Find / Count
    if (s.find(3) != s.end()) cout << "3 is present!\n";
    cout << "Count of 5: " << s.count(5) << "\n";

    // 5. Example — Remove duplicates from array
    vector<int> nums = {1, 2, 2, 3, 4, 4, 5};
    unordered_set<int> uniq(nums.begin(), nums.end());
    cout << "Unique array: ";
    for (auto x : uniq) cout << x << " ";
    cout << "\n";

    // 6. Example — Longest Consecutive Sequence
    vector<int> arr = {100, 4, 200, 1, 3, 2};
    unordered_set<int> hs(arr.begin(), arr.end());
    int longest = 0;

    for (auto x : hs) {
        if (!hs.count(x - 1)) { // start of sequence
            int y = x;
            while (hs.count(y)) y++;
            longest = max(longest, y - x);
        }
    }
    cout << "Longest consecutive length: " << longest << "\n";
}

```

**🧾 Output (Simplified):**

```
Unordered set elements: 3 1 2
3 is present!
Count of 5: 1
Unique array: 5 4 3 2 1
Longest consecutive length: 4

```

---

---

## 🧩 **13. STL `stack` — Complete Notes**

### 📘 **Concept Summary**

- `stack` is a **container adapter** that follows **LIFO (Last In, First Out)** principle.
- Defined in `<stack>` header.
- You can only **access the top element**, not random indices.
- Default underlying container: **`deque`** (can also use `vector` or `list`).
- Excellent for:
    - Expression evaluation (`(), {}, []`)
    - DFS, recursion simulations
    - Monotonic stacks (for next greater/smaller problems)

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `stack<int> st;` | Empty stack | O(1) |
| Push | `st.push(x);` | Insert at top | O(1) |
| Emplace | `st.emplace(x);` | Faster insertion | O(1) |
| Pop | `st.pop();` | Remove top element | O(1) |
| Top | `st.top();` | Access top element | O(1) |
| Size | `st.size();` | No. of elements | O(1) |
| Empty | `st.empty();` | Check if empty | O(1) |
| Swap | `st1.swap(st2);` | Swap two stacks | O(1) |

---

### ⚖️ **Key Notes**

- You can **iterate only by popping** (no iterators).
- If you need iteration → use `vector` or `deque` instead.
- Can be initialized with another container:
    
    ```cpp
    stack<int, vector<int>> s; // uses vector internally
    
    ```
    

---

### 🧠 **LeetCode Problems Using `stack`**

*(All levels — parentheses, monotonic stacks, evaluation problems)*

### 🔹 **Beginner**

1. [#20 — Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)
2. [#155 — Min Stack](https://leetcode.com/problems/min-stack/)
3. [#844 — Backspace String Compare](https://leetcode.com/problems/backspace-string-compare/)
4. [#1021 — Remove Outermost Parentheses](https://leetcode.com/problems/remove-outermost-parentheses/)
5. [#1047 — Remove All Adjacent Duplicates In String](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/)
6. [#232 — Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/)
7. [#225 — Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)
8. [#682 — Baseball Game](https://leetcode.com/problems/baseball-game/)
9. [#844 — String Backspace Compare](https://leetcode.com/problems/backspace-string-compare/)
10. [#1003 — Check If Word Is Valid After Substitutions](https://leetcode.com/problems/check-if-word-is-valid-after-substitutions/)

### 🔸 **Intermediate**

1. [#394 — Decode String](https://leetcode.com/problems/decode-string/)
2. [#739 — Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)
3. [#496 — Next Greater Element I](https://leetcode.com/problems/next-greater-element-i/)
4. [#503 — Next Greater Element II](https://leetcode.com/problems/next-greater-element-ii/)
5. [#901 — Online Stock Span](https://leetcode.com/problems/online-stock-span/)
6. [#316 — Remove Duplicate Letters](https://leetcode.com/problems/remove-duplicate-letters/)
7. [#402 — Remove K Digits](https://leetcode.com/problems/remove-k-digits/)
8. [#907 — Sum of Subarray Minimums](https://leetcode.com/problems/sum-of-subarray-minimums/)
9. [#739 — Monotonic Stack Practice](https://leetcode.com/problems/daily-temperatures/)
10. [#1475 — Final Prices With a Special Discount](https://leetcode.com/problems/final-prices-with-a-special-discount-in-a-shop/)

### 🔺 **Advanced**

1. [#84 — Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/)
2. [#85 — Maximal Rectangle](https://leetcode.com/problems/maximal-rectangle/)
3. [#316 — Remove Duplicate Letters](https://leetcode.com/problems/remove-duplicate-letters/)
4. [#856 — Score of Parentheses](https://leetcode.com/problems/score-of-parentheses/)
5. [#739 — Monotonic Stack Optimized](https://leetcode.com/problems/daily-temperatures/)
6. [#2104 — Sum of Subarray Ranges](https://leetcode.com/problems/sum-of-subarray-ranges/)
7. [#321 — Create Maximum Number](https://leetcode.com/problems/create-maximum-number/)
8. [#42 — Trapping Rain Water (stack variant)](https://leetcode.com/problems/trapping-rain-water/)
9. [#84 — Histogram Stack Pattern](https://leetcode.com/problems/largest-rectangle-in-histogram/)
10. [#735 — Asteroid Collision](https://leetcode.com/problems/asteroid-collision/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    stack<int> st;

    // 2. Push / Pop
    st.push(10);
    st.push(20);
    st.push(30);
    cout << "Top element: " << st.top() << "\n"; // 30
    st.pop();
    cout << "After pop, Top: " << st.top() << "\n"; // 20

    // 3. Size and Empty
    cout << "Size: " << st.size() << "\n";
    cout << "Empty? " << (st.empty() ? "Yes" : "No") << "\n";

    // 4. Example — Reverse a string using stack
    string s = "Vinay";
    stack<char> stk;
    for (char c : s) stk.push(c);
    string rev;
    while (!stk.empty()) {
        rev += stk.top();
        stk.pop();
    }
    cout << "Reversed string: " << rev << "\n";

    // 5. Example — Valid Parentheses
    string str = "{[()]}";
    stack<char> stc;
    bool valid = true;
    for (char c : str) {
        if (c == '(' || c == '[' || c == '{')
            stc.push(c);
        else {
            if (stc.empty() || (c == ')' && stc.top() != '(') ||
                (c == ']' && stc.top() != '[') ||
                (c == '}' && stc.top() != '{')) {
                valid = false; break;
            }
            stc.pop();
        }
    }
    cout << "Valid parentheses? " << (valid && stc.empty() ? "Yes" : "No") << "\n";
}

```

**🧾 Output (Simplified):**

```
Top element: 30
After pop, Top: 20
Size: 2
Empty? No
Reversed string: yanaV
Valid parentheses? Yes

```

---

---

## 🧩 **14. STL `pair` — Complete Notes**

### 📘 **Concept Summary**

- `pair` is a simple container that stores **two values** of possibly different types.
- Defined in `<utility>` (or available via `<bits/stdc++.h>`).
- Commonly used for:
    - Returning two values from a function
    - Representing coordinates `(x, y)`
    - Storing key-value relationships temporarily
    - Sorting + mapping problems

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `pair<int, string> p;` | Empty pair | O(1) |
| Initialize | `pair<int, string> p(1, "Vinay");` | Direct init | O(1) |
| Using braces | `pair<int, string> p = {1, "Vinay"};` | Uniform init | O(1) |
| Make pair | `auto p = make_pair(1, "AI");` | Type inference | O(1) |
| Access | `p.first`, `p.second` | Access elements | O(1) |
| Swap | `p1.swap(p2);` | Swap pairs | O(1) |
| Comparison | `p1 < p2` | Lexicographic compare | O(1) |
| Nested | `pair<int, pair<int,int>> p;` | Pair of pairs | O(1) |
| In array/vector | `vector<pair<int,int>> vp;` | Useful for sorting | O(1) |

---

### ⚡ **Lexicographical Comparison**

- Comparison works like dictionary order:
    
    1️⃣ Compare `first`
    
    2️⃣ If equal, compare `second`
    

Example:

```cpp
pair<int,int> a = {1,3};
pair<int,int> b = {1,4};
cout << (a < b); // true

```

---

### 💡 **Usage Patterns**

| Use Case | Example |
| --- | --- |
| Coordinate representation | `pair<int,int> point = {x, y};` |
| Storing frequency | `pair<int,int> freq = {num, count};` |
| Sorting with values | `vector<pair<int,int>> arr; sort(arr.begin(), arr.end());` |
| Priority queue with pair | `priority_queue<pair<int,int>> pq;` |
| Mapping graph edges | `vector<pair<int,int>> edges;` |
| Nested pairs | `pair<int, pair<int,int>> info;` |

---

### 🧠 **LeetCode Problems Using `pair`**

*(All levels — coordinates, sorting, graphs, frequency pairs)*

### 🔹 **Beginner**

1. [#1 — Two Sum](https://leetcode.com/problems/two-sum/) *(store value + index)*
2. [#136 — Single Number](https://leetcode.com/problems/single-number/) *(pair for XOR tracking)*
3. [#217 — Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
4. [#242 — Valid Anagram](https://leetcode.com/problems/valid-anagram/)
5. [#283 — Move Zeroes](https://leetcode.com/problems/move-zeroes/)

### 🔸 **Intermediate**

1. [#56 — Merge Intervals](https://leetcode.com/problems/merge-intervals/) *(pair<start,end>)*
2. [#973 — K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/) *(pair<distance,index>)*
3. [#451 — Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/) *(pair<char,int>)*
4. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#1337 — K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)

### 🔺 **Advanced**

1. [#743 — Network Delay Time](https://leetcode.com/problems/network-delay-time/) *(pair<cost,node>)*
2. [#787 — Cheapest Flights Within K Stops](https://leetcode.com/problems/cheapest-flights-within-k-stops/) *(pair<cost,node>)*
3. [#1235 — Maximum Profit in Job Scheduling](https://leetcode.com/problems/maximum-profit-in-job-scheduling/)
4. [#1584 — Min Cost to Connect All Points](https://leetcode.com/problems/min-cost-to-connect-all-points/) *(Prim’s algorithm)*
5. [#502 — IPO](https://leetcode.com/problems/ipo/) *(pair<profit,capital>)*
6. [#1631 — Path With Minimum Effort](https://leetcode.com/problems/path-with-minimum-effort/)
7. [#1514 — Path with Maximum Probability](https://leetcode.com/problems/path-with-maximum-probability/)
8. [#1976 — Number of Ways to Arrive at Destination](https://leetcode.com/problems/number-of-ways-to-arrive-at-destination/)
9. [#332 — Reconstruct Itinerary](https://leetcode.com/problems/reconstruct-itinerary/)
10. [#743 — Dijkstra-based problems](https://leetcode.com/problems/network-delay-time/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Initialization
    pair<int, string> p1 = {1, "Vinay"};
    auto p2 = make_pair(2, "AI Engineer");

    cout << p1.first << " -> " << p1.second << "\n";
    cout << p2.first << " -> " << p2.second << "\n";

    // 2. Swapping
    swap(p1, p2);
    cout << "After swap: " << p1.first << " -> " << p1.second << "\n";

    // 3. Nested pairs
    pair<int, pair<int, int>> nested = {1, {2, 3}};
    cout << "Nested pair: " << nested.first << " "
         << nested.second.first << " " << nested.second.second << "\n";

    // 4. Vector of pairs
    vector<pair<int, int>> vp = {{2, 30}, {1, 50}, {3, 40}};
    sort(vp.begin(), vp.end()); // sorts by first, then second

    cout << "Sorted pairs:\n";
    for (auto &p : vp)
        cout << "(" << p.first << "," << p.second << ") ";
    cout << "\n";

    // 5. Pair with priority_queue (min-heap)
    priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;
    pq.push({2,100});
    pq.push({1,200});
    pq.push({3,50});

    cout << "Min-heap top: " << pq.top().first << " -> " << pq.top().second << "\n";
}

```

**🧾 Output (Simplified):**

```
1 -> Vinay
2 -> AI Engineer
After swap: 2 -> AI Engineer
Nested pair: 1 2 3
Sorted pairs:
(1,50) (2,30) (3,40)
Min-heap top: 1 -> 200

```

---

### 💡 **Tips & Tricks**

- ✅ Use `make_pair()` to avoid manually specifying types.
- ✅ For sorting based on second → custom comparator or lambda.
- ✅ `pair` is used **everywhere** in Dijkstra, Prim, Kruskal algorithms.
- ✅ For returning 2 values from a function:
    
    ```cpp
    pair<int,int> getMinMax(vector<int>& v) {
        return { *min_element(v.begin(), v.end()),
                 *max_element(v.begin(), v.end()) };
    }
    
    ```
    

---

---

## 🧩 **15. STL `tuple` — Complete Notes**

### 📘 **Concept Summary**

- `tuple` is a **generalized version of `pair`** that can store **multiple elements of different types**.
- Defined in `<tuple>` header.
- Allows **structured data grouping** (like returning multiple values from a function).
- Perfect for **storing compound data**, **custom sorting**, or **multi-return operations**.

---

### ⚙️ **Common Operations**

| Operation | Syntax | Description | Time Complexity |
| --- | --- | --- | --- |
| Create | `tuple<int, string, float> t;` | Empty tuple | O(1) |
| Initialize | `tuple<int, string, float> t(1, "Vinay", 9.8);` | Direct initialization | O(1) |
| Using braces | `tuple<int, string, float> t = {1, "AI", 9.81};` | Uniform init | O(1) |
| `make_tuple()` | `auto t = make_tuple(1, "Data", 3.14);` | Type inference | O(1) |
| Access | `get<index>(t)` | Access element by index | O(1) |
| Modify | `get<1>(t) = "Updated";` | Modify element | O(1) |
| Size | `tuple_size<decltype(t)>::value` | No. of elements | O(1) |
| Type | `tuple_element<index, decltype(t)>::type` | Element type | O(1) |
| Compare | `t1 < t2` | Lexicographical compare | O(1) |
| Swap | `swap(t1, t2)` | Swap all elements | O(1) |

---

### ⚡ **Example**

```cpp
tuple<int, string, double> person(23, "Vinay", 75.8);
cout << get<0>(person); // 23
cout << get<1>(person); // Vinay
cout << get<2>(person); // 75.8

```

---

### 🔁 **Unpacking a Tuple**

Using **structured bindings** (C++17+):

```cpp
auto [age, name, weight] = person;
cout << name; // Vinay

```

Using `tie()` (older C++):

```cpp
int a; string b; double c;
tie(a, b, c) = person;

```

Ignore elements with `_`:

```cpp
tie(ignore, b, c) = person;

```

---

### 💡 **Nested & Vector Tuples**

```cpp
vector<tuple<int, string, double>> people = {
    {1, "Alice", 65.2},
    {2, "Bob", 72.3},
    {3, "Charlie", 68.1}
};

// Sort by first element (ID)
sort(people.begin(), people.end());

```

---

### 🧠 **LeetCode Problems Using `tuple`**

*(Mostly for storing multiple attributes: cost, node, time, etc.)*

### 🔹 **Beginner**

1. [#1684 — Count Consistent Strings](https://leetcode.com/problems/count-consistent-strings/) *(tuple for (char, freq, bool))*
2. [#937 — Reorder Data in Log Files](https://leetcode.com/problems/reorder-data-in-log-files/)
3. [#506 — Relative Ranks](https://leetcode.com/problems/relative-ranks/) *(tuple for (score,index,rank))*
4. [#1365 — How Many Numbers Are Smaller Than the Current Number](https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/)
5. [#1779 — Find Nearest Point That Has the Same X or Y Coordinate](https://leetcode.com/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/)

### 🔸 **Intermediate**

1. [#743 — Network Delay Time](https://leetcode.com/problems/network-delay-time/) *(tuple<time,node>)*
2. [#787 — Cheapest Flights Within K Stops](https://leetcode.com/problems/cheapest-flights-within-k-stops/) *(tuple<cost,stops,node>)*
3. [#1631 — Path With Minimum Effort](https://leetcode.com/problems/path-with-minimum-effort/) *(tuple<effort,x,y>)*
4. [#1976 — Number of Ways to Arrive at Destination](https://leetcode.com/problems/number-of-ways-to-arrive-at-destination/) *(tuple<time,node>)*
5. [#1268 — Search Suggestions System](https://leetcode.com/problems/search-suggestions-system/) *(tuple for sorting results)*

### 🔺 **Advanced**

1. [#1851 — Minimum Interval to Include Each Query](https://leetcode.com/problems/minimum-interval-to-include-each-query/) *(tuple<start,end,len>)*
2. [#882 — Reachable Nodes in Subdivided Graph](https://leetcode.com/problems/reachable-nodes-in-subdivided-graph/) *(tuple<dist,node>)*
3. [#787 — K Stops Graph Traversal](https://leetcode.com/problems/cheapest-flights-within-k-stops/) *(tuple<cost,stops,node>)*
4. [#1514 — Path with Maximum Probability](https://leetcode.com/problems/path-with-maximum-probability/) *(tuple<prob,node>)*
5. [#221 — Maximal Square](https://leetcode.com/problems/maximal-square/) *(tuple<i,j,val>)*
6. [#2392 — Build a Matrix With Conditions](https://leetcode.com/problems/build-a-matrix-with-conditions/)
7. [#1802 — Maximum Value at a Given Index in a Bounded Array](https://leetcode.com/problems/maximum-value-at-a-given-index-in-a-bounded-array/)
8. [#2616 — Minimize the Maximum Difference of Pairs](https://leetcode.com/problems/minimize-the-maximum-difference-of-pairs/)
9. [#332 — Reconstruct Itinerary](https://leetcode.com/problems/reconstruct-itinerary/) *(tuple<from,to>)*
10. [#1584 — Min Cost to Connect All Points](https://leetcode.com/problems/min-cost-to-connect-all-points/) *(tuple<dist,i,j>)*

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // 1. Basic initialization
    tuple<int, string, double> t1(23, "Vinay", 75.5);
    cout << "Age: " << get<0>(t1) << ", Name: " << get<1>(t1)
         << ", Weight: " << get<2>(t1) << "\n";

    // 2. Structured binding (C++17)
    auto [age, name, weight] = t1;
    cout << name << " is " << age << " years old.\n";

    // 3. Modify tuple element
    get<2>(t1) = 76.2;

    // 4. Nested tuples
    tuple<int, pair<string, double>> nested = {1, {"AI Engineer", 99.9}};
    cout << get<0>(nested) << " -> " << get<0>(get<1>(nested))
         << " : " << get<1>(get<1>(nested)) << "\n";

    // 5. Vector of tuples
    vector<tuple<int,string,double>> people = {
        {3, "Alice", 65.1},
        {1, "Bob", 72.4},
        {2, "Charlie", 68.5}
    };

    // Sort by ID (first element)
    sort(people.begin(), people.end());
    cout << "Sorted by ID:\n";
    for (auto &[id, n, w] : people)
        cout << id << " " << n << " " << w << "\n";
}

```

**🧾 Output (Simplified):**

```
Age: 23, Name: Vinay, Weight: 75.5
Vinay is 23 years old.
1 -> AI Engineer : 99.9
Sorted by ID:
1 Bob 72.4
2 Charlie 68.5
3 Alice 65.1

```

---

### 💡 **Tips & Tricks**

- ✅ Use `structured bindings` for clean unpacking (`auto [x,y,z]` syntax).
- ✅ `tie()` helps unpack tuples before C++17.
- ✅ Can compare tuples directly — C++ handles lexicographic order automatically.
- ✅ Often used in Dijkstra or BFS problems to carry `(distance, node, cost)` triples.
- ✅ In advanced sorting, you can sort by multiple fields effortlessly:
    
    ```cpp
    sort(v.begin(), v.end()); // automatically sorts by first, then second, etc.
    
    ```
    

---

---

## 🧩 **16. STL `<algorithm>` — Complete Notes**

### 📘 **Concept Summary

- `<algorithm>` is the **heart of STL** providing **ready-made functions** for searching, sorting, modifying, counting, comparing, and rearranging sequences.
- Works with **iterators** — compatible with all STL containers (`vector`, `set`, `string`, etc.).
- Most functions run in **O(n)** or **O(log n)** time (based on data type).

---

## ⚙️ **1️⃣ Sorting Functions**

### 🔹 `sort()`

```cpp
sort(v.begin(), v.end());

```

✅ Sorts ascending by default (O(n log n)).

Descending:

```cpp
sort(v.begin(), v.end(), greater<int>());

```

Custom comparator:

```cpp
sort(v.begin(), v.end(), [](int a, int b){ return a > b; });

```

Sort vector of pairs:

```cpp
sort(v.begin(), v.end(), [](auto &a, auto &b){
    return a.second < b.second; // sort by second element
});

```

---

### 🔹 `stable_sort()`

Preserves relative order of equal elements.

Used when stability matters.

```cpp
stable_sort(v.begin(), v.end());

```

---

### 🔹 `partial_sort()`

Sorts only first `k` elements.

```cpp
partial_sort(v.begin(), v.begin()+k, v.end());

```

---

### 🔹 `nth_element()`

Places nth element in correct position (O(n)).

All elements before are smaller, after are larger (not sorted).

```cpp
nth_element(v.begin(), v.begin()+k, v.end());

```

---

## ⚙️ **2️⃣ Searching & Counting**

### 🔹 `find()`

Linear search.

```cpp
auto it = find(v.begin(), v.end(), 5);
if (it != v.end()) cout << "Found";

```

---

### 🔹 `binary_search()`

Used in **sorted containers**.

```cpp
bool present = binary_search(v.begin(), v.end(), x);

```

---

### 🔹 `lower_bound()` / `upper_bound()`

Works only on sorted containers.

| Function | Returns |
| --- | --- |
| `lower_bound(v.begin(), v.end(), x)` | iterator to first ≥ x |
| `upper_bound(v.begin(), v.end(), x)` | iterator to first > x |

Example:

```cpp
int idx = lower_bound(v.begin(), v.end(), x) - v.begin();

```

---

### 🔹 `count()` / `count_if()`

Count occurrences.

```cpp
int c = count(v.begin(), v.end(), 5);
int even = count_if(v.begin(), v.end(), [](int x){ return x%2==0; });

```

---

## ⚙️ **3️⃣ Min / Max Utilities**

| Function | Description |
| --- | --- |
| `min(a,b)` | Smaller of two |
| `max(a,b)` | Larger of two |
| `min_element(v.begin(), v.end())` | Iterator to smallest element |
| `max_element(v.begin(), v.end())` | Iterator to largest element |
| `minmax_element(v.begin(), v.end())` | Pair of iterators (min,max) |

---

## ⚙️ **4️⃣ Modifying Operations**

| Function | Description |
| --- | --- |
| `reverse()` | Reverses order |
| `rotate()` | Rotates elements |
| `unique()` | Removes duplicates (needs sort first) |
| `fill()` | Assigns same value |
| `replace()` | Replaces values |
| `copy()` | Copies range |
| `swap()` | Swaps values |
| `transform()` | Applies function to all elements |

Examples:

```cpp
reverse(v.begin(), v.end());
rotate(v.begin(), v.begin()+2, v.end());
v.erase(unique(v.begin(), v.end()), v.end());
fill(v.begin(), v.end(), 0);
replace(v.begin(), v.end(), 2, 99);
transform(v.begin(), v.end(), v.begin(), [](int x){ return x*2; });

```

---

## ⚙️ **5️⃣ Set Operations (Sorted Containers)**

| Function | Description |
| --- | --- |
| `set_union(a,b,...)` | Union |
| `set_intersection(a,b,...)` | Common elements |
| `set_difference(a,b,...)` | A−B |
| `set_symmetric_difference(a,b,...)` | AΔB |

Example:

```cpp
vector<int> A = {1,2,3}, B = {2,3,4}, C(10);
auto it = set_intersection(A.begin(), A.end(), B.begin(), B.end(), C.begin());
C.resize(it - C.begin());

```

---

## ⚙️ **6️⃣ Permutation Functions**

| Function | Description |
| --- | --- |
| `next_permutation()` | Next lexicographic order |
| `prev_permutation()` | Previous order |

Example:

```cpp
vector<int> v = {1,2,3};
do {
    for (auto x : v) cout << x << " ";
    cout << "\n";
} while(next_permutation(v.begin(), v.end()));

```

---

## ⚙️ **7️⃣ Comparing Ranges**

| Function | Description |
| --- | --- |
| `equal(a,b)` | Check equality |
| `lexicographical_compare()` | Compare like dictionary |

---

## ⚙️ **8️⃣ Heap Utilities**

| Function | Description |
| --- | --- |
| `make_heap()` | Converts vector to heap |
| `push_heap()` | Adds element |
| `pop_heap()` | Removes top |
| `sort_heap()` | Sorts heap |

Example:

```cpp
vector<int> h = {3,1,4,1,5};
make_heap(h.begin(), h.end());
pop_heap(h.begin(), h.end()); // moves largest to end

```

---

## ⚙️ **9️⃣ Miscellaneous**

| Function | Description |
| --- | --- |
| `all_of()` | Returns true if all elements satisfy condition |
| `any_of()` | True if any element satisfies condition |
| `none_of()` | True if none satisfy condition |
| `for_each()` | Apply a function to all elements |

Example:

```cpp
if(all_of(v.begin(), v.end(), [](int x){return x>0;}))
    cout << "All positive!";
for_each(v.begin(), v.end(), [](int x){ cout << x << " "; });

```

---

### 🧠 **LeetCode Problems Using `<algorithm>`**

*(All levels — uses sort, binary_search, minmax, unique, etc.)*

### 🔹 **Beginner**

1. [#88 — Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)
2. [#217 — Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
3. [#268 — Missing Number](https://leetcode.com/problems/missing-number/)
4. [#350 — Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
5. [#485 — Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/)
6. [#977 — Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)

### 🔸 **Intermediate**

1. [#56 — Merge Intervals](https://leetcode.com/problems/merge-intervals/)
2. [#15 — 3Sum](https://leetcode.com/problems/3sum/)
3. [#75 — Sort Colors](https://leetcode.com/problems/sort-colors/)
4. [#347 — Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
5. [#350 — Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
6. [#451 — Sort Characters by Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
7. [#540 — Single Element in a Sorted Array](https://leetcode.com/problems/single-element-in-a-sorted-array/)
8. [#33 — Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
9. [#162 — Find Peak Element](https://leetcode.com/problems/find-peak-element/)

### 🔺 **Advanced**

1. [#853 — Car Fleet](https://leetcode.com/problems/car-fleet/)
2. [#1235 — Job Scheduling](https://leetcode.com/problems/maximum-profit-in-job-scheduling/)
3. [#148 — Sort List](https://leetcode.com/problems/sort-list/)
4. [#218 — Skyline Problem](https://leetcode.com/problems/the-skyline-problem/)
5. [#1851 — Minimum Interval to Include Each Query](https://leetcode.com/problems/minimum-interval-to-include-each-query/)
6. [#295 — Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)
7. [#2402 — Meeting Rooms III](https://leetcode.com/problems/meeting-rooms-iii/)
8. [#973 — K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/)
9. [#630 — Course Schedule III](https://leetcode.com/problems/course-schedule-iii/)
10. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {4, 1, 7, 3, 9, 2};

    // 1. Sort ascending
    sort(v.begin(), v.end());
    cout << "Sorted: "; for (auto x : v) cout << x << " "; cout << "\n";

    // 2. Reverse
    reverse(v.begin(), v.end());
    cout << "Reversed: "; for (auto x : v) cout << x << " "; cout << "\n";

    // 3. Binary search
    cout << "Is 3 present? " << binary_search(v.begin(), v.end(), 3) << "\n";

    // 4. Min/Max
    cout << "Min: " << *min_element(v.begin(), v.end())
         << ", Max: " << *max_element(v.begin(), v.end()) << "\n";

    // 5. Transform (double elements)
    transform(v.begin(), v.end(), v.begin(), [](int x){ return x*2; });
    cout << "Doubled: "; for (auto x : v) cout << x << " "; cout << "\n";

    // 6. next_permutation
    vector<int> p = {1, 2, 3};
    next_permutation(p.begin(), p.end());
    cout << "Next permutation: "; for (auto x : p) cout << x << " "; cout << "\n";
}

```

**🧾 Output (Simplified):**

```
Sorted: 1 2 3 4 7 9
Reversed: 9 7 4 3 2 1
Is 3 present? 0
Min: 1, Max: 9
Doubled: 18 14 8 6 4 2
Next permutation: 1 3 2

```

---

### 💡 **Pro Tips**

- ✅ Always sort before using `binary_search`, `lower_bound`, or `set_*` functions.
- ✅ Combine `unique()` + `erase()` to remove duplicates.
- ✅ Use `transform()` + lambda to replace loops.
- ✅ `all_of`, `any_of`, `none_of` → clean condition checks.
- ✅ `next_permutation` helps generate all orderings in backtracking problems.
- ✅ `nth_element` for Kth smallest/largest problems efficiently.

---

---

## 🧩 **17. STL Iterators & Ranges — Complete Notes**

---

### 📘 **Concept Summary**

- **Iterators** are **pointers-like objects** used to traverse elements of STL containers (but in a uniform way).
- Every container (vector, map, set, etc.) provides iterators.
- Syntax is **similar to pointers** — you can `++`, , and `>` them.
- Iterators act as a **bridge between containers and algorithms** (like `sort`, `find`, `reverse`, etc.).

---

### ⚙️ **Iterator Types**

| Type | Description | Supported Containers |
| --- | --- | --- |
| **Input Iterator** | Read-only, single-pass | `istream`, read streams |
| **Output Iterator** | Write-only, single-pass | `ostream`, write streams |
| **Forward Iterator** | Multi-pass, read/write | `forward_list`, `unordered_*` |
| **Bidirectional Iterator** | Forward & backward traversal | `list`, `set`, `map`, `multiset`, `multimap` |
| **Random Access Iterator** | Jump + indexing | `vector`, `deque`, `array` |

---

### ⚙️ **Basic Operations**

| Operation | Syntax | Meaning |
| --- | --- | --- |
| **Begin iterator** | `v.begin()` | First element |
| **End iterator** | `v.end()` | Points past the last element |
| **Dereference** | `*it` | Access value |
| **Increment** | `++it` | Move forward |
| **Decrement** | `--it` | Move backward (bidirectional only) |
| **Next / Prev** | `next(it, k)` / `prev(it, k)` | Jump iterators |
| **Advance** | `advance(it, k)` | Move iterator by `k` |
| **Distance** | `distance(it1, it2)` | Number of elements between iterators |
| **cbegin / cend** | Read-only iterators (const) |  |
| **rbegin / rend** | Reverse iteration |  |

---

### 💡 **Example: Basic Iterator Usage**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40};

    // Iterator declaration
    vector<int>::iterator it;

    cout << "Forward traversal: ";
    for (it = v.begin(); it != v.end(); ++it)
        cout << *it << " ";  // Dereference to access

    cout << "\nReverse traversal: ";
    for (auto rit = v.rbegin(); rit != v.rend(); ++rit)
        cout << *rit << " ";
}

```

**🧾 Output:**

```
Forward traversal: 10 20 30 40
Reverse traversal: 40 30 20 10

```

---

### ⚙️ **`advance()`, `next()`, `prev()`**

```cpp
auto it = v.begin();
advance(it, 2);   // moves 2 steps → points to 30
cout << *it;      // 30

auto next_it = next(v.begin(), 3); // points to 40
auto prev_it = prev(v.end(), 2);   // points to 30

```

---

### ⚙️ **`distance()`**

Find number of elements between two iterators:

```cpp
cout << distance(v.begin(), v.end()); // 4

```

---

### ⚙️ **Const Iterators**

```cpp
vector<int>::const_iterator it = v.begin();
// *it = 5; ❌ not allowed (read-only)

```

---

### ⚙️ **Reverse Iterators**

```cpp
for (auto it = v.rbegin(); it != v.rend(); ++it)
    cout << *it << " ";

```

---

### ⚙️ **Iterator + Algorithm Integration**

All STL algorithms accept iterators instead of containers directly.

```cpp
sort(v.begin(), v.end());
reverse(v.begin(), v.end());
find(v.begin(), v.end(), x);
unique(v.begin(), v.end());

```

---

### 🧩 **Iterators in Different Containers**

| Container | Iterator Type | Example |
| --- | --- | --- |
| `vector` | Random Access | `v.begin(), v.end()` |
| `deque` | Random Access | `dq.begin()` |
| `list` | Bidirectional | `lst.begin()` |
| `set` / `map` | Bidirectional | `s.begin()` |
| `unordered_set` / `unordered_map` | Forward | `um.begin()` |
| `stack` / `queue` | ❌ No iterators | Use copy + pop |

---

### 🧠 **LeetCode Problems (Iterator-based)**

*(They rely on iteration, traversal, and pointer simulation)*

### 🔹 **Beginner**

1. [#94 — Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/) *(manual stack = iterator idea)*
2. [#144 — Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)
3. [#145 — Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/)
4. [#284 — Peeking Iterator](https://leetcode.com/problems/peeking-iterator/)
5. [#173 — Binary Search Tree Iterator](https://leetcode.com/problems/binary-search-tree-iterator/)

### 🔸 **Intermediate**

1. [#341 — Flatten Nested List Iterator](https://leetcode.com/problems/flatten-nested-list-iterator/)
2. [#281 — Zigzag Iterator](https://leetcode.com/problems/zigzag-iterator/)
3. [#251 — Flatten 2D Vector](https://leetcode.com/problems/flatten-2d-vector/)
4. [#160 — Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/)
5. [#21 — Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)

### 🔺 **Advanced**

1. [#1429 — First Unique Number](https://leetcode.com/problems/first-unique-number/)
2. [#1472 — Design Browser History](https://leetcode.com/problems/design-browser-history/)
3. [#1586 — Binary Search Tree Iterator II](https://leetcode.com/problems/binary-search-tree-iterator-ii/)
4. [#341 — Custom Iterator Pattern](https://leetcode.com/problems/flatten-nested-list-iterator/)
5. [#1348 — Tweet Counts per Frequency](https://leetcode.com/problems/tweet-counts-per-frequency/)

---

### 💻 **Example Code (Full Demonstration)**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    list<int> lst = {10, 20, 30, 40, 50};

    // 1. Using iterators
    for (auto it = lst.begin(); it != lst.end(); ++it)
        cout << *it << " ";
    cout << "\n";

    // 2. Using advance, next, prev
    auto it = lst.begin();
    advance(it, 2); // move 2 steps
    cout << "3rd element: " << *it << "\n";

    auto it_next = next(it);
    cout << "Next element: " << *it_next << "\n";

    auto it_prev = prev(it);
    cout << "Previous element: " << *it_prev << "\n";

    // 3. Using distance
    cout << "Distance between begin and end: "
         << distance(lst.begin(), lst.end()) << "\n";

    // 4. Reverse iteration
    cout << "Reverse: ";
    for (auto rit = lst.rbegin(); rit != lst.rend(); ++rit)
        cout << *rit << " ";
}

```

**🧾 Output:**

```
10 20 30 40 50
3rd element: 30
Next element: 40
Previous element: 20
Distance between begin and end: 5
Reverse: 50 40 30 20 10

```

---

### 💡 **Pro Tips**

- ✅ Prefer `auto` for cleaner iterator declarations.
- ✅ Use `rbegin()` and `rend()` for easy reverse traversal.
- ✅ Combine iterators with `<algorithm>` for clean, generic code.
- ✅ `const_iterator` prevents accidental modification.
- ✅ `advance()` and `distance()` are key for custom traversal logic.

---

---

## 🧩 **18. STL `<numeric>` — Complete Notes**

---

### 📘 **Concept Summary**

- `<numeric>` provides **numeric operations** for containers and ranges — sums, products, prefixes, GCDs, etc.
- Works seamlessly with all iterators (like `<algorithm>`).
- Commonly used in:
    - Array/Vector summations
    - Prefix sum problems
    - Product and difference operations
    - Mathematical optimizations

---

### ⚙️ **Header**

```cpp
#include <numeric>

```

---

## ⚙️ **1️⃣ accumulate() — Sum or Reduce Elements**

> Combines elements in a range using a binary operation (default: addition).
> 

**Syntax:**

```cpp
accumulate(start, end, initial_value);
accumulate(start, end, initial_value, operation);

```

**Example:**

```cpp
vector<int> v = {1, 2, 3, 4, 5};
int sum = accumulate(v.begin(), v.end(), 0); // 15
int product = accumulate(v.begin(), v.end(), 1, multiplies<int>()); // 120

```

**Custom Operation:**

```cpp
int diff = accumulate(v.begin(), v.end(), 100, [](int a, int b){ return a - b; }); // 85

```

**Complexity:** O(n)

---

## ⚙️ **2️⃣ inner_product() — Dot Product**

> Computes sum of element-wise products.
> 

**Syntax:**

```cpp
inner_product(a.begin(), a.end(), b.begin(), initial_value);

```

**Example:**

```cpp
vector<int> a = {1, 2, 3};
vector<int> b = {4, 5, 6};
int dot = inner_product(a.begin(), a.end(), b.begin(), 0); // (1*4 + 2*5 + 3*6) = 32

```

---

## ⚙️ **3️⃣ partial_sum() — Prefix Sum**

> Stores running totals of elements in another container.
> 

**Syntax:**

```cpp
partial_sum(v.begin(), v.end(), result.begin());

```

**Example:**

```cpp
vector<int> v = {1, 2, 3, 4, 5}, prefix(5);
partial_sum(v.begin(), v.end(), prefix.begin());
// prefix = [1, 3, 6, 10, 15]

```

You can also customize:

```cpp
partial_sum(v.begin(), v.end(), prefix.begin(), multiplies<int>());
// prefix = [1, 2, 6, 24, 120]

```

---

## ⚙️ **4️⃣ adjacent_difference()**

> Stores difference between consecutive elements.
> 

**Syntax:**

```cpp
adjacent_difference(v.begin(), v.end(), result.begin());

```

**Example:**

```cpp
vector<int> v = {2, 4, 7, 11}, diff(4);
adjacent_difference(v.begin(), v.end(), diff.begin());
// diff = [2, 2, 3, 4]

```

Custom operation (ratio, xor, etc.) is also allowed.

---

## ⚙️ **5️⃣ iota() — Fill with Sequential Values**

> Assigns increasing values to range elements.
> 

**Syntax:**

```cpp
iota(v.begin(), v.end(), start_value);

```

**Example:**

```cpp
vector<int> v(5);
iota(v.begin(), v.end(), 100); // v = [100, 101, 102, 103, 104]

```

---

## ⚙️ **6️⃣ gcd() and lcm() — Greatest Common Divisor / Least Common Multiple**

Available from **C++17** onward.

```cpp
int g = gcd(24, 36); // 12
int l = lcm(12, 18); // 36

```

**Custom Example:**

```cpp
vector<int> v = {8, 12, 16};
int g = accumulate(v.begin()+1, v.end(), v[0], gcd<int,int>);

```

---

## ⚙️ **7️⃣ reduce() — Parallel Accumulate (C++17)**

> Similar to accumulate, but may run in parallel on large datasets.
> 

```cpp
#include <execution>
int sum = reduce(execution::par, v.begin(), v.end(), 0);

```

---

### ⚡ **Summary Table**

| Function | Purpose | Default Op | Result |
| --- | --- | --- | --- |
| `accumulate()` | Combine all elements | `+` | Single value |
| `inner_product()` | Sum of products | `+` and `*` | Scalar |
| `partial_sum()` | Prefix running totals | `+` | Vector |
| `adjacent_difference()` | Difference between consecutive elements | `-` | Vector |
| `iota()` | Fill with sequential values | `++` | Vector |
| `gcd() / lcm()` | Math utilities | — | Scalar |
| `reduce()` | Parallel accumulation | `+` | Scalar |

---

### 🧠 **LeetCode Problems Using `<numeric>`**

*(These rely on sum, prefix, product, or GCD logic)*

### 🔹 **Beginner**

1. [#1480 — Running Sum of 1D Array](https://leetcode.com/problems/running-sum-of-1d-array/) *(use `partial_sum`)*
2. [#724 — Find Pivot Index](https://leetcode.com/problems/find-pivot-index/) *(use `accumulate`)*
3. [#560 — Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/) *(prefix sum + accumulate)*
4. [#121 — Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) *(adjacent_difference)*
5. [#66 — Plus One](https://leetcode.com/problems/plus-one/) *(accumulation logic)*

### 🔸 **Intermediate**

1. [#238 — Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) *(prefix-suffix)*
2. [#152 — Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/) *(accumulate + multiply)*
3. [#128 — Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) *(iota test setup)*
4. [#1037 — Valid Boomerang](https://leetcode.com/problems/valid-boomerang/) *(gcd + difference check)*
5. [#1991 — Find the Middle Index in Array](https://leetcode.com/problems/find-the-middle-index-in-array/)

### 🔺 **Advanced**

1. [#2147 — Number of Ways to Divide a Long Corridor](https://leetcode.com/problems/number-of-ways-to-divide-a-long-corridor/) *(prefix combinations)*
2. [#1442 — Count Triplets That Can Form Two Arrays of Equal XOR](https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/) *(prefix XOR)*
3. [#1359 — Count All Valid Pickup and Delivery Options](https://leetcode.com/problems/count-all-valid-pickup-and-delivery-options/) *(product reduce)*
4. [#1910 — Remove All Occurrences of a Substring](https://leetcode.com/problems/remove-all-occurrences-of-a-substring/) *(accumulate for rebuild)*
5. [#2968 — Apply Operations to Maximize Frequency Score](https://leetcode.com/problems/apply-operations-to-maximize-frequency-score/) *(prefix & reduce)*

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {1, 2, 3, 4, 5};

    // 1. accumulate
    cout << "Sum = " << accumulate(v.begin(), v.end(), 0) << "\n";

    // 2. product using custom op
    cout << "Product = " << accumulate(v.begin(), v.end(), 1, multiplies<int>()) << "\n";

    // 3. inner_product
    vector<int> b = {5, 4, 3, 2, 1};
    cout << "Dot product = " << inner_product(v.begin(), v.end(), b.begin(), 0) << "\n";

    // 4. partial_sum
    vector<int> prefix(v.size());
    partial_sum(v.begin(), v.end(), prefix.begin());
    cout << "Prefix sums: ";
    for (int x : prefix) cout << x << " ";
    cout << "\n";

    // 5. iota
    vector<int> seq(5);
    iota(seq.begin(), seq.end(), 100);
    cout << "Iota: ";
    for (int x : seq) cout << x << " ";
    cout << "\n";

    // 6. gcd/lcm
    cout << "gcd(18, 24) = " << gcd(18, 24) << "\n";
    cout << "lcm(6, 8) = " << lcm(6, 8) << "\n";
}

```

**🧾 Output:**

```
Sum = 15
Product = 120
Dot product = 35
Prefix sums: 1 3 6 10 15
Iota: 100 101 102 103 104
gcd(18, 24) = 6
lcm(6, 8) = 24

```

---

### 💡 **Pro Tips**

- ✅ Use `accumulate` for sums — cleaner than manual loops.
- ✅ Use `partial_sum` for prefix-sum patterns.
- ✅ Use `adjacent_difference` to find deltas or slopes.
- ✅ Combine with lambdas for flexible operations.
- ✅ Prefer `reduce` in large-scale data (C++17+ parallelism).
- ✅ Use `gcd/lcm` directly for ratio simplifications and math problems.

---

---

## 🧩 **19. STL `string` Utilities — Complete Notes**

---

### 📘 **Concept Summary**

- `string` is part of `<string>` (included automatically via `<bits/stdc++.h>`).
- It’s a **dynamic array of characters** — supports concatenation, slicing, searching, and comparison.
- STL provides **powerful built-in methods** for string manipulation, replacing manual C-style code (`char[]`).

---

## ⚙️ **1️⃣ Declaration & Initialization**

```cpp
string s1 = "Vinay";
string s2("AI Engineer");
string s3(5, 'x');     // s3 = "xxxxx"
string s4 = s1 + " Rocks!"; // Concatenation

```

**From character array:**

```cpp
char arr[] = "Hello";
string s(arr);

```

---

## ⚙️ **2️⃣ Basic Operations**

| Operation | Syntax | Example | Result |
| --- | --- | --- | --- |
| Length / Size | `s.size()` / `s.length()` | `"Vinay".size()` | 5 |
| Append | `s += "X";` or `s.append("X");` | `"AI" + " ML"` | `"AI ML"` |
| Insert | `s.insert(pos, "text");` | `"ABC".insert(1, "Z")` | `"AZBC"` |
| Erase | `s.erase(pos, len);` | `"abcdef".erase(2,3)` | `"abf"` |
| Replace | `s.replace(pos, len, "X")` | `"abcde".replace(1,2,"ZZ")` | `"aZZde"` |
| Clear | `s.clear();` | Removes all chars |  |
| Empty | `s.empty()` | Returns true if empty |  |
| Swap | `s1.swap(s2);` | Exchanges content |  |

---

## ⚙️ **3️⃣ Access & Iteration**

```cpp
cout << s[0];       // random access
for(char c : s)     // range loop
    cout << c;

```

`at()` is safer:

```cpp
cout << s.at(2); // throws out_of_range if invalid

```

---

## ⚙️ **4️⃣ Substring & Finding**

| Operation | Syntax | Description |
| --- | --- | --- |
| `substr(pos, len)` | Returns substring | `"Hello".substr(1,3)` → `"ell"` |
| `find("sub")` | Finds first occurrence | `"abcabc".find("bc")` → 1 |
| `rfind("sub")` | Finds last occurrence | `"abcabc".rfind("bc")` → 4 |
| `find_first_of("set")` | Finds any char from set | `"hello".find_first_of("le")` → 2 |
| `find_last_of("set")` | Finds last matching char | `"hello".find_last_of("le")` → 3 |
| `find_first_not_of("set")` | Finds first char *not* in set | `"aaaab".find_first_not_of("a")` → 4 |

---

## ⚙️ **5️⃣ Comparison**

| Operator / Method | Example | Result |
| --- | --- | --- |
| `==, !=, <, >` | `"abc" < "abd"` | true |
| `compare()` | `s1.compare(s2)` | 0 if equal, <0 if s1<s2, >0 otherwise |

---

## ⚙️ **6️⃣ Conversion Between String & Numbers**

```cpp
int x = stoi("1234");
long y = stol("100000");
float z = stof("3.14");
string s = to_string(2025);

```

---

## ⚙️ **7️⃣ Reverse, Sort, Unique**

```cpp
string s = "vinay";
reverse(s.begin(), s.end());   // "yaniv"
sort(s.begin(), s.end());      // "ainvy"
s.erase(unique(s.begin(), s.end()), s.end()); // remove duplicates

```

---

## ⚙️ **8️⃣ String Streams (`<sstream>`)**

Used for **tokenizing and number extraction** from strings.

### 🔹 Split Words

```cpp
#include <sstream>
string text = "AI Engineer India";
stringstream ss(text);
string word;
while (ss >> word)
    cout << word << "\n";

```

### 🔹 Convert Number to String & Back

```cpp
stringstream ss;
int num = 50;
ss << num;
string s = ss.str(); // "50"

ss.clear();
ss.str("123");
int val;
ss >> val; // 123

```

---

## ⚙️ **9️⃣ Transformations**

```cpp
transform(s.begin(), s.end(), s.begin(), ::toupper);
transform(s.begin(), s.end(), s.begin(), ::tolower);

```

---

## ⚙️ **🔟 Other Handy Functions**

| Function | Example | Purpose |
| --- | --- | --- |
| `s.pop_back()` | Remove last char |  |
| `s.push_back('x')` | Add char at end |  |
| `s.front()` | First char |  |
| `s.back()` | Last char |  |
| `s.resize(n, 'x')` | Resize with fill |  |
| `s.reserve(n)` | Preallocate memory |  |

---

## 🧠 **LeetCode Problems Using STL String Functions**

### 🔹 **Beginner**

1. [#344 — Reverse String](https://leetcode.com/problems/reverse-string/) *(reverse)*
2. [#58 — Length of Last Word](https://leetcode.com/problems/length-of-last-word/) *(find, substr)*
3. [#125 — Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) *(tolower, erase)*
4. [#242 — Valid Anagram](https://leetcode.com/problems/valid-anagram/) *(sort)*
5. [#389 — Find the Difference](https://leetcode.com/problems/find-the-difference/) *(accumulate)*
6. [#14 — Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/) *(substr)*
7. [#58 — Length of Last Word](https://leetcode.com/problems/length-of-last-word/)

### 🔸 **Intermediate**

1. [#151 — Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/) *(stringstream, reverse)*
2. [#67 — Add Binary](https://leetcode.com/problems/add-binary/) *(reverse, carry logic)*
3. [#165 — Compare Version Numbers](https://leetcode.com/problems/compare-version-numbers/) *(split using stringstream)*
4. [#6 — Zigzag Conversion](https://leetcode.com/problems/zigzag-conversion/) *(string appends)*
5. [#937 — Reorder Data in Log Files](https://leetcode.com/problems/reorder-data-in-log-files/) *(sort + custom comparator)*
6. [#415 — Add Strings](https://leetcode.com/problems/add-strings/) *(manual addition)*
7. [#49 — Group Anagrams](https://leetcode.com/problems/group-anagrams/) *(sort)*
8. [#290 — Word Pattern](https://leetcode.com/problems/word-pattern/) *(stringstream split)*

### 🔺 **Advanced**

1. [#5 — Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/) *(substr)*
2. [#1514 — Path with Maximum Probability](https://leetcode.com/problems/path-with-maximum-probability/) *(string to graph mapping)*
3. [#227 — Basic Calculator II](https://leetcode.com/problems/basic-calculator-ii/) *(stringstream token parsing)*
4. [#187 — Repeated DNA Sequences](https://leetcode.com/problems/repeated-dna-sequences/) *(substr, unordered_set)*
5. [#224 — Basic Calculator](https://leetcode.com/problems/basic-calculator/) *(stack + parsing)*

---

### 💻 **Example Code**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s = "Vinay AI Engineer";

    // 1. Basic ops
    cout << "Size: " << s.size() << "\n";
    s.append(" Rocks!");
    cout << "After append: " << s << "\n";

    // 2. Substring
    cout << "Substring (0,5): " << s.substr(0,5) << "\n";

    // 3. Find
    cout << "Position of 'AI': " << s.find("AI") << "\n";

    // 4. Replace
    s.replace(6, 2, "ML");
    cout << "After replace: " << s << "\n";

    // 5. Erase
    s.erase(0, 6);
    cout << "After erase: " << s << "\n";

    // 6. Transform (upper)
    transform(s.begin(), s.end(), s.begin(), ::toupper);
    cout << "Uppercase: " << s << "\n";

    // 7. Tokenize using stringstream
    string text = "Deep Learning AI";
    stringstream ss(text);
    string word;
    cout << "Tokens:\n";
    while (ss >> word)
        cout << word << "\n";
}

```

**🧾 Output:**

```
Size: 16
After append: Vinay AI Engineer Rocks!
Substring (0,5): Vinay
Position of 'AI': 6
After replace: Vinay ML Engineer Rocks!
After erase: ML Engineer Rocks!
Uppercase: ML ENGINEER ROCKS!
Tokens:
Deep
Learning
AI

```

---

### 💡 **Pro Tips**

- ✅ Use `transform()` for `toupper()` / `tolower()` conversion.
- ✅ Use `stringstream` for splitting and parsing input lines.
- ✅ Combine `find` + `substr` for substring extraction.
- ✅ Always check for `string::npos` when using `find`.
- ✅ For reverse word problems, use `reverse()` or `stringstream`.
- ✅ Prefer `stoi`, `stoll`, and `stof` for safe conversions.

---

### 🎯 **Now You’ve Completed 100% STL Mastery**

✅ Sequence Containers

✅ Associative & Unordered Containers

✅ Adapters (`stack`, `queue`, `priority_queue`)

✅ Utility (`pair`, `tuple`)

✅ Algorithm & Numeric libraries

✅ Iterators & Ranges

✅ String STL & Streams

---

---

# 🧩 **C++ STL Complete Cheat Sheet (Interview + DSA Focus)**

---

## 🧱 **1. Sequence Containers**

| Container | Description | Key Functions | Time Complexity | Common Use-Cases | Example LeetCode Problems |
| --- | --- | --- | --- | --- | --- |
| **vector** | Dynamic array | `push_back`, `pop_back`, `insert`, `erase`, `size`, `sort` | O(1) amortized | Arrays, dynamic lists | #1 Two Sum, #15 3Sum, #75 Sort Colors |
| **deque** | Double-ended queue | `push_front`, `push_back`, `pop_front`, `pop_back` | O(1) both ends | Sliding windows, queues | #239 Sliding Window Max |
| **list** | Doubly linked list | `push_front`, `push_back`, `remove`, `sort`, `unique` | O(1) insert/erase | LRU cache, reordering | #146 LRU Cache |
| **array** | Static array | `.fill()`, `.size()` | O(1) | Fixed-size collections | #88 Merge Sorted Array |
| **forward_list** | Singly linked list | `push_front`, `remove`, `reverse` | O(1) front ops | Low-memory linked ops | #206 Reverse Linked List |

---

## 🧱 **2. Container Adapters**

| Adapter | Description | Functions | Typical Use | LeetCode Examples |
| --- | --- | --- | --- | --- |
| **stack** | LIFO structure | `push`, `pop`, `top` | Parentheses, expression eval | #20 Valid Parentheses, #739 Daily Temperatures |
| **queue** | FIFO structure | `push`, `pop`, `front` | BFS, scheduling | #102 Binary Tree Level Order |
| **priority_queue** | Heap-based structure | `push`, `pop`, `top` | Kth element, max/min heaps | #215 Kth Largest Element, #973 K Closest Points |

---

## 🌳 **3. Associative Containers (Tree-based)**

| Container | Description | Key Ops | Time Complexity | Use-Cases | LeetCode Examples |
| --- | --- | --- | --- | --- | --- |
| **set** | Unique, sorted elements | `insert`, `erase`, `find`, `count`, `lower_bound` | O(log n) | Sorted unique storage | #128 Longest Consecutive Seq |
| **multiset** | Sorted duplicates | `insert`, `count`, `erase` | O(log n) | Frequency-based sorting | #347 Top K Frequent Elements |
| **map** | Key-value pairs (unique keys) | `insert`, `erase`, `find`, `[]` | O(log n) | Key lookup | #1 Two Sum, #560 Subarray Sum |
| **multimap** | Duplicated keys allowed | same as map | O(log n) | Grouping similar keys | #350 Intersection of Arrays |

---

## ⚡ **4. Unordered Containers (Hash-based)**

| Container | Description | Key Ops | Avg Complexity | Use-Cases | LeetCode Examples |
| --- | --- | --- | --- | --- | --- |
| **unordered_set** | Unique unordered | `insert`, `erase`, `find`, `count` | O(1) | Duplicates removal | #217 Contains Duplicate |
| **unordered_map** | Key-value unordered | `insert`, `[]`, `find` | O(1) | Fast lookup, frequency maps | #1 Two Sum, #560 Subarray Sum |
| **unordered_multiset** | Duplicate elements | `insert`, `count` | O(1) | Frequency store | #451 Sort by Frequency |

---

## ⚙️ **5. Utility Components**

| Utility | Purpose | Common Usage | LeetCode Examples |
| --- | --- | --- | --- |
| **pair** | Store 2 related values | Coordinates, sorting, maps | #743 Network Delay Time, #973 K Closest Points |
| **tuple** | Store multiple heterogeneous values | Graphs, multiple returns | #787 Cheapest Flights, #1584 Min Cost Connect Points |

---

## 🧮 **6. `<algorithm>` Library**

| Category | Function | Description | Example |
| --- | --- | --- | --- |
| Sorting | `sort`, `stable_sort`, `partial_sort` | Sort entire or partial range | `sort(v.begin(), v.end())` |
| Searching | `find`, `binary_search`, `lower_bound`, `upper_bound` | Linear / Binary search | `binary_search(v.begin(), v.end(), x)` |
| Counting | `count`, `count_if`, `all_of`, `any_of`, `none_of` | Logical tests | `count(v.begin(), v.end(), x)` |
| Modifying | `reverse`, `rotate`, `replace`, `unique`, `fill`, `transform` | Modify sequences | `reverse(v.begin(), v.end())` |
| Set Ops | `set_union`, `set_intersection`, `set_difference` | Combine sorted sets | `set_union(a,b,c)` |
| Permutations | `next_permutation`, `prev_permutation` | Generate next order | Used in #31 Next Permutation |
| Heap Ops | `make_heap`, `push_heap`, `pop_heap`, `sort_heap` | Heap operations | Used in #215 Kth Largest Element |

---

## 🔢 **7. `<numeric>` Library**

| Function | Purpose | Example |
| --- | --- | --- |
| `accumulate()` | Sum / reduce elements | `accumulate(v.begin(), v.end(), 0)` |
| `inner_product()` | Dot product | `inner_product(a.begin(), a.end(), b.begin(), 0)` |
| `partial_sum()` | Prefix sums | `partial_sum(v.begin(), v.end(), result.begin())` |
| `adjacent_difference()` | Consecutive diffs | `adjacent_difference(v.begin(), v.end(), diff.begin())` |
| `iota()` | Fill sequentially | `iota(v.begin(), v.end(), 1)` |
| `gcd(), lcm()` | Math helpers | `gcd(24,36)` |
| `reduce()` | Parallel accumulate (C++17) | `reduce(execution::par, v.begin(), v.end(), 0)` |

---

## 🔁 **8. Iterators & Ranges**

| Function | Description | Example |
| --- | --- | --- |
| `begin()`, `end()` | Start & end iterators | `v.begin()` |
| `rbegin()`, `rend()` | Reverse iterators | Reverse loop |
| `advance(it, n)` | Move iterator | `advance(it, 3)` |
| `next(it, k)`, `prev(it, k)` | Jump iterators | `next(v.begin(), 2)` |
| `distance(a,b)` | Elements between | `distance(v.begin(), v.end())` |
| `cbegin()`, `cend()` | Const iterators | Read-only |
| `for_each()` | Apply lambda to all | `for_each(v.begin(), v.end(), print)` |

---

## 🧵 **9. String STL Utilities**

| Category | Function | Description |
| --- | --- | --- |
| Basic | `size()`, `append()`, `insert()`, `erase()`, `replace()` | Core modification |
| Substring | `substr(pos, len)` | Extract substring |
| Search | `find()`, `rfind()`, `find_first_of()` | Locate substrings |
| Transform | `transform(::toupper/::tolower)` | Case change |
| Compare | `==`, `<`, `compare()` | Lexicographic compare |
| Conversion | `stoi`, `stof`, `to_string` | Type conversion |
| Stream | `stringstream` | Tokenize & parse |
| Reverse/Sort | `reverse`, `sort`, `unique` | Modify order |
| Check | `empty()`, `clear()`, `resize()`, `reserve()` | Maintenance |

---

## 💡 **10. Lambda & Custom Comparators**

| Feature | Example | Use-Case |
| --- | --- | --- |
| Lambda function | `[](int a, int b){ return a > b; }` | Custom sort |
| Capture variables | `[&sum](int x){ sum += x; }` | Modify outer vars |
| Comparator for PQ | `auto cmp = [](auto &a, auto &b){ return a.second > b.second; };` | Min-heap |
| Comparator in set/map | `set<int, greater<int>> s;` | Descending order |

---

## ⚙️ **11. Must-Know STL Problem Patterns**

| Pattern | STL Tool | Example Problems |
| --- | --- | --- |
| **Sorting + Searching** | `sort`, `binary_search` | #1 Two Sum, #15 3Sum |
| **Prefix Sums** | `partial_sum`, `accumulate` | #560 Subarray Sum |
| **Frequency Count** | `unordered_map` | #347 Top K Frequent |
| **Intervals** | `pair`, `sort` | #56 Merge Intervals |
| **Graph Edges** | `vector<pair<int,int>>` | #743 Network Delay Time |
| **Heap / Priority Queue** | `priority_queue` | #215 Kth Largest, #502 IPO |
| **Sliding Window** | `deque` | #239 Sliding Window Max |
| **Duplicates Removal** | `set`, `unique` | #26 Remove Duplicates |
| **Expression Evaluation** | `stack` | #20 Valid Parentheses |
| **String Tokenization** | `stringstream` | #151 Reverse Words |

---

## 🏁 **12. Quick Reference Commands**

| Action | Code |
| --- | --- |
| Remove duplicates | `v.erase(unique(v.begin(), v.end()), v.end());` |
| Reverse vector | `reverse(v.begin(), v.end());` |
| Kth smallest | `nth_element(v.begin(), v.begin()+k, v.end());` |
| Fast sum | `accumulate(v.begin(), v.end(), 0);` |
| Sort by second | `sort(v.begin(), v.end(), [](auto &a, auto &b){ return a.second < b.second; });` |
| Lower/Upper bound | `lower_bound(v.begin(), v.end(), x);` |
| Check all positives | `all_of(v.begin(), v.end(), [](int x){ return x>0; });` |
| Fill sequence | `iota(v.begin(), v.end(), 1);` |
| Tokenize string | `stringstream ss(s); while (ss >> word) cout << word;` |

---

## 🧠 **Bonus: Top 10 LeetCode Problems to Master STL**

| Level | Problem | STL Focus |
| --- | --- | --- |
| 🟢 Easy | #217 Contains Duplicate | `unordered_set` |
| 🟢 Easy | #1 Two Sum | `unordered_map` |
| 🟡 Medium | #56 Merge Intervals | `pair`, `sort` |
| 🟡 Medium | #347 Top K Frequent Elements | `priority_queue` |
| 🟡 Medium | #15 3Sum | `sort`, `two pointers` |
| 🟡 Medium | #739 Daily Temperatures | `stack` |
| 🟡 Medium | #128 Longest Consecutive Sequence | `unordered_set` |
| 🔴 Hard | #84 Largest Rectangle in Histogram | `stack` |
| 🔴 Hard | #1235 Job Scheduling | `pair`, `sort`, `binary_search` |
| 🔴 Hard | #787 Cheapest Flights Within K Stops | `tuple`, `priority_queue` |

---

✅ **This cheat sheet covers everything you need for:**

- **FAANG / Google / Amazon Interviews**
- **Competitive programming (Codeforces, LeetCode)**
- **AI/ML engineering codebases (clean, efficient STL use)**

---
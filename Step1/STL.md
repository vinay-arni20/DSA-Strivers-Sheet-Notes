# DSA-Strivers-Sheet-Notes
Standard Template Libraries in C++

## **C++ STL Pairs — Complete Reference**

```cpp
#include <bits/stdc++.h>
using namespace std;
int main() {
    pair<int, int> p1(10, 20);
    pair<int, int> p2 = {30, 40};

    // Accessing elements of the pair
    cout << "First pair: (" << p1.first << ", " << p1.second << ")\n";
    cout << "Second pair: (" << p2.first << ", " << p2.second << ")\n";

    // Swapping pairs
    swap(p1, p2);
    cout << "After swapping:\n";
    cout << "First pair: (" << p1.first << ", " << p1.second << ")\n";
    cout << "Second pair: (" << p2.first << ", " << p2.second << ")\n";

    // Nested parirs
    pair<int, pair<int, int>> nestedPair = {1, {2, 3}};
    cout << "Nested pair: (" << nestedPair.first << ", ("
            << nestedPair.second.first << ", "
            << nestedPair.second.second << "))\n";

    // Array of pairs
    pair<int , int> arr[] = { {1, 2}, {3, 4}, {5, 6} };
    cout << "Array of pairs:\n";
    for (const auto& p : arr) {
        cout << "(" << p.first << ", " << p.second << ") ";
    }

    cout << endl;
    // Accessing elements in an array of pairs
    cout << "First element of a pair at the index 0: "
         << arr[0].first << endl;
    cout << "First element of a pair at the index 1: "
         << arr[1].first << endl;
    cout << "Second element of a pair at the index 1: "
         << arr[1].second << endl;

    return 0;
}
```

```cpp
First pair: (10, 20)
Second pair: (30, 40)
After swapping:
First pair: (30, 40)
Second pair: (10, 20)
Nested pair: (1, (2, 3))
Array of pairs:
(1, 2) (3, 4) (5, 6)
First element of a pair at the index 0: 1
First element of a pair at the index 1: 3
Second element of a pair at the index 1: 4
```

## **C++ STL Vector — Complete Reference**

### **1. Creating & Initializing**

```cpp
vector<int> v1;                  // empty
vector<int> v2(5, 10);           // size 5, all elements 10
vector<int> v3 = {1, 2, 3, 4};   // initializer list
vector<int> v4(v3);              // copy from v3

```

**Output:**

```
v2 → 10 10 10 10 10
v3 → 1 2 3 4
v4 → 1 2 3 4

```

---

### **2. Adding Elements**

```cpp
vector<int> v;
v.push_back(5);   // add at end
v.emplace_back(10); // faster than push_back

```

**Output:**

```
5 10

```

---

### **3. Accessing Elements**

```cpp
vector<int> v = {10, 20, 30};
cout << v[0];      // 10
cout << v.at(1);   // 20
cout << v.front(); // 10
cout << v.back();  // 30

```

**Output:**

```
10
20
10
30

```

---

### **4. Size, Capacity, Empty**

```cpp
vector<int> v = {1, 2, 3};
cout << v.size();     // number of elements
cout << v.capacity(); // allocated space
cout << v.empty();    // 0 (false)

```

**Output (capacity may vary):**

```
3
4
0

```

---

### **5. Iterators**

```cpp
vector<int> v = {10, 20, 30};

// forward
for (auto it = v.begin(); it != v.end(); it++)
    cout << *it << " ";

// reverse
for (auto rit = v.rbegin(); rit != v.rend(); rit++)
    cout << *rit << " ";

```

**Output:**

```
10 20 30
30 20 10

```

---
### **6. Insert & Erase**

```cpp
vector<int> v = {1, 2, 4};
v.insert(v.begin() + 2, 3);     // 1 2 3 4
v.erase(v.begin() + 1);         // 1 3 4

```

**Output:**

```
1 3 4

```

---

### **7. Pop Back & Clear**

```cpp
vector<int> v = {1, 2, 3};
v.pop_back();   // removes last element
v.clear();      // removes all elements

```

**Output:**

```
After pop_back: 1 2
After clear size: 0

```

---

### **8. Assign**

```cpp
vector<int> v;
v.assign(5, 100); // fill with 5 copies of 100

```

**Output:**

```
100 100 100 100 100

```

---

### **9. Resize**

```cpp
vector<int> v = {1, 2, 3};
v.resize(5);     // expands with 0s
v.resize(2);     // shrinks

```

**Output:**

```
After resize(5): 1 2 3 0 0
After resize(2): 1 2

```

---

### **10. Swap**

```cpp
vector<int> a = {1, 2};
vector<int> b = {3, 4};
a.swap(b);

```

**Output:**

```
a: 3 4
b: 1 2

```

---

### **11. Sort & Reverse**

```cpp
vector<int> v = {40, 10, 30, 20};
sort(v.begin(), v.end());       // ascending
reverse(v.begin(), v.end());    // reverse order

```

**Output:**

```
Ascending: 10 20 30 40
Reversed: 40 30 20 10

```

---

### **12. Find**

```cpp
vector<int> v = {10, 20, 30};
auto it = find(v.begin(), v.end(), 20);
if (it != v.end()) cout << "Found at index " << (it - v.begin());

```

**Output:**

```
Found at index 1

```

---

### **13. Remove Duplicates**

```cpp
vector<int> v = {1, 1, 2, 2, 3};
v.erase(unique(v.begin(), v.end()), v.end());

```

**Output:**

```
1 2 3

```

---

### **14. 2D Vector**

```cpp
vector<vector<int>> mat = {
    {1, 2, 3},
    {4, 5, 6}
};

```

**Output:**

```
1 2 3
4 5 6

```

---

### **15. Vector of Pairs**

```cpp
vector<pair<int, int>> vp = {{1, 2}, {3, 4}};
for (auto p : vp) cout << p.first << "," << p.second << endl;

```

**Output:**

```
1,2
3,4

```

---

### **16. Max & Min**

```cpp
vector<int> v = {10, 20, 5};
cout << *max_element(v.begin(), v.end());
cout << *min_element(v.begin(), v.end());

```

**Output:**

```
20
5

```

---

### **17. Sum of Elements**

```cpp
vector<int> v = {1, 2, 3};
cout << accumulate(v.begin(), v.end(), 0);

```

**Output:**

```
6

```

---

### **18. Count Occurrences**

```cpp
vector<int> v = {1, 2, 2, 3};
cout << count(v.begin(), v.end(), 2);

```

**Output:**

```
2

```

---

### **19. Delete Specific Value**

```cpp
vector<int> v = {1, 2, 3, 2};
v.erase(remove(v.begin(), v.end(), 2), v.end());

```

**Output:**

```
1 3

```

---

### **20. Check if Sorted**

```cpp
vector<int> v = {1, 2, 3};
cout << is_sorted(v.begin(), v.end());

```

**Output:**

```
1  (true)

```

---

## **C++ STL List — Complete Notes**

---

### **1. Creating & Initializing**

```cpp
list<int> l1;                  // empty
list<int> l2(5, 10);           // size 5, all elements 10
list<int> l3 = {1, 2, 3, 4};   // initializer list
list<int> l4(l3);              // copy from l3
```

**Output:**

```
l2 → 10 10 10 10 10
l3 → 1 2 3 4
l4 → 1 2 3 4
```

---

### **2. Adding Elements**

```cpp
list<int> l;
l.push_back(5);      // add at end
l.push_front(1);     // add at front
l.emplace_back(10);  // faster insert at end
l.emplace_front(0);  // faster insert at front
```

**Output:**

```
0 1 5 10
```

---

### **3. Accessing Elements**

```cpp
list<int> l = {10, 20, 30};
cout << l.front(); // 10
cout << l.back();  // 30
```

**Output:**

```
10
30
```


---

### **4. Size & Empty**

```cpp
list<int> l = {1, 2, 3};
cout << l.size();  // 3
cout << l.empty(); // 0 (false)
```

**Output:**

```
3
0
```

---

### **5. Iterators**

```cpp
list<int> l = {10, 20, 30};

// forward
for (auto it = l.begin(); it != l.end(); it++)
    cout << *it << " ";

// reverse
for (auto rit = l.rbegin(); rit != l.rend(); rit++)
    cout << *rit << " ";
```

**Output:**

```
10 20 30
30 20 10
```

---

### **6. Insert & Erase**

```cpp
list<int> l = {1, 2, 4};
auto it = l.begin();
advance(it, 2);     // move iterator to index 2
l.insert(it, 3);    // insert before index 2
it = l.begin();
advance(it, 1);
l.erase(it);        // erase element at index 1
```

**Output:**

```
1 3 4
```

---

### **7. Pop Back & Pop Front**

```cpp
list<int> l = {1, 2, 3};
l.pop_back();   // remove last
l.pop_front();  // remove first
```

**Output:**

```
After pops: 2
```

---

### **8. Clear**

```cpp
list<int> l = {1, 2, 3};
l.clear(); // removes all
```

**Output:**

```
size: 0
```

---

### **9. Assign**

```cpp
list<int> l;
l.assign(4, 100); // fill with 4 copies of 100
```

**Output:**

```
100 100 100 100
```

---

### **10. Resize**

```cpp
list<int> l = {1, 2, 3};
l.resize(5); // expands with 0s
l.resize(2); // shrinks
```

**Output:**

```
After resize(5): 1 2 3 0 0
After resize(2): 1 2
```

---

### **11. Swap**

```cpp
list<int> a = {1, 2};
list<int> b = {3, 4};
a.swap(b);
```

**Output:**

```
a: 3 4
b: 1 2
```

---

### **12. Sort & Reverse**

```cpp
list<int> l = {40, 10, 30, 20};
l.sort();    // ascending
l.reverse(); // reverse order
```

**Output:**

```
Ascending: 10 20 30 40
Reversed: 40 30 20 10
```

---

### **13. Merge**

```cpp
list<int> l1 = {1, 3, 5};
list<int> l2 = {2, 4, 6};
l1.merge(l2); // l1 & l2 must be sorted
```

**Output:**

```
1 2 3 4 5 6
```

---

### **14. Remove**

```cpp
list<int> l = {1, 2, 2, 3};
l.remove(2); // removes all 2s
```

**Output:**

```
1 3
```

---

### **15. Remove If**

```cpp
list<int> l = {1, 2, 3, 4};
l.remove_if([](int x) { return x % 2 == 0; }); // remove even numbers
```

**Output:**

```
1 3
```

---

### **16. Unique**

```cpp
list<int> l = {1, 1, 2, 2, 3};
l.unique(); // remove consecutive duplicates
```

**Output:**

```
1 2 3
```

---

### **17. Splice**

```cpp
list<int> l1 = {1, 2};
list<int> l2 = {3, 4};
auto it = l1.begin();
advance(it, 1);
l1.splice(it, l2); // move all from l2 into l1 at position it
```

**Output:**

```
l1: 1 3 4 2
l2: (empty)
```

---

### **18. Max & Min**

```cpp
list<int> l = {10, 20, 5};
cout << *max_element(l.begin(), l.end());
cout << *min_element(l.begin(), l.end());
```

**Output:**

```
20
5
```

---

### **19. Count Occurrences**

```cpp
list<int> l = {1, 2, 2, 3};
cout << count(l.begin(), l.end(), 2);
```

**Output:**

```
2
```

---

### **20. Check if Sorted**

```cpp
list<int> l = {1, 2, 3};
cout << is_sorted(l.begin(), l.end());
```

**Output:**

```
1  (true)
```

---

### 🔹 Key Points about `list`

- **Doubly linked list** → No random access like `[]`.
- Insertions/removals in the middle are **O(1)** (if iterator is known).
- Sequential traversal is **O(n)**.
- Memory overhead is higher than `vector` due to pointers.

---
##  **C++ STL Deque — Complete Notes**

### **1. Creating & Initializing**

```cpp
deque<int> d1;                  // empty
deque<int> d2(5, 10);           // size 5, all elements 10
deque<int> d3 = {1, 2, 3, 4};   // initializer list
deque<int> d4(d3);              // copy from d3

```

**Output:**

```
d2 → 10 10 10 10 10
d3 → 1 2 3 4
d4 → 1 2 3 4

```

---

### **2. Adding Elements**

```cpp
deque<int> d;
d.push_back(5);     // add at end
d.push_front(1);    // add at front
d.emplace_back(10); // faster insert at end
d.emplace_front(0); // faster insert at front

```

**Output:**

```
0 1 5 10

```

---

### **3. Accessing Elements**

```cpp
deque<int> d = {10, 20, 30};
cout << d[0];      // 10
cout << d.at(1);   // 20
cout << d.front(); // 10
cout << d.back();  // 30

```

**Output:**

```
10
20
10
30

```

---

### **4. Size & Empty**

```cpp
deque<int> d = {1, 2, 3};
cout << d.size();  // 3
cout << d.empty(); // 0 (false)

```

**Output:**

```
3
0

```

---

### **5. Iterators**

```cpp
deque<int> d = {10, 20, 30};

// forward
for (auto it = d.begin(); it != d.end(); it++)
    cout << *it << " ";

// reverse
for (auto rit = d.rbegin(); rit != d.rend(); rit++)
    cout << *rit << " ";

```

**Output:**

```
10 20 30
30 20 10

```

---

### **6. Insert & Erase**

```cpp
deque<int> d = {1, 2, 4};
d.insert(d.begin() + 2, 3); // 1 2 3 4
d.erase(d.begin() + 1);     // 1 3 4

```

**Output:**

```
1 3 4

```

---

### **7. Pop Back & Pop Front**

```cpp
deque<int> d = {1, 2, 3};
d.pop_back();   // removes last
d.pop_front();  // removes first

```

**Output:**

```
After pops: 2

```

---

### **8. Clear**

```cpp
deque<int> d = {1, 2, 3};
d.clear(); // removes all

```

**Output:**

```
size: 0

```

---

### **9. Assign**

```cpp
deque<int> d;
d.assign(4, 100); // fill with 4 copies of 100

```

**Output:**

```
100 100 100 100

```

---

### **10. Resize**

```cpp
deque<int> d = {1, 2, 3};
d.resize(5); // expands with 0s
d.resize(2); // shrinks

```

**Output:**

```
After resize(5): 1 2 3 0 0
After resize(2): 1 2

```

---

### **11. Swap**

```cpp
deque<int> a = {1, 2};
deque<int> b = {3, 4};
a.swap(b);

```

**Output:**

```
a: 3 4
b: 1 2

```

---

### **12. Sort & Reverse**

```cpp
deque<int> d = {40, 10, 30, 20};
sort(d.begin(), d.end());    // ascending
reverse(d.begin(), d.end()); // reverse order

```

**Output:**

```
Ascending: 10 20 30 40
Reversed: 40 30 20 10

```

---

### **13. Max & Min**

```cpp
deque<int> d = {10, 20, 5};
cout << *max_element(d.begin(), d.end());
cout << *min_element(d.begin(), d.end());

```

**Output:**

```
20
5

```

---

### **14. Count Occurrences**

```cpp
deque<int> d = {1, 2, 2, 3};
cout << count(d.begin(), d.end(), 2);

```

**Output:**

```
2

```

---

### **15. Check if Sorted**

```cpp
deque<int> d = {1, 2, 3};
cout << is_sorted(d.begin(), d.end());

```

**Output:**

```
1  (true)

```

---

### 🔹 Key Points about `deque`

- **Double-ended queue** → Fast insert/delete at both ends.
- Random access supported (`[]` and `.at()`).
- Slower than `vector` for iterating (due to segmented storage).
- No continuous memory guarantee like `vector`.

---

## **C++ STL Queue — Complete Reference**

### **1. Creating & Initializing**

```cpp
queue<int> q;        // empty
queue<int> q2(q);    // copy from another queue

```

**Output:**

```
(empty queue, no direct print — must pop to access)

```

---

### **2. Adding Elements (`push` / `emplace`)**

```cpp
queue<int> q;
q.push(10);         // add at back
q.push(20);
q.emplace(30);      // faster insert

```

**Queue State:**

```
Front → 10 20 30 → Back

```

---

### **3. Removing Elements (`pop`)**

```cpp
queue<int> q;
q.push(1); q.push(2); q.push(3);
q.pop();  // removes front (1)

```

**Queue State:**

```
Front → 2 3 → Back

```

---

### **4. Accessing Elements**

```cpp
queue<int> q;
q.push(10); q.push(20);
cout << q.front(); // 10
cout << q.back();  // 20

```

**Output:**

```
10
20

```

---

### **5. Size & Empty**

```cpp
queue<int> q;
q.push(1); q.push(2);
cout << q.size();  // 2
cout << q.empty(); // 0 (false)

```

**Output:**

```
2
0

```

---

### **6. Example — Processing a Queue**

```cpp
queue<string> q;
q.push("A");
q.push("B");
q.push("C");

while (!q.empty()) {
    cout << q.front() << " ";
    q.pop();
}

```

**Output:**

```
A B C

```

---

### **7. Swap**

```cpp
queue<int> q1, q2;
q1.push(1); q1.push(2);
q2.push(3);
q1.swap(q2);

```

**Queue States:**

```
q1: 3
q2: 1 2

```

---

### 🔹 Key Points about `queue`

- **FIFO** → First element in is the first element out.
- **Only access front and back** — no iterators or random access.
- Default underlying container is `deque`, but can also be `list` or `vector`.
- Both insertions and deletions are **O(1)** operations.

---

## **C++ STL Priority Queue — Complete Reference**

### **1. Creating & Initializing**

```cpp
priority_queue<int> pq;                       // max-heap (default)
priority_queue<int, vector<int>, greater<int>> minpq; // min-heap
```

---

### **2. Adding Elements (`push` / `emplace`)**

```cpp
priority_queue<int> pq;
pq.push(10);
pq.push(30);
pq.push(20);
pq.emplace(40); // faster insert
```

**State (max-heap):**

```
Top → 40
Other elements in heap order
```

---

### **3. Accessing Top Element**

```cpp
priority_queue<int> pq;
pq.push(10); pq.push(50); pq.push(30);
cout << pq.top();
```

**Output:**

```
50
```

---

### **4. Removing Elements**

```cpp
priority_queue<int> pq;
pq.push(10); pq.push(20); pq.push(30);
pq.pop(); // removes top (30 in this case)
```

**Remaining State (max-heap):**

```
Top → 20
```

---

### **5. Size & Empty**

```cpp
priority_queue<int> pq;
pq.push(5); pq.push(15);
cout << pq.size();  // 2
cout << pq.empty(); // 0 (false)
```

**Output:**

```
2
0
```

---

### **6. Example — Processing Priority Queue**

```cpp
priority_queue<int> pq;
pq.push(3);
pq.push(5);
pq.push(1);

while (!pq.empty()) {
    cout << pq.top() << " ";
    pq.pop();
}
```

**Output (max-heap):**

```
5 3 1
```

---

### **7. Min-Heap Example**

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
pq.push(3);
pq.push(5);
pq.push(1);

while (!pq.empty()) {
    cout << pq.top() << " ";
    pq.pop();
}
```

**Output (min-heap):**

```
1 3 5
```

---

### **8. Swap**

```cpp
priority_queue<int> pq1, pq2;
pq1.push(10); pq2.push(20);
pq1.swap(pq2);
```

**State:**

```
pq1: top = 20
pq2: top = 10
```

---

### 🔹 Key Points about `priority_queue`

- Default is **max-heap** → largest element is `top()`.
- For **min-heap**, use:`priority_queue&lt;Type, vector&lt;Type&gt;, greater&lt;Type&gt;&gt;`
- Internally implemented as a **binary heap**.
- Time complexity: Insertion → **O(log n)**, Removal → **O(log n)**, Access top → **O(1)**.
- No iterators or random access.

---

## **C++ STL Set — Complete Reference**

### **1. Creating & Initializing**

```cpp
set<int> s;                  // empty set
set<int> s2 = {1, 2, 3, 4};  // initializer list
set<int> s3(s2);             // copy constructor

```

---

### **2. Inserting Elements**

```cpp
set<int> s;
s.insert(10);
s.insert(5);
s.insert(20);
s.insert(10); // duplicate ignored

```

**Output:**

```
5 10 20   // automatically sorted & unique

```

---

### **3. Accessing Elements (Iterators)**

```cpp
set<int> s = {10, 20, 30};
for (auto it = s.begin(); it != s.end(); ++it)
    cout << *it << " ";

```

**Output:**

```
10 20 30

```

---

### **4. Searching**

```cpp
set<int> s = {10, 20, 30};
auto it = s.find(20);
if (it != s.end()) cout << "Found";
else cout << "Not Found";

```

**Output:**

```
Found

```

---

### **5. Counting (Presence Check)**

```cpp
set<int> s = {10, 20, 30};
cout << s.count(20); // 1
cout << s.count(40); // 0

```

---

### **6. Removing Elements**

```cpp
set<int> s = {10, 20, 30};
s.erase(20);                  // by value
s.erase(s.begin());           // by iterator
s.erase(s.find(30));          // by iterator from find()

```

---

### **7. Size & Empty**

```cpp
set<int> s = {1, 2, 3};
cout << s.size();  // 3
cout << s.empty(); // 0 (false)

```

---

### **8. Lower Bound & Upper Bound**

```cpp
set<int> s = {10, 20, 30, 40};
cout << *s.lower_bound(25); // 30 (>= 25)
cout << *s.upper_bound(30); // 40 (> 30)

```

---

### **9. Example — Simple Usage**

```cpp
set<int> s;
s.insert(3); s.insert(1); s.insert(2);

for (auto x : s) cout << x << " ";

```

**Output:**

```
1 2 3

```

---

### **10. Swap**

```cpp
set<int> s1 = {1, 2}, s2 = {3, 4};
s1.swap(s2);

```

**State:**

```
s1: 3 4
s2: 1 2

```

---

### 🔹 Key Points about `set`

- **Unique elements only** — duplicates are ignored.
- Elements are **automatically sorted** (ascending by default).
- Internally implemented as a **balanced BST (Red-Black Tree)**.
- All operations → **O(log n)** time complexity.
- Iterators are **bidirectional**.
- For **unsorted** version → use `unordered_set` (hash-based, O(1) average).
---

## **C++ STL Multiset — Complete Reference**

### **1. Creating & Initializing**

```cpp
multiset<int> ms;                    // empty
multiset<int> ms2 = {1, 2, 2, 3};    // initializer list (duplicates allowed)
multiset<int> ms3(ms2);              // copy constructor

```

---

### **2. Inserting Elements**

```cpp
multiset<int> ms;
ms.insert(10);
ms.insert(5);
ms.insert(10); // duplicate allowed

```

**Output (ordered):**

```
5 10 10

```

---

### **3. Accessing Elements (Iterators)**

```cpp
multiset<int> ms = {10, 20, 10};
for (auto it = ms.begin(); it != ms.end(); ++it)
    cout << *it << " ";

```

**Output:**

```
10 10 20

```

---

### **4. Searching**

```cpp
multiset<int> ms = {10, 20, 30};
auto it = ms.find(20); // returns iterator to first 20
if (it != ms.end()) cout << "Found";

```

**Output:**

```
Found

```

---

### **5. Counting Occurrences**

```cpp
multiset<int> ms = {10, 20, 20, 30};
cout << ms.count(20); // 2

```

---

### **6. Removing Elements**

```cpp
multiset<int> ms = {10, 20, 20, 30};
ms.erase(20);                  // removes ALL 20s
// OR
ms.erase(ms.find(20));         // removes only one occurrence

```

---

### **7. Size & Empty**

```cpp
multiset<int> ms = {1, 2, 2};
cout << ms.size();  // 3
cout << ms.empty(); // 0 (false)

```

---

### **8. Lower Bound & Upper Bound**

```cpp
multiset<int> ms = {10, 20, 20, 30};
cout << *ms.lower_bound(20); // 20 (first >= 20)
cout << *ms.upper_bound(20); // 30 (first > 20)

```

---

### **9. Equal Range (Get All Duplicates)**

```cpp
multiset<int> ms = {10, 20, 20, 30};
auto range = ms.equal_range(20);
for (auto it = range.first; it != range.second; ++it)
    cout << *it << " ";

```

**Output:**

```
20 20

```

---

### **10. Example — Simple Usage**

```cpp
multiset<int> ms;
ms.insert(3); ms.insert(1); ms.insert(2); ms.insert(2);

for (auto x : ms) cout << x << " ";

```

**Output:**

```
1 2 2 3

```

---

### **11. Swap**

```cpp
multiset<int> ms1 = {1, 1}, ms2 = {2, 2};
ms1.swap(ms2);

```

**State:**

```
ms1: 2 2
ms2: 1 1

```

---

### 🔹 Key Points about `multiset`

- **Duplicates allowed** (unlike `set`).
- **Automatically sorted** (ascending by default).
- Internally implemented as a **balanced BST (Red-Black Tree)**.
- All operations have **O(log n)** time complexity.
- Iterators are **bidirectional**.
- For **unsorted** duplicates, use `unordered_multiset` (hash-based, O(1) average).

---

## **C++ STL unordered_multiset — Complete Notes**

### **1. Creating & Initializing**

```cpp
unordered_multiset<int> ums;                  // empty
unordered_multiset<int> ums2 = {1, 2, 2, 3};  // allows duplicates
unordered_multiset<int> ums3(ums2);           // copy constructor

```

---

### **2. Inserting Elements**

```cpp
unordered_multiset<int> ums;
ums.insert(10);
ums.insert(5);
ums.insert(10); // duplicate allowed

```

**Output (unordered, duplicates kept):**

```
5 10 10

```

_(Order may vary)_

---

### **3. Iterating**

```cpp
unordered_multiset<int> ums = {10, 20, 10};
for (auto it = ums.begin(); it != ums.end(); ++it)
    cout << *it << " ";

```

**Possible Output:**

```
10 20 10

```

_(Order not guaranteed)_

---

### **4. Searching**

```cpp
unordered_multiset<int> ums = {10, 20, 30};
auto it = ums.find(20);
if (it != ums.end()) cout << "Found";

```

**Output:**

```
Found

```

---

### **5. Counting Occurrences**

```cpp
unordered_multiset<int> ums = {10, 20, 20, 30};
cout << ums.count(20); // 2

```

---

### **6. Removing Elements**

```cpp
unordered_multiset<int> ums = {10, 20, 20, 30};
ums.erase(20);                  // removes ALL 20s
// OR
ums.erase(ums.find(20));        // removes one occurrence

```

---

### **7. Size & Empty**

```cpp
unordered_multiset<int> ums = {1, 2, 2};
cout << ums.size();  // 3
cout << ums.empty(); // 0 (false)

```

---

### **8. Equal Range**

```cpp
unordered_multiset<int> ums = {10, 20, 20, 30};
auto range = ums.equal_range(20);
for (auto it = range.first; it != range.second; ++it)
    cout << *it << " ";

```

**Output (order may vary):**

```
20 20

```

---

### **9. Swap**

```cpp
unordered_multiset<int> ums1 = {1, 1}, ums2 = {2, 2};
ums1.swap(ums2);

```

**State (order may vary):**

```
ums1: 2 2
ums2: 1 1

```

---

### 🔹 Key Points about `unordered_multiset`

- **Duplicates allowed**.
- **No guaranteed order** of elements.
- Implemented using **hash table**.
- Average complexity: **O(1)** for insert/search/erase.
- Worst-case complexity: **O(n)** (rare, if many collisions).
- Iterators are **forward iterators** (not bidirectional).

---

## **C++ STL map — Complete Notes**

### **1. Creating & Initializing**

```cpp
map<int, string> m;                      // empty
map<int, string> m2 = {{1, "one"}, {2, "two"}}; // list initialization
map<int, string> m3(m2);                  // copy constructor

```

---

### **2. Inserting Elements**

```cpp
map<int, string> m;
m.insert({1, "one"});
m.insert(make_pair(2, "two"));
m[3] = "three"; // also inserts

```

**State (sorted by key):**

```
1 -> one
2 -> two
3 -> three

```

---

### **3. Accessing Elements**

```cpp
map<int, string> m = {{1, "one"}, {2, "two"}};
cout << m[1];           // "one"
cout << m.at(2);        // "two"
// m[3];                // Inserts key 3 with default value if not present

```

---

### **4. Iterating**

```cpp
map<int, string> m = {{2, "two"}, {1, "one"}};
for (auto it = m.begin(); it != m.end(); ++it)
    cout << it->first << " => " << it->second << "\n";

```

**Output (sorted by key):**

```
1 => one
2 => two

```

---

### **5. Searching**

```cpp
map<int, string> m = {{1, "one"}, {2, "two"}};
auto it = m.find(2);
if (it != m.end()) cout << "Found: " << it->second;

```

**Output:**

```
Found: two

```

---

### **6. Checking Key Existence**

```cpp
map<int, string> m = {{1, "one"}};
cout << m.count(1); // 1
cout << m.count(5); // 0

```

---

### **7. Removing Elements**

```cpp
map<int, string> m = {{1, "one"}, {2, "two"}, {3, "three"}};
m.erase(2);              // remove key 2
m.erase(m.begin());      // remove first element
m.clear();               // remove all

```

---

### **8. Size & Empty**

```cpp
map<int, string> m = {{1, "one"}};
cout << m.size();  // 1
cout << m.empty(); // 0 (false)

```

---

### **9. Lower Bound & Upper Bound**

```cpp
map<int, string> m = {{1, "one"}, {3, "three"}, {5, "five"}};
auto it = m.lower_bound(3); // >= 3
cout << it->first;          // 3
it = m.upper_bound(3);      // > 3
cout << it->first;          // 5

```

---

### **10. Swap**

```cpp
map<int, string> m1 = {{1, "one"}}, m2 = {{2, "two"}};
m1.swap(m2);

```

**State:**

```
m1: 2 => two
m2: 1 => one

```

---

### 🔹 Key Points about `map`

- Stores **unique keys** in **sorted order**.
- Implemented as a **balanced binary search tree** (usually Red-Black Tree).
- Insertion, deletion, and search operations are **O(log n)**.
- Keys are **const** (cannot be modified directly via iterator).
- Supports **bidirectional iterators**.

---

## **C++ STL multimap — Complete Notes**

### **1. Creating & Initializing**

```cpp
multimap<int, string> mm; // empty
multimap<int, string> mm2 = {{1, "one"}, {2, "two"}, {1, "uno"}}; // duplicates allowed
multimap<int, string> mm3(mm2); // copy constructor

```

---

### **2. Inserting Elements**

```cpp
multimap<int, string> mm;
mm.insert({1, "one"});
mm.insert(make_pair(2, "two"));
mm.insert({1, "uno"}); // duplicate key

```

**State (sorted by key):**

```
1 -> one
1 -> uno
2 -> two

```

---

### **3. Iterating**

```cpp
multimap<int, string> mm = {{2, "two"}, {1, "one"}, {1, "uno"}};
for (auto it = mm.begin(); it != mm.end(); ++it)
    cout << it->first << " => " << it->second << "\n";

```

**Output:**

```
1 => one
1 => uno
2 => two

```

---

### **4. Finding Elements**

```cpp
multimap<int, string> mm = {{1, "one"}, {1, "uno"}, {2, "two"}};
auto it = mm.find(1);
if (it != mm.end()) cout << it->first << " => " << it->second;

```

**Output:**

```
1 => one

```

> find() returns first occurrence of the key.

---

### **5. Counting Elements with Same Key**

```cpp
multimap<int, string> mm = {{1, "one"}, {1, "uno"}, {2, "two"}};
cout << mm.count(1); // 2

```

---

### **6. Getting All Values of a Key**

```cpp
multimap<int, string> mm = {{1, "one"}, {1, "uno"}, {2, "two"}};
auto range = mm.equal_range(1); // returns pair<iterator, iterator>
for (auto it = range.first; it != range.second; ++it)
    cout << it->second << " ";

```

**Output:**

```
one uno

```

---

### **7. Removing Elements**

```cpp
multimap<int, string> mm = {{1, "one"}, {1, "uno"}, {2, "two"}};
mm.erase(1);            // removes all elements with key = 1
mm.erase(mm.begin());   // remove first element
mm.clear();             // remove all

```

---

### **8. Size & Empty**

```cpp
multimap<int, string> mm = {{1, "one"}};
cout << mm.size();  // 1
cout << mm.empty(); // 0 (false)

```

---

### **9. Lower Bound & Upper Bound**

```cpp
multimap<int, string> mm = {{1, "one"}, {1, "uno"}, {3, "three"}};
auto it = mm.lower_bound(1); // first >= 1
cout << it->second;          // one
it = mm.upper_bound(1);      // first > 1
cout << it->second;          // three

```

---

### **10. Swap**

```cpp
multimap<int, string> mm1 = {{1, "one"}}, mm2 = {{2, "two"}};
mm1.swap(mm2);

```

**State:**

```
mm1: 2 => two
mm2: 1 => one

```

---

### 🔹 Key Points about `multimap`

- **Allows duplicate keys**, keeps sorted order.
- Keys are **const** (cannot modify directly).
- Implemented as a **balanced binary search tree** (usually Red-Black Tree).
- Insertion, deletion, search → **O(log n)**.
- Supports **bidirectional iterators**.
- Best when **you need sorted data but may have multiple same keys**.

---

## **C++ STL Cheatsheet (Containers)**

| Container              | Type                   | Ordering                      | Duplicates | Iterator Type | Insert/Search/Delete Complexity                                   |
| ---------------------- | ---------------------- | ----------------------------- | ---------- | ------------- | ----------------------------------------------------------------- |
| **vector**             | Dynamic array          | Maintains insertion order     | Yes        | Random Access | Insert (end): O(1) amortized, Insert (middle): O(n), Search: O(n) |
| **deque**              | Double-ended queue     | Maintains insertion order     | Yes        | Random Access | Insert front/back: O(1), Middle: O(n), Search: O(n)               |
| **list**               | Doubly linked list     | Maintains insertion order     | Yes        | Bidirectional | Insert/Delete anywhere: O(1) (with iterator), Search: O(n)        |
| **forward_list**       | Singly linked list     | Maintains insertion order     | Yes        | Forward       | Insert/Delete: O(1) (with iterator), Search: O(n)                 |
| **array**              | Fixed-size array       | Maintains index order         | Yes        | Random Access | Access: O(1), Search: O(n)                                        |
| **stack**              | Adapter (LIFO)         | N/A                           | Yes        | No Iterators  | Push/Pop/Top: O(1)                                                |
| **queue**              | Adapter (FIFO)         | N/A                           | Yes        | No Iterators  | Push/Pop/Front: O(1)                                              |
| **priority_queue**     | Heap                   | Sorted by priority            | Yes        | No Iterators  | Push: O(log n), Pop: O(log n), Top: O(1)                          |
| **set**                | Balanced BST (RB-tree) | Sorted (ascending by default) | No         | Bidirectional | Insert/Search/Delete: O(log n)                                    |
| **multiset**           | Balanced BST (RB-tree) | Sorted                        | Yes        | Bidirectional | Insert/Search/Delete: O(log n)                                    |
| **unordered_set**      | Hash Table             | Unordered                     | No         | Forward       | Avg O(1), Worst O(n)                                              |
| **unordered_multiset** | Hash Table             | Unordered                     | Yes        | Forward       | Avg O(1), Worst O(n)                                              |
| **map**                | Balanced BST (RB-tree) | Sorted by key                 | No         | Bidirectional | Insert/Search/Delete: O(log n)                                    |
| **multimap**           | Balanced BST (RB-tree) | Sorted by key                 | Yes        | Bidirectional | Insert/Search/Delete: O(log n)                                    |
| **unordered_map**      | Hash Table             | Unordered                     | No         | Forward       | Avg O(1), Worst O(n)                                              |
| **unordered_multimap** | Hash Table             | Unordered                     | Yes        | Forward       | Avg O(1), Worst O(n)                                              |

---

### **Iterators Types Summary**

| Iterator Type | Moves                 | Read/Write | Example Containers              |
| ------------- | --------------------- | ---------- | ------------------------------- |
| Input         | Forward only          | Read       | `istream_iterator`              |
| Output        | Forward only          | Write      | `ostream_iterator`              |
| Forward       | Forward only          | Read/Write | `forward_list`, `unordered_set` |
| Bidirectional | Forward/Backward      | Read/Write | `list`, `set`, `map`            |
| Random Access | Any direction + jumps | Read/Write | `vector`, `deque`, `array`      |

---

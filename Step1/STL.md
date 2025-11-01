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
First element of a pair at the index 1: 4
```



## **C++ STL String — Complete Reference**

### **1. Creating & Initializing**

```cpp
string s1;                      // empty string
string s2 = "Hello";            // initialize with C-string
string s3("World");             // constructor
string s4(5, 'A');              // "AAAAA"
string s5(s2);                  // copy from s2
string s6 = s2 + " " + s3;      // concatenation

```

**Output:**

```
s2 → Hello
s3 → World
s4 → AAAAA
s5 → Hello
s6 → Hello World

```

---

### **2. Adding Characters/Strings**

```cpp
string s = "Hello";
s.push_back('!');               // add single char at end
s += " World";                  // concatenate
s.append(" 2025");              // append string
s.insert(5, " C++");            // insert at position 5

```

**Output:**

```
Hello! World 2025
Hello C++! World 2025

```

---

### **3. Accessing Characters**

```cpp
string s = "Hello";
cout << s[0];       // 'H'
cout << s.at(1);    // 'e' (with bounds checking)
cout << s.front();  // 'H' (first char)
cout << s.back();   // 'o' (last char)

```

**Output:**

```
H
e
H
o

```

---

### **4. Size & Length**

```cpp
string s = "Hello";
cout << s.size();      // 5
cout << s.length();    // 5 (same as size)
cout << s.empty();     // 0 (false)
cout << s.capacity();  // allocated capacity

```

**Output:**

```
5
5
0

```

---

### **5. Iterators**

```cpp
string s = "ABC";

// forward
for (auto it = s.begin(); it != s.end(); it++)
    cout << *it << " ";

// reverse
for (auto rit = s.rbegin(); rit != s.rend(); rit++)
    cout << *rit << " ";

```

**Output:**

```
A B C
C B A

```

---

### **6. Substring**

```cpp
string s = "HelloWorld";
string sub = s.substr(0, 5);    // from index 0, length 5
string sub2 = s.substr(5);      // from index 5 to end

```

**Output:**

```
sub → Hello
sub2 → World

```

---

### **7. Find & Search**

```cpp
string s = "Hello World";
size_t pos = s.find("World");       // returns index (6)
size_t pos2 = s.find("C++");        // returns string::npos (not found)
size_t pos3 = s.rfind("o");         // reverse find, last occurrence (7)
size_t pos4 = s.find_first_of("aeiou"); // first vowel (1, 'e')
size_t pos5 = s.find_last_of("aeiou");  // last vowel (7, 'o')

```

**Output:**

```
6
string::npos (not found)
7
1
7

```

---

### **8. Replace**

```cpp
string s = "Hello World";
s.replace(6, 5, "C++");         // replace 5 chars from index 6

```

**Output:**

```
Hello C++

```

---

### **9. Erase**

```cpp
string s = "Hello World";
s.erase(5, 6);                  // erase 6 chars from index 5
s.erase(s.begin() + 2);         // erase single char at index 2

```

**Output:**

```
After first erase: Hello
After second erase: Helo

```

---

### **10. Clear**

```cpp
string s = "Hello";
s.clear();      // removes all characters

```

**Output:**

```
size: 0
empty: 1 (true)

```

---

### **11. Compare**

```cpp
string s1 = "ABC";
string s2 = "ABC";
string s3 = "XYZ";

cout << s1.compare(s2);  // 0 (equal)
cout << s1.compare(s3);  // negative (s1 < s3)
cout << s3.compare(s1);  // positive (s3 > s1)

```

**Output:**

```
0
-1 (or negative value)
1 (or positive value)

```

---

### **12. C-String Conversion**

```cpp
string s = "Hello";
const char* cstr = s.c_str();   // C-string (const char*)
char* data = s.data();          // direct access to internal buffer

```

**Output:**

```
cstr → Hello (as C-string)

```

---

### **13. String to Number Conversion**

```cpp
string s1 = "123";
string s2 = "45.67";
string s3 = "100";

int num = stoi(s1);             // string to int
double d = stod(s2);            // string to double
long l = stol(s3);              // string to long
long long ll = stoll(s3);       // string to long long

```

**Output:**

```
123
45.67
100
100

```

---

### **14. Number to String Conversion**

```cpp
int num = 123;
double d = 45.67;

string s1 = to_string(num);     // int to string
string s2 = to_string(d);       // double to string

```

**Output:**

```
"123"
"45.670000"

```

---

### **15. Uppercase & Lowercase**

```cpp
string s = "Hello World";

// Convert to uppercase
transform(s.begin(), s.end(), s.begin(), ::toupper);
cout << s << endl;

// Convert to lowercase
transform(s.begin(), s.end(), s.begin(), ::tolower);
cout << s << endl;

```

**Output:**

```
HELLO WORLD
hello world

```

---

### **16. Reverse String**

```cpp
string s = "Hello";
reverse(s.begin(), s.end());

```

**Output:**

```
olleH

```

---

### **17. Sort String**

```cpp
string s = "dcba";
sort(s.begin(), s.end());       // ascending
sort(s.begin(), s.end(), greater<char>()); // descending

```

**Output:**

```
Ascending: abcd
Descending: dcba

```

---

### **18. Check if Palindrome**

```cpp
string s = "racecar";
string rev = s;
reverse(rev.begin(), rev.end());
cout << (s == rev ? "Palindrome" : "Not Palindrome");

```

**Output:**

```
Palindrome

```

---

### **19. Count Character Occurrences**

```cpp
string s = "hello world";
cout << count(s.begin(), s.end(), 'l');

```

**Output:**

```
3

```

---

### **20. Remove Specific Character**

```cpp
string s = "hello world";
s.erase(remove(s.begin(), s.end(), 'l'), s.end());

```

**Output:**

```
heo word

```

---

### **21. Check if Substring Exists**

```cpp
string s = "Hello World";
if (s.find("World") != string::npos)
    cout << "Found";
else
    cout << "Not Found";

```

**Output:**

```
Found

```

---

### **22. Split String (Using Stringstream)**

```cpp
string s = "Hello World C++";
stringstream ss(s);
string word;

while (ss >> word)
    cout << word << endl;

```

**Output:**

```
Hello
World
C++

```

---

### **23. Join Strings**

```cpp
vector<string> words = {"Hello", "World", "C++"};
string result;

for (int i = 0; i < words.size(); i++) {
    result += words[i];
    if (i < words.size() - 1) result += " ";
}

```

**Output:**

```
Hello World C++

```

---

### **24. Trim Whitespace**

```cpp
string s = "  Hello World  ";

// Left trim
s.erase(s.begin(), find_if(s.begin(), s.end(), [](char c) {
    return !isspace(c);
}));

// Right trim
s.erase(find_if(s.rbegin(), s.rend(), [](char c) {
    return !isspace(c);
}).base(), s.end());

```

**Output:**

```
Hello World

```

---

### **25. Swap Strings**

```cpp
string s1 = "Hello";
string s2 = "World";
s1.swap(s2);

```

**Output:**

```
s1: World
s2: Hello

```

---

### **26. Resize String**

```cpp
string s = "Hello";
s.resize(10, '!');      // expand with '!'
s.resize(3);            // shrink

```

**Output:**

```
After resize(10): Hello!!!!!
After resize(3): Hel

```

---

### **27. Check if String is Sorted**

```cpp
string s = "abc";
cout << is_sorted(s.begin(), s.end());

```

**Output:**

```
1  (true)

```

---

### **28. Lexicographic Comparison**

```cpp
string s1 = "apple";
string s2 = "banana";

if (s1 < s2) cout << s1 << " comes before " << s2;

```

**Output:**

```
apple comes before banana

```

---

### **29. String Permutation (Next)**

```cpp
string s = "abc";
next_permutation(s.begin(), s.end());

```

**Output:**

```
acb

```

---

### **30. Check if Anagram**

```cpp
string s1 = "listen";
string s2 = "silent";

sort(s1.begin(), s1.end());
sort(s2.begin(), s2.end());

cout << (s1 == s2 ? "Anagram" : "Not Anagram");

```

**Output:**

```
Anagram

```

---

### 🔹 Key Points about `string`

- **Dynamic array of characters** → automatically resizes.
- Part of `<string>` header (not `<cstring>`).
- Supports **random access** with `[]` and `.at()`.
- All major operations: **concatenation, search, replace, substring**.
- **O(1)** access, **O(n)** for search operations.
- Interoperable with **C-strings** via `.c_str()`.
- Strings are **mutable** (can be modified in place).

---

## 📌 **String Manipulation Examples — LeetCode Problems**

### **1. Valid Palindrome (LeetCode #125)**

**Problem:** Check if a string is a palindrome, ignoring non-alphanumeric characters and case.

```cpp
bool isPalindrome(string s) {
    int left = 0, right = s.size() - 1;
    
    while (left < right) {
        // Skip non-alphanumeric from left
        while (left < right && !isalnum(s[left])) left++;
        // Skip non-alphanumeric from right
        while (left < right && !isalnum(s[right])) right--;
        
        // Compare characters (case-insensitive)
        if (tolower(s[left]) != tolower(s[right]))
            return false;
        
        left++;
        right--;
    }
    return true;
}
```

**Test Cases:**

```cpp
isPalindrome("A man, a plan, a canal: Panama");  // true
isPalindrome("race a car");                       // false
isPalindrome(" ");                                // true
```

**Output:**

```
true
false
true
```

---

### **2. Reverse String (LeetCode #344)**

**Problem:** Reverse a string in-place.

```cpp
void reverseString(vector<char>& s) {
    int left = 0, right = s.size() - 1;
    
    while (left < right) {
        swap(s[left], s[right]);
        left++;
        right--;
    }
}
```

**Test Cases:**

```cpp
vector<char> s1 = {'h', 'e', 'l', 'l', 'o'};
reverseString(s1);  // ['o','l','l','e','h']

vector<char> s2 = {'H', 'a', 'n', 'n', 'a', 'h'};
reverseString(s2);  // ['h','a','n','n','a','H']
```

**Output:**

```
olleh
hannaH
```

---

### **3. Valid Anagram (LeetCode #242)**

**Problem:** Check if two strings are anagrams.

```cpp
bool isAnagram(string s, string t) {
    if (s.size() != t.size()) return false;
    
    sort(s.begin(), s.end());
    sort(t.begin(), t.end());
    
    return s == t;
}

// Optimized using frequency map
bool isAnagram(string s, string t) {
    if (s.size() != t.size()) return false;
    
    unordered_map<char, int> freq;
    
    for (char c : s) freq[c]++;
    for (char c : t) {
        if (--freq[c] < 0) return false;
    }
    return true;
}
```

**Test Cases:**

```cpp
isAnagram("anagram", "nagaram");  // true
isAnagram("rat", "car");          // false
```

**Output:**

```
true
false
```

---

### **4. Longest Common Prefix (LeetCode #14)**

**Problem:** Find the longest common prefix among an array of strings.

```cpp
string longestCommonPrefix(vector<string>& strs) {
    if (strs.empty()) return "";
    
    string prefix = strs[0];
    
    for (int i = 1; i < strs.size(); i++) {
        while (strs[i].find(prefix) != 0) {
            prefix = prefix.substr(0, prefix.size() - 1);
            if (prefix.empty()) return "";
        }
    }
    return prefix;
}
```

**Test Cases:**

```cpp
vector<string> strs1 = {"flower", "flow", "flight"};
longestCommonPrefix(strs1);  // "fl"

vector<string> strs2 = {"dog", "racecar", "car"};
longestCommonPrefix(strs2);  // ""
```

**Output:**

```
"fl"
""
```

---

### **5. First Unique Character (LeetCode #387)**

**Problem:** Find the first non-repeating character in a string.

```cpp
int firstUniqChar(string s) {
    unordered_map<char, int> freq;
    
    // Count frequencies
    for (char c : s) freq[c]++;
    
    // Find first unique
    for (int i = 0; i < s.size(); i++) {
        if (freq[s[i]] == 1) return i;
    }
    return -1;
}
```

**Test Cases:**

```cpp
firstUniqChar("leetcode");      // 0 ('l')
firstUniqChar("loveleetcode");  // 2 ('v')
firstUniqChar("aabb");          // -1
```

**Output:**

```
0
2
-1
```

---

### **6. Reverse Words in a String (LeetCode #151)**

**Problem:** Reverse the order of words in a string.

```cpp
string reverseWords(string s) {
    stringstream ss(s);
    string word, result;
    vector<string> words;
    
    // Extract words
    while (ss >> word) {
        words.push_back(word);
    }
    
    // Reverse and join
    for (int i = words.size() - 1; i >= 0; i--) {
        result += words[i];
        if (i > 0) result += " ";
    }
    return result;
}
```

**Test Cases:**

```cpp
reverseWords("the sky is blue");      // "blue is sky the"
reverseWords("  hello world  ");      // "world hello"
reverseWords("a good   example");     // "example good a"
```

**Output:**

```
"blue is sky the"
"world hello"
"example good a"
```

---

### **7. String to Integer (atoi) (LeetCode #8)**

**Problem:** Convert a string to an integer with edge cases.

```cpp
int myAtoi(string s) {
    int i = 0, n = s.size();
    int sign = 1;
    long result = 0;
    
    // Skip leading whitespace
    while (i < n && s[i] == ' ') i++;
    
    // Check sign
    if (i < n && (s[i] == '+' || s[i] == '-')) {
        sign = (s[i] == '-') ? -1 : 1;
        i++;
    }
    
    // Convert digits
    while (i < n && isdigit(s[i])) {
        result = result * 10 + (s[i] - '0');
        
        // Check overflow
        if (result * sign > INT_MAX) return INT_MAX;
        if (result * sign < INT_MIN) return INT_MIN;
        
        i++;
    }
    
    return (int)(result * sign);
}
```

**Test Cases:**

```cpp
myAtoi("42");              // 42
myAtoi("   -42");          // -42
myAtoi("4193 with words"); // 4193
myAtoi("words and 987");   // 0
```

**Output:**

```
42
-42
4193
0
```

---

### **8. Longest Substring Without Repeating Characters (LeetCode #3)**

**Problem:** Find the length of the longest substring without repeating characters.

```cpp
int lengthOfLongestSubstring(string s) {
    unordered_map<char, int> lastSeen;
    int maxLen = 0, start = 0;
    
    for (int end = 0; end < s.size(); end++) {
        char c = s[end];
        
        // If char seen, move start
        if (lastSeen.count(c) && lastSeen[c] >= start) {
            start = lastSeen[c] + 1;
        }
        
        lastSeen[c] = end;
        maxLen = max(maxLen, end - start + 1);
    }
    return maxLen;
}
```

**Test Cases:**

```cpp
lengthOfLongestSubstring("abcabcbb");  // 3 ("abc")
lengthOfLongestSubstring("bbbbb");     // 1 ("b")
lengthOfLongestSubstring("pwwkew");    // 3 ("wke")
```

**Output:**

```
3
1
3
```

---

### **9. Group Anagrams (LeetCode #49)**

**Problem:** Group strings that are anagrams together.

```cpp
vector<vector<string>> groupAnagrams(vector<string>& strs) {
    unordered_map<string, vector<string>> groups;
    
    for (string s : strs) {
        string key = s;
        sort(key.begin(), key.end());
        groups[key].push_back(s);
    }
    
    vector<vector<string>> result;
    for (auto& pair : groups) {
        result.push_back(pair.second);
    }
    return result;
}
```

**Test Cases:**

```cpp
vector<string> strs = {"eat", "tea", "tan", "ate", "nat", "bat"};
groupAnagrams(strs);
// [["bat"], ["nat","tan"], ["ate","eat","tea"]]
```

**Output:**

```
[["bat"], ["nat","tan"], ["ate","eat","tea"]]
```

---

### **10. Longest Palindromic Substring (LeetCode #5)**

**Problem:** Find the longest palindromic substring.

```cpp
string longestPalindrome(string s) {
    int n = s.size();
    if (n < 2) return s;
    
    int start = 0, maxLen = 1;
    
    auto expandAroundCenter = [&](int left, int right) {
        while (left >= 0 && right < n && s[left] == s[right]) {
            int len = right - left + 1;
            if (len > maxLen) {
                start = left;
                maxLen = len;
            }
            left--;
            right++;
        }
    };
    
    for (int i = 0; i < n; i++) {
        expandAroundCenter(i, i);      // odd length
        expandAroundCenter(i, i + 1);  // even length
    }
    
    return s.substr(start, maxLen);
}
```

**Test Cases:**

```cpp
longestPalindrome("babad");   // "bab" or "aba"
longestPalindrome("cbbd");    // "bb"
```

**Output:**

```
"bab"
"bb"
```

---

### **11. Implement strStr() (LeetCode #28)**

**Problem:** Find the index of the first occurrence of needle in haystack.

```cpp
int strStr(string haystack, string needle) {
    if (needle.empty()) return 0;
    
    int n = haystack.size(), m = needle.size();
    
    for (int i = 0; i <= n - m; i++) {
        if (haystack.substr(i, m) == needle) {
            return i;
        }
    }
    return -1;
}

// Alternative using find()
int strStr(string haystack, string needle) {
    size_t pos = haystack.find(needle);
    return (pos == string::npos) ? -1 : (int)pos;
}
```

**Test Cases:**

```cpp
strStr("hello", "ll");      // 2
strStr("aaaaa", "bba");     // -1
strStr("", "");             // 0
```

**Output:**

```
2
-1
0
```

---

### **12. Valid Parentheses (LeetCode #20)**

**Problem:** Check if parentheses are valid.

```cpp
bool isValid(string s) {
    stack<char> st;
    unordered_map<char, char> pairs = {
        {')', '('}, 
        {']', '['}, 
        {'}', '{'}
    };
    
    for (char c : s) {
        if (pairs.count(c)) {
            // Closing bracket
            if (st.empty() || st.top() != pairs[c])
                return false;
            st.pop();
        } else {
            // Opening bracket
            st.push(c);
        }
    }
    return st.empty();
}
```

**Test Cases:**

```cpp
isValid("()");        // true
isValid("()[]{}");    // true
isValid("(]");        // false
isValid("([)]");      // false
isValid("{[]}");      // true
```

**Output:**

```
true
true
false
false
true
```

---

### **13. Remove Duplicates from String (LeetCode #1047)**

**Problem:** Remove all adjacent duplicates in a string.

```cpp
string removeDuplicates(string s) {
    stack<char> st;
    
    for (char c : s) {
        if (!st.empty() && st.top() == c) {
            st.pop();
        } else {
            st.push(c);
        }
    }
    
    string result;
    while (!st.empty()) {
        result = st.top() + result;
        st.pop();
    }
    return result;
}
```

**Test Cases:**

```cpp
removeDuplicates("abbaca");   // "ca"
removeDuplicates("azxxzy");   // "ay"
```

**Output:**

```
"ca"
"ay"
```

---

### **14. Count and Say (LeetCode #38)**

**Problem:** Generate the nth term in the count-and-say sequence.

```cpp
string countAndSay(int n) {
    if (n == 1) return "1";
    
    string prev = countAndSay(n - 1);
    string result;
    
    int count = 1;
    for (int i = 0; i < prev.size(); i++) {
        if (i + 1 < prev.size() && prev[i] == prev[i + 1]) {
            count++;
        } else {
            result += to_string(count) + prev[i];
            count = 1;
        }
    }
    return result;
}
```

**Test Cases:**

```cpp
countAndSay(1);  // "1"
countAndSay(2);  // "11"
countAndSay(3);  // "21"
countAndSay(4);  // "1211"
```

**Output:**

```
"1"
"11"
"21"
"1211"
```

---

### **15. Zigzag Conversion (LeetCode #6)**

**Problem:** Convert string in zigzag pattern.

```cpp
string convert(string s, int numRows) {
    if (numRows == 1 || numRows >= s.size()) return s;
    
    vector<string> rows(numRows);
    int currentRow = 0;
    bool goingDown = false;
    
    for (char c : s) {
        rows[currentRow] += c;
        
        if (currentRow == 0 || currentRow == numRows - 1) {
            goingDown = !goingDown;
        }
        
        currentRow += goingDown ? 1 : -1;
    }
    
    string result;
    for (string row : rows) {
        result += row;
    }
    return result;
}
```

**Test Cases:**

```cpp
convert("PAYPALISHIRING", 3);  // "PAHNAPLSIIGYIR"
convert("PAYPALISHIRING", 4);  // "PINALSIGYAHRPI"
```

**Output:**

```
"PAHNAPLSIIGYIR"
"PINALSIGYAHRPI"
```

---

### 🔹 **Time Complexity Summary**

| Problem | Time Complexity | Space Complexity |
|---------|----------------|------------------|
| Valid Palindrome | O(n) | O(1) |
| Reverse String | O(n) | O(1) |
| Valid Anagram | O(n log n) or O(n) | O(1) or O(n) |
| Longest Common Prefix | O(n * m) | O(1) |
| First Unique Character | O(n) | O(n) |
| Reverse Words | O(n) | O(n) |
| String to Integer | O(n) | O(1) |
| Longest Substring | O(n) | O(min(n,m)) |
| Group Anagrams | O(n * k log k) | O(n * k) |
| Longest Palindrome | O(n²) | O(1) |
| Implement strStr() | O(n * m) | O(1) |
| Valid Parentheses | O(n) | O(n) |
| Remove Duplicates | O(n) | O(n) |
| Count and Say | O(2ⁿ) | O(2ⁿ) |
| Zigzag Conversion | O(n) | O(n) |

---

## **C++ STL Array — Complete Reference**

### **1. Creating & Initializing**

```cpp
array<int, 5> arr1;                     // uninitialized (garbage values)
array<int, 5> arr2 = {1, 2, 3, 4, 5};   // initializer list
array<int, 5> arr3 = {1, 2};            // remaining elements = 0
array<int, 5> arr4{};                   // all elements = 0
array<int, 3> arr5 = arr2;              // copy (must be same size)

```

**Output:**

```
arr2 → 1 2 3 4 5
arr3 → 1 2 0 0 0
arr4 → 0 0 0 0 0

```

---

### **2. Accessing Elements**

```cpp
array<int, 5> arr = {10, 20, 30, 40, 50};
cout << arr[0];       // 10 (no bounds checking)
cout << arr.at(1);    // 20 (with bounds checking)
cout << arr.front();  // 10 (first element)
cout << arr.back();   // 50 (last element)

```

**Output:**

```
10
20
10
50

```

---

### **3. Size & Empty**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
cout << arr.size();      // 5 (fixed size)
cout << arr.max_size();  // 5 (same as size)
cout << arr.empty();     // 0 (false)

```

**Output:**

```
5
5
0

```

---

### **4. Iterators**

```cpp
array<int, 5> arr = {10, 20, 30, 40, 50};

// forward
for (auto it = arr.begin(); it != arr.end(); it++)
    cout << *it << " ";

// reverse
for (auto rit = arr.rbegin(); rit != arr.rend(); rit++)
    cout << *rit << " ";

```

**Output:**

```
10 20 30 40 50
50 40 30 20 10

```

---

### **5. Fill**

```cpp
array<int, 5> arr;
arr.fill(100);      // fill all elements with 100

```

**Output:**

```
100 100 100 100 100

```

---

### **6. Swap**

```cpp
array<int, 3> a = {1, 2, 3};
array<int, 3> b = {4, 5, 6};
a.swap(b);

```

**Output:**

```
a: 4 5 6
b: 1 2 3

```

---

### **7. Data Pointer**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
int* ptr = arr.data();      // pointer to first element
cout << ptr[0];             // 1
cout << *(ptr + 2);         // 3

```

**Output:**

```
1
3

```

---

### **8. Sort**

```cpp
array<int, 5> arr = {40, 10, 30, 20, 50};
sort(arr.begin(), arr.end());       // ascending
sort(arr.begin(), arr.end(), greater<int>()); // descending

```

**Output:**

```
Ascending: 10 20 30 40 50
Descending: 50 40 30 20 10

```

---

### **9. Reverse**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
reverse(arr.begin(), arr.end());

```

**Output:**

```
5 4 3 2 1

```

---

### **10. Find**

```cpp
array<int, 5> arr = {10, 20, 30, 40, 50};
auto it = find(arr.begin(), arr.end(), 30);
if (it != arr.end())
    cout << "Found at index " << (it - arr.begin());

```

**Output:**

```
Found at index 2

```

---

### **11. Count Occurrences**

```cpp
array<int, 7> arr = {1, 2, 2, 3, 2, 4, 5};
cout << count(arr.begin(), arr.end(), 2);

```

**Output:**

```
3

```

---

### **12. Max & Min**

```cpp
array<int, 5> arr = {10, 50, 5, 30, 20};
cout << *max_element(arr.begin(), arr.end());
cout << *min_element(arr.begin(), arr.end());

```

**Output:**

```
50
5

```

---

### **13. Sum of Elements**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
cout << accumulate(arr.begin(), arr.end(), 0);

```

**Output:**

```
15

```

---

### **14. Binary Search**

```cpp
array<int, 5> arr = {10, 20, 30, 40, 50}; // must be sorted
cout << binary_search(arr.begin(), arr.end(), 30); // true (1)
cout << binary_search(arr.begin(), arr.end(), 25); // false (0)

```

**Output:**

```
1
0

```

---

### **15. Lower Bound & Upper Bound**

```cpp
array<int, 5> arr = {10, 20, 30, 40, 50};
auto lb = lower_bound(arr.begin(), arr.end(), 30); // >= 30
auto ub = upper_bound(arr.begin(), arr.end(), 30); // > 30
cout << *lb;  // 30
cout << *ub;  // 40

```

**Output:**

```
30
40

```

---

### **16. Check if Sorted**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
cout << is_sorted(arr.begin(), arr.end());

```

**Output:**

```
1  (true)

```

---

### **17. Rotate**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
rotate(arr.begin(), arr.begin() + 2, arr.end()); // rotate left by 2

```

**Output:**

```
3 4 5 1 2

```

---

### **18. Partition**

```cpp
array<int, 6> arr = {1, 2, 3, 4, 5, 6};
auto it = partition(arr.begin(), arr.end(), [](int x) { return x % 2 == 0; });
// Moves even numbers to front

```

**Output:**

```
2 4 6 1 3 5  (order may vary)

```

---

### **19. Next Permutation**

```cpp
array<int, 3> arr = {1, 2, 3};
next_permutation(arr.begin(), arr.end());

```

**Output:**

```
1 3 2

```

---

### **20. 2D Array (Array of Arrays)**

```cpp
array<array<int, 3>, 2> mat = {{
    {1, 2, 3},
    {4, 5, 6}
}};

for (auto& row : mat) {
    for (auto& val : row)
        cout << val << " ";
    cout << endl;
}

```

**Output:**

```
1 2 3
4 5 6

```

---

### **21. Copy Array**

```cpp
array<int, 5> arr1 = {1, 2, 3, 4, 5};
array<int, 5> arr2;
copy(arr1.begin(), arr1.end(), arr2.begin());

```

**Output:**

```
arr2: 1 2 3 4 5

```

---

### **22. Transform (Modify Elements)**

```cpp
array<int, 5> arr = {1, 2, 3, 4, 5};
transform(arr.begin(), arr.end(), arr.begin(), [](int x) { return x * 2; });

```

**Output:**

```
2 4 6 8 10

```

---

### **23. All Of / Any Of / None Of**

```cpp
array<int, 5> arr = {2, 4, 6, 8, 10};
cout << all_of(arr.begin(), arr.end(), [](int x) { return x % 2 == 0; });  // all even
cout << any_of(arr.begin(), arr.end(), [](int x) { return x > 5; });       // any > 5
cout << none_of(arr.begin(), arr.end(), [](int x) { return x < 0; });      // none negative

```

**Output:**

```
1  (true)
1  (true)
1  (true)

```

---

### **24. Remove Duplicates (with sort)**

```cpp
array<int, 7> arr = {1, 2, 2, 3, 3, 4, 5};
sort(arr.begin(), arr.end());
auto it = unique(arr.begin(), arr.end());
// Elements after 'it' are undefined, but size remains same

```

**Output (unique elements):**

```
1 2 3 4 5  (remaining elements undefined)

```

---

### **25. Merge Two Arrays**

```cpp
array<int, 3> arr1 = {1, 3, 5};
array<int, 3> arr2 = {2, 4, 6};
array<int, 6> result;
merge(arr1.begin(), arr1.end(), arr2.begin(), arr2.end(), result.begin());

```

**Output:**

```
1 2 3 4 5 6

```

---

### 🔹 Key Points about `array`

- **Fixed size** → size must be known at compile time.
- Part of `<array>` header (C++11 onwards).
- Supports **random access** with `[]` and `.at()`.
- **No dynamic resizing** (unlike `vector`).
- Memory is **stack-allocated** (faster than heap).
- Compatible with **STL algorithms** (sort, find, etc.).
- **Size is part of the type** → `array<int, 5>` ≠ `array<int, 10>`.
- All operations: **O(1)** access, **O(n)** for search/algorithms.
- Safer than **C-style arrays** with bounds checking via `.at()`.

---

## **C++ STL Vector — Complete Reference**
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

## 📌 **Vector Manipulation Examples — LeetCode Problems**

### **1. Two Sum (LeetCode #1)**

**Problem:** Find two numbers that add up to a target.

```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> seen;
    
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        
        if (seen.count(complement)) {
            return {seen[complement], i};
        }
        seen[nums[i]] = i;
    }
    return {};
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {2, 7, 11, 15};
twoSum(nums1, 9);  // [0, 1]

vector<int> nums2 = {3, 2, 4};
twoSum(nums2, 6);  // [1, 2]
```

**Output:**

```
[0, 1]
[1, 2]
```

---

### **2. Remove Duplicates from Sorted Array (LeetCode #26)**

**Problem:** Remove duplicates in-place and return new length.

```cpp
int removeDuplicates(vector<int>& nums) {
    if (nums.empty()) return 0;
    
    int j = 0;  // slow pointer
    
    for (int i = 1; i < nums.size(); i++) {
        if (nums[i] != nums[j]) {
            j++;
            nums[j] = nums[i];
        }
    }
    return j + 1;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 1, 2};
removeDuplicates(nums1);  // 2, nums = [1, 2, ...]

vector<int> nums2 = {0, 0, 1, 1, 1, 2, 2, 3, 3, 4};
removeDuplicates(nums2);  // 5, nums = [0, 1, 2, 3, 4, ...]
```

**Output:**

```
2
5
```

---

### **3. Best Time to Buy and Sell Stock (LeetCode #121)**

**Problem:** Find maximum profit from stock prices.

```cpp
int maxProfit(vector<int>& prices) {
    int minPrice = INT_MAX;
    int maxProfit = 0;
    
    for (int price : prices) {
        minPrice = min(minPrice, price);
        maxProfit = max(maxProfit, price - minPrice);
    }
    return maxProfit;
}
```

**Test Cases:**

```cpp
vector<int> prices1 = {7, 1, 5, 3, 6, 4};
maxProfit(prices1);  // 5 (buy at 1, sell at 6)

vector<int> prices2 = {7, 6, 4, 3, 1};
maxProfit(prices2);  // 0 (no profit)
```

**Output:**

```
5
0
```

---

### **4. Contains Duplicate (LeetCode #217)**

**Problem:** Check if array contains any duplicates.

```cpp
bool containsDuplicate(vector<int>& nums) {
    unordered_set<int> seen;
    
    for (int num : nums) {
        if (seen.count(num)) return true;
        seen.insert(num);
    }
    return false;
}

// Alternative using set
bool containsDuplicate(vector<int>& nums) {
    return nums.size() > unordered_set<int>(nums.begin(), nums.end()).size();
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3, 1};
containsDuplicate(nums1);  // true

vector<int> nums2 = {1, 2, 3, 4};
containsDuplicate(nums2);  // false
```

**Output:**

```
true
false
```

---

### **5. Product of Array Except Self (LeetCode #238)**

**Problem:** Return array where each element is product of all others (without division).

```cpp
vector<int> productExceptSelf(vector<int>& nums) {
    int n = nums.size();
    vector<int> result(n, 1);
    
    // Left products
    int leftProduct = 1;
    for (int i = 0; i < n; i++) {
        result[i] = leftProduct;
        leftProduct *= nums[i];
    }
    
    // Right products
    int rightProduct = 1;
    for (int i = n - 1; i >= 0; i--) {
        result[i] *= rightProduct;
        rightProduct *= nums[i];
    }
    
    return result;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3, 4};
productExceptSelf(nums1);  // [24, 12, 8, 6]

vector<int> nums2 = {-1, 1, 0, -3, 3};
productExceptSelf(nums2);  // [0, 0, 9, 0, 0]
```

**Output:**

```
[24, 12, 8, 6]
[0, 0, 9, 0, 0]
```

---

### **6. Maximum Subarray (Kadane's Algorithm) (LeetCode #53)**

**Problem:** Find contiguous subarray with largest sum.

```cpp
int maxSubArray(vector<int>& nums) {
    int maxSum = nums[0];
    int currentSum = nums[0];
    
    for (int i = 1; i < nums.size(); i++) {
        currentSum = max(nums[i], currentSum + nums[i]);
        maxSum = max(maxSum, currentSum);
    }
    return maxSum;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
maxSubArray(nums1);  // 6 ([4, -1, 2, 1])

vector<int> nums2 = {1};
maxSubArray(nums2);  // 1

vector<int> nums3 = {5, 4, -1, 7, 8};
maxSubArray(nums3);  // 23
```

**Output:**

```
6
1
23
```

---

### **7. Merge Sorted Array (LeetCode #88)**

**Problem:** Merge two sorted arrays in-place.

```cpp
void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
    int i = m - 1, j = n - 1, k = m + n - 1;
    
    while (i >= 0 && j >= 0) {
        if (nums1[i] > nums2[j]) {
            nums1[k--] = nums1[i--];
        } else {
            nums1[k--] = nums2[j--];
        }
    }
    
    while (j >= 0) {
        nums1[k--] = nums2[j--];
    }
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3, 0, 0, 0};
vector<int> nums2 = {2, 5, 6};
merge(nums1, 3, nums2, 3);  // nums1 = [1, 2, 2, 3, 5, 6]
```

**Output:**

```
[1, 2, 2, 3, 5, 6]
```

---

### **8. Move Zeroes (LeetCode #283)**

**Problem:** Move all zeros to end while maintaining order.

```cpp
void moveZeroes(vector<int>& nums) {
    int j = 0;  // position for next non-zero
    
    for (int i = 0; i < nums.size(); i++) {
        if (nums[i] != 0) {
            swap(nums[i], nums[j]);
            j++;
        }
    }
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {0, 1, 0, 3, 12};
moveZeroes(nums1);  // [1, 3, 12, 0, 0]

vector<int> nums2 = {0};
moveZeroes(nums2);  // [0]
```

**Output:**

```
[1, 3, 12, 0, 0]
[0]
```

---

### **9. Find All Numbers Disappeared (LeetCode #448)**

**Problem:** Find all numbers in range [1, n] missing from array.

```cpp
vector<int> findDisappearedNumbers(vector<int>& nums) {
    int n = nums.size();
    
    // Mark presence by negating value at index
    for (int i = 0; i < n; i++) {
        int index = abs(nums[i]) - 1;
        if (nums[index] > 0) {
            nums[index] = -nums[index];
        }
    }
    
    vector<int> result;
    for (int i = 0; i < n; i++) {
        if (nums[i] > 0) {
            result.push_back(i + 1);
        }
    }
    return result;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {4, 3, 2, 7, 8, 2, 3, 1};
findDisappearedNumbers(nums1);  // [5, 6]

vector<int> nums2 = {1, 1};
findDisappearedNumbers(nums2);  // [2]
```

**Output:**

```
[5, 6]
[2]
```

---

### **10. Rotate Array (LeetCode #189)**

**Problem:** Rotate array to the right by k steps.

```cpp
void rotate(vector<int>& nums, int k) {
    int n = nums.size();
    k = k % n;
    
    // Reverse entire array
    reverse(nums.begin(), nums.end());
    // Reverse first k elements
    reverse(nums.begin(), nums.begin() + k);
    // Reverse remaining elements
    reverse(nums.begin() + k, nums.end());
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3, 4, 5, 6, 7};
rotate(nums1, 3);  // [5, 6, 7, 1, 2, 3, 4]

vector<int> nums2 = {-1, -100, 3, 99};
rotate(nums2, 2);  // [3, 99, -1, -100]
```

**Output:**

```
[5, 6, 7, 1, 2, 3, 4]
[3, 99, -1, -100]
```

---

### **11. Three Sum (LeetCode #15)**

**Problem:** Find all unique triplets that sum to zero.

```cpp
vector<vector<int>> threeSum(vector<int>& nums) {
    vector<vector<int>> result;
    sort(nums.begin(), nums.end());
    
    for (int i = 0; i < nums.size(); i++) {
        if (i > 0 && nums[i] == nums[i - 1]) continue;
        
        int left = i + 1, right = nums.size() - 1;
        
        while (left < right) {
            int sum = nums[i] + nums[left] + nums[right];
            
            if (sum == 0) {
                result.push_back({nums[i], nums[left], nums[right]});
                
                while (left < right && nums[left] == nums[left + 1]) left++;
                while (left < right && nums[right] == nums[right - 1]) right--;
                
                left++;
                right--;
            } else if (sum < 0) {
                left++;
            } else {
                right--;
            }
        }
    }
    return result;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {-1, 0, 1, 2, -1, -4};
threeSum(nums1);  // [[-1, -1, 2], [-1, 0, 1]]

vector<int> nums2 = {0, 1, 1};
threeSum(nums2);  // []
```

**Output:**

```
[[-1, -1, 2], [-1, 0, 1]]
[]
```

---

### **12. Container With Most Water (LeetCode #11)**

**Problem:** Find two lines that form container with most water.

```cpp
int maxArea(vector<int>& height) {
    int left = 0, right = height.size() - 1;
    int maxWater = 0;
    
    while (left < right) {
        int width = right - left;
        int h = min(height[left], height[right]);
        maxWater = max(maxWater, width * h);
        
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }
    return maxWater;
}
```

**Test Cases:**

```cpp
vector<int> height1 = {1, 8, 6, 2, 5, 4, 8, 3, 7};
maxArea(height1);  // 49

vector<int> height2 = {1, 1};
maxArea(height2);  // 1
```

**Output:**

```
49
1
```

---

### **13. Next Permutation (LeetCode #31)**

**Problem:** Find next lexicographically greater permutation.

```cpp
void nextPermutation(vector<int>& nums) {
    int n = nums.size();
    int i = n - 2;
    
    // Find first decreasing element from right
    while (i >= 0 && nums[i] >= nums[i + 1]) {
        i--;
    }
    
    if (i >= 0) {
        // Find element just larger than nums[i]
        int j = n - 1;
        while (nums[j] <= nums[i]) {
            j--;
        }
        swap(nums[i], nums[j]);
    }
    
    // Reverse the suffix
    reverse(nums.begin() + i + 1, nums.end());
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3};
nextPermutation(nums1);  // [1, 3, 2]

vector<int> nums2 = {3, 2, 1};
nextPermutation(nums2);  // [1, 2, 3]

vector<int> nums3 = {1, 1, 5};
nextPermutation(nums3);  // [1, 5, 1]
```

**Output:**

```
[1, 3, 2]
[1, 2, 3]
[1, 5, 1]
```

---

### **14. Find Peak Element (LeetCode #162)**

**Problem:** Find a peak element (element greater than neighbors).

```cpp
int findPeakElement(vector<int>& nums) {
    int left = 0, right = nums.size() - 1;
    
    while (left < right) {
        int mid = left + (right - left) / 2;
        
        if (nums[mid] > nums[mid + 1]) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }
    return left;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 2, 3, 1};
findPeakElement(nums1);  // 2

vector<int> nums2 = {1, 2, 1, 3, 5, 6, 4};
findPeakElement(nums2);  // 5 or 1
```

**Output:**

```
2
5
```

---

### **15. Sort Colors (Dutch National Flag) (LeetCode #75)**

**Problem:** Sort array with 0s, 1s, and 2s in-place.

```cpp
void sortColors(vector<int>& nums) {
    int low = 0, mid = 0, high = nums.size() - 1;
    
    while (mid <= high) {
        if (nums[mid] == 0) {
            swap(nums[low], nums[mid]);
            low++;
            mid++;
        } else if (nums[mid] == 1) {
            mid++;
        } else {
            swap(nums[mid], nums[high]);
            high--;
        }
    }
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {2, 0, 2, 1, 1, 0};
sortColors(nums1);  // [0, 0, 1, 1, 2, 2]

vector<int> nums2 = {2, 0, 1};
sortColors(nums2);  // [0, 1, 2]
```

**Output:**

```
[0, 0, 1, 1, 2, 2]
[0, 1, 2]
```

---

### **16. Majority Element (LeetCode #169)**

**Problem:** Find element appearing more than n/2 times.

```cpp
int majorityElement(vector<int>& nums) {
    int candidate = nums[0];
    int count = 1;
    
    // Boyer-Moore Voting Algorithm
    for (int i = 1; i < nums.size(); i++) {
        if (count == 0) {
            candidate = nums[i];
            count = 1;
        } else if (nums[i] == candidate) {
            count++;
        } else {
            count--;
        }
    }
    return candidate;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {3, 2, 3};
majorityElement(nums1);  // 3

vector<int> nums2 = {2, 2, 1, 1, 1, 2, 2};
majorityElement(nums2);  // 2
```

**Output:**

```
3
2
```

---

### **17. Spiral Matrix (LeetCode #54)**

**Problem:** Return all elements in spiral order.

```cpp
vector<int> spiralOrder(vector<vector<int>>& matrix) {
    vector<int> result;
    if (matrix.empty()) return result;
    
    int top = 0, bottom = matrix.size() - 1;
    int left = 0, right = matrix[0].size() - 1;
    
    while (top <= bottom && left <= right) {
        // Traverse right
        for (int i = left; i <= right; i++) {
            result.push_back(matrix[top][i]);
        }
        top++;
        
        // Traverse down
        for (int i = top; i <= bottom; i++) {
            result.push_back(matrix[i][right]);
        }
        right--;
        
        if (top <= bottom) {
            // Traverse left
            for (int i = right; i >= left; i--) {
                result.push_back(matrix[bottom][i]);
            }
            bottom--;
        }
        
        if (left <= right) {
            // Traverse up
            for (int i = bottom; i >= top; i--) {
                result.push_back(matrix[i][left]);
            }
            left++;
        }
    }
    return result;
}
```

**Test Cases:**

```cpp
vector<vector<int>> matrix1 = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
spiralOrder(matrix1);  // [1, 2, 3, 6, 9, 8, 7, 4, 5]

vector<vector<int>> matrix2 = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};
spiralOrder(matrix2);  // [1, 2, 3, 4, 8, 12, 11, 10, 9, 5, 6, 7]
```

**Output:**

```
[1, 2, 3, 6, 9, 8, 7, 4, 5]
[1, 2, 3, 4, 8, 12, 11, 10, 9, 5, 6, 7]
```

---

### **18. Subarray Sum Equals K (LeetCode #560)**

**Problem:** Count number of subarrays with sum equal to k.

```cpp
int subarraySum(vector<int>& nums, int k) {
    unordered_map<int, int> prefixSum;
    prefixSum[0] = 1;
    
    int sum = 0, count = 0;
    
    for (int num : nums) {
        sum += num;
        
        if (prefixSum.count(sum - k)) {
            count += prefixSum[sum - k];
        }
        
        prefixSum[sum]++;
    }
    return count;
}
```

**Test Cases:**

```cpp
vector<int> nums1 = {1, 1, 1};
subarraySum(nums1, 2);  // 2

vector<int> nums2 = {1, 2, 3};
subarraySum(nums2, 3);  // 2
```

**Output:**

```
2
2
```

---

### 🔹 **Time Complexity Summary**

| Problem | Time Complexity | Space Complexity |
|---------|----------------|------------------|
| Two Sum | O(n) | O(n) |
| Remove Duplicates | O(n) | O(1) |
| Best Time to Buy Stock | O(n) | O(1) |
| Contains Duplicate | O(n) | O(n) |
| Product Except Self | O(n) | O(1) |
| Maximum Subarray | O(n) | O(1) |
| Merge Sorted Array | O(m + n) | O(1) |
| Move Zeroes | O(n) | O(1) |
| Find Disappeared | O(n) | O(1) |
| Rotate Array | O(n) | O(1) |
| Three Sum | O(n²) | O(1) |
| Container Most Water | O(n) | O(1) |
| Next Permutation | O(n) | O(1) |
| Find Peak Element | O(log n) | O(1) |
| Sort Colors | O(n) | O(1) |
| Majority Element | O(n) | O(1) |
| Spiral Matrix | O(m * n) | O(1) |
| Subarray Sum Equals K | O(n) | O(n) |

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

## 📌 **List (Linked List) Manipulation Examples — LeetCode Problems**

### **1. Reverse Linked List (LeetCode #206)**

**Problem:** Reverse a singly linked list.

```cpp
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* reverseList(ListNode* head) {
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

// Using STL list
void reverseSTLList() {
    list<int> l = {1, 2, 3, 4, 5};
    l.reverse();  // Built-in reverse
    // Output: 5 4 3 2 1
}
```

**Output:**

```
5 -> 4 -> 3 -> 2 -> 1
```

---

### **2. Merge Two Sorted Lists (LeetCode #21)**

**Problem:** Merge two sorted linked lists.

```cpp
ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    ListNode dummy(0);
    ListNode* tail = &dummy;
    
    while (l1 && l2) {
        if (l1->val <= l2->val) {
            tail->next = l1;
            l1 = l1->next;
        } else {
            tail->next = l2;
            l2 = l2->next;
        }
        tail = tail->next;
    }
    
    tail->next = l1 ? l1 : l2;
    return dummy.next;
}

// Using STL list
void mergeSTLLists() {
    list<int> l1 = {1, 3, 5};
    list<int> l2 = {2, 4, 6};
    l1.merge(l2);  // Built-in merge (both must be sorted)
    // Output: 1 2 3 4 5 6
}
```

**Output:**

```
1 -> 2 -> 3 -> 4 -> 5 -> 6
```

---

### **3. Remove Duplicates from Sorted List (LeetCode #83)**

**Problem:** Remove duplicates from a sorted linked list.

```cpp
ListNode* deleteDuplicates(ListNode* head) {
    if (!head) return nullptr;
    
    ListNode* curr = head;
    
    while (curr->next) {
        if (curr->val == curr->next->val) {
            ListNode* temp = curr->next;
            curr->next = curr->next->next;
            delete temp;
        } else {
            curr = curr->next;
        }
    }
    return head;
}

// Using STL list
void removeDuplicatesSTL() {
    list<int> l = {1, 1, 2, 2, 3, 3, 4};
    l.sort();    // Ensure sorted
    l.unique();  // Remove consecutive duplicates
    // Output: 1 2 3 4
}
```

**Output:**

```
1 -> 2 -> 3 -> 4
```

---

### **4. Middle of Linked List (LeetCode #876)**

**Problem:** Find the middle node of a linked list.

```cpp
ListNode* middleNode(ListNode* head) {
    ListNode* slow = head;
    ListNode* fast = head;
    
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
    }
    return slow;
}

// Using STL list
int findMiddleSTL() {
    list<int> l = {1, 2, 3, 4, 5};
    auto it = l.begin();
    advance(it, l.size() / 2);
    return *it;  // Returns 3
}
```

**Output:**

```
3 (middle element)
```

---

### **5. Palindrome Linked List (LeetCode #234)**

**Problem:** Check if a linked list is a palindrome.

```cpp
bool isPalindrome(ListNode* head) {
    vector<int> vals;
    
    while (head) {
        vals.push_back(head->val);
        head = head->next;
    }
    
    int left = 0, right = vals.size() - 1;
    while (left < right) {
        if (vals[left] != vals[right]) return false;
        left++;
        right--;
    }
    return true;
}

// Using STL list
bool isPalindromeSTL() {
    list<int> l = {1, 2, 3, 2, 1};
    list<int> rev = l;
    rev.reverse();
    return l == rev;
}
```

**Output:**

```
true
```

---

### **6. Remove Nth Node From End (LeetCode #19)**

**Problem:** Remove the nth node from the end of list.

```cpp
ListNode* removeNthFromEnd(ListNode* head, int n) {
    ListNode dummy(0);
    dummy.next = head;
    ListNode* first = &dummy;
    ListNode* second = &dummy;
    
    // Move first n+1 steps ahead
    for (int i = 0; i <= n; i++) {
        first = first->next;
    }
    
    // Move both until first reaches end
    while (first) {
        first = first->next;
        second = second->next;
    }
    
    // Remove nth node
    ListNode* temp = second->next;
    second->next = second->next->next;
    delete temp;
    
    return dummy.next;
}
```

**Output:**

```
1 -> 2 -> 3 -> 5 (removed 4th from end)
```

---

### **7. Detect Cycle in Linked List (LeetCode #141)**

**Problem:** Detect if linked list has a cycle.

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

**Output:**

```
true (if cycle exists)
false (if no cycle)
```

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

## 📌 **Queue & Stack Manipulation Examples — LeetCode Problems**

### **1. Implement Queue using Stacks (LeetCode #232)**

**Problem:** Implement a queue using two stacks.

```cpp
class MyQueue {
    stack<int> input, output;
    
    void transfer() {
        while (!input.empty()) {
            output.push(input.top());
            input.pop();
        }
    }
    
public:
    void push(int x) {
        input.push(x);
    }
    
    int pop() {
        if (output.empty()) transfer();
        int val = output.top();
        output.pop();
        return val;
    }
    
    int peek() {
        if (output.empty()) transfer();
        return output.top();
    }
    
    bool empty() {
        return input.empty() && output.empty();
    }
};
```

---

### **2. Implement Stack using Queues (LeetCode #225)**

**Problem:** Implement a stack using queues.

```cpp
class MyStack {
    queue<int> q;
    
public:
    void push(int x) {
        q.push(x);
        int size = q.size();
        // Rotate queue to make last element front
        for (int i = 0; i < size - 1; i++) {
            q.push(q.front());
            q.pop();
        }
    }
    
    int pop() {
        int val = q.front();
        q.pop();
        return val;
    }
    
    int top() {
        return q.front();
    }
    
    bool empty() {
        return q.empty();
    }
};
```

---

### **3. Valid Parentheses (LeetCode #20)**

**Problem:** Check if parentheses are valid using stack.

```cpp
bool isValid(string s) {
    stack<char> st;
    unordered_map<char, char> pairs = {
        {')', '('}, {']', '['}, {'}', '{'}
    };
    
    for (char c : s) {
        if (pairs.count(c)) {
            if (st.empty() || st.top() != pairs[c])
                return false;
            st.pop();
        } else {
            st.push(c);
        }
    }
    return st.empty();
}
```

**Output:**

```
"()" -> true
"()[]{}" -> true
"(]" -> false
```

---

### **4. Min Stack (LeetCode #155)**

**Problem:** Design a stack with getMin() in O(1).

```cpp
class MinStack {
    stack<int> st;
    stack<int> minSt;
    
public:
    void push(int val) {
        st.push(val);
        if (minSt.empty() || val <= minSt.top()) {
            minSt.push(val);
        }
    }
    
    void pop() {
        if (st.top() == minSt.top()) {
            minSt.pop();
        }
        st.pop();
    }
    
    int top() {
        return st.top();
    }
    
    int getMin() {
        return minSt.top();
    }
};
```

---

### **5. Sliding Window Maximum (LeetCode #239)**

**Problem:** Find maximum in each sliding window using deque.

```cpp
vector<int> maxSlidingWindow(vector<int>& nums, int k) {
    deque<int> dq;  // stores indices
    vector<int> result;
    
    for (int i = 0; i < nums.size(); i++) {
        // Remove elements outside window
        while (!dq.empty() && dq.front() <= i - k) {
            dq.pop_front();
        }
        
        // Remove smaller elements
        while (!dq.empty() && nums[dq.back()] < nums[i]) {
            dq.pop_back();
        }
        
        dq.push_back(i);
        
        if (i >= k - 1) {
            result.push_back(nums[dq.front()]);
        }
    }
    return result;
}
```

**Output:**

```
nums = [1,3,-1,-3,5,3,6,7], k = 3
Output: [3,3,5,5,6,7]
```

---

### **6. Daily Temperatures (LeetCode #739)**

**Problem:** Find next warmer temperature using stack.

```cpp
vector<int> dailyTemperatures(vector<int>& temps) {
    int n = temps.size();
    vector<int> result(n, 0);
    stack<int> st;  // stores indices
    
    for (int i = 0; i < n; i++) {
        while (!st.empty() && temps[i] > temps[st.top()]) {
            int idx = st.top();
            st.pop();
            result[idx] = i - idx;
        }
        st.push(i);
    }
    return result;
}
```

**Output:**

```
temps = [73,74,75,71,69,72,76,73]
Output: [1,1,4,2,1,1,0,0]
```

---

### **7. Evaluate Reverse Polish Notation (LeetCode #150)**

**Problem:** Evaluate postfix expression using stack.

```cpp
int evalRPN(vector<string>& tokens) {
    stack<int> st;
    
    for (string& token : tokens) {
        if (token == "+" || token == "-" || token == "*" || token == "/") {
            int b = st.top(); st.pop();
            int a = st.top(); st.pop();
            
            if (token == "+") st.push(a + b);
            else if (token == "-") st.push(a - b);
            else if (token == "*") st.push(a * b);
            else st.push(a / b);
        } else {
            st.push(stoi(token));
        }
    }
    return st.top();
}
```

**Output:**

```
["2","1","+","3","*"] -> 9  ((2 + 1) * 3)
```

---

### **8. Number of Recent Calls (LeetCode #933)**

**Problem:** Count requests in last 3000ms using queue.

```cpp
class RecentCounter {
    queue<int> q;
    
public:
    RecentCounter() {}
    
    int ping(int t) {
        q.push(t);
        
        // Remove requests older than t-3000
        while (!q.empty() && q.front() < t - 3000) {
            q.pop();
        }
        
        return q.size();
    }
};
```

---

### **9. Design Circular Queue (LeetCode #622)**

**Problem:** Design a circular queue.

```cpp
class MyCircularQueue {
    vector<int> data;
    int head, tail, size, capacity;
    
public:
    MyCircularQueue(int k) : data(k), head(0), tail(0), size(0), capacity(k) {}
    
    bool enQueue(int value) {
        if (isFull()) return false;
        data[tail] = value;
        tail = (tail + 1) % capacity;
        size++;
        return true;
    }
    
    bool deQueue() {
        if (isEmpty()) return false;
        head = (head + 1) % capacity;
        size--;
        return true;
    }
    
    int Front() {
        return isEmpty() ? -1 : data[head];
    }
    
    int Rear() {
        return isEmpty() ? -1 : data[(tail - 1 + capacity) % capacity];
    }
    
    bool isEmpty() {
        return size == 0;
    }
    
    bool isFull() {
        return size == capacity;
    }
};
```

---

### **10. Decode String (LeetCode #394)**

**Problem:** Decode encoded string using stack.

```cpp
string decodeString(string s) {
    stack<int> numStack;
    stack<string> strStack;
    string currStr;
    int currNum = 0;
    
    for (char c : s) {
        if (isdigit(c)) {
            currNum = currNum * 10 + (c - '0');
        } else if (c == '[') {
            numStack.push(currNum);
            strStack.push(currStr);
            currNum = 0;
            currStr = "";
        } else if (c == ']') {
            int num = numStack.top(); numStack.pop();
            string prevStr = strStack.top(); strStack.pop();
            
            string temp;
            for (int i = 0; i < num; i++) {
                temp += currStr;
            }
            currStr = prevStr + temp;
        } else {
            currStr += c;
        }
    }
    return currStr;
}
```

**Output:**

```
"3[a]2[bc]" -> "aaabcbc"
"3[a2[c]]" -> "accaccacc"
```

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

## 📌 **Priority Queue (Heap) Examples — LeetCode Problems**

### **1. Kth Largest Element in Array (LeetCode #215)**

**Problem:** Find the kth largest element.

```cpp
int findKthLargest(vector<int>& nums, int k) {
    priority_queue<int, vector<int>, greater<int>> minHeap;
    
    for (int num : nums) {
        minHeap.push(num);
        if (minHeap.size() > k) {
            minHeap.pop();
        }
    }
    return minHeap.top();
}
```

**Output:**

```
nums = [3,2,1,5,6,4], k = 2
Output: 5
```

---

### **2. Top K Frequent Elements (LeetCode #347)**

**Problem:** Find k most frequent elements.

```cpp
vector<int> topKFrequent(vector<int>& nums, int k) {
    unordered_map<int, int> freq;
    for (int num : nums) freq[num]++;
    
    auto cmp = [](pair<int,int>& a, pair<int,int>& b) {
        return a.second > b.second;
    };
    priority_queue<pair<int,int>, vector<pair<int,int>>, decltype(cmp)> minHeap(cmp);
    
    for (auto& p : freq) {
        minHeap.push(p);
        if (minHeap.size() > k) minHeap.pop();
    }
    
    vector<int> result;
    while (!minHeap.empty()) {
        result.push_back(minHeap.top().first);
        minHeap.pop();
    }
    return result;
}
```

**Output:**

```
nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
```

---

### **3. Merge K Sorted Lists (LeetCode #23)**

**Problem:** Merge k sorted linked lists using heap.

```cpp
ListNode* mergeKLists(vector<ListNode*>& lists) {
    auto cmp = [](ListNode* a, ListNode* b) {
        return a->val > b->val;
    };
    priority_queue<ListNode*, vector<ListNode*>, decltype(cmp)> minHeap(cmp);
    
    for (auto list : lists) {
        if (list) minHeap.push(list);
    }
    
    ListNode dummy(0);
    ListNode* tail = &dummy;
    
    while (!minHeap.empty()) {
        ListNode* node = minHeap.top();
        minHeap.pop();
        
        tail->next = node;
        tail = tail->next;
        
        if (node->next) {
            minHeap.push(node->next);
        }
    }
    return dummy.next;
}
```

---

### **4. Find Median from Data Stream (LeetCode #295)**

**Problem:** Maintain median using two heaps.

```cpp
class MedianFinder {
    priority_queue<int> maxHeap;  // left half
    priority_queue<int, vector<int>, greater<int>> minHeap;  // right half
    
public:
    void addNum(int num) {
        if (maxHeap.empty() || num <= maxHeap.top()) {
            maxHeap.push(num);
        } else {
            minHeap.push(num);
        }
        
        // Balance heaps
        if (maxHeap.size() > minHeap.size() + 1) {
            minHeap.push(maxHeap.top());
            maxHeap.pop();
        } else if (minHeap.size() > maxHeap.size()) {
            maxHeap.push(minHeap.top());
            minHeap.pop();
        }
    }
    
    double findMedian() {
        if (maxHeap.size() == minHeap.size()) {
            return (maxHeap.top() + minHeap.top()) / 2.0;
        }
        return maxHeap.top();
    }
};
```

---

### **5. Kth Smallest Element in Sorted Matrix (LeetCode #378)**

**Problem:** Find kth smallest in n×n matrix.

```cpp
int kthSmallest(vector<vector<int>>& matrix, int k) {
    int n = matrix.size();
    auto cmp = [&](pair<int,int>& a, pair<int,int>& b) {
        return matrix[a.first][a.second] > matrix[b.first][b.second];
    };
    priority_queue<pair<int,int>, vector<pair<int,int>>, decltype(cmp)> minHeap(cmp);
    
    // Add first element of each row
    for (int i = 0; i < min(n, k); i++) {
        minHeap.push({i, 0});
    }
    
    int result = 0;
    while (k--) {
        auto [row, col] = minHeap.top();
        minHeap.pop();
        result = matrix[row][col];
        
        if (col + 1 < n) {
            minHeap.push({row, col + 1});
        }
    }
    return result;
}
```

---

### **6. Last Stone Weight (LeetCode #1046)**

**Problem:** Smash stones until one or none remain.

```cpp
int lastStoneWeight(vector<int>& stones) {
    priority_queue<int> maxHeap(stones.begin(), stones.end());
    
    while (maxHeap.size() > 1) {
        int first = maxHeap.top(); maxHeap.pop();
        int second = maxHeap.top(); maxHeap.pop();
        
        if (first != second) {
            maxHeap.push(first - second);
        }
    }
    
    return maxHeap.empty() ? 0 : maxHeap.top();
}
```

**Output:**

```
stones = [2,7,4,1,8,1]
Output: 1
```

---

### **7. K Closest Points to Origin (LeetCode #973)**

**Problem:** Find k closest points to origin.

```cpp
vector<vector<int>> kClosest(vector<vector<int>>& points, int k) {
    auto cmp = [](vector<int>& a, vector<int>& b) {
        return a[0]*a[0] + a[1]*a[1] < b[0]*b[0] + b[1]*b[1];
    };
    priority_queue<vector<int>, vector<vector<int>>, decltype(cmp)> maxHeap(cmp);
    
    for (auto& point : points) {
        maxHeap.push(point);
        if (maxHeap.size() > k) {
            maxHeap.pop();
        }
    }
    
    vector<vector<int>> result;
    while (!maxHeap.empty()) {
        result.push_back(maxHeap.top());
        maxHeap.pop();
    }
    return result;
}
```

---

### **8. Task Scheduler (LeetCode #621)**

**Problem:** Schedule tasks with cooling time.

```cpp
int leastInterval(vector<char>& tasks, int n) {
    unordered_map<char, int> freq;
    for (char task : tasks) freq[task]++;
    
    priority_queue<int> maxHeap;
    for (auto& p : freq) {
        maxHeap.push(p.second);
    }
    
    int time = 0;
    while (!maxHeap.empty()) {
        vector<int> temp;
        
        for (int i = 0; i <= n; i++) {
            if (!maxHeap.empty()) {
                temp.push_back(maxHeap.top() - 1);
                maxHeap.pop();
            }
        }
        
        for (int count : temp) {
            if (count > 0) maxHeap.push(count);
        }
        
        time += maxHeap.empty() ? temp.size() : n + 1;
    }
    return time;
}
```

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

## 📌 **Set & Map Manipulation Examples — LeetCode Problems**

### **1. Intersection of Two Arrays (LeetCode #349)**

**Problem:** Find unique common elements using set.

```cpp
vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
    unordered_set<int> set1(nums1.begin(), nums1.end());
    unordered_set<int> result;
    
    for (int num : nums2) {
        if (set1.count(num)) {
            result.insert(num);
        }
    }
    
    return vector<int>(result.begin(), result.end());
}
```

**Output:**

```
nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2]
```

---

### **2. Two Sum (LeetCode #1)**

**Problem:** Find two indices that add up to target using map.

```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> seen;
    
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        
        if (seen.count(complement)) {
            return {seen[complement], i};
        }
        seen[nums[i]] = i;
    }
    return {};
}
```

**Output:**

```
nums = [2,7,11,15], target = 9
Output: [0,1]
```

---

### **3. Contains Duplicate II (LeetCode #219)**

**Problem:** Check if duplicate exists within k distance.

```cpp
bool containsNearbyDuplicate(vector<int>& nums, int k) {
    unordered_map<int, int> lastSeen;
    
    for (int i = 0; i < nums.size(); i++) {
        if (lastSeen.count(nums[i]) && i - lastSeen[nums[i]] <= k) {
            return true;
        }
        lastSeen[nums[i]] = i;
    }
    return false;
}
```

**Output:**

```
nums = [1,2,3,1], k = 3
Output: true
```

---

### **4. Longest Consecutive Sequence (LeetCode #128)**

**Problem:** Find longest consecutive sequence using set.

```cpp
int longestConsecutive(vector<int>& nums) {
    unordered_set<int> numSet(nums.begin(), nums.end());
    int maxLen = 0;
    
    for (int num : numSet) {
        // Only start from sequence beginning
        if (!numSet.count(num - 1)) {
            int currentNum = num;
            int currentLen = 1;
            
            while (numSet.count(currentNum + 1)) {
                currentNum++;
                currentLen++;
            }
            
            maxLen = max(maxLen, currentLen);
        }
    }
    return maxLen;
}
```

**Output:**

```
nums = [100,4,200,1,3,2]
Output: 4 (sequence: 1,2,3,4)
```

---

### **5. Happy Number (LeetCode #202)**

**Problem:** Detect cycle in sum of squares using set.

```cpp
bool isHappy(int n) {
    unordered_set<int> seen;
    
    auto sumOfSquares = [](int num) {
        int sum = 0;
        while (num > 0) {
            int digit = num % 10;
            sum += digit * digit;
            num /= 10;
        }
        return sum;
    };
    
    while (n != 1 && !seen.count(n)) {
        seen.insert(n);
        n = sumOfSquares(n);
    }
    
    return n == 1;
}
```

**Output:**

```
n = 19
Output: true (1² + 9² = 82, 8² + 2² = 68, ..., eventually reaches 1)
```

---

### **6. Group Anagrams (LeetCode #49)**

**Problem:** Group anagrams using map.

```cpp
vector<vector<string>> groupAnagrams(vector<string>& strs) {
    unordered_map<string, vector<string>> groups;
    
    for (string& s : strs) {
        string key = s;
        sort(key.begin(), key.end());
        groups[key].push_back(s);
    }
    
    vector<vector<string>> result;
    for (auto& [key, group] : groups) {
        result.push_back(group);
    }
    return result;
}
```

**Output:**

```
strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

---

### **7. Isomorphic Strings (LeetCode #205)**

**Problem:** Check if two strings are isomorphic using maps.

```cpp
bool isIsomorphic(string s, string t) {
    if (s.size() != t.size()) return false;
    
    unordered_map<char, char> mapS, mapT;
    
    for (int i = 0; i < s.size(); i++) {
        char c1 = s[i], c2 = t[i];
        
        if (mapS.count(c1) && mapS[c1] != c2) return false;
        if (mapT.count(c2) && mapT[c2] != c1) return false;
        
        mapS[c1] = c2;
        mapT[c2] = c1;
    }
    return true;
}
```

**Output:**

```
s = "egg", t = "add"
Output: true
```

---

### **8. Word Pattern (LeetCode #290)**

**Problem:** Check if string follows a pattern using map.

```cpp
bool wordPattern(string pattern, string s) {
    vector<string> words;
    stringstream ss(s);
    string word;
    
    while (ss >> word) words.push_back(word);
    
    if (pattern.size() != words.size()) return false;
    
    unordered_map<char, string> charToWord;
    unordered_map<string, char> wordToChar;
    
    for (int i = 0; i < pattern.size(); i++) {
        char c = pattern[i];
        string w = words[i];
        
        if (charToWord.count(c) && charToWord[c] != w) return false;
        if (wordToChar.count(w) && wordToChar[w] != c) return false;
        
        charToWord[c] = w;
        wordToChar[w] = c;
    }
    return true;
}
```

**Output:**

```
pattern = "abba", s = "dog cat cat dog"
Output: true
```

---

### **9. Majority Element (LeetCode #169)**

**Problem:** Find element appearing > n/2 times using map.

```cpp
int majorityElement(vector<int>& nums) {
    unordered_map<int, int> count;
    int n = nums.size();
    
    for (int num : nums) {
        count[num]++;
        if (count[num] > n / 2) return num;
    }
    return -1;
}
```

**Output:**

```
nums = [3,2,3]
Output: 3
```

---

### **10. Top K Frequent Words (LeetCode #692)**

**Problem:** Find k most frequent words using map and sorting.

```cpp
vector<string> topKFrequent(vector<string>& words, int k) {
    unordered_map<string, int> freq;
    for (string& word : words) freq[word]++;
    
    vector<pair<string, int>> items(freq.begin(), freq.end());
    
    sort(items.begin(), items.end(), [](auto& a, auto& b) {
        return a.second > b.second || 
               (a.second == b.second && a.first < b.first);
    });
    
    vector<string> result;
    for (int i = 0; i < k; i++) {
        result.push_back(items[i].first);
    }
    return result;
}
```

**Output:**

```
words = ["i","love","leetcode","i","love","coding"], k = 2
Output: ["i","love"]
```

---

### **11. Ransom Note (LeetCode #383)**

**Problem:** Check if ransom note can be constructed using map.

```cpp
bool canConstruct(string ransomNote, string magazine) {
    unordered_map<char, int> freq;
    
    for (char c : magazine) freq[c]++;
    
    for (char c : ransomNote) {
        if (--freq[c] < 0) return false;
    }
    return true;
}
```

**Output:**

```
ransomNote = "aa", magazine = "aab"
Output: true
```

---

### **12. Logger Rate Limiter (LeetCode #359)**

**Problem:** Design logger with cooldown using map.

```cpp
class Logger {
    unordered_map<string, int> messageTime;
    
public:
    bool shouldPrintMessage(int timestamp, string message) {
        if (!messageTime.count(message) || 
            timestamp - messageTime[message] >= 10) {
            messageTime[message] = timestamp;
            return true;
        }
        return false;
    }
};
```

---

### **13. LRU Cache (LeetCode #146)**

**Problem:** Implement LRU cache using map and list.

```cpp
class LRUCache {
    int capacity;
    list<pair<int, int>> cache;  // {key, value}
    unordered_map<int, list<pair<int,int>>::iterator> map;
    
public:
    LRUCache(int capacity) : capacity(capacity) {}
    
    int get(int key) {
        if (!map.count(key)) return -1;
        
        // Move to front
        cache.splice(cache.begin(), cache, map[key]);
        return map[key]->second;
    }
    
    void put(int key, int value) {
        if (map.count(key)) {
            cache.splice(cache.begin(), cache, map[key]);
            map[key]->second = value;
            return;
        }
        
        if (cache.size() == capacity) {
            int oldKey = cache.back().first;
            cache.pop_back();
            map.erase(oldKey);
        }
        
        cache.push_front({key, value});
        map[key] = cache.begin();
    }
};
```

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

## 📌 **C++ STL Algorithms — Complete Reference**

### **1. Sorting Algorithms**

#### **sort()** - Sort in ascending/descending order

```cpp
vector<int> v = {5, 2, 8, 1, 9};
sort(v.begin(), v.end());                      // Ascending: 1 2 5 8 9
sort(v.begin(), v.end(), greater<int>());      // Descending: 9 8 5 2 1

// Custom comparator
sort(v.begin(), v.end(), [](int a, int b) {
    return a > b;  // Descending
});
```

**Time Complexity:** O(n log n)

---

#### **stable_sort()** - Sort maintaining relative order

```cpp
vector<pair<int, char>> v = {{3, 'a'}, {1, 'b'}, {3, 'c'}, {1, 'd'}};
stable_sort(v.begin(), v.end());
// Output: {1,'b'}, {1,'d'}, {3,'a'}, {3,'c'}  (relative order preserved)
```

**Time Complexity:** O(n log n)

---

#### **partial_sort()** - Sort first k elements

```cpp
vector<int> v = {5, 2, 8, 1, 9, 3};
partial_sort(v.begin(), v.begin() + 3, v.end());
// First 3 elements sorted: 1 2 3 8 9 5
```

**Time Complexity:** O(n log k)

---

#### **nth_element()** - Partition around nth element

```cpp
vector<int> v = {5, 2, 8, 1, 9, 3};
nth_element(v.begin(), v.begin() + 2, v.end());
// Element at index 2 is in correct position (3)
// Smaller elements before, larger after
```

**Time Complexity:** O(n) average

---

### **2. Searching Algorithms**

#### **binary_search()** - Check if element exists (must be sorted)

```cpp
vector<int> v = {1, 2, 3, 5, 8, 9};
bool found = binary_search(v.begin(), v.end(), 5);  // true
bool notFound = binary_search(v.begin(), v.end(), 4);  // false
```

**Time Complexity:** O(log n)

---

#### **lower_bound()** - First element >= value

```cpp
vector<int> v = {1, 2, 4, 4, 5, 8};
auto it = lower_bound(v.begin(), v.end(), 4);
cout << *it;  // 4 (first occurrence)
cout << (it - v.begin());  // index: 2
```

**Time Complexity:** O(log n)

---

#### **upper_bound()** - First element > value

```cpp
vector<int> v = {1, 2, 4, 4, 5, 8};
auto it = upper_bound(v.begin(), v.end(), 4);
cout << *it;  // 5 (first element > 4)
cout << (it - v.begin());  // index: 4
```

**Time Complexity:** O(log n)

---

#### **equal_range()** - Get range of equal elements

```cpp
vector<int> v = {1, 2, 4, 4, 4, 5, 8};
auto range = equal_range(v.begin(), v.end(), 4);
// range.first points to first 4
// range.second points to element after last 4
```

**Time Complexity:** O(log n)

---

#### **find()** - Linear search for element

```cpp
vector<int> v = {5, 2, 8, 1, 9};
auto it = find(v.begin(), v.end(), 8);
if (it != v.end()) {
    cout << "Found at index: " << (it - v.begin());
}
```

**Time Complexity:** O(n)

---

#### **find_if()** - Find with predicate

```cpp
vector<int> v = {1, 3, 5, 8, 10};
auto it = find_if(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;  // Find first even
});
cout << *it;  // 8
```

**Time Complexity:** O(n)

---

### **3. Min/Max Algorithms**

#### **min_element() / max_element()**

```cpp
vector<int> v = {5, 2, 8, 1, 9};
auto minIt = min_element(v.begin(), v.end());
auto maxIt = max_element(v.begin(), v.end());
cout << *minIt;  // 1
cout << *maxIt;  // 9
```

**Time Complexity:** O(n)

---

#### **minmax_element()**

```cpp
vector<int> v = {5, 2, 8, 1, 9};
auto [minIt, maxIt] = minmax_element(v.begin(), v.end());
cout << *minIt << " " << *maxIt;  // 1 9
```

**Time Complexity:** O(n)

---

### **4. Counting & Accumulation**

#### **count()** - Count occurrences

```cpp
vector<int> v = {1, 2, 2, 3, 2, 4};
int cnt = count(v.begin(), v.end(), 2);  // 3
```

**Time Complexity:** O(n)

---

#### **count_if()** - Count with predicate

```cpp
vector<int> v = {1, 2, 3, 4, 5, 6};
int evenCount = count_if(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});  // 3
```

**Time Complexity:** O(n)

---

#### **accumulate()** - Sum/Reduce elements

```cpp
#include <numeric>

vector<int> v = {1, 2, 3, 4, 5};
int sum = accumulate(v.begin(), v.end(), 0);  // 15

// Custom operation
int product = accumulate(v.begin(), v.end(), 1, multiplies<int>());  // 120
```

**Time Complexity:** O(n)

---

### **5. Transformation Algorithms**

#### **transform()** - Apply function to elements

```cpp
vector<int> v = {1, 2, 3, 4, 5};
vector<int> result(v.size());

transform(v.begin(), v.end(), result.begin(), [](int x) {
    return x * x;
});
// result: 1, 4, 9, 16, 25
```

**Time Complexity:** O(n)

---

#### **replace()** - Replace values

```cpp
vector<int> v = {1, 2, 3, 2, 5};
replace(v.begin(), v.end(), 2, 99);
// v: 1, 99, 3, 99, 5
```

**Time Complexity:** O(n)

---

#### **replace_if()** - Replace with predicate

```cpp
vector<int> v = {1, 2, 3, 4, 5};
replace_if(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
}, 0);
// v: 1, 0, 3, 0, 5
```

**Time Complexity:** O(n)

---

### **6. Permutation & Combination**

#### **next_permutation()** - Next lexicographic permutation

```cpp
vector<int> v = {1, 2, 3};
next_permutation(v.begin(), v.end());
// v: 1, 3, 2

// Generate all permutations
sort(v.begin(), v.end());
do {
    // Process permutation
} while (next_permutation(v.begin(), v.end()));
```

**Time Complexity:** O(n)

---

#### **prev_permutation()** - Previous permutation

```cpp
vector<int> v = {3, 2, 1};
prev_permutation(v.begin(), v.end());
// v: 3, 1, 2
```

**Time Complexity:** O(n)

---

### **7. Removal & Unique**

#### **remove()** - Remove elements (logical)

```cpp
vector<int> v = {1, 2, 3, 2, 5};
auto newEnd = remove(v.begin(), v.end(), 2);
v.erase(newEnd, v.end());
// v: 1, 3, 5
```

**Time Complexity:** O(n)

---

#### **remove_if()** - Remove with predicate

```cpp
vector<int> v = {1, 2, 3, 4, 5};
auto newEnd = remove_if(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});
v.erase(newEnd, v.end());
// v: 1, 3, 5
```

**Time Complexity:** O(n)

---

#### **unique()** - Remove consecutive duplicates

```cpp
vector<int> v = {1, 1, 2, 2, 3, 3, 3};
auto newEnd = unique(v.begin(), v.end());
v.erase(newEnd, v.end());
// v: 1, 2, 3
```

**Time Complexity:** O(n)

---

### **8. Reversing & Rotating**

#### **reverse()** - Reverse elements

```cpp
vector<int> v = {1, 2, 3, 4, 5};
reverse(v.begin(), v.end());
// v: 5, 4, 3, 2, 1
```

**Time Complexity:** O(n)

---

#### **rotate()** - Rotate elements

```cpp
vector<int> v = {1, 2, 3, 4, 5};
rotate(v.begin(), v.begin() + 2, v.end());
// v: 3, 4, 5, 1, 2  (rotated left by 2)
```

**Time Complexity:** O(n)

---

### **9. Partitioning**

#### **partition()** - Partition by predicate

```cpp
vector<int> v = {1, 2, 3, 4, 5, 6};
auto pivot = partition(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});
// Even numbers first, then odd
```

**Time Complexity:** O(n)

---

#### **stable_partition()** - Partition maintaining order

```cpp
vector<int> v = {1, 2, 3, 4, 5, 6};
stable_partition(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});
// Even: 2, 4, 6, then Odd: 1, 3, 5
```

**Time Complexity:** O(n log n)

---

### **10. Set Operations (on sorted ranges)**

#### **merge()** - Merge two sorted ranges

```cpp
vector<int> v1 = {1, 3, 5};
vector<int> v2 = {2, 4, 6};
vector<int> result(6);

merge(v1.begin(), v1.end(), v2.begin(), v2.end(), result.begin());
// result: 1, 2, 3, 4, 5, 6
```

**Time Complexity:** O(n)

---

#### **set_union()** - Union of two sorted sets

```cpp
vector<int> v1 = {1, 2, 3, 4};
vector<int> v2 = {3, 4, 5, 6};
vector<int> result;

set_union(v1.begin(), v1.end(), v2.begin(), v2.end(), back_inserter(result));
// result: 1, 2, 3, 4, 5, 6
```

**Time Complexity:** O(n)

---

#### **set_intersection()** - Intersection of two sorted sets

```cpp
vector<int> v1 = {1, 2, 3, 4};
vector<int> v2 = {3, 4, 5, 6};
vector<int> result;

set_intersection(v1.begin(), v1.end(), v2.begin(), v2.end(), back_inserter(result));
// result: 3, 4
```

**Time Complexity:** O(n)

---

#### **set_difference()** - Elements in first but not second

```cpp
vector<int> v1 = {1, 2, 3, 4};
vector<int> v2 = {3, 4, 5, 6};
vector<int> result;

set_difference(v1.begin(), v1.end(), v2.begin(), v2.end(), back_inserter(result));
// result: 1, 2
```

**Time Complexity:** O(n)

---

### **11. Predicates (Boolean Check)**

#### **all_of()** - Check if all satisfy condition

```cpp
vector<int> v = {2, 4, 6, 8};
bool allEven = all_of(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});  // true
```

**Time Complexity:** O(n)

---

#### **any_of()** - Check if any satisfies condition

```cpp
vector<int> v = {1, 3, 5, 8};
bool hasEven = any_of(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});  // true
```

**Time Complexity:** O(n)

---

#### **none_of()** - Check if none satisfies condition

```cpp
vector<int> v = {1, 3, 5, 7};
bool noEven = none_of(v.begin(), v.end(), [](int x) {
    return x % 2 == 0;
});  // true
```

**Time Complexity:** O(n)

---

#### **is_sorted()** - Check if range is sorted

```cpp
vector<int> v = {1, 2, 3, 4, 5};
bool sorted = is_sorted(v.begin(), v.end());  // true
```

**Time Complexity:** O(n)

---

### **12. Copying & Filling**

#### **copy()** - Copy elements

```cpp
vector<int> v1 = {1, 2, 3, 4, 5};
vector<int> v2(5);

copy(v1.begin(), v1.end(), v2.begin());
```

**Time Complexity:** O(n)

---

#### **copy_if()** - Copy with condition

```cpp
vector<int> v = {1, 2, 3, 4, 5, 6};
vector<int> evens;

copy_if(v.begin(), v.end(), back_inserter(evens), [](int x) {
    return x % 2 == 0;
});
// evens: 2, 4, 6
```

**Time Complexity:** O(n)

---

#### **fill()** - Fill with value

```cpp
vector<int> v(5);
fill(v.begin(), v.end(), 42);
// v: 42, 42, 42, 42, 42
```

**Time Complexity:** O(n)

---

#### **generate()** - Fill with function results

```cpp
vector<int> v(5);
int n = 0;
generate(v.begin(), v.end(), [&n]() { return n++; });
// v: 0, 1, 2, 3, 4
```

**Time Complexity:** O(n)

---

## 📌 **STL Algorithms — LeetCode Problems**

### **1. Kth Largest Element (using nth_element) (LeetCode #215)**

```cpp
int findKthLargest(vector<int>& nums, int k) {
    nth_element(nums.begin(), nums.begin() + k - 1, nums.end(), greater<int>());
    return nums[k - 1];
}
```

**Output:**

```
nums = [3,2,1,5,6,4], k = 2
Output: 5
```

---

### **2. Merge Intervals (using sort) (LeetCode #56)**

```cpp
vector<vector<int>> merge(vector<vector<int>>& intervals) {
    sort(intervals.begin(), intervals.end());
    vector<vector<int>> result;
    
    for (auto& interval : intervals) {
        if (result.empty() || result.back()[1] < interval[0]) {
            result.push_back(interval);
        } else {
            result.back()[1] = max(result.back()[1], interval[1]);
        }
    }
    return result;
}
```

**Output:**

```
intervals = [[1,3],[2,6],[8,10],[15,18]]
Output: [[1,6],[8,10],[15,18]]
```

---

### **3. Next Permutation (using next_permutation) (LeetCode #31)**

```cpp
void nextPermutation(vector<int>& nums) {
    next_permutation(nums.begin(), nums.end());
}
```

**Output:**

```
nums = [1,2,3]
Output: [1,3,2]
```

---

### **4. Remove Duplicates (using unique) (LeetCode #26)**

```cpp
int removeDuplicates(vector<int>& nums) {
    auto newEnd = unique(nums.begin(), nums.end());
    return distance(nums.begin(), newEnd);
}
```

**Output:**

```
nums = [1,1,2]
Output: 2, nums = [1,2,...]
```

---

### **5. Search Insert Position (using lower_bound) (LeetCode #35)**

```cpp
int searchInsert(vector<int>& nums, int target) {
    return lower_bound(nums.begin(), nums.end(), target) - nums.begin();
}
```

**Output:**

```
nums = [1,3,5,6], target = 5
Output: 2
```

---

### **6. Single Number (using accumulate with XOR) (LeetCode #136)**

```cpp
int singleNumber(vector<int>& nums) {
    return accumulate(nums.begin(), nums.end(), 0, bit_xor<int>());
}
```

**Output:**

```
nums = [4,1,2,1,2]
Output: 4
```

---

### **7. Maximum Subarray (using partial_sum) (LeetCode #53)**

```cpp
int maxSubArray(vector<int>& nums) {
    int maxSum = nums[0], currentSum = 0;
    
    for (int num : nums) {
        currentSum = max(num, currentSum + num);
        maxSum = max(maxSum, currentSum);
    }
    return maxSum;
}
```

**Output:**

```
nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6 ([4,-1,2,1])
```

---

### **8. Reverse String (using reverse) (LeetCode #344)**

```cpp
void reverseString(vector<char>& s) {
    reverse(s.begin(), s.end());
}
```

**Output:**

```
s = ['h','e','l','l','o']
Output: ['o','l','l','e','h']
```

---

### **9. Rotate Array (using rotate) (LeetCode #189)**

```cpp
void rotate(vector<int>& nums, int k) {
    k = k % nums.size();
    reverse(nums.begin(), nums.end());
    reverse(nums.begin(), nums.begin() + k);
    reverse(nums.begin() + k, nums.end());
}
```

**Output:**

```
nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
```

---

### **10. Move Zeroes (using partition) (LeetCode #283)**

```cpp
void moveZeroes(vector<int>& nums) {
    stable_partition(nums.begin(), nums.end(), [](int x) {
        return x != 0;
    });
}
```

**Output:**

```
nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

---

### **11. Intersection of Two Arrays (using set_intersection) (LeetCode #349)**

```cpp
vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
    sort(nums1.begin(), nums1.end());
    sort(nums2.begin(), nums2.end());
    
    vector<int> result;
    set_intersection(nums1.begin(), nums1.end(), 
                     nums2.begin(), nums2.end(), 
                     back_inserter(result));
    
    auto newEnd = unique(result.begin(), result.end());
    result.erase(newEnd, result.end());
    
    return result;
}
```

**Output:**

```
nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2]
```

---

### **12. Missing Number (using accumulate) (LeetCode #268)**

```cpp
int missingNumber(vector<int>& nums) {
    int n = nums.size();
    int expectedSum = n * (n + 1) / 2;
    int actualSum = accumulate(nums.begin(), nums.end(), 0);
    return expectedSum - actualSum;
}
```

**Output:**

```
nums = [3,0,1]
Output: 2
```

---

### **13. Valid Anagram (using is_permutation) (LeetCode #242)**

```cpp
bool isAnagram(string s, string t) {
    if (s.size() != t.size()) return false;
    return is_permutation(s.begin(), s.end(), t.begin());
}
```

**Output:**

```
s = "anagram", t = "nagaram"
Output: true
```

---

### **14. Contains Duplicate (using adjacent_find) (LeetCode #217)**

```cpp
bool containsDuplicate(vector<int>& nums) {
    sort(nums.begin(), nums.end());
    return adjacent_find(nums.begin(), nums.end()) != nums.end();
}
```

**Output:**

```
nums = [1,2,3,1]
Output: true
```

---

### **15. Sort Colors (using partition) (LeetCode #75)**

```cpp
void sortColors(vector<int>& nums) {
    auto mid1 = partition(nums.begin(), nums.end(), [](int x) { return x == 0; });
    partition(mid1, nums.end(), [](int x) { return x == 1; });
}
```

**Output:**

```
nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
```

---

### 🔹 **STL Algorithms Complexity Summary**

| Algorithm | Time Complexity | Space Complexity |
|-----------|----------------|------------------|
| sort | O(n log n) | O(log n) |
| stable_sort | O(n log n) | O(n) |
| partial_sort | O(n log k) | O(1) |
| nth_element | O(n) avg | O(1) |
| binary_search | O(log n) | O(1) |
| lower_bound / upper_bound | O(log n) | O(1) |
| find | O(n) | O(1) |
| count | O(n) | O(1) |
| accumulate | O(n) | O(1) |
| transform | O(n) | O(1) |
| reverse | O(n) | O(1) |
| rotate | O(n) | O(1) |
| partition | O(n) | O(1) |
| merge | O(n) | O(1) |
| unique | O(n) | O(1) |
| next_permutation | O(n) | O(1) |

---



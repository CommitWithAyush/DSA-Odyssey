
````markdown
# 🔷 Merge Sorted Array

[![LeetCode](https://img.shields.io/badge/LeetCode-000?style=for-the-badge&logo=leetcode&logoColor=white)](https://leetcode.com/u/Crypt0xAyush/)

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen?style=for-the-badge)
![Topic](https://img.shields.io/badge/Topic-Array%2C%20Two%20Pointers%2C%20Sorting-blue?style=for-the-badge)

---

## 📌 Problem Summary
Merge two sorted arrays `nums1` and `nums2` into `nums1` as one sorted array.  
👉 Note: `nums1` has enough space at the end to hold all elements of `nums2`.

---

## 🎥 Intuition (Visual)

Instead of filling from the **front** (jisme shifting karni padti),  
we fill from the **end** → always place the largest element at the last index.  

📊 Visual Representation:  
![Merge Process](https://raw.githubusercontent.com/akshaybahadur21/Visuals/main/merge-array.gif)  
*(Replace with your own GIF if needed)*

---

## 🚀 Approach
1️⃣ Start pointers at the end → `i = m-1`, `j = n-1`, `k = m+n-1`  
2️⃣ Compare `nums1[i]` and `nums2[j]`  
3️⃣ Place the bigger one at `nums1[k]`  
4️⃣ Move pointer (`i` or `j`) accordingly  
5️⃣ Continue until `nums2` is exhausted  

---

## ⏱️ Complexity
![Time](https://img.shields.io/badge/Time%20Complexity-O(m%20%2B%20n)-yellow?style=for-the-badge)  
![Space](https://img.shields.io/badge/Space%20Complexity-O(1)-orange?style=for-the-badge)

---

## 💻 Solutions

<details>
<summary>🟦 C++ Solution</summary>

```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int k = m + n - 1;
        int i = m - 1;
        int j = n - 1;

        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k--] = nums1[i--];
            } else {
                nums1[k--] = nums2[j--];
            }
        }
    }
};
````

</details>

<details>
<summary>🐍 Python Solution</summary>

```python
class Solution:
    def merge(self, nums1, m, nums2, n):
        k = m + n - 1
        i = m - 1
        j = n - 1

        while j >= 0:
            if i >= 0 and nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1
```

</details>

---

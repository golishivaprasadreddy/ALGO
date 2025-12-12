

# 📘 **Kadane’s Algorithm – Notes**

## ✅ **1. What is Kadane’s Algorithm?**

Kadane’s Algorithm is an **efficient algorithm** used to find the **maximum sum of any contiguous subarray** in an array.

This is also known as the **Maximum Subarray Sum Problem**.

It transforms a brute-force **O(n³)** or **O(n²)** approach into a highly optimized **O(n)** solution.

---

## ✅ **2. Why Do We Need Kadane’s Algorithm?**

Given an array of positive/negative integers, we often need to find:

👉 The contiguous subarray which produces the **maximum possible sum**

Example:

```
Input:  [-2, 1, -3, 4, -1, 2, 1, -5, 4]
Output: 6
Explanation: [4, -1, 2, 1] gives max sum = 6
```

Kadane does this **efficiently in one pass**.

---

## ✅ **3. Key Idea Behind Kadane’s Algorithm**

Kadane’s Algorithm keeps track of two things:

### **1. currSum (Current Sum)**

* Best sum ending at the current index.
* Either:

  * Start fresh from current element
    **OR**
  * Continue the previous subarray

Formula:

```
currSum = Math.max(nums[i], currSum + nums[i])
```

### **2. maxSum (Global Best Sum)**

Tracks the **maximum sum seen so far**:

```
maxSum = Math.max(maxSum, currSum)
```

---

# 🚀 **4. How Kadane’s Algorithm Works (Concept)**

For each element:

### ✔ Option 1: Take the element as a new start

(If previous sum is negative, drop it)

### ✔ Option 2: Continue adding to the existing sum

(If it increases the total)

Kadane automatically chooses the **best option** at each step.

---

# 🧠 **5. When is Kadane’s Algorithm Useful?**

Kadane’s is used when:

### ✔ You need maximum sum of a **contiguous** subarray

### ✔ You want to handle **negative numbers** efficiently

### ✔ Input size is large → need **O(n)** performance

### ✔ Used in interview problems, DP problems

### ✔ Solving stock problems (variation), game score analysis, signal processing

### ✔ Finding periods of highest profit or performance

---

# 📈 **6. Kadane’s Algorithm Code (Java)**

```java
public int maxSubArray(int[] nums) {
    int currSum = nums[0];
    int maxSum = nums[0];

    for (int i = 1; i < nums.length; i++) {
        currSum = Math.max(nums[i], currSum + nums[i]);
        maxSum = Math.max(maxSum, currSum);
    }

    return maxSum;
}
```

---

# 🔍 **7. Time and Space Complexity**

| Operation | Complexity |
| --------- | ---------- |
| Time      | **O(n)**   |
| Space     | **O(1)**   |

Kadane is optimal for this problem.

---

# 📌 **8. Important Points to Remember**

* Works for **all negative arrays** too
  → The maximum element becomes the result
* Uses **Dynamic Programming** (DP concept)
* Simple but powerful logic
* Huge improvement over brute-force

---

# 📝 **9. Example Walkthrough**

Array:
`[5, -2, 3, -1]`

| Element | currSum | maxSum |
| ------- | ------- | ------ |
| 5       | 5       | 5      |
| -2      | 3       | 5      |
| 3       | 6       | 6      |
| -1      | 5       | 6      |

Final Answer: **6**

---

# 🎯 **Summary**

**Kadane’s Algorithm** is a linear-time algorithm to find the **maximum sum of a contiguous subarray** in an array.
It is efficient, simple, and widely used in coding interviews and real-world problems.

---


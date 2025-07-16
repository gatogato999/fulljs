## Chapter 2: Core JavaScript - LeetCode Style Problems

These problems focus on applying core JavaScript concepts like functions,
loops, arrays, objects, and string manipulation. They are designed to build
your problem-solving skills and familiarity with common data structures and
algorithms in a JavaScript context.

---

### Problems

#### Problem 1: Two Sum

**Description:** Given an array of integers `nums` and an integer `target`,
return *indices of the two numbers such that they add up to `target`*. You may
assume that each input would have **exactly one solution**, and you may not use
the *same* element twice. You can return the answer in any order.

**Example 1:**
```
Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**
```
Input: nums = [3, 2, 4], target = 6
Output: [1, 2]
```

> solution : 
  ``` js
        let array = [2, 7, 11, 15]
        let target = 9
        let copy = [...array]
        for (let e in array){
          for (let i in copy){
            if (array[e] + copy[i] === target){
              console.log(` found : ${array[e]} + ${copy[i]} = ${target}`);
            }
          }
        }
```

#### Problem 2: Reverse Integer

**Description:** Given a signed 32-bit integer `x`, return `x` *with its digits
reversed*. If reversing `x` causes the value to go outside the signed 32-bit
integer range `[-2^31, 2^31 - 1]`, then return `0`.

**Example 1:**
```
Input: x = 123
Output: 321
```

**Example 2:**
```
Input: x = -123
Output: -321
```

**Example 3:**
```
Input: x = 120
Output: 21
```

#### Problem 3: Palindrome Number

**Description:** Given an integer `x`, return `true` *if* `x` *is a palindrome,
and* `false` *otherwise*.

**Example 1:**
```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

**Example 2:**
```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

#### Problem 4: Valid Parentheses

**Description:** Given a string `s` containing just the characters `(`, `)`,
`{`, `}`, `[` and `]`, determine if the input string is valid. An input string
is valid if:
1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

**Example 1:**
```
Input: s = "()"
Output: true
```

**Example 2:**
```
Input: s = "()[]{}"
Output: true
```

**Example 3:**
```
Input: s = "(]"
Output: false
```

#### Problem 5: Remove Duplicates from Sorted Array

**Description:** Given an integer array `nums` sorted in **non-decreasing
order**, remove the duplicates **in-place** such that each unique element
appears only **once**. The relative order of the elements should be kept the
**same**. Then return *the number of unique elements in* `nums`.

Consider the number of unique elements of `nums` to be `k`, to get accepted,
you need to do the following things:
* Change the array `nums` such that the first `k` elements of `nums` contain
  the unique elements in the order they were present in `nums` initially. The
  remaining elements of `nums` are not important as well as the size of `nums`.
* Return `k`.

**Example 1:**
```
Input: nums = [1, 1, 2]
Output: 2, nums = [1, 2, _]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively. It does not matter what you leave beyond the returned k (hence they are underscores).
```

#### Problem 6: Maximum Subarray

**Description:** Given an integer array `nums`, find the subarray with the
largest sum, and return *its sum*.

**Example 1:**
```
Input: nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
Output: 6
Explanation: The subarray [4, -1, 2, 1] has the largest sum 6.
```

#### Problem 7: Length of Last Word

**Description:** Given a string `s` consisting of words and spaces, return *the
length of the **last** word in the string*. A **word** is a maximal substring
consisting of non-space characters only.

**Example 1:**
```
Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
```

#### Problem 8: Plus One

**Description:** You are given a **large integer** represented as an integer
array `digits`, where each `digits[i]` is the `ith` digit of the integer. The
digits are ordered from most significant to least significant in left-to-right
order. The large integer does not contain any leading `0`'s. Increment the
large integer by one and return *the resulting array of digits*.

**Example 1:**
```
Input: digits = [1, 2, 3]
Output: [1, 2, 4]
Explanation: The array represents the integer 123. Incrementing by one gives 123 + 1 = 124. Thus, the result should be [1, 2, 4].
```

#### Problem 9: Sqrt(x)

**Description:** Given a non-negative integer `x`, return *the square root of*
`x` *rounded down to the nearest integer*. The returned integer should be
**non-negative** as well. You **must not use** any built-in exponent function
or operator (e.g., `pow(x, 0.5)` or `x ** 0.5`).

**Example 1:**
```
Input: x = 4
Output: 2
Explanation: The square root of 4 is 2, so we return 2.
```

**Example 2:**
```
Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since we round down to the nearest integer, 2 is returned.
```

#### Problem 10: Climbing Stairs

**Description:** You are climbing a staircase. It takes `n` steps to reach the
top. Each time you can either climb 1 or 2 steps. In how many distinct ways can
you climb to the top?

**Example 1:**
```
Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

**Example 2:**
```
Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

#### Problem 11: Merge Sorted Array

**Description:** You are given two integer arrays `nums1` and `nums2`, sorted
in **non-decreasing order**, and two integers `m` and `n`, representing the
number of elements in `nums1` and `nums2` respectively. **Merge** `nums1` and
`nums2` into a single array sorted in **non-decreasing order**. The final
sorted array should not be returned by the function, but instead be **stored
inside the array** `nums1`. To accommodate this, `nums1` has a length of `m +
n`, where the first `m` elements denote the elements that should be merged, and
the last `n` elements are set to `0` and should be ignored. `nums2` has a
length of `n`.

**Example 1:**
```
Input: nums1 = [1, 2, 3, 0, 0, 0], m = 3, nums2 = [2, 5, 6], n = 3
Output: [1, 2, 2, 3, 5, 6]
Explanation: The arrays we are merging are [1, 2, 3] and [2, 5, 6].
The result of the merge is [1, 2, 2, 3, 5, 6] with the underlined elements coming from nums1.
```

#### Problem 12: Binary Tree Inorder Traversal

**Description:** Given the `root` of a binary tree, return *the inorder
traversal of its nodes' values*.

**Example 1:**
```
Input: root = [1, null, 2, 3]
Output: [1, 3, 2]
```

**Example 2:**
```
Input: root = []
Output: []
```

*(Note: For this problem, you can assume a basic TreeNode structure is provided
or define one yourself, e.g., `function TreeNode(val, left, right) { this.val =
(val===undefined ? 0 : val); this.left = (left===undefined ? null : left);
this.right = (right===undefined ? null : right); }`)*

#### Problem 13: Symmetric Tree

**Description:** Given the `root` of a binary tree, *check whether it is a
mirror of itself* (i.e., symmetric around its center).

**Example 1:**
```
Input: root = [1, 2, 2, 3, 4, 4, 3]
Output: true
```

**Example 2:**
```
Input: root = [1, 2, 2, null, 3, null, 3]
Output: false
```

#### Problem 14: Maximum Depth of Binary Tree

**Description:** Given the `root` of a binary tree, return *its maximum depth*.
A binary tree's **maximum depth** is the number of nodes along the longest path
from the root node down to the farthest leaf node.

**Example 1:**
```
Input: root = [3, 9, 20, null, null, 15, 7]
Output: 3
```

#### Problem 15: Single Number

**Description:** Given a **non-empty** array of integers `nums`, every element
appears *twice* except for one. Find that single one. You must implement a
solution with a linear runtime complexity and use only constant extra space.

**Example 1:**
```
Input: nums = [2, 2, 1]
Output: 1
```

**Example 2:**
```
Input: nums = [4, 1, 2, 1, 2]
Output: 4
```

#### Problem 16: Majority Element

**Description:** Given an array `nums` of size `n`, return *the majority
element*. The majority element is the element that appears more than `⌊n / 2⌋`
times. You may assume that the majority element always exists in the array.

**Example 1:**
```
Input: nums = [3, 2, 3]
Output: 3
```

**Example 2:**
```
Input: nums = [2, 2, 1, 1, 1, 2, 2]
Output: 2
```

#### Problem 17: Contains Duplicate

**Description:** Given an integer array `nums`, return `true` if any value
appears **at least twice** in the array, and return `false` if every element is
distinct.

**Example 1:**
```
Input: nums = [1, 2, 3, 1]
Output: true
```

**Example 2:**
```
Input: nums = [1, 2, 3, 4]
Output: false
```

#### Problem 18: Missing Number

**Description:** Given an array `nums` containing `n` distinct numbers in the
range `[0, n]`, return *the only number in the range that is missing from the
array*.

**Example 1:**
```
Input: nums = [3, 0, 1]
Output: 2
Explanation: n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.
```

#### Problem 19: Move Zeroes

**Description:** Given an integer array `nums`, move all `0`'s to the end of it
while maintaining the relative order of the non-zero elements. **Note** that
    you must do this in-place without making a copy of the array.

**Example 1:**
```
Input: nums = [0, 1, 0, 3, 12]
Output: [1, 3, 12, 0, 0]
```

#### Problem 20: Best Time to Buy and Sell Stock

**Description:** You are given an array `prices` where `prices[i]` is the price
of a given stock on the `ith` day. You want to maximize your profit by choosing
a **single day** to buy one stock and choosing a **different day in the
future** to sell that stock. Return *the maximum profit you can achieve from
this transaction*. If you cannot achieve any profit, return `0`.

**Example 1:**
```
Input: prices = [7, 1, 5, 3, 6, 4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```

#### Problem 21: Valid Anagram

**Description:** Given two strings `s` and `t`, return `true` *if* `t` *is an
anagram of* `s`*, and* `false` *otherwise*. An **Anagram** is a word or phrase
formed by rearranging the letters of a different word or phrase, typically
using all the original letters exactly once.

**Example 1:**
```
Input: s = "anagram", t = "nagaram"
Output: true
```

**Example 2:**
```
Input: s = "rat", t = "car"
Output: false
```

#### Problem 22: First Unique Character in a String

**Description:** Given a string `s`, *find the first non-repeating character in
it and return its index*. If it does not exist, return `-1`.

**Example 1:**
```
Input: s = "leetcode"
Output: 0
```

**Example 2:**
```
Input: s = "loveleetcode"
Output: 2
```

#### Problem 23: Intersection of Two Arrays II

**Description:** Given two integer arrays `nums1` and `nums2`, return *an array
of their intersection*. Each element in the result must appear as many times as
it shows in both arrays and you may return the result in **any order**.

**Example 1:**
```
Input: nums1 = [1, 2, 2, 1], nums2 = [2, 2]
Output: [2, 2]
```

#### Problem 24: Fizz Buzz

**Description:** Given an integer `n`, return *a string array* `answer`
*(1-indexed) where:*
* `answer[i] == "FizzBuzz"` if `i` is divisible by `3` and `5`.
* `answer[i] == "Fizz"` if `i` is divisible by `3`.
* `answer[i] == "Buzz"` if `i` is divisible by `5`.
* `answer[i] == i` (as a string) if none of the above conditions are true.

**Example 1:**
```
Input: n = 3
Output: ["1", "2", "Fizz"]
```

#### Problem 25: Reverse String

**Description:** Write a function that reverses a string. The input string is
given as an array of characters `s`. You must do this by modifying the input
array **in-place** with `O(1)` extra memory.

**Example 1:**
```
Input: s = ["h", "e", "l", "l", "o"]
Output: ["o", "l", "l", "e", "h"]
```

#### Problem 26: Power of Two

**Description:** Given an integer `n`, return `true` *if it is a power of two*.
Otherwise, return `false`. An integer `n` is a power of two, if there exists an
integer `x` such that `n == 2^x`.

**Example 1:**
```
Input: n = 1
Output: true
Explanation: 2^0 = 1
```

**Example 2:**
```
Input: n = 16
Output: true
Explanation: 2^4 = 16
```

#### Problem 27: Valid Palindrome

**Description:** A phrase is a **palindrome** if, after converting all
uppercase letters into lowercase letters and removing all non-alphanumeric
characters, it reads the same forward and backward. Alphanumeric characters
include letters and numbers. Given a string `s`, return `true` *if it is a
palindrome, or* `false` *otherwise*.

**Example 1:**
```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

#### Problem 28: Linked List Cycle

**Description:** Given `head`, the head of a linked list, determine if the
linked list has a cycle in it. There is a cycle in a linked list if there is
some node in the list that can be reached again by continuously following the
`next` pointer. Internally, `pos` is used to denote the index of the node that
tail's `next` pointer is connected to. **Note that `pos` is not passed as a
parameter**. Return `true` *if there is a cycle in the linked list*. Otherwise,
return `false`.

*(Note: For this problem, assume a basic ListNode structure: `function ListNode(val) { this.val = val; this.next = null; }`)*

**Example 1:**
```
Input: head = [3, 2, 0, -4], pos = 1
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).
```

#### Problem 29: Convert Sorted Array to Binary Search Tree

**Description:** Given an integer array `nums` where the elements are sorted in
**ascending order**, convert it to a **height-balanced** binary search tree.

**Example 1:**
```
Input: nums = [-10, -3, 0, 5, 9]
Output: [0, -3, 9, -10, null, 5]
Explanation: [0, -10, 5, null, -3, null, 9] is also accepted.
```

#### Problem 30: Implement strStr()

**Description:** Given two strings `haystack` and `needle`, return the index of
the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part
of `haystack`.

**Example 1:**
```
Input: haystack = "hello", needle = "ll"
Output: 2
```

**Example 2:**
```
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

---

### Solutions

#### Problem 1: Two Sum

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const twoSum = (nums, target) => {
    const numMap = new Map(); // To store number and its index
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (numMap.has(complement)) {
            return [numMap.get(complement), i];
        }
        numMap.set(nums[i], i);
    }
    return []; // Should not be reached based on problem description (exactly one solution)
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once. Map operations (get, set, has) are O(1) on average.
// Space Complexity: O(N) - In the worst case, the map stores N-1 elements.
```

#### Problem 2: Reverse Integer

```javascript
/**
 * @param {number} x
 * @return {number}
 */
const reverseInteger = (x) => {
    const INT_MAX = 2**31 - 1;
    const INT_MIN = -(2**31);

    let reversed = 0;
    const sign = x < 0 ? -1 : 1;
    x = Math.abs(x);

    while (x > 0) {
        const digit = x % 10;
        reversed = reversed * 10 + digit;
        x = Math.floor(x / 10);
    }

    reversed *= sign;

    if (reversed > INT_MAX || reversed < INT_MIN) {
        return 0;
    }

    return reversed;
};

// Big-O Analysis:
// Time Complexity: O(log10(N)) - Where N is the input number. The number of digits is proportional to log10(N).
// Space Complexity: O(1) - We only use a few variables.
```

#### Problem 3: Palindrome Number

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
const isPalindromeNumber = (x) => {
    if (x < 0) {
        return false; // Negative numbers are not palindromes
    }
    if (x === 0) {
        return true;
    }

    const s = String(x);
    let left = 0;
    let right = s.length - 1;

    while (left < right) {
        if (s[left] !== s[right]) {
            return false;
        }
        left++;
        right--;
    }
    return true;

    // Alternative without converting to string (more complex):
    // if (x < 0 || (x % 10 === 0 && x !== 0)) {
    //     return false;
    // }
    // let revertedNumber = 0;
    // while (x > revertedNumber) {
    //     revertedNumber = revertedNumber * 10 + x % 10;
    //     x = Math.floor(x / 10);
    // }
    // return x === revertedNumber || x === Math.floor(revertedNumber / 10);
};

// Big-O Analysis (String conversion method):
// Time Complexity: O(D) - Where D is the number of digits in x. String conversion and loop take D steps.
// Space Complexity: O(D) - To store the string representation.
```

#### Problem 4: Valid Parentheses

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
const isValidParentheses = (s) => {
    const stack = [];
    const map = {
        ")": "(",
        "}": "{",
        "]": "["
    };

    for (let i = 0; i < s.length; i++) {
        const char = s[i];
        if (char === "(" || char === "{" || char === "[") {
            stack.push(char);
        } else if (char === ")" || char === "}" || char === "]") {
            if (stack.length === 0 || stack.pop() !== map[char]) {
                return false;
            }
        }
    }
    return stack.length === 0;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the string once. Stack operations (push, pop) are O(1).
// Space Complexity: O(N) - In the worst case (e.g., "((("), the stack can store all characters.
```

#### Problem 5: Remove Duplicates from Sorted Array

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const removeDuplicates = (nums) => {
    if (nums.length === 0) {
        return 0;
    }
    let k = 1; // Pointer for the next unique element
    for (let i = 1; i < nums.length; i++) {
        if (nums[i] !== nums[i - 1]) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - We modify the array in-place.
```

#### Problem 6: Maximum Subarray

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const maxSubArray = (nums) => {
    if (nums.length === 0) {
        return 0; // Or throw error for empty array, problem implies non-empty or handles it
    }
    let maxSoFar = nums[0];
    let currentMax = nums[0];

    for (let i = 1; i < nums.length; i++) {
        currentMax = Math.max(nums[i], currentMax + nums[i]);
        maxSoFar = Math.max(maxSoFar, currentMax);
    }
    return maxSoFar;
};

// Big-O Analysis (Kadane's Algorithm):
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - We only use a few variables.
```

#### Problem 7: Length of Last Word

```javascript
/**
 * @param {string} s
 * @return {number}
 */
const lengthOfLastWord = (s) => {
    const trimmed = s.trim(); // Remove leading/trailing spaces
    if (trimmed.length === 0) {
        return 0;
    }
    const words = trimmed.split(" ");
    return words[words.length - 1].length;
};

// Big-O Analysis:
// Time Complexity: O(L) - Where L is the length of the string. trim() and split() can take O(L).
// Space Complexity: O(W) - Where W is the number of words, as split() creates an array of words.
```

#### Problem 8: Plus One

```javascript
/**
 * @param {number[]} digits
 * @return {number[]}
 */
const plusOne = (digits) => {
    for (let i = digits.length - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i]++;
            return digits;
        }
        digits[i] = 0;
    }
    // If we reach here, it means all digits were 9 (e.g., [9, 9])
    digits.unshift(1);
    return digits;
};

// Big-O Analysis:
// Time Complexity: O(N) - In the worst case (all 9s), we iterate through all digits.
// Space Complexity: O(1) - In most cases. O(N) if unshift is needed (e.g., [9,9,9] -> [1,0,0,0]), but this is amortized O(1) for unshift if we consider typical array implementations or if a new array is returned.
```

#### Problem 9: Sqrt(x)

```javascript
/**
 * @param {number} x
 * @return {number}
 */
const mySqrt = (x) => {
    if (x < 0) return NaN; // Or throw error, problem states non-negative
    if (x === 0) return 0;
    if (x === 1) return 1;

    // Binary search approach
    let left = 1;
    let right = Math.floor(x / 2) + 1; // Optimization: sqrt(x) <= x/2 for x >= 4
    let ans = 0;

    while (left <= right) {
        let mid = Math.floor(left + (right - left) / 2);
        if (mid <= x / mid) { // Use mid <= x / mid to avoid overflow for mid*mid
            ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
};

// Big-O Analysis:
// Time Complexity: O(log N) - Due to binary search.
// Space Complexity: O(1) - Constant space.
```

#### Problem 10: Climbing Stairs

```javascript
/**
 * @param {number} n
 * @return {number}
 */
const climbStairs = (n) => {
    if (n <= 0) return 0;
    if (n === 1) return 1;
    if (n === 2) return 2;

    // Dynamic Programming approach (Fibonacci sequence)
    let dp = new Array(n + 1);
    dp[1] = 1;
    dp[2] = 2;

    for (let i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];

    // Space optimized DP:
    // let oneStepBefore = 2;
    // let twoStepsBefore = 1;
    // for (let i = 3; i <= n; i++) {
    //     const current = oneStepBefore + twoStepsBefore;
    //     twoStepsBefore = oneStepBefore;
    //     oneStepBefore = current;
    // }
    // return oneStepBefore;
};

// Big-O Analysis (DP with array):
// Time Complexity: O(N) - We iterate from 3 to N.
// Space Complexity: O(N) - For the DP array.
// (Space optimized DP has O(1) space complexity)
```

#### Problem 11: Merge Sorted Array

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
const mergeSortedArray = (nums1, m, nums2, n) => {
    let p1 = m - 1; // Pointer for nums1 (actual elements)
    let p2 = n - 1; // Pointer for nums2
    let p = m + n - 1; // Pointer for the end of nums1 (merged array)

    while (p1 >= 0 && p2 >= 0) {
        if (nums1[p1] > nums2[p2]) {
            nums1[p] = nums1[p1];
            p1--;
        } else {
            nums1[p] = nums2[p2];
            p2--;
        }
        p--;
    }

    // If there are remaining elements in nums2, copy them
    while (p2 >= 0) {
        nums1[p] = nums2[p2];
        p2--;
        p--;
    }
    // No need to handle remaining elements in nums1 as they are already in place.
};

// Big-O Analysis:
// Time Complexity: O(m + n) - We iterate through both arrays once.
// Space Complexity: O(1) - We modify nums1 in-place.
```

#### Problem 12: Binary Tree Inorder Traversal

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[]}
 */
const inorderTraversal = (root) => {
    const result = [];
    const traverse = (node) => {
        if (!node) {
            return;
        }
        traverse(node.left);  // Visit left subtree
        result.push(node.val); // Visit root node
        traverse(node.right); // Visit right subtree
    };
    traverse(root);
    return result;

    // Iterative approach using a stack:
    // const stack = [];
    // let current = root;
    // while (current || stack.length > 0) {
    //     while (current) {
    //         stack.push(current);
    //         current = current.left;
    //     }
    //     current = stack.pop();
    //     result.push(current.val);
    //     current = current.right;
    // }
    // return result;
};

// Big-O Analysis (Recursive and Iterative):
// Time Complexity: O(N) - We visit each node once.
// Space Complexity: O(H) - Where H is the height of the tree. For a balanced tree, H = log N. For a skewed tree, H = N (due to recursion stack or explicit stack).
```

#### Problem 13: Symmetric Tree

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
const isSymmetric = (root) => {
    if (!root) {
        return true;
    }

    const isMirror = (leftNode, rightNode) => {
        if (!leftNode && !rightNode) return true;
        if (!leftNode || !rightNode || leftNode.val !== rightNode.val) return false;
        return isMirror(leftNode.left, rightNode.right) && isMirror(leftNode.right, rightNode.left);
    };

    return isMirror(root.left, root.right);
};

// Big-O Analysis:
// Time Complexity: O(N) - We visit each node once.
// Space Complexity: O(H) - Where H is the height of the tree (recursion stack).
```

#### Problem 14: Maximum Depth of Binary Tree

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
const maxDepth = (root) => {
    if (!root) {
        return 0;
    }
    const leftDepth = maxDepth(root.left);
    const rightDepth = maxDepth(root.right);
    return Math.max(leftDepth, rightDepth) + 1;
};

// Big-O Analysis:
// Time Complexity: O(N) - We visit each node once.
// Space Complexity: O(H) - Where H is the height of the tree (recursion stack).
```

#### Problem 15: Single Number

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const singleNumber = (nums) => {
    let result = 0;
    for (let i = 0; i < nums.length; i++) {
        result ^= nums[i]; // XOR operation
    }
    return result;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - We only use one variable for the result.
```

#### Problem 16: Majority Element

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const majorityElement = (nums) => {
    // Boyer-Moore Voting Algorithm
    let candidate = null;
    let count = 0;
    for (let i = 0; i < nums.length; i++) {
        if (count === 0) {
            candidate = nums[i];
            count = 1;
        } else if (nums[i] === candidate) {
            count++;
        } else {
            count--;
        }
    }
    return candidate;

    // Alternative using a Map (simpler to understand, but O(N) space)
    // const counts = new Map();
    // const n = nums.length;
    // for (const num of nums) {
    //     counts.set(num, (counts.get(num) || 0) + 1);
    //     if (counts.get(num) > n / 2) {
    //         return num;
    //     }
    // }
};

// Big-O Analysis (Boyer-Moore):
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - Constant space.
```

#### Problem 17: Contains Duplicate

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
const containsDuplicate = (nums) => {
    const seen = new Set();
    for (let i = 0; i < nums.length; i++) {
        if (seen.has(nums[i])) {
            return true;
        }
        seen.add(nums[i]);
    }
    return false;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once. Set operations (has, add) are O(1) on average.
// Space Complexity: O(N) - In the worst case (all elements are unique), the set stores N elements.
```

#### Problem 18: Missing Number

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const missingNumber = (nums) => {
    const n = nums.length;
    // Expected sum of numbers from 0 to n is n * (n + 1) / 2
    const expectedSum = n * (n + 1) / 2;

    let actualSum = 0;
    for (let i = 0; i < nums.length; i++) {
        actualSum += nums[i];
    }

    return expectedSum - actualSum;

    // Alternative using XOR:
    // let missing = n;
    // for (let i = 0; i < n; i++) {
    //     missing ^= i ^ nums[i];
    // }
    // return missing;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - Constant space.
```

#### Problem 19: Move Zeroes

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
const moveZeroes = (nums) => {
    let nonZeroIndex = 0; // Pointer for the next position to place a non-zero element

    // Move all non-zero elements to the front
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] !== 0) {
            nums[nonZeroIndex] = nums[i];
            nonZeroIndex++;
        }
    }

    // Fill the remaining positions with zeroes
    for (let i = nonZeroIndex; i < nums.length; i++) {
        nums[i] = 0;
    }
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array twice in the worst case.
// Space Complexity: O(1) - We modify the array in-place.
```

#### Problem 20: Best Time to Buy and Sell Stock

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
const maxProfit = (prices) => {
    if (prices.length < 2) {
        return 0;
    }
    let minPrice = prices[0];
    let maxProfit = 0;

    for (let i = 1; i < prices.length; i++) {
        const currentPrice = prices[i];
        const potentialProfit = currentPrice - minPrice;
        maxProfit = Math.max(maxProfit, potentialProfit);
        minPrice = Math.min(minPrice, currentPrice);
    }
    return maxProfit;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the array once.
// Space Complexity: O(1) - Constant space.
```

#### Problem 21: Valid Anagram

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
const isAnagram = (s, t) => {
    if (s.length !== t.length) {
        return false;
    }

    const charCount = new Array(26).fill(0); // Assuming lowercase English letters
    const aCharCode = "a".charCodeAt(0);

    for (let i = 0; i < s.length; i++) {
        charCount[s.charCodeAt(i) - aCharCode]++;
        charCount[t.charCodeAt(i) - aCharCode]--;
    }

    for (let count of charCount) {
        if (count !== 0) {
            return false;
        }
    }
    return true;

    // Alternative: Sort strings
    // return s.split("").sort().join("") === t.split("").sort().join("");
};

// Big-O Analysis (Char count method):
// Time Complexity: O(N) - Where N is the length of the strings. We iterate through the strings once.
// Space Complexity: O(1) - The charCount array has a fixed size (26).
// (Sort method has O(N log N) time and O(N) space for sorting strings)
```

#### Problem 22: First Unique Character in a String

```javascript
/**
 * @param {string} s
 * @return {number}
 */
const firstUniqChar = (s) => {
    const charCounts = new Map();

    // Count frequencies of each character
    for (let i = 0; i < s.length; i++) {
        charCounts.set(s[i], (charCounts.get(s[i]) || 0) + 1);
    }

    // Find the first character with a frequency of 1
    for (let i = 0; i < s.length; i++) {
        if (charCounts.get(s[i]) === 1) {
            return i;
        }
    }
    return -1;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through the string twice in the worst case.
// Space Complexity: O(K) - Where K is the number of unique characters (at most 26 for lowercase English letters, or up to N for arbitrary characters).
```

#### Problem 23: Intersection of Two Arrays II

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
const intersect = (nums1, nums2) => {
    const counts1 = new Map();
    for (const num of nums1) {
        counts1.set(num, (counts1.get(num) || 0) + 1);
    }

    const result = [];
    for (const num of nums2) {
        if (counts1.has(num) && counts1.get(num) > 0) {
            result.push(num);
            counts1.set(num, counts1.get(num) - 1);
        }
    }
    return result;

    // Alternative if arrays are sorted: Two-pointer approach (O(N+M) time, O(1) space if result array not counted)
};

// Big-O Analysis (Map method):
// Time Complexity: O(N + M) - Where N is length of nums1, M is length of nums2. We iterate through both arrays.
// Space Complexity: O(N) - In the worst case, the map stores all elements of nums1.
```

#### Problem 24: Fizz Buzz

```javascript
/**
 * @param {number} n
 * @return {string[]}
 */
const fizzBuzzSolution = (n) => {
    const answer = [];
    for (let i = 1; i <= n; i++) {
        let currentString = "";
        if (i % 3 === 0) {
            currentString += "Fizz";
        }
        if (i % 5 === 0) {
            currentString += "Buzz";
        }
        if (currentString === "") {
            answer.push(String(i));
        } else {
            answer.push(currentString);
        }
    }
    return answer;
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate from 1 to N.
// Space Complexity: O(N) - To store the answer array.
```

#### Problem 25: Reverse String

```javascript
/**
 * @param {character[]} s
 * @return {void} Do not return anything, modify s in-place instead.
 */
const reverseStringInPlace = (s) => {
    let left = 0;
    let right = s.length - 1;
    while (left < right) {
        // Swap characters
        const temp = s[left];
        s[left] = s[right];
        s[right] = temp;
        // [s[left], s[right]] = [s[right], s[left]]; // ES6 destructuring swap

        left++;
        right--;
    }
};

// Big-O Analysis:
// Time Complexity: O(N) - We iterate through half of the array.
// Space Complexity: O(1) - We modify the array in-place.
```

#### Problem 26: Power of Two

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
const isPowerOfTwo = (n) => {
    if (n <= 0) {
        return false;
    }
    // A power of two in binary has only one bit set to 1 (e.g., 1, 10, 100, 1000)
    // n & (n - 1) will be 0 if n is a power of two.
    // Example: n = 8 (1000), n-1 = 7 (0111). 1000 & 0111 = 0000
    // Example: n = 6 (0110), n-1 = 5 (0101). 0110 & 0101 = 0100 (not 0)
    return (n & (n - 1)) === 0;

    // Iterative approach:
    // while (n % 2 === 0) {
    //     n /= 2;
    // }
    // return n === 1;
};

// Big-O Analysis (Bitwise method):
// Time Complexity: O(1) - Constant time bitwise operation.
// Space Complexity: O(1) - Constant space.
```

#### Problem 27: Valid Palindrome

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
const isValidPalindrome = (s) => {
    // Convert to lowercase and remove non-alphanumeric characters
    const cleanedString = s.toLowerCase().replace(/[^a-z0-9]/g, "");

    if (cleanedString.length === 0) {
        return true;
    }

    let left = 0;
    let right = cleanedString.length - 1;

    while (left < right) {
        if (cleanedString[left] !== cleanedString[right]) {
            return false;
        }
        left++;
        right--;
    }
    return true;
};

// Big-O Analysis:
// Time Complexity: O(N) - Where N is the length of the string. Cleaning the string and the two-pointer scan take linear time.
// Space Complexity: O(N) - In the worst case, cleanedString can be of length N.
```

#### Problem 28: Linked List Cycle

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */
const hasCycle = (head) => {
    if (!head || !head.next) {
        return false;
    }

    let slow = head;
    let fast = head.next;

    while (fast && fast.next) {
        if (slow === fast) {
            return true;
        }
        slow = slow.next;
        fast = fast.next.next;
    }
    return false;

    // Alternative using a Set to store visited nodes (O(N) space)
    // const visited = new Set();
    // let current = head;
    // while (current) {
    //     if (visited.has(current)) {
    //         return true;
    //     }
    //     visited.add(current);
    //     current = current.next;
    // }
    // return false;
};

// Big-O Analysis (Floyd's Tortoise and Hare Algorithm):
// Time Complexity: O(N) - In the worst case, both pointers traverse the list.
// Space Complexity: O(1) - Constant space.
```

#### Problem 29: Convert Sorted Array to Binary Search Tree

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {number[]} nums
 * @return {TreeNode}
 */
const sortedArrayToBST = (nums) => {
    if (nums.length === 0) {
        return null;
    }

    const buildBST = (left, right) => {
        if (left > right) {
            return null;
        }

        const mid = Math.floor(left + (right - left) / 2);
        const root = new TreeNode(nums[mid]);

        root.left = buildBST(left, mid - 1);
        root.right = buildBST(mid + 1, right);

        return root;
    };

    return buildBST(0, nums.length - 1);
};

// Big-O Analysis:
// Time Complexity: O(N) - We visit each element of the array once to create a tree node.
// Space Complexity: O(log N) - For a balanced tree, the recursion stack depth is O(log N). In the worst case (skewed tree, though this algorithm produces balanced), it could be O(N).
```

#### Problem 30: Implement strStr()

```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
const strStr = (haystack, needle) => {
    if (needle.length === 0) {
        return 0;
    }
    if (haystack.length < needle.length) {
        return -1;
    }

    for (let i = 0; i <= haystack.length - needle.length; i++) {
        let found = true;
        for (let j = 0; j < needle.length; j++) {
            if (haystack[i + j] !== needle[j]) {
                found = false;
                break;
            }
        }
        if (found) {
            return i;
        }
    }
    return -1;

    // Built-in method (usually not allowed for this problem type in interviews)
    // return haystack.indexOf(needle);
};

// Big-O Analysis (Naive approach):
// Time Complexity: O((N-M+1) * M) which is roughly O(N*M) in the worst case - Where N is length of haystack, M is length of needle.
// Space Complexity: O(1) - Constant space.
// (More advanced algorithms like KMP can achieve O(N+M) time complexity.)
```



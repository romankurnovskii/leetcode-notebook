Array / String
1768. Merge Strings Alternately / Easy
1071. Greatest Common Divisor of Strings  (Easy)
1431. Kids With the Greatest Number of Candies (Easy)
605. Can Place Flowers (Easy)
345. Reverse Vowels of a String (Easy)
151. Reverse Words in a String (Medium)
238. Product of Array Except Self (Medium)
334. Increasing Triplet Subsequence (Medium)
443. String Compression (Medium)
Two Pointers
283. Move Zeroes (Easy)
392. Is Subsequence (Easy)
11. Container With Most Water (Medium)
1679. Max Number of K-Sum Pairs (Medium)
Sliding Window
643. Maximum Average Subarray I (Easy)
644. 
645.  Maximum Number of Vowels in a Substring of Given Length (Medium)
646.  Max Consecutive Ones III (Medium)
647.  Longest Subarray of 1's After Deleting One Element (Medium)
Prefix Sum
1.    Find the Highest Altitude (Easy)
2.    Find the Middle Index in Array (Easy)
Hash Map / Set
1.    Find the Difference of Two Arrays (Easy)
2.    Unique Number of Occurrences (Easy)
3.    Determine if Two Strings Are Close (Medium)
4.    Equal Row and Column Pairs (Medium)
Stack
1.    Removing Stars From a String (Medium)
2.   Asteroid Collision (Medium)
3.   Decode String (Medium)
Summary
Queue
1.   Number of Recent Calls (Easy)
2.   Dota2 Senate (Medium)
Linked List
1.   Reverse Linked List (Easy)
2.    Delete the Middle Node of a Linked List (Medium)
3.   Odd Even Linked List (Medium)
4.    Maximum Twin Sum of a Linked List (Medium)
Binary Tree - DFS
Iteration
Aggregation
1.   Maximum Depth of Binary Tree (Easy)
2.   Leaf-Similar Trees (Easy)
3.    Count Good Nodes in Binary Tree (Medium)
4.   Path Sum III (Medium)
5.    Longest ZigZag Path in a Binary Tree (Medium)
6.   Lowest Common Ancestor of a Binary Tree (Medium)
Binary Tree - BFS
1.   Binary Tree Right Side View (Medium)
2.    Maximum Level Sum of a Binary Tree (Medium)
Binary Search Tree
1.   Search in a Binary Search Tree (Easy)
2.   Delete Node in a BST (Medium)
Graphs
Graphs - DFS
1.    Find if Path Exists in Graph (Easy)
2.   Keys and Rooms (Medium)
3.   Number of Provinces (Medium)
4.    Reorder Routes to Make All Paths Lead to the City Zero (Medium)
5.   Evaluate Division (Medium)
Graphs - BFS
Pattern for 2D Array Problems
1.    Nearest Exit from Entrance in Maze (Medium)
2.   Rotting Oranges (Medium)
Heap / Priority Queue
1.    Minimum Number Game (Easy)
2.   Kth Largest Element in an Array (Medium)
3.    Smallest Number in Infinite Set (Medium)
4.    Maximum Subsequence Score (Medium)
5.    Total Cost to Hire K Workers (Medium)
Binary Search
1.   Guess Number Higher or Lower (Easy)
2.    Successful Pairs of Spells and Potions (Medium)
3.   Find Peak Element (Medium)
4.   Koko Eating Bananas (Medium)
Backtracking
1.  Letter Combinations of a Phone Number (Medium)
2.   Combination Sum III (Medium)
DP - 1D
1.    N-th Tribonacci Number (Easy)
2.   Min Cost Climbing Stairs (Easy)
3.   House Robber (Medium)
4.   Domino and Tromino Tiling (Medium)
Tips and Patterns
DP - Multidimensional
1.  Unique Paths (Medium)
2.    Longest Common Subsequence (Medium)
3.   Best Time to Buy and Sell Stock (Easy)
4.   Best Time to Buy and Sell Stock with Transaction Fee (Medium)
5.  Edit Distance (Medium)
Bit Manipulation
1.   Counting Bits (Easy)
2.   Single Number (Easy)
3.    Minimum Flips to Make a OR b Equal to c (Medium)
Trie
1.   Implement Trie (Prefix Tree) (Medium)
2.    Search Suggestions System (Medium)
Intervals
1.   Non-overlapping Intervals (Medium)
2.   Minimum Number of Arrows to Burst Balloons (Medium)
Monotonic Stack
1.   Daily Temperatures (Medium)
2.   Online Stock Span (Medium)

====
# Array / String

## 1768. Merge Strings Alternately / Easy

https://leetcode.com/problems/merge-strings-alternately

You are given two strings, `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with word1. If a string is longer than the other, append the additional letters onto the end of the merged string.

Example 1:
```
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
```

Example 2:
```
Input: word1 = "ab", word2 = "pqrs"
Output: "apbqrs"
```

Constraints:
```
- 1 <= word1.length, word2.length <= 100
- word1 and word2 consist of lowercase English letters.
```

> **Hint:**  
> In most cases, LeetCode Easy problems have a straightforward solution that can be derived from the description or the examples provided.

### Step by Step Explanation (Bill Nye style!)

Hey science friends! Imagine you have two strings, like two lines of colored beads. You want to make a new necklace by picking one bead from the first string, then one from the second, and keep going! If one string runs out, just add the rest from the other.

We use two pointers to keep track of our position in each string, because this lets us alternate letters easily and ensures we don't miss any. By appending the remaining part of the longer string at the end, we make sure no letters are left out—this is important for correctness, especially when the strings are different lengths.

**Example:**  
word1 = "ab", word2 = "pqrs"  
- Take 'a' and 'p' → "ap"
- Take 'b' and 'q' → "apbq"
- word1 is done, so add the rest of word2: "rs"
- Final answer: "apbqrs"

We use a list to collect the letters because lists in Python are efficient for appending, and then join them at the end for the final string.

### Python Solution

```python
def mergeAlternately(word1, word2):
    res = []
    i = 0
    while i < len(word1) and i < len(word2):
        res.append(word1[i])
        res.append(word2[i])
        i += 1
    res.append(word1[i:])
    res.append(word2[i:])
    return ''.join(res)
```

====

## 1071. Greatest Common Divisor of Strings (Easy)

https://leetcode.com/problems/greatest-common-divisor-of-strings

Given two strings `str1` and `str2`, return the largest string that divides both of them. A string `x` divides string `y` if `y` is made up of one or more copies of `x`.

Example 1:
```
Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"
```

Example 2:
```
Input: str1 = "ABABAB", str2 = "ABAB"
Output: "AB"
```

Constraints:
```
- 1 <= str1.length, str2.length <= 1000
- str1 and str2 consist of English uppercase letters.
```

> **Hint:**  
> Try to find the greatest common divisor (GCD) of the lengths of the two strings, and check if the substring of that length divides both strings.

### Step by Step Explanation (Sal Khan style!)

Alright, let's break this down step by step!  
Suppose you have two strings, and you want to find the biggest chunk that can be repeated to make both strings. Think of it like finding the biggest building block that fits perfectly into both.

First, we check if both strings can be built by repeating the same substring, because if they can't, there's no common divisor string. We do this by comparing `str1 + str2` and `str2 + str1`—if they're not the same, it means the order of repetition doesn't match, so no common divisor exists. This check is important because it quickly rules out impossible cases, saving us time and effort.

Next, we use the greatest common divisor (GCD) of the lengths of the two strings. We do this because the largest possible repeating substring must fit evenly into both strings, and the GCD gives us the largest length that divides both. This is a mathematical shortcut that ensures we only check the most promising candidate.

Finally, we take the substring of that length from the start of either string and check if repeating it forms both strings. This works because if a substring can build both strings by repetition, it must be the answer.

### Python Solution

```python
def gcdOfStrings(str1, str2):
    def gcd(a, b):
        while b:
            a, b = b, a % b
        return a
    if str1 + str2 != str2 + str1:
        return ""
    length = gcd(len(str1), len(str2))
    return str1[:length]
```

====

## 1431. Kids With the Greatest Number of Candies (Easy)

https://leetcode.com/problems/kids-with-the-greatest-number-of-candies

Given the array `candies` and the integer `extraCandies`, where `candies[i]` represents the number of candies that the i-th kid has, for each kid check if giving them all the extraCandies would make them have the greatest number of candies among all the kids. Return a boolean list.

Example:
```
Input: candies = [2,3,5,1,3], extraCandies = 3
Output: [true,true,true,false,true]
```

Constraints:
```
- 2 <= candies.length <= 100
- 1 <= candies[i] <= 100
- 1 <= extraCandies <= 50
```

> **Hint:**  
> For each kid, check if their candies plus extraCandies is at least as much as the current maximum.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
First, we want to know the highest number of candies any kid currently has. This is important because we need a reference point to see if giving extra candies to a kid will make them "the greatest."

For each kid, we add the extraCandies to their current amount. We do this because we want to see if, after the bonus, they can reach or beat the current maximum. If they do, we mark them as `True` in our answer list; otherwise, `False`.

This approach is efficient because we only need to find the maximum once, and then just compare each kid's total to it. This saves us from recalculating the maximum for every kid, making our solution faster and cleaner.

### Python Solution

```python
def kidsWithCandies(candies, extraCandies):
    max_candies = max(candies)  # Find the current maximum
    return [(c + extraCandies) >= max_candies for c in candies]
```

====

## 605. Can Place Flowers (Easy)

https://leetcode.com/problems/can-place-flowers

You have a flowerbed (list of plots) containing 0s and 1s, where 0 means empty and 1 means not empty. Flowers cannot be planted in adjacent plots. Given the flowerbed and a number n, return if n new flowers can be planted without violating the rule.

Example:
```
Input: flowerbed = [1,0,0,0,1], n = 1
Output: true
```

Constraints:
```
- 1 <= flowerbed.length <= 2 * 10^4
- flowerbed[i] is 0 or 1.
- There are no two adjacent flowers in the flowerbed.
```

> **Hint:**  
> Check each empty plot and see if both neighbors are empty (or out of bounds).

### Step by Step Explanation (Bill Nye style!)

Let's imagine the flowerbed as a row of garden plots. We want to plant new flowers, but we can't put them right next to each other. So, for each empty spot, we check the spots to the left and right. If both are empty (or if we're at the edge), we can plant a flower there.

We do this because it's the only way to guarantee we never break the "no neighbors" rule. By checking each spot, we make sure we don't miss any possible planting locations.

We keep a count of how many flowers we've planted. If we reach the required number, we can stop early and return `True`. This helps us avoid unnecessary work and makes our solution efficient.

### Python Solution

```python
def canPlaceFlowers(flowerbed, n):
    count = 0
    for i in range(len(flowerbed)):
        if flowerbed[i] == 0:
            empty_left = (i == 0) or (flowerbed[i-1] == 0)
            empty_right = (i == len(flowerbed)-1) or (flowerbed[i+1] == 0)
            if empty_left and empty_right:
                flowerbed[i] = 1
                count += 1
                if count >= n:
                    return True
    return count >= n
```

====

## 345. Reverse Vowels of a String (Easy)

https://leetcode.com/problems/reverse-vowels-of-a-string

Given a string, reverse only the vowels in the string and return it.

Example:
```
Input: s = "hello"
Output: "holle"
```

Constraints:
```
- 1 <= s.length <= 3 * 10^5
- s consists of printable ASCII characters.
```

> **Hint:**  
> Use two pointers to find vowels from both ends and swap them.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to reverse only the vowels in the string. To do this efficiently, we use two pointers: one starting from the left, one from the right. We move each pointer until it finds a vowel. When both pointers are at vowels, we swap them.

We do this because it lets us reverse the vowels in-place, without affecting the other characters. Using two pointers is efficient and avoids unnecessary work, especially for long strings.

We keep moving the pointers toward each other, swapping vowels as we go, until they meet in the middle. This ensures every vowel is swapped exactly once, making the solution both correct and efficient.

### Python Solution

```python
def reverseVowels(s):
    vowels = set('aeiouAEIOU')
    s = list(s)
    left, right = 0, len(s) - 1
    while left < right:
        while left < right and s[left] not in vowels:
            left += 1
        while left < right and s[right] not in vowels:
            right -= 1
        if left < right:
            s[left], s[right] = s[right], s[left]
            left += 1
            right -= 1
    return ''.join(s)
```

====

## 151. Reverse Words in a String (Medium)

https://leetcode.com/problems/reverse-words-in-a-string

Given an input string, reverse the order of the words.

Example:
```
Input: s = "the sky is blue"
Output: "blue is sky the"
```

Constraints:
```
- 1 <= s.length <= 10^4
- s contains English letters and spaces.
- There is at least one word in s.
```

> **Hint:**  
> Split the string into words, reverse the list, and join them back.

### Step by Step Explanation (Bill Nye style!)

Let's think of the sentence as a row of blocks, each block being a word. To reverse the sentence, we break it into blocks, flip the order, and stick them back together.

We do this because splitting and reversing is much easier than trying to move words around in the original string. Python's split and join functions make this super efficient, and by removing extra spaces, we make sure the result is clean and matches the requirements.

This approach is both simple and effective, making it a great example of using built-in tools to solve a problem quickly.

### Python Solution

```python
def reverseWords(s):
    words = s.strip().split()
    return ' '.join(reversed(words))
```

====

## 238. Product of Array Except Self (Medium)

https://leetcode.com/problems/product-of-array-except-self

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

You must write an algorithm that runs in O(n) time and without using the division operation.

Example:
```
Input: nums = [1,2,3,4]
Output: [24,12,8,6]
```

Constraints:
```
- 2 <= nums.length <= 10^5
- -30 <= nums[i] <= 30
- The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.
```

> **Hint:**  
> Use two passes: one to calculate products to the left of each index, and one for the right.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to find the product of all numbers except the one at each position. If we used division, we could just multiply everything and divide by nums[i], but the problem says no division!

So, we use two passes. First, we go from left to right, building up the product of all numbers to the left of each index. We do this because it lets us know, for each position, what the product is before that number.

Then, we go from right to left, multiplying each answer by the product of all numbers to the right. This way, each answer[i] ends up being the product of everything except nums[i].

This approach is efficient because it only needs two passes and uses O(1) extra space (not counting the output array), making it perfect for large arrays.

### Python Solution

```python
def productExceptSelf(nums):
    n = len(nums)
    answer = [1] * n
    left = 1
    for i in range(n):
        answer[i] = left
        left *= nums[i]
    right = 1
    for i in range(n-1, -1, -1):
        answer[i] *= right
        right *= nums[i]
    return answer
```

====

## 334. Increasing Triplet Subsequence (Medium)

https://leetcode.com/problems/increasing-triplet-subsequence

Given an integer array nums, return true if there exists a triple of indices (i, j, k) such that i < j < k and nums[i] < nums[j] < nums[k]. If no such indices exist, return false.

Example:
```
Input: nums = [1,2,3,4,5]
Output: true
```

Constraints:
```
- 1 <= nums.length <= 5 * 10^5
- -2^31 <= nums[i] <= 2^31 - 1
```

> **Hint:**  
> Track the smallest and second smallest values as you iterate.

### Step by Step Explanation (Bill Nye style!)

Let's imagine you're looking for three numbers in order, each bigger than the last. We keep track of the smallest number we've seen so far, and then the next smallest after that. If we find a number bigger than both, we know we have a triplet!

We do this because it's much faster than checking every possible combination. By updating our two smallest values as we go, we make sure we're always ready to spot a valid triplet as soon as it appears.

This approach is efficient and uses only constant extra space, making it perfect for large arrays.

### Python Solution

```python
def increasingTriplet(nums):
    first = second = float('inf')
    for n in nums:
        if n <= first:
            first = n
        elif n <= second:
            second = n
        else:
            return True
    return False
```

====

## 443. String Compression (Medium)

https://leetcode.com/problems/string-compression

Given an array of characters chars, compress it in-place. The length after compression must always be less than or equal to the original array.

Example:
```
Input: chars = ["a","a","b","b","c","c","c"]
Output: Return 6, and the first 6 characters of the input array should be: ["a","2","b","2","c","3"]
```

Constraints:
```
- 1 <= chars.length <= 2000
- chars[i] is a lowercase English letter, uppercase English letter, digit, or symbol.
```

> **Hint:**  
> Use two pointers: one for reading, one for writing.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to compress the string by replacing sequences of the same character with that character followed by the count. We use two pointers: one to read through the array, and one to write the compressed result.

We do this because it lets us modify the array in-place, which saves memory and meets the problem's requirements. By counting consecutive characters and writing the count only when needed, we keep the result as short as possible.

This approach is efficient and avoids creating extra arrays, making it suitable for large inputs.

### Python Solution

```python
def compress(chars):
    write = 0
    read = 0
    n = len(chars)
    while read < n:
        char = chars[read]
        count = 0
        while read < n and chars[read] == char:
            read += 1
            count += 1
        chars[write] = char
        write += 1
        if count > 1:
            for c in str(count):
                chars[write] = c
                write += 1
    return write
```

====

## 643. Maximum Average Subarray I (Easy)

https://leetcode.com/problems/maximum-average-subarray-i

Given an array consisting of n integers, find the contiguous subarray of length k that has the maximum average value. Return this value.

Example:
```
Input: nums = [1,12,-5,-6,50,3], k = 4
Output: 12.75
Explanation: Maximum average is (12-5-6+50)/4 = 51/4 = 12.75
```

Constraints:
```
- 1 <= k <= n <= 10^5
- -10^4 <= nums[i] <= 10^4
```

> **Hint:**  
> Use a sliding window to keep track of the sum of k elements.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the array as a long row of numbers. We want to find a group of k numbers in a row that, when averaged, gives us the biggest value. Instead of checking every possible group from scratch, we use a sliding window: we add the next number and remove the first number from the previous group.

We do this because it saves us from recalculating the sum for every window, making our solution much faster, especially for large arrays. By updating the sum as we slide the window, we always know the current total for the k numbers we're looking at.

This approach is efficient and perfect for problems where you need to look at all subarrays of a fixed size.

### Python Solution

```python
def findMaxAverage(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum
    for i in range(k, len(nums)):
        window_sum += nums[i] - nums[i - k]
        max_sum = max(max_sum, window_sum)
    return max_sum / k
```

====

## 1456. Maximum Number of Vowels in a Substring of Given Length (Medium)

https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length

Given a string s and an integer k, return the maximum number of vowel letters in any substring of s with length k.

Example:
```
Input: s = "abciiidef", k = 3
Output: 3
Explanation: The substring "iii" contains 3 vowels.
```

Constraints:
```
- 1 <= s.length <= 10^5
- s consists of lowercase English letters.
- 1 <= k <= s.length
```

> **Hint:**  
> Use a sliding window to count vowels in each substring of length k.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to find the most vowels in any substring of length k. To do this efficiently, we use a sliding window: we count the vowels in the first window, then as we move the window, we subtract the letter that leaves and add the new letter that enters.

We do this because it lets us update our count in constant time, instead of recounting every window from scratch. This makes our solution much faster, especially for long strings.

By always keeping track of the current number of vowels, we can quickly find the maximum as we slide the window across the string.

### Python Solution

```python
def maxVowels(s, k):
    vowels = set('aeiou')
    count = max_count = 0
    for i in range(len(s)):
        if s[i] in vowels:
            count += 1
        if i >= k and s[i - k] in vowels:
            count -= 1
        max_count = max(max_count, count)
    return max_count
```

====

## 1004. Max Consecutive Ones III (Medium)

https://leetcode.com/problems/max-consecutive-ones-iii

Given a binary array nums and an integer k, return the maximum number of consecutive 1's in the array if you can flip at most k 0's.

Example:
```
Input: nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
Output: 6
Explanation: [1,1,1,0,0,1,1,1,1,1,1] -> flip two zeros
```

Constraints:
```
- 1 <= nums.length <= 10^5
- nums[i] is either 0 or 1.
- 0 <= k <= nums.length
```

> **Hint:**  
> Use a sliding window to keep track of the number of zeros in the current window.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the array as a row of light switches, where 1 is on and 0 is off. We want to find the longest stretch of lights that can be on, if we're allowed to flip up to k switches from off to on.

We use a sliding window to keep track of the current stretch. Every time we add a new number, we check if we've flipped more than k zeros. If so, we move the left end of the window forward until we're back within our limit.

We do this because it lets us efficiently find the longest possible stretch without checking every possible subarray. By only moving the window when needed, we keep our solution fast and memory-efficient.

### Python Solution

```python
def longestOnes(nums, k):
    left = 0
    zeros = 0
    max_len = 0
    for right in range(len(nums)):
        if nums[right] == 0:
            zeros += 1
        while zeros > k:
            if nums[left] == 0:
                zeros -= 1
            left += 1
        max_len = max(max_len, right - left + 1)
    return max_len
```

====

## 1493. Longest Subarray of 1's After Deleting One Element (Medium)

https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element

Given a binary array nums, you should delete one element from it. Return the size of the longest non-empty subarray containing only 1's in the resulting array.

Example:
```
Input: nums = [1,1,0,1]
Output: 3
Explanation: After deleting the zero at index 2, the array is [1,1,1].
```

Constraints:
```
- 1 <= nums.length <= 10^5
- nums[i] is either 0 or 1.
```

> **Hint:**  
> Use a sliding window to keep at most one zero in the window.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want the longest run of 1's after deleting one element. That means we can have at most one zero in our current window, since deleting it would leave only 1's.

We use a sliding window to keep track of the current sequence. Every time we have more than one zero, we move the left end of the window forward until we're back to at most one zero.

We do this because it lets us efficiently find the longest possible sequence without checking every possible subarray. By only moving the window when needed, we keep our solution fast and memory-efficient, especially for large arrays.

### Python Solution

```python
def longestSubarray(nums):
    left = 0
    zeros = 0
    max_len = 0
    for right in range(len(nums)):
        if nums[right] == 0:
            zeros += 1
        while zeros > 1:
            if nums[left] == 0:
                zeros -= 1
            left += 1
        max_len = max(max_len, right - left)
    return max_len
```

====

## 1732. Find the Highest Altitude (Easy)

https://leetcode.com/problems/find-the-highest-altitude

There is a biker going on a road trip. The road trip consists of n + 1 points at different altitudes. You are given an integer array gain of length n where gain[i] is the net gain in altitude between points i and i + 1. Return the highest altitude of a point.

Example:
```
Input: gain = [-5,1,5,0,-7]
Output: 1
Explanation: The altitudes are [0,-5,-4,1,1,-6]. The highest is 1.
```

Constraints:
```
- n == gain.length
- 1 <= n <= 100
- -100 <= gain[i] <= 100
```

> **Hint:**  
> Track the running sum and keep the maximum seen so far.

### Step by Step Explanation (Bill Nye style!)

Let's imagine you're on a bike ride, and you start at sea level (altitude 0). Each number in the gain array tells you how much you go up or down at each step. We keep track of our current altitude as we go, and always remember the highest point we've reached so far.

We do this because it lets us find the maximum altitude in a single pass, without having to store all the altitudes. By updating the highest altitude as we go, we make our solution efficient and easy to understand.

### Python Solution

```python
def largestAltitude(gain):
    altitude = 0
    max_altitude = 0
    for g in gain:
        altitude += g
        max_altitude = max(max_altitude, altitude)
    return max_altitude
```

====

## 1991. Find the Middle Index in Array (Easy)

https://leetcode.com/problems/find-the-middle-index-in-array

Given a 0-indexed integer array nums, find the leftmost middleIndex such that the sum of the numbers to the left of middleIndex is equal to the sum of the numbers to the right of middleIndex. Return -1 if no such index exists.

Example:
```
Input: nums = [2,3,-1,8,4]
Output: 3
Explanation: The sum of the numbers to the left of index 3 is 4 (2+3-1), and to the right is also 4 (4).
```

Constraints:
```
- 1 <= nums.length <= 100
- -1000 <= nums[i] <= 1000
```

> **Hint:**  
> Use prefix sums to keep track of the left and right sums efficiently.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to find an index where the sum of all numbers to the left equals the sum to the right. We use a running total (prefix sum) as we move through the array, so we always know the sum to the left. The right sum can be found by subtracting the left sum and the current number from the total sum.

We do this because it lets us check each index in constant time, making our solution efficient. By using prefix sums, we avoid recalculating sums for every index, which would be much slower.

### Python Solution

```python
def findMiddleIndex(nums):
    total = sum(nums)
    left_sum = 0
    for i, num in enumerate(nums):
        if left_sum == total - left_sum - num:
            return i
        left_sum += num
    return -1
```

====

## 2215. Find the Difference of Two Arrays (Easy)

https://leetcode.com/problems/find-the-difference-of-two-arrays

Given two 0-indexed integer arrays nums1 and nums2, return a list answer of size 2 where:
- answer[0] is a list of all distinct integers in nums1 which are not present in nums2.
- answer[1] is a list of all distinct integers in nums2 which are not present in nums1.

Example:
```
Input: nums1 = [1,2,3], nums2 = [2,4,6]
Output: [[1,3],[4,6]]
```

Constraints:
```
- 1 <= nums1.length, nums2.length <= 1000
- -1000 <= nums1[i], nums2[i] <= 1000
```

> **Hint:**  
> Use sets to efficiently find unique elements in each array.

### Step by Step Explanation (Bill Nye style!)

Let's imagine you have two boxes of colored marbles (numbers). You want to find out which colors are only in the first box and which are only in the second. We use sets to quickly check for unique marbles in each box.

We do this because sets make it easy and fast to find differences—checking if something is in a set is much quicker than searching through a list. By converting the lists to sets, we can use set operations to get the answer efficiently.

### Python Solution

```python
def findDifference(nums1, nums2):
    set1, set2 = set(nums1), set(nums2)
    return [list(set1 - set2), list(set2 - set1)]
```

====

## 1207. Unique Number of Occurrences (Easy)

https://leetcode.com/problems/unique-number-of-occurrences

Given an array of integers arr, return true if the number of occurrences of each value in the array is unique, or false otherwise.

Example:
```
Input: arr = [1,2,2,1,1,3]
Output: true
Explanation: The value 1 occurs 3 times, 2 occurs 2 times, and 3 occurs 1 time. All counts are unique.
```

Constraints:
```
- 1 <= arr.length <= 1000
- -1000 <= arr[i] <= 1000
```

> **Hint:**  
> Use a dictionary to count occurrences, then check if the counts are unique using a set.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to know if every number in the array appears a unique number of times. First, we count how many times each number appears using a dictionary. Then, we check if all those counts are different by putting them in a set.

We do this because using a dictionary makes counting fast and easy, and a set lets us quickly check for duplicates among the counts. This approach is efficient and avoids unnecessary loops.

### Python Solution

```python
def uniqueOccurrences(arr):
    from collections import Counter
    count = Counter(arr)
    return len(set(count.values())) == len(count)
```

====

## 1657. Determine if Two Strings Are Close (Medium)

https://leetcode.com/problems/determine-if-two-strings-are-close

Two strings are considered close if you can attain one from the other using the following operations:
1. Swap any two existing characters.
2. Transform every occurrence of one existing character into another existing character, and do the same with the other character.

You can use the operations any number of times.

Return true if and only if s1 and s2 are close.

Example:
```
Input: word1 = "abc", word2 = "bca"
Output: true
```

Constraints:
```
- 1 <= word1.length, word2.length <= 10^5
- word1 and word2 consist of only lowercase English letters.
```

> **Hint:**  
> Check if both strings have the same set of characters and the same frequency counts (in any order).

### Step by Step Explanation (Bill Nye style!)

Let's imagine you have two sets of colored blocks (letters). You can swap blocks or change all blocks of one color to another color, as long as you swap the other way too. To see if you can make one set look like the other, first check if both sets have the same colors, and then check if the counts of each color can be rearranged to match.

We do this because if the sets of letters are different, you can never make them match. And if the counts of each letter can't be rearranged, you can't match the frequencies either. By checking these two things, we can quickly decide if the strings are close.

### Python Solution

```python
def closeStrings(word1, word2):
    from collections import Counter
    c1, c2 = Counter(word1), Counter(word2)
    return set(c1.keys()) == set(c2.keys()) and sorted(c1.values()) == sorted(c2.values())
```

====

## 2352. Equal Row and Column Pairs (Medium)

https://leetcode.com/problems/equal-row-and-column-pairs

Given a 0-indexed n x n integer matrix grid, return the number of pairs (ri, cj) such that the row ri and column cj are equal.

Example:
```
Input: grid = [[3,2,1],[1,7,6],[2,7,7]]
Output: 1
Explanation: There is 1 equal row and column pair: (row 1, column 1).
```

Constraints:
```
- n == grid.length == grid[i].length
- 1 <= n <= 200
- 1 <= grid[i][j] <= 10^5
```

> **Hint:**  
> Use a dictionary to count the frequency of each row, then compare with columns.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to count how many times a row in the matrix matches a column. First, we count how many times each row appears using a dictionary. Then, for each column, we check if it matches any row and add up the counts.

We do this because using a dictionary makes it fast to count and compare rows and columns, and avoids checking every possible pair directly, which would be much slower for large matrices.

### Python Solution

```python
def equalPairs(grid):
    from collections import Counter
    n = len(grid)
    row_counts = Counter(tuple(row) for row in grid)
    count = 0
    for col in zip(*grid):
        count += row_counts[tuple(col)]
    return count
```

====

## 2390. Removing Stars From a String (Medium)

https://leetcode.com/problems/removing-stars-from-a-string

You are given a string s, which contains stars '*'. When you see a star, remove the closest non-star character to its left, as well as the star itself. Return the resulting string after all stars have been processed.

Example:
```
Input: s = "leet**cod*e"
Output: "lecoe"
```

Constraints:
```
- 1 <= s.length <= 10^5
- s consists of lowercase English letters and stars '*'.
- The operation is always possible.
```

> **Hint:**  
> Use a stack to process the string efficiently.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the string as a row of blocks, and every time you see a star, you knock out the block just before it and the star itself. We use a stack to keep track of the blocks, so when we see a star, we can quickly remove the last block we added.

We do this because a stack lets us efficiently remove the most recent character, which matches the rule of removing the closest non-star to the left. This approach is both fast and easy to implement, especially for long strings.

### Python Solution

```python
def removeStars(s):
    stack = []
    for c in s:
        if c == '*':
            if stack:
                stack.pop()
        else:
            stack.append(c)
    return ''.join(stack)
```

====

## 735. Asteroid Collision (Medium)

https://leetcode.com/problems/asteroid-collision

We are given an array asteroids of integers representing asteroids in a row. For each asteroid, the absolute value represents its size, and the sign represents its direction (positive means right, negative means left). Each asteroid moves at the same speed. Find out the state of the asteroids after all collisions.

Example:
```
Input: asteroids = [5,10,-5]
Output: [5,10]
Explanation: The 10 and -5 collide resulting in 10. The 5 and 10 never collide.
```

Constraints:
```
- 2 <= asteroids.length <= 10^4
- -1000 <= asteroids[i] <= 1000
- asteroids[i] != 0
```

> **Hint:**  
> Use a stack to simulate the collisions.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to simulate the collisions between asteroids. We use a stack to keep track of the asteroids moving to the right. When we see a left-moving asteroid, we check for collisions with the stack's top. If the left-moving asteroid is bigger, it destroys the right-moving one; if it's smaller, it gets destroyed; if they're equal, both disappear.

We do this because a stack lets us efficiently manage the sequence of possible collisions, always comparing the current asteroid with the last right-moving one. This approach is both intuitive and efficient for simulating the process.

### Python Solution

```python
def asteroidCollision(asteroids):
    stack = []
    for a in asteroids:
        while stack and a < 0 < stack[-1]:
            if stack[-1] < -a:
                stack.pop()
                continue
            elif stack[-1] == -a:
                stack.pop()
            break
        else:
            stack.append(a)
    return stack
```

====

## 394. Decode String (Medium)

https://leetcode.com/problems/decode-string

Given an encoded string, return its decoded string. The encoding rule is: k[encoded_string], where the encoded_string inside the square brackets is repeated exactly k times. You may assume that the input string is always valid.

Example:
```
Input: s = "3[a]2[bc]"
Output: "aaabcbc"
```

Constraints:
```
- 1 <= s.length <= 30
- s consists of digits, letters, and square brackets '[]'.
- s is guaranteed to be a valid input.
```

> **Hint:**  
> Use a stack to keep track of numbers and strings as you process the input.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the string as a set of instructions for a robot: every time it sees a number and a bracket, it knows to repeat what's inside the brackets that many times. We use a stack to keep track of the current string and the repeat count. When we see a closing bracket, we pop from the stack and build the decoded string.

We do this because a stack lets us handle nested encodings easily, always working on the innermost part first. This approach is both intuitive and efficient for decoding these kinds of strings.

### Python Solution

```python
def decodeString(s):
    stack = []
    curr_num = 0
    curr_str = ''
    for c in s:
        if c.isdigit():
            curr_num = curr_num * 10 + int(c)
        elif c == '[':
            stack.append((curr_str, curr_num))
            curr_str = ''
            curr_num = 0
        elif c == ']':
            last_str, num = stack.pop()
            curr_str = last_str + num * curr_str
        else:
            curr_str += c
    return curr_str
```

====

## 933. Number of Recent Calls (Easy)

https://leetcode.com/problems/number-of-recent-calls

You have a RecentCounter class that counts the number of recent requests within a certain time window. Implement the RecentCounter class:
- RecentCounter() Initializes the counter with zero recent requests.
- int ping(int t) Adds a new request at time t (measured in milliseconds), and returns the number of requests that have happened in the past 3000 milliseconds (including the new request).

Example:
```
Input: ["RecentCounter", "ping", "ping", "ping", "ping"]
        [[], [1], [100], [3001], [3002]]
Output: [null, 1, 2, 3, 3]
```

Constraints:
```
- 1 <= t <= 10^9
- Each test case will call ping with strictly increasing values of t.
- At most 10^4 calls will be made to ping.
```

> **Hint:**  
> Use a queue to keep track of the times of recent requests.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to count how many requests happened in the last 3000 milliseconds. We use a queue to keep track of the times of each request. Every time we get a new request, we add it to the queue and remove any requests that are too old.

We do this because a queue lets us efficiently add new requests and remove old ones from the front. This approach is both simple and efficient for problems where you need to keep track of a moving window of events.

### Python Solution

```python
from collections import deque
class RecentCounter:
    def __init__(self):
        self.q = deque()
    def ping(self, t):
        self.q.append(t)
        while self.q[0] < t - 3000:
            self.q.popleft()
        return len(self.q)
```

====

## 649. Dota2 Senate (Medium)

https://leetcode.com/problems/dota2-senate

In the world of Dota2, there are two parties: the Radiant and the Dire. The senate consists of senators from both parties. Each round, each senator can ban one member of the opposite party. The first party to have all their senators banned loses. Given a string representing the senate, return which party will win.

Example:
```
Input: senate = "RDD"
Output: "Dire"
```

Constraints:
```
- 1 <= senate.length <= 10^4
- senate[i] is either 'R' or 'D'.
```

> **Hint:**  
> Use two queues to simulate the banning process for each party.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the senate as two lines of people, one for each party. Each time someone gets a turn, they can ban a member of the other party. We use two queues to keep track of the positions of each party's senators. Each round, the senator with the earlier position acts first, and then goes to the end of their queue with an updated position.

We do this because queues let us efficiently manage the order of turns and simulate the process round by round. This approach is both intuitive and efficient for simulating the game.

### Python Solution

```python
from collections import deque

def predictPartyVictory(senate):
    n = len(senate)
    radiant = deque()
    dire = deque()
    for i, s in enumerate(senate):
        if s == 'R':
            radiant.append(i)
        else:
            dire.append(i)
    while radiant and dire:
        r = radiant.popleft()
        d = dire.popleft()
        if r < d:
            radiant.append(r + n)
        else:
            dire.append(d + n)
    return "Radiant" if radiant else "Dire"
```

====

## 206. Reverse Linked List (Easy)

https://leetcode.com/problems/reverse-linked-list

Given the head of a singly linked list, reverse the list, and return the reversed list.

Example:
```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```

Constraints:
```
- The number of nodes in the list is the range [0, 5000].
- -5000 <= Node.val <= 5000
```

> **Hint:**  
> Use three pointers to reverse the links one by one.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to reverse the direction of the links in the list. We use three pointers: one for the current node, one for the previous node, and one for the next node. At each step, we reverse the link, then move all pointers forward.

We do this because reversing the links one by one is the most efficient way to reverse a linked list in-place, without using extra memory. This approach is both simple and effective for linked list problems.

### Python Solution

```python
def reverseList(head):
    prev = None
    curr = head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev
```

====

## 2095. Delete the Middle Node of a Linked List (Medium)

https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list

Given the head of a linked list, delete the middle node, and return the head of the modified list. If there are two middle nodes, delete the second middle node.

Example:
```
Input: head = [1,3,4,7,1,2,6]
Output: [1,3,4,1,2,6]
```

Constraints:
```
- The number of nodes in the list is in the range [1, 10^5].
- 1 <= Node.val <= 10^5
```

> **Hint:**  
> Use two pointers (slow and fast) to find the middle node efficiently.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the linked list as a line of people. To find the middle, we send one person (the slow pointer) walking one step at a time, and another (the fast pointer) walking two steps at a time. When the fast pointer reaches the end, the slow pointer is at the middle. We then remove the middle person from the line.

We do this because using two pointers lets us find the middle in a single pass, making our solution efficient even for long lists. This approach is both clever and practical for linked list problems.

### Python Solution

```python
def deleteMiddle(head):
    if not head or not head.next:
        return None
    slow = head
    fast = head
    prev = None
    while fast and fast.next:
        prev = slow
        slow = slow.next
        fast = fast.next.next
    prev.next = slow.next
    return head
```

====

## 328. Odd Even Linked List (Medium)

https://leetcode.com/problems/odd-even-linked-list

Given the head of a singly linked list, group all the nodes with odd indices together followed by the nodes with even indices, and return the reordered list. (The indices are 1-based.)

Example:
```
Input: head = [1,2,3,4,5]
Output: [1,3,5,2,4]
```

Constraints:
```
- The number of nodes in the list is in the range [0, 10^4].
- -10^6 <= Node.val <= 10^6
```

> **Hint:**  
> Use two pointers to separate odd and even nodes, then join them at the end.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to rearrange the nodes so that all odd-indexed nodes come before all even-indexed nodes. We use two pointers: one for odd nodes and one for even nodes. As we go through the list, we link odd nodes together and even nodes together, then join the two lists at the end.

We do this because separating the nodes as we go makes it easy to rearrange them in a single pass, without extra space. This approach is both efficient and elegant for linked list problems.

### Python Solution

```python
def oddEvenList(head):
    if not head or not head.next:
        return head
    odd = head
    even = head.next
    even_head = even
    while even and even.next:
        odd.next = even.next
        odd = odd.next
        even.next = odd.next
        even = even.next
    odd.next = even_head
    return head
```

====

## 2130. Maximum Twin Sum of a Linked List (Medium)

https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list

In a linked list of even length, every node has a twin: the ith node and the (n-1-i)th node are twins. The twin sum is the sum of a node and its twin. Return the maximum twin sum of the list.

Example:
```
Input: head = [5,4,2,1]
Output: 6
Explanation: Twin pairs are (5,1) and (4,2). Max twin sum is max(5+1, 4+2) = 6.
```

Constraints:
```
- The number of nodes in the list is even and in the range [2, 10^5].
- 1 <= Node.val <= 10^5
```

> **Hint:**  
> Use a stack or reverse the second half of the list to pair nodes efficiently.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the linked list as a line of people, and you want to pair the first with the last, the second with the second last, and so on. To do this, we can use a stack to remember the values from the first half, or reverse the second half of the list and walk from both ends at once.

We do this because it lets us efficiently pair up the nodes and calculate the twin sums in a single pass, without extra space if we reverse the list. This approach is both clever and practical for linked list problems.

### Python Solution

```python
def pairSum(head):
    # Find the middle
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    # Reverse second half
    prev = None
    curr = slow
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    # Calculate twin sums
    max_sum = 0
    first = head
    second = prev
    while second:
        max_sum = max(max_sum, first.val + second.val)
        first = first.next
        second = second.next
    return max_sum
```

====

## 104. Maximum Depth of Binary Tree (Easy)

https://leetcode.com/problems/maximum-depth-of-binary-tree

Given the root of a binary tree, return its maximum depth. A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

Example:
```
Input: root = [3,9,20,null,null,15,7]
Output: 3
```

Constraints:
```
- The number of nodes in the tree is in the range [0, 10^4].
- -100 <= Node.val <= 100
```

> **Hint:**  
> Use recursion to explore each branch and keep track of the depth.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to find the longest path from the root to a leaf. We use recursion to go down each branch, adding 1 for each level. At each node, we take the maximum depth of its left and right children.

We do this because recursion naturally follows the tree structure, making it easy to explore all paths and keep track of the depth. This approach is both simple and effective for tree problems.

### Python Solution

```python
def maxDepth(root):
    if not root:
        return 0
    return 1 + max(maxDepth(root.left), maxDepth(root.right))
```

====

## 872. Leaf-Similar Trees (Easy)

https://leetcode.com/problems/leaf-similar-trees

Consider all the leaves of a binary tree. Two binary trees are considered leaf-similar if their leaf value sequence is the same. Return true if and only if the two trees are leaf-similar.

Example:
```
Input: root1 = [3,5,1,6,2,9,8,null,null,7,4], root2 = [3,5,1,6,7,4,2,null,null,null,null,null,null,9,8]
Output: true
```

Constraints:
```
- The number of nodes in each tree is in the range [1, 200].
- 0 <= Node.val <= 200
```

> **Hint:**  
> Use DFS to collect the leaf values for both trees and compare them.

### Step by Step Explanation (Bill Nye style!)

Let's imagine two trees as two mazes. We want to collect all the leaves (end points) from each maze in the order we find them. We use depth-first search (DFS) to walk through each tree and record the leaves. Then, we compare the two lists.

We do this because DFS lets us explore each path to the end, ensuring we don't miss any leaves. By comparing the lists, we can quickly check if the trees are leaf-similar.

### Python Solution

```python
def leafSimilar(root1, root2):
    def dfs(node, leaves):
        if node:
            if not node.left and not node.right:
                leaves.append(node.val)
            dfs(node.left, leaves)
            dfs(node.right, leaves)
    leaves1, leaves2 = [], []
    dfs(root1, leaves1)
    dfs(root2, leaves2)
    return leaves1 == leaves2
```

====

## 1448. Count Good Nodes in Binary Tree (Medium)

https://leetcode.com/problems/count-good-nodes-in-binary-tree

Given a binary tree, a node X in the tree is named good if in the path from root to X there are no nodes with a value greater than X. Return the number of good nodes in the binary tree.

Example:
```
Input: root = [3,1,4,3,null,1,5]
Output: 4
```

Constraints:
```
- The number of nodes in the tree is in the range [1, 10^5].
- -10^4 <= Node.val <= 10^4
```

> **Hint:**  
> Use DFS and keep track of the maximum value seen so far on the path.

### Step by Step Explanation (Sal Khan style!)

Let's break it down!  
We want to count nodes that are not smaller than any node on the path from the root. We use depth-first search (DFS) to walk through the tree, keeping track of the largest value we've seen so far. If the current node's value is at least as big as that, it's a good node.

We do this because DFS lets us explore every path, and by carrying the maximum value along, we can check the "goodness" of each node efficiently. This approach is both clear and effective for tree problems.

### Python Solution

```python
def goodNodes(root):
    def dfs(node, max_so_far):
        if not node:
            return 0
        good = 1 if node.val >= max_so_far else 0
        max_so_far = max(max_so_far, node.val)
        return good + dfs(node.left, max_so_far) + dfs(node.right, max_so_far)
    return dfs(root, root.val)
```

====

## 437. Path Sum III (Medium)

https://leetcode.com/problems/path-sum-iii

Given the root of a binary tree and an integer targetSum, return the number of paths where the sum of the values along the path equals targetSum. The path does not need to start or end at the root or a leaf, but it must go downwards.

Example:
```
Input: root = [10,5,-3,3,2,null,11,3,-2,null,1], targetSum = 8
Output: 3
```

Constraints:
```
- The number of nodes in the tree is in the range [1, 1000].
- -10^9 <= Node.val <= 10^9
- -1000 <= targetSum <= 1000
```

> **Hint:**  
> Use DFS from each node to count all paths starting from that node.

### Step by Step Explanation (Bill Nye style!)

Let's imagine the tree as a network of pipes, and we want to count all the ways water can flow from any point down to reach a certain total. We use depth-first search (DFS) to start at each node and count all paths that sum to the target.

We do this because starting DFS from every node ensures we don't miss any possible path, and by keeping track of the running sum, we can check if we've hit the target at each step. This approach is thorough and works well for tree path problems.

### Python Solution

```python
def pathSum(root, targetSum):
    def dfs(node, curr_sum):
        if not node:
            return 0
        count = 1 if curr_sum + node.val == targetSum else 0
        count += dfs(node.left, curr_sum + node.val)
        count += dfs(node.right, curr_sum + node.val)
        return count
    if not root:
        return 0
    return dfs(root, 0) + pathSum(root.left, targetSum) + pathSum(root.right, targetSum)
```

====
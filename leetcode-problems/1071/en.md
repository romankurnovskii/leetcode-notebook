## Description

Given two strings `str1` and `str2`, return the largest string that divides both of them. A string `x` divides string `y` if `y` is made up of one or more copies of `x`.

Example:
```
Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"

Input: str1 = "ABABAB", str2 = "ABAB"
Output: "AB"
```

Constraints:
```
- 1 <= str1.length, str2.length <= 1000
- str1 and str2 consist of English uppercase letters.
```

## Hint

> Try to find the greatest common divisor (GCD) of the lengths of the two strings, and check if the substring of that length divides both strings.

## Explanation

Suppose you have two strings, and you want to find the biggest chunk that can be repeated to make both strings. Think of it like finding the biggest building block that fits perfectly into both.

First, we check if both strings can be built by repeating the same substring, because if they can't, there's no common divisor string. We do this by comparing `str1 + str2` and `str2 + str1`—if they're not the same, it means the order of repetition doesn't match, so no common divisor exists. This check is important because it quickly rules out impossible cases, saving us time and effort.

Next, we use the greatest common divisor (GCD) of the lengths of the two strings. We do this because the largest possible repeating substring must fit evenly into both strings, and the GCD gives us the largest length that divides both. This is a mathematical shortcut that ensures we only check the most promising candidate.

Finally, we take the substring of that length from the start of either string and check if repeating it forms both strings. This works because if a substring can build both strings by repetition, it must be the answer.

## Solution
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
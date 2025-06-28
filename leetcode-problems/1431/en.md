## Description

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

## Hint

> For each kid, check if their candies plus extraCandies is at least as much as the current maximum.

## Explanation

Let's break it down!  
First, we want to know the highest number of candies any kid currently has. This is important because we need a reference point to see if giving extra candies to a kid will make them "the greatest."

For each kid, we add the extraCandies to their current amount. We do this because we want to see if, after the bonus, they can reach or beat the current maximum. If they do, we mark them as `True` in our answer list; otherwise, `False`.

This approach is efficient because we only need to find the maximum once, and then just compare each kid's total to it. This saves us from recalculating the maximum for every kid, making our solution faster and cleaner.

## Solution
```python
def kidsWithCandies(candies, extraCandies):
    max_candies = max(candies)  # Find the current maximum
    return [(c + extraCandies) >= max_candies for c in candies]
``` 
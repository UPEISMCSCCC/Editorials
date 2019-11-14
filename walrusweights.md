# walrusweights

https://open.kattis.com/problems/walrusweights

In this problem, you need to find what sum of numbers is closest to a target value (1000). It's important to note that you can add any number of weights together, but you cannot add the same weight twice (though they aren't necessarily unique, so two different weights may have the same value).

A first approach might be a bfs. You keep track of whichever sum is closest, and at each step in the bfs you either add the next weight, or you don't. This approach is too slow for two reasons:
1. You're doubling the size of the queue each time, and 2^n is too big to handle without exceeding time limit
2. You're handling lots of duplicate values.

To elaborate on point 2, if you have weights:
```
5 2 3
```
There are multiple ways to get the sum `5` (`2+3` and `5`). Using the above bfs approach, your queue has identical sums in it, and every time you double the size of your queue you'll also double the amount of identical sums. All in all this means you're doing a large amount of extra work for no reason.

The fix for this is to use *Dynamic Programming*. Instead of storing combination of weights, we want to store valid sums we've previously seen. We can use a boolean array for this, which we set to have the size `2001`.

What we want is to check for each value. The value `arr[n]` will determine whether `n` is a sum we've seen before. Initially, we set `arr[0] = true` since 0 is always achievable by using no weights, but set every other value to `false`.

Then we can add each value to the current weights. If our first weight was `5`, we would do something along the lines of:
```cpp
for (int i = 2000; i >= 0; i--)
  if (arr[i] && i + n <= 2000)
    arr[i + n] = true;
```
This will mean that we've found the sums `0, 5`. If we repeat with a new weight `2`, we would then end up with `0, 2, 5, 7`. Once we add `3`, we get `0, 2, 3, 5, 7, 8, 10`. While there would be overlap at 5, it doesn't matter because `arr[5]` is `true` either way. Essentially, we're ignoring any overlaps.

Once we've added all the weights this way, we just have to iterate through the array back and forth to find the closest sum that we've seen.

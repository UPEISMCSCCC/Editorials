# beatspread

https://open.kattis.com/problems/beatspread

Beat the spread is a problem where you have to find a value that matches some simple constraints. We are given the sum of two scores and the difference of those two scores.

There's some things that make this problem fairly easy to tackle. One is that scores have to be positive, and another is that they have to be integers. We also know that the numbers are fairly small (maximum of 1000), so we can just iterate over all possibilities:

To do this, we can start by assuming that one team's score is 's' (sum) and the other team's is 0. We check whether their difference is the 'd' (difference) we need to find. If not, we decrease team 1's score and increase team 2's score.

For example, if we had `s = 8` and were trying to find `d = 4`, we could do it as:
```
8 & 0 | s = 8, d = 8 | wrong
7 & 1 | s = 8, d = 6 | wrong
6 & 2 | s = 8, d = 4 | right
```

The code for this sort of checking could look something like:
```cpp
int found = -1;
for (int i = s; found == -1 && i >= 0; i--)
  if (i - (s - i) == d)
    found = i;
```

---

As a note, this problem can also be solved using a binary search. If the problem size was larger and the O(n) algorithm we used above doesn't work, binary search's O(log n) time might be sufficient.

---

This problem can also be solved mathematically. This would be useful if we're not dealing with integer values.

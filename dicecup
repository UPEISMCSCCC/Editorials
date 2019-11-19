# dicecup

https://open.kattis.com/problems/dicecup

There are several ways to approach this problem. The description can seem to suggest this is a harder problem than it is, but looking at the output should make it clearer what the solution is.

Conceptually, there are several different values with overlap. To demonstrate, with two 4-sided dice:
```
2 = 1+1
3 = 1+2, 2+1
4 = 1+3, 2+2, 3+1
5 = 1+4, 2+3, 3+2, 4+1
6 = 2+4, 3+3, 4+2
7 = 3+4, 4+3
8 = 4+4
```
And with a 4-sided dice and a 6-sided dice:
```
2  = 1+1
3  = 1+2, 2+1
4  = 1+3, 2+2, 3+1
5  = 1+4, 2+3, 3+2, 4+1
6  = 1+5, 2+4, 3+3, 4+2
7  = 1+6, 2+5, 3+4, 4+3
8  = 2+6, 3+5, 4+4
9  = 3+6, 4+5
10 = 4+6
```

Recognizing the pattern, the simplest way is to loop from `n + 1` to `m + 1 ` inclusive, where `n` and `m` are the dice sides that we read in.

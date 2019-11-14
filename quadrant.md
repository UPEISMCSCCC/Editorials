# quadrant

https://open.kattis.com/problems/quadrant

In this problem, there you are given a number and want to see which quadrant it exists on. At first, it appears like a geometry problem, but its solution can be calculated without any of that.

Quadrants can be determined based off the x and y values like this:
```
 x,  y = 1
-x,  y = 2
-x, -y = 3
 x, -y = 4
 ```
 The simple solution is to use `if` and `else` to determine which quadrant it's in, based on whether `x` and `y` are `> 0` or not.

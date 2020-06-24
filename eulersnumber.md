# Euler's Number

https://open.kattis.com/problems/eulersnumber

This problem gives us a simple formula, and asks us to find the implement it. Because a factorial is an important part of this problem, we can calculate a factorial like:

```cpp
int factorial = 1;
for (int i = 1; i <= n; i++)
    factorial *= i;
```

With this we can slightly modify the loop to also add to a sum that represents our approximated `e` value and solve the problem.

```cpp
int factorial = 1;
double sum = 1.0;
for (int i = 1; i <= n; i++) {
    factorial *= i;
    sum += 1.0 / factorial;
}
```

There is a major gotcha in this problem when we do that. `n` can be as large as `10000`. This factorial is way too big to represent in an `int` or a `unsigned long long` or any other type available in C++. In fact it's over 30 thousand digits long and would be impractical in languages like Java or Python that support arbitrarily large integers.

But it can be noticed that when our factorial is very large, `1.0 / factorial` becomes extremely small, and will likely be too small for the precision in the final answer to matter. Turning our `factorial` variable to a `double` from an `int` solves this problem, so our loop should look like:

```cpp
double factorial = 1.0;
double sum = 1.0;
for (int i = 1; i <= n; i++) {
    factorial *= i;
    sum += 1.0 / factorial;
}
```

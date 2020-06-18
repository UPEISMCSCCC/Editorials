# modulo

https://open.kattis.com/problems/modulo

In this problem, we are given some amount of numbers (terminated by the end of input). We want to count how many unique values there are when the input numbers are modulo 42.

Because we're dealing with unique values, a `set` is a good data structure to employ. For every input, we can insert that value mod 42 directly.

```cpp
set<int> values;
int current;
while (cin >> current)
    values.insert(current % 42);
```

With this, `values.size()` will give us the number of unique modulo values.

---

An alternative that does not rely on standard library data structures would be to use an array:

```cpp
int arr[42] = {0};
int current;
while (cin >> current)
    arr[current % 42] = 1;
```

We can then count how many elements of `arr` are set to `1` to see the number of unique values modulo 42.

```cpp
int count = 0;
for (int i = 0; i < 42; i++)
    if (arr[i] == 1)
        count++;
```

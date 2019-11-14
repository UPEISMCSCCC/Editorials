# lastfactorialdigit

https://open.kattis.com/problems/lastfactorialdigit

At first look, this problem wants us to calculate the factorial of a number, and then look at its last digit. Calculating the factorial can be done easily with a for-loop:
```cpp
int factorial = 1;
for (int i = 2; i <= n; i++)
  factorial *= i;
```
And then you can calculate its last digit using modulus very easily:
```cpp
cout << factorial % 10 << "\n";
```

---

Alternatively, the range of numbers is incredibly small. Because there can only be the numbers 1 through 10, we can hardcode each value. We can calculate each factorial and print out its last digit.

---

Even better, something you'll notice about factorials is that pretty quickly their last digit will be 0, and once it's 0 it'll never stop being 0. Here's the factorials up to 10! to show this:
```
1
2
6
24
120
720
5040
40320
362880
3628800
```
Because of this, we know that `if (n >= 5)` then the last factorial digit will be 0, and we only need to consider 4 other base cases.

Which approach you take doesn't really matter, since the bounds of this problem are so small. If the numbers were significantly larger, you would likely have to do the third approach (since the first one would overflow or exceed time limit, and the second one would be too many cases to write out)

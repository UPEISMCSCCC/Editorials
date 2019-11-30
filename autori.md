# autori

https://open.kattis.com/problems/autori

In this problem, we have to abbreviate longer name combinations like `Knuth-Morris-Pratt` into `KMP`. The input description can give us some good insight into how we might solve this:

> The first character will always be an uppercase letter. Hyphens will always be followed by an uppercase letter. All other characters will be lowercase letters.

We can implement this as it is. We print the first character of the input, we look through the string from there until we see a `-`, and then we print the character after that (not the `-` but the capital letter that follows it).

---

If we ignore the hyphens, we can notice that we can simplify it a bit more. Because the start of a name is always capitalized, and everything else is always lowercase, we only need to check if a letter is capitalized or not. With that, we just iterate over the entire string and print any capital letters we see.

---

So far, we've been going through the string and taking whatever we need. We can also look at it the other way -- getting rid of what we don't want. There are multiple ways, but we can do this with regex like in the python code:

```python3
re.sub("[a-z-]+", "", inputString)
```

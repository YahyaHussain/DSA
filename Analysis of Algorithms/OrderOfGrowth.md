Let $f(n)$ and $g(n)$ be the time taken by two algorithms where $n >= 9$ and $f(n)$ and $g(n)$ are also greater than equal to $0$. A function $f(n)$ is said to be growing faster than $g(n)$ if $g(n)/f(n)$ for $n$ tends to $infinity$ is $0$ (or $f(n)/g(n)$ for $n$ tends to $infinity$ is $infinity$).

```md
Example 1:  f(n) = 1000,  g(n) = n + 1
- For n > 999, g(n) would always be greater than f(n) because order of growth of g(n) is more than f(n).

Example 2: f(n) = 4n2 ,  g(n) = 2n + 2000
- f(n) has higher order of growth as it grows quadratically in terms of input size.
```

**How do we Quickly find order of Growth?**

When $n >= 0$, $f(n) >= 0$ and $g(n) >= 0$, we can use the below steps.
- Ignore the order terms
- Ignore the constants

```md
Example 1 : 4n2 + 3n + 100 
- After ignoring lower order terms, we get 4n2
- After ignoring constants, we get n2
- Hence order of growth is n2

Example 2 : 100 n Log n + 3n + 100 Log n  + 2
- After ignoring lower order terms, we get 100 n  Log n
- After ignoring constants, we get n Log n
- Hence order of growth is n Log n
```

**How do we compare two order of growths?**

The following are some standard terms that we must remember for comparison.

$c < Log Log n < Log n  < n^{1/3} < n^{1/2}  < n < n Log n < n^2 < n^2 Log n < n^3  < n^4 < 2^n  < n^n$

Here $c$ is a constant

# Basic Math Concepts

## Finding number of Digits in a Number

Given an integral number ```N```. The task is to find the count of digits present in this number. <br>
Let's say:
```
N = 2019

Number of digits in N here is 4 and,
the digits are: 2, 0, 1, 9.
```

Some more Examples:
```
N = 1567
Number of digits = 4

N = 256
Number of digits = 3

N = 58964
Number of digits = 5
```

### Solution 1

**Simple Solution:** A Simple Solution that comes in mind is:

1. Check whether the number N is equal to zero.
1. Increase the count of digits by 1 if N is not zero.
1. Reduce the number by dividing it by 10.
1. Repeat the above steps until the number is reduced to zero.

**Dry-run of above algorithm:** Consider an example, N = 58964. Initialize a variable ```digitsCount``` to zero which will store the count of digits. Keep incrementing *digitsCount* until N is not zero, and reduce it by dividing by 10 at each step.
```
Iteration 1: N not equals to 0
Increment digitsCount, digitsCount = digitsCount + 1.
digitsCount = 0 + 1 = 1.
N = N/10 = 58964/10 = 5896.

Iteration 2: N not equals to 0
Increment digitsCount, digitsCount = digitsCount + 1.
digitsCount = 1 + 1 = 2.
N = N/10 = 5896/10 = 589.

Iteration 3: N not equals to 0
Increment digitsCount, digitsCount = digitsCount + 1.
digitsCount = 2 + 1 = 3.
N = N/10 = 589/10 = 58.

Iteration 4: N not equals to 0
Increment digitsCount, digitsCount = digitsCount + 1.
digitsCount = 3 + 1 = 4.
N = N/10 = 58/10 = 5.

Iteration 5: N not equals to 0
Increment digitsCount, digitsCount = digitsCount + 1.
digitsCount = 4 + 1 = 5.
N = N/10 = 5/10 = 0.

Iteration 6: N becomes equal to 0.
Terminate any further operation.
Return value of digitsCount.

Therefore, number of digits = 5.
```
**Analysis of above algorithm:** You can clearly see that the number of operations performed in the above solution is equal to the count of digits present in the number. So, the time complexity of the solution is ```O(digitsCount)```.

### Solution 2

**Better Solution:** A better solution is to use mathematics to solve this problem. The number of digits in a number say N can be easily obtained by using the formula:

Number of digits in N = $```log_{10}(N) + 1```$.

**Derivation:** Suppose the number of digits in the number **N** is **K**.

Therefore, we can say that: <br>
$```10^{K-1} <= N < 10^K```$

Applying base-10 logarithm to both sides in the above equation, we get: <br>
$```K-1 <= log_{10}(N) < K.```$ <br>

$```or, K - 1 + 1 <= log_{10}(N) + 1 < K + 1```$ <br>
$```or, K <= log_{10}(N) + 1 < K + 1```$ <br>

Therefore, <br>
$```K = floor(log_{10}(N) + 1)```$

**Analysis of above algorithm:** Since the above algorithm works in a single operation by using two mathematical operations i.e., finding logarithmic and floor value. Therefore, the time complexity of the solution is **O(1)**.

## Arithmetic and Geometric Progressions 

### Arithmetic Progression

A sequence of numbers is said to be in an Arithmetic progression if the difference between any two consecutive terms is always the same. In simple terms, it means that the next number in the series is calculated by adding a fixed number to the previous number in the series. For example, 2, 4, 6, 8, 10 is an AP because the difference between any two consecutive terms in the series (common difference) is same (4 - 2 = 6 - 4 = 8 - 6 = 10 - 8 = 2).

**Facts about Arithmetic Progression:**
1. **Initial term:** In an arithmetic progression, the first number in the series is called the initial term.
1. **Common difference:** The value by which consecutive terms increase or decrease is called the common difference.
1. The behavior of the arithmetic progression depends on the common difference d. If the common difference is positive, then the members (terms) will grow towards positive infinity, but if the common difference is negative, then the members (terms) will grow towards negative infinity.

**Formula of $n^th$ term of an A.P:** <br>
If 'a' is the initial term and 'd' is the common difference. Thus, the explicit formula is: <br>
$$a_n = a_1 + (n - 1)d$$
$a_n$ &rarr; nth term <br>
$a_1$ &rarr; first term <br>
$n$ &rarr; term position <br>
$d$ &rarr; common difference

**Formula of sum of first n term of A.P:** <br>
$$S_n = \frac{n}{2}[2a+(n - 1)d]$$
$S_n$ &rarr; sum of a term of A.P.<br>
$a$ &rarr; first form of A.P. <br>
$d$ &rarr; common difference <br>
$n$ &rarr; Number of terms

**General Formulas to solve problems related to Arithmetic Progressions:** If 'a' is the first term and 'd' is the common difference:
* **nth term** of an AP = $a + (n-1)d$.
* **Arithmetic Mean** = $\frac{Sum of all terms in the AP}{Number of terms in the AP}$.
* **Sum of 'n' terms** of an AP = $0.5n(first term + last term)$ = $0.5n[2a + (n - 1)d]$.

### Geometric Progression

A sequence of numbers is said to be in a **Geometric progression** if the ratio of any two consecutive terms is always the same. In simple terms, it means that the next number in the series is calculated by multiplying a fixed number to the previous number in the series. For example, 2, 4, 8, 16 is a GP because ratio of any two consecutive terms in the series (common ratio) is the same (4 / 2 = 8 / 4 = 16 / 8 = 2).

**Facts about Geometric Progression:** <br>
1. **Initial term:** In a geometric progression, the first number is called the initial term.
1. **Common ratio:** The ratio of any two consecutive terms by taking the previous term in the denominator.
1. The behaviour of a geometric sequence depends on the value of the common ratio. If the common ratio is:
   * Positive, the terms will all be of the same sign as the initial term.
   * Negative, the terms will alternate between positive and negative.
   * Greater than 1, there will be exponential growth towards positive or negative infinity (depending on the sign of the initial term).
   * 1, the progression is a constant sequence.
   * Between -1 and 1 but not zero, there will be exponential decay towards zero.
   * -1, the progression is an alternating sequence.
   * Less than -1, for the absolute values there is exponential growth towards (unsigned) infinity, due to the alternating sign.

**Formula of $n^th$ term of a Geometric Progression:** If 'a' is the first term and 'r' is the common ratio. Thus, the explicit formula is: <br>
$$a_n = a_1 * r^{n - 1}$$
$a_n$ &rarr; General term <br>
$a_1$ &rarr; First term <br>
$r$ &rarr; Common ratio

**Formula of sum of nth term of Geometric Progression:**
$$Sum = \frac{a(r^n - 1)}{r - 1}$$
$r$ &rarr; Common ratio <br>
$n$ &rarr; Number of terms <br>
$Sum$ &rarr; Sum of all Geometric Progression

**General Formulas to solve problems related to Geometric Progressions:**

If 'a' is the first term and 'r' is the common ratio:
* **nth term of a GP** = $a*r^{n-1}$.
* **Geometric Mean** = nth root of the product of n terms in the GP.
* **Sum of ‘n’ terms** of a GP (r < 1) = $\frac{a*(1 – r^n)}{1 – r}$.
* **Sum of ‘n’ terms** of a GP (r > 1) = $\frac{a*(r^n – 1)}{r – 1}$.
* **Sum of infinite terms** of a GP (r < 1) = $\frac{a}{1 – r}$.

## Quadratic Equations

A **quadratic equation** is a second-order polynomial equation of a variable say **x**. The general form of a quadratic equation is given as: <br>

$```ax^2 + bx + c = 0```$

Where a,b and c are real known values and, $a$ can't be zero.

**Roots of an Equation:** The roots of an equation are the values for which the equation satisfies the given condition. For Example, the roots of equation $x^2 - 7x - 12 = 0$ are $3$ and $4$ respectively. If we replace the value of $x$ by $3$ and $4$ individually in the equation, the equation will evaluate to zero.

*A quadratic equation has two roots.* The roots of a quadratic equation can be easily obtained by using the quadratic formula:
$$roots = \frac{-b ± \sqrt{(b^2 - 4ac)}}{2a}$$

**Derivation:**
$ax^2 + bx + c = 0$

or, $ax^2 + bx = -c$

or, $x^2 + (\frac{b}{a})x = -\fract{c}{a}$

or, $x^2 + (b/a)x + (b^2/4a^2) - (b^2/4a^2) = -(c/a)$

or, $x^2 + (b/a)x + (b2/4a2) = -(c/a) + (b^2/4a^2)$

or, $(x + b/2a)^2  = -(c/a) + (b^2/4a^2)$

or, %(x + b/2a)^2  = (b^2  - 4ac) /4a^2$

or, $(x + \frac{b}{2a}) = ± 'frac{\sqrt(b^2 - 4ac)}{2a}$

or, $x = \frac{(-b ± \sqrt{(b^2 - 4ac)})}{2^a}$

There arises three cases as described below while finding the roots of a quadratic equation:
If b2 < 4ac, then roots are complex
(not real).
For example, roots of x2 + x + 1 = 0 are
-0.5 + i1.73205 and -0.5 - i1.73205

If b2 = 4ac, then roots are real 
and both roots are same.
For example, roots of x2 - 2x + 1 = 0 are 1 and 1

If b2 > 4ac, then roots are real 
and different.
For example, roots of x2 - 7x - 12 = 0 are 3 and 4









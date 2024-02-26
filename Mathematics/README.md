# Basic Math Concepts

## Finding number of Digits in a Number

Given an integral number $N$. The task is to find the count of digits present in this number. <br>
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

**Simple Solution:** <br>
A Simple Solution that comes in mind is: <br>
1. Check whether the number $N$ is equal to zero.
1. Increase the count of digits by $1$ if $N$ is not zero.
1. Reduce the number by dividing it by $10$.
1. Repeat the above steps until the number is reduced to zero.

**Dry-run of above algorithm:** <br>
Consider an example, $N = 58964$. Initialize a variable *digitsCount* to zero which will store the count of digits. Keep incrementing *digitsCount* until $N$ is not zero, and reduce it by dividing by $10$ at each step.
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
**Analysis of above algorithm:** <br>
You can clearly see that the number of operations performed in the above solution is equal to the count of digits present in the number. So, the time complexity of the solution is $O(digitsCount)$.

### Solution 2

**Better Solution:** <br>
A better solution is to use mathematics to solve this problem. The number of digits in a number say $N$ can be easily obtained by using the formula: <br>
Number of digits in $N = log_{10}(N) + 1$.

**Derivation:** <br>
Suppose the number of digits in the number $N$ is $K$. <br>
Ttherefore, we can say that: $10^{K-1} <= N < 10^K$

Applying $base-10$ logarithm to both sides in the above equation, we get: <br>
$K-1 <= log_{10}(N) < K.$ <br>
$or, K - 1 + 1 <= log_{10}(N) + 1 < K + 1$ <br>
$or, K <= log_{10}(N) + 1 < K + 1$ <br>
$\therefore K = floor(log_{10}(N) + 1)$

**Analysis of above algorithm:** <br>
Since the above algorithm works in a single operation by using two mathematical operations $i.e.,$ finding logarithmic and floor value. Therefore, the time complexity of the solution is $O(1)$.

## Arithmetic and Geometric Progressions 

### Arithmetic Progression

A sequence of numbers is said to be in an Arithmetic progression if the difference between any two consecutive terms is always the same. In simple terms, it means that the next number in the series is calculated by adding a fixed number to the previous number in the series. For example, $2, 4, 6, 8, 10$ is an AP because the difference between any two consecutive terms in the series (common difference) is same $(4 - 2 = 6 - 4 = 8 - 6 = 10 - 8 = 2)$.

**Facts about Arithmetic Progression:**
1. **Initial term:** In an arithmetic progression, the first number in the series is called the initial term.
1. **Common difference:** The value by which consecutive terms increase or decrease is called the common difference.
1. The behavior of the arithmetic progression depends on the common difference $d$. If the common difference is positive, then the members (terms) will grow towards positive infinity, but if the common difference is negative, then the members (terms) will grow towards negative infinity.

**Formula of $n^{th}$ term of an A.P:** <br>
If $a$ is the initial term and $d$ is the common difference. Thus, the explicit formula is: <br>
$$a_n = a_1 + (n - 1)d$$
$a_n$ &rarr; nth term <br>
$a_1$ &rarr; first term <br>
$n$ &rarr; term position <br>
$d$ &rarr; common difference

**Formula of sum of first $n$ term of A.P:** <br>
$$S_n = \frac{n}{2}[2a+(n - 1)d]$$
$S_n$ &rarr; sum of a term of A.P.<br>
$a$ &rarr; first form of A.P. <br>
$d$ &rarr; common difference <br>
$n$ &rarr; Number of terms

**General Formulas to solve problems related to Arithmetic Progressions:** If $a$ is the first term and $d$ is the common difference:
* $n^{th}$ term of an AP = $a + (n-1)d$.
* **Arithmetic Mean** = ${Sum \space Of \space All \space Terms \space In \space The \space AP \over Number \space Of \space Terms \space In \space The \space AP}$.
* **Sum of $n$ terms** of an AP = $\frac{n}{2}(first \space term + last \space term) = \frac{n}{2}[2a + (n - 1)d]$.

### Geometric Progression

A sequence of numbers is said to be in a **Geometric progression** if the ratio of any two consecutive terms is always the same. In simple terms, it means that the next number in the series is calculated by multiplying a fixed number to the previous number in the series. For example, $2, 4, 8, 16$ is a GP because ratio of any two consecutive terms in the series (common ratio) is the same $(\frac{4}{2} = \frac{8}{4} = \frac{16}{8} = 2)$.

**Facts about Geometric Progression:** <br>
1. **Initial term:** In a geometric progression, the first number is called the initial term.
1. **Common ratio:** The ratio of any two consecutive terms by taking the previous term in the denominator.
1. The behaviour of a geometric sequence depends on the value of the common ratio. If the common ratio is:
   * Positive, the terms will all be of the same sign as the initial term.
   * Negative, the terms will alternate between positive and negative.
   * Greater than $1$, there will be exponential growth towards positive or negative infinity (depending on the sign of the initial term).
   * $1$, the progression is a constant sequence.
   * Between $-1$ and $1$ but not zero, there will be exponential decay towards zero.
   * $-1$, the progression is an alternating sequence.
   * Less than $-1$, for the absolute values there is exponential growth towards (unsigned) infinity, due to the alternating sign.

**Formula of $n^{th}$ term of a Geometric Progression:** <br>
If $a$ is the first term and $r$ is the common ratio. Thus, the explicit formula is: <br>
$$a_n = a_1r^{n - 1}$$
$a_n$ &rarr; General term <br>
$a_1$ &rarr; First term <br>
$r$ &rarr; Common ratio

**Formula of sum of $n^{th}$ term of Geometric Progression:**
$$Sum = \frac{a(r^n - 1)}{r - 1}$$
$r$ &rarr; Common ratio <br>
$n$ &rarr; Number of terms <br>
$Sum$ &rarr; Sum of all Geometric Progression

**General Formulas to solve problems related to Geometric Progressions:** <br>
If $a$ is the first term and $r$ is the common ratio:
* **$n^{th}$ term of a GP** = $a*r^{n-1}$.
* **Geometric Mean** = nth root of the product of n terms in the GP.
* **Sum of $n$ terms** of a GP $(r < 1) = \frac{a*(1 – r^n)}{1 – r}$.
* **Sum of $n$ terms** of a GP $(r > 1) = \frac{a*(r^n – 1)}{r – 1}$.
* **Sum of infinite terms** of a GP $(r < 1) = \frac{a}{1 – r}$.

## Quadratic Equations

A **quadratic equation** is a second-order polynomial equation of a variable say $x$. The general form of a quadratic equation is given as: <br>
$$ax^2 + bx + c = 0$$

Where $a$, $b$ and $c$ are real known values and, $a$ can't be zero.

**Roots of an Equation:** The roots of an equation are the values for which the equation satisfies the given condition. For Example, the roots of equation $x^2 - 7x - 12 = 0$ are $3$ and $4$ respectively. If we replace the value of $x$ by $3$ and $4$ individually in the equation, the equation will evaluate to zero.

*A quadratic equation has two roots.* The roots of a quadratic equation can be easily obtained by using the quadratic formula:
$$roots = \frac{-b ± \sqrt{(b^2 - 4ac)}}{2a}$$

**Derivation:** <br>
$ax^2 + bx + c = 0$ <br>
$or, ax^2 + bx = -c$ <br>
$or, x^2 + (\frac{b}{a})x = -(\frac{c}{a})$ <br>
$or, x^2 + (\frac{b}{a})x + (\frac{b^2}{4a^2}) - (\frac{b^2}{4a^2}) = -(\frac{c}{a})$ <br>
$or, x^2 + (\frac{b}{a})x + (\frac{b^2}{4a^2}) = -(\frac{c}{a}) + (\frac{b^2}{4a^2})$ <br>
$or, (x + \frac{b}{2a})^2  = -(\frac{c}{a}) + (\frac{b^2}{4a^2})$ <br>
$or, (x + \frac{b}{2a})^2  = \frac{(b^2  - 4ac)}{4a^2}$ <br>
$or, (x + \frac{b}{2a}) = \pm \frac{\sqrt{(b^2 - 4ac)}}{2a}$ <br>
$or, x = \frac{(-b ± \sqrt{(b^2 - 4ac)})}{2a}$ <br>

There arises three cases as described below while finding the roots of a quadratic equation: <br>
* If $b^2 < 4ac$, then roots are complex (not real). <br>
For example, roots of $x^2 + x + 1 = 0$ are $-0.5 + i1.73205$ and $-0.5 - i1.73205$
* If $b^2 = 4ac$, then roots are real and both roots are same. <br>
For example, roots of $x2 - 2x + 1 = 0$ are $1$ and $1$
* If $b^2 > 4ac$, then roots are real and different. <br>
For example, roots of $x^2 - 7x - 12 = 0$ are $3$ and $4$

## Mean and Median

### Mean

Mean is defined as the average of a given set of data. Let us consider the sequence of numbers $2, 4, 4, 4, 5, 5, 7, 9$, the mean (average) of this given sequence is $5$.

**Formula for finding Mean:**
$$\bar x = \frac{x_1 + x_2 + \dots + x_n}{n}$$
Where, $x_1, x_2, \dots , x_n$ denotes the terms of the given sequence and n is the count of numbers present in the given sequence.

**Facts about Mean:**
* The mean (or average) is the most popular and well known measure of central tendency.
* It can be used with both discrete and continuous data, although its use is most often with continuous data.
* There are other types of means such as Geometric mean, Harmonic mean, and Arithmetic mean.
* Mean is the only measure of central tendency where the sum of the deviations of each value from the mean is always zero.

### Median
Median is the middle value of a set of data. To determine the median value in a sequence of numbers, the numbers must first be arranged in an ascending order.
* If the count of numbers in the sequence is ODD, the median value is the number that is in the middle, with the same amount of numbers below and above.
* If the count of numbers in the sequence is EVEN, the median is the average of the two middle values.

**Formula for finding Median:**

**If the count of numbers is odd:** After sorting the sequence,
```
Median = {(N+1)/2}th value;
N is the number of terms.
```

**If the count of numbers is even:** After sorting the sequence,
```
Median  =  Average of (N/2)th and {(N/2) + 1}th value;
N is the number of terms
```

**Facts about Median:**
Median is an important measure (compared to mean) for distorted data, because median is not so easily distorted. For example, median of $(1, 2, 2, 5, 100)$ is $2$ and mean is $22$.
* If the user adds a constant to every value, the mean and median increases by the same constant.
* If the user multiplies every value by a constant, the mean and the median will also be multiplied by that constant.

## Prime Numbers

A prime number is a whole number greater than $1$, which is only divisible by $1$ and itself. <br>
First few prime numbers are : $2, 3, 5, 7, 11, 13, 17, 19, 23, \dots$

**Naive Method to Check if a number is Prime:** <br>
Since a number is prime only if it is divisible by $1$ and the number itself, the naive method to check for primality of a number would be to iterate from $1$ to $N$ and check if there aren't any factors of $N$ except and $1$ and $N$ itself.

**Algorithm:**
* If $N$ is less than $2$, it is not prime. Return False.
* else:
   * Iterate from $2$ to $N-1$ and check if any of the numbers between $2$ and $N-1$ (both inclusive) divides $N$ or not. If yes, then $N$ is not prime, return False.
   * Otherwise, return True.

**Analysis of the above algorithm:** <br>
Since we are traversing linearly from $2$ to $N-1$, the time complexity of the above algorithm will be linear $O(N)$.

### Sieve of Eratosthenes

Using Sieve of Eratosthenes is the most efficient way of generating prime numbers up to a given number $N$.

Following is the algorithm to find all the prime numbers less than or equal to a given integer $n$ by Eratosthenes' method:
* Create a list of consecutive integers from $2$ to $n$: $(2, 3, 4, \dots, n)$.
* Initially, let $p$ equal $2$, the first prime number.
* Starting from $p^2$, count up in increments of $p$ and mark each of these numbers greater than or equal to $p^2$ itself in the list. These numbers will be $p(p+1)$, $p(p+2)$, $p(p+3)$, etc...
* Find the first number greater than $p$ in the list that is not marked. If there was no such number, stop. Otherwise, let $p$ now equal this number (which is the next prime), and repeat from step $3$.

**Explanation with Example:** <br>
Let us take an example when $n = 50$. So we need to print all print numbers smaller than or equal to $50$.

We create a list of all numbers from $2$ to $50$.

![list](https://github.com/YahyaHussain/DSA/assets/91454966/012f1c8e-3a96-4986-b7d8-a1c95f408469)

According to the algorithm we will mark all the numbers which are divisible by $2$ and are greater than or equal to the square of it.

![marking_multiples_of_2](https://github.com/YahyaHussain/DSA/assets/91454966/c00bd6d4-6c12-4332-a758-54f8b56a136c)

Now we move to our next unmarked number $3$ and mark all the numbers which are multiples of $3$ and are greater than or equal to the square of it.

![marking_multiples_of_3](https://github.com/YahyaHussain/DSA/assets/91454966/22028457-27f2-4efa-bad4-918f8fed1601)

We move to our next unmarked number $5$ and mark all multiples of $5$ and are greater than or equal to the square of it.

![marking_multiples_of_5](https://github.com/YahyaHussain/DSA/assets/91454966/0cc595af-072f-48c9-8f88-244689bf0372)

We continue this process and our final table will look like below:

![final_table](https://github.com/YahyaHussain/DSA/assets/91454966/d49a72fe-487d-4d61-9736-e49ed609a57a)

So the prime numbers are the unmarked ones: $2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47$.

## LCM and HCF 

### Factors and Multiples:

All numbers that divide a number completely, i.e., without leaving any remainder, are called factors of that number. For example, $24$ is completely divisible by $1, 2, 3, 4, 6, 8, 12, 24$. Each of these numbers is called a factor of $24$ and $24$ is called a multiple of each of these numbers.

### LCM:

LCM stands for Least Common Multiple. The lowest number that is exactly divisible by each of the given numbers is called the least common multiple of those numbers. For example, consider the numbers $3, 31$, and $62 (2$ x $31)$. The LCM of these numbers would be $2$ x $3$ x $31 = 186$.

To find the LCM of the given numbers, express each number as its prime factors. The product of the highest power of the prime numbers that appear in the prime factorization of any of the numbers gives us the LCM. <br>
For example, consider the numbers $2, 3, 4 (2$ x $2), 5, 6 (2$ x $3)$. The LCM of these numbers is $2$ x $2$ x $3$ x $5 = 60$. The highest power of $2$ comes from prime factorization of $4$, the highest power of $3$ comes from prime factorization of $3$ and prime factorization of $6$, and the highest power of $5$ comes from prime factorization of $5$.

### HCF:
The term HCF stands for Highest Common Factor. The largest number that divides two or more numbers is the highest common factor (HCF) for those numbers. For example, consider the numbers $30 (2$ x $3$ x $5), 36 (2$ x $2$ x $3$ x $3), 42 (2$ x $3$ x $7), 45 (3$ x $3$ x $5)$. $3$ is the largest number that divides each of these numbers, and hence, is the HCF for these numbers.

HCF is also known as Greatest Common Divisor (GCD). <br>
To find the HCF of two or more numbers, express each number as its prime factors. The product of the minimum powers of common prime terms in both of the prime factorization gives the HCF. This is the method we illustrated in the above step.

Also, for finding the HCF of two numbers, we can proceed by the long division method. We divide the larger number by the smaller number (divisor). Now, we divide the divisor by the remainder obtained in the previous stage. We repeat the same procedure until we get zero as the remainder. At that stage, the last divisor would be the required HCF.

For example, HCF of $30$ and $42$:

![HCF_of_30_and_42](https://github.com/YahyaHussain/DSA/assets/91454966/f7622966-dbe1-4130-83d9-8affc8e67c63)

### Basic Euclidean Algorithm for HCF

**The Euclidean algorithm is based on the below facts:** <br>
* If we subtract the smaller number from larger (we reduce larger number), GCD doesn't change. So if we keep subtracting repeatedly the larger of two, we end up with GCD.
* Now instead of subtraction, if we divide the smaller number, the algorithm stops when the remainder is found to be $0$.

Below is the recursive function for finding GCD using Euclidean Algorithm:
```c
int gcd(int a, int b)    {
    if (a == 0)
        return b;

    return gcd(b % a, a);
}
```
**Time Complexity:** $O(\log(min(a, b)))$

**Important properties of LCM and HCF:**
* For two numbers say, $'a'$ and $'b'$, $LCM$ x $HCF = a$ x $b$.
* HCF of co-primes = $1$.
* For two fractions,
  * $HCF = \frac{HCF}{LCM}$
  * $LCM = \frac{LCM}{HCF}$

## Factorials

**Factorial:** <br>
In mathematics, the factorial of a number say $N$ is denoted by $N!$. The factorial of a number is calculated by multiplying all the integers between $1$ and $N$ (both inclusive).

For Example, $4! = 4 * 3 * 2 * 1 = 24$.

That is,
```
N! = N * (N-1) * (N-2) * ... * 2 * 1
```
**Note:** As per convention, $0! = 1$.

### Problem:

Given a number $N$, the task is to count number of trailing zeroes in factorial of $N$. That is, number of zeroes at the end in the number $N!$.

**For Example:**
```
Input: N = 5
Output: 1 
Factorial of 5 is 120 which has one trailing 0.

Input: N = 20
Output: 4
Factorial of 20 is 2432902008176640000 which has 4 trailing zeroes.
```

An efficient way to solve this problem is to observe the properties of prime factorization. Consider prime factors of $N!$. A trailing zero is always produced by the prime factors $2$ and $5$. If we can count the number of $5s$ and $2s$ in prime factorization of $N!$, our task is done.

**Consider the following examples:**
* $N = 5$: There is one $5$ and three $2s$ in prime factors of $5!$ $(2 * 2 * 2 * 3 * 5)$. So count of trailing $0s$ is $1$.
* $N = 11$: There are two $5s$ and three $2s$ in prime factors of $11!$ $(28 * 34 * 52 * 7)$. So count of trailing $0s$ is $2$.

We can easily observe that the number of $2s$ in prime factors is always more than or equal to the number of $5s$. So if we count $5s$ in prime factors, we are done.

Now, how to count the total number of $5s$ in prime factors of $N!$? A simple way is to calculate $floor(N/5)$. For example, $7!$ has one $5$, $10!$ has two $5s$. It is not done yet, there is one more thing to consider. Numbers like $25, 125$, etc have more than one $5$. For example, if we consider $28!$, we get one extra $5$, and the number of $0s$ becomes $6$. Handling this is simple, first divide $N$ by $5$ and remove all single $5s$, then divide by $25$ to remove extra $5s$, and so on. Following is the summarized formula for counting trailing $0s$.
```
Trailing 0s in N! = Count of 5s in prime factors of n!
                  = floor(n/5) + floor(n/25) + floor(n/125) + ...
```

## Permutation and Combinations Basics

### Permutation
Permutation is the different arrangements of a given number of elements taken one by one, or some, or all at a time. For example, if we have two elements $A$ and $B$, then there are two possible arrangements, $AB$ and $BA$.

Number of permutations when $'r'$ elements are arranged out of a total of $'n'$ elements is 
$$nPr = \frac{n!}{(n - r)!}$$
For example, let $n = 4$ $(A, B, C$ and $D)$ and $r = 2$ (All permutations of size $2$). The answer is $\frac{4!}{(4-2)!}$ $=$ $12$. The twelve permutations are $AB, AC, AD, BA, BC, BD, CA, CB, CD, DA, DB$ and $DC$.

**Important Properties of Permutation:**
* $n P n$ $=$ $n * (n-1) * (n-2) * \dots * 1$ = $n!$.
* $n P 0$ $=$ $\frac{n!}{n!}$ $=$ $1$.
* $n P 1$ $=$ $n$.
* $n P (n-1)$ $=$ $n!$.
* $\frac{n P r}{n P (r-1)}$ $=$ $n - r + 1$.

**Permutation with repetition allowed:** <br>
The number of permutation or arrangements of $N$ numbers with repetition allowed will be $NN$. For Example, permutaions of ${1,2}$ with repetitions will be ${{1,1}, {1,2}, {2,1},{2,2}}$.

**Permutation with duplicates:** <br>
The number of permutations or arrangements of $N$ objects of which $p_1$ are of one kind, $p_2$ are of second kind, $\dots$, $p_k$ are of $k^{th}$ kind and the rest if any, are of different kinds is: $$\frac{N!}{(p_1! * p_2! * \dots * p_k!)}$$

### Combination
Combination is the different selections of a given number of elements taken one by one, or some, or all at a time. <br>
For example, if we have two elements $A$ and $B$, then there is only one way to select two items, we select both of them.

Number of combinations when $'r'$ elements are selected out of a total of $'n'$ elements is 
$$n C r = \frac{n!}{(r!) * (n - r)!}$$
For example, let $n = 4$ $(A, B, C$ and $D)$ and $r = 2$ (All combinations of size $2$). The answer is $\frac{4!}{((4-2)!*2!}$ $=$ $6$. The six combinations are $AB, AC, AD, BC, BD, CD$.

**Important Properties of Combination:**
* $n C 0$ $=$ $n C n$ $=$ $1$.
* $n C r$ $=$ $n C n-r$.
* $n C r$ $+$ $n C r-1$ $=$ $n+1 C r$.
* $(n * n-1) C (r-1)$ $=$ $((n - r + 1) * n) C (r-1)$.

## Modular Arithmetic

Let us take a look at some of the basic rules and properties that can be applied in Modular Arithmetic (Addition, Subtraction, Multiplication etc.). Consider numbers $a$ and $b$ operated under modulo $M$.
* (a + b) mod M = ((a mod M) + (b mod M)) mod M.
* (a - b) mod M = ((a mod M) - (b mod M)) mod M.
* (a * b) mod M = ((a mod M) * (b mod M)) mod M.

The above three expressions are valid and can be performed as stated. But when it comes to modular division, there are some limitations.

There isn't any formula to calculate:
```
(a / b) mod M
```
For this we have to learn modular inverse.

### Modular Inverse
The modular inverse is an integer 'x' such that.
```
ax ≡ 1 (mod M) 
```
The value of x should be in ${0, 1, 2, \dots, M-1}$, i.e., in the ring of integer modulo $M$.

The multiplicative inverse of $a$ modulo $M$ exists if and only if $a$ and $M$ are relatively prime (i.e., if $gcd(a, M) = 1$).

**Examples:**
```
Input:  a = 3, M = 11
Output: 4
Since (4*3) mod 11 = 1, 4 is modulo inverse of 3
One might think, 15 also as a valid output as "(15*3) mod 11" 
is also 1, but 15 is not in ring {0, 1, 2, ... 10}, so not 
valid.

Input:  a = 10, M = 17
Output: 12
Since (10*12) mod 17 = 1, 12 is modulo inverse of 3
```

**Methods of finding Modular Inverse:**
There are two very popular methods of finding modular inverse of any number a under modulo $M$.
* **Extended Euclidean Algorithm:** This method can be used when $a$ and $M$ are co-prime.
* **Fermat Little Theorem:** This method can be used when $M$ is prime.

Let us look at each of the above two methods in details:

**Extended Euclidean algorithm** that takes two integers $'a'$ and $'b'$, finds their gcd and also find $'x'$ and $'y'$ such that,
```
ax + by = gcd(a, b)
```

To find the modulo inverse of $'a'$ under $'M'$, we put $b$ $=$ $M$ in the above formula. Since we know that $a$ and $M$ are relatively prime, we can put value of gcd as $1$.

So, the formula becomes:
```
ax + My = 1 
```

If we take modulo $M$ on both sides, we get:
```
ax + My ≡ 1 (mod M)
```

We can remove the second term on the left side, as $My$ $(mod M)$ would always be $0$ for an integer $y$.

Therefore,
```
ax ≡ 1 (mod M) 
```

So the 'x' that we can find using Extended Euclid Algorithm is modulo inverse of $'a'$.

**Fermat Little Theorem:** The Fermat’s little theorem states that if $M$ is a prime number, then for any integer $a$, the number $a^M – a$ is an integer multiple of $M$.

That is,

$a^M ≡ a$ $(mod$ $M)$

Since, $a$ and $M$ are co-prime to each other then $a^{M-1}$ is an integral multiple of $M$. <br>
That is,

$a^{M-1} ≡ 1$ $(mod$ $M)$

If we multiply both sides by $a^{-1}$, we get:

$a^{-1} ≡ a^{M-2}$ $mod$ $M$

Therefore, if $M$ is a prime number to find modulo inverse of $a$ under $M$, find modular exponentiation of $a^{M-2}$ under modulo $M$.

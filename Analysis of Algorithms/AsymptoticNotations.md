## Asymptotic Notations for Analysis of Algorithms

The main idea of asymptotic analysis is to have a measure of the efficiency of algorithms that don't depend on machine-specific constants and don't require algorithms to be implemented and time taken by programs to be compared. Asymptotic notations are mathematical tools to represent the time complexity of algorithms for asymptotic analysis.

**Asymptotic Notations:**
- Asymptotic Notations are mathematical tools used to analyze the performance of algorithms by understanding how their efficiency changes as the input size grows.
- These notations provide a concise way to express the behavior of an algorithm's time or space complexity as the input size approaches infinity.
- Rather than comparing algorithms directly, asymptotic analysis focuses on understanding the relative growth rates of algorithms' complexities.
- It enables comparisons of algorithms' efficiency by abstracting away machine-specific constants and implementation details, focusing instead on fundamental trends.
- Asymptotic analysis allows for the comparison of algorithms' space and time complexities by examining their performance characteristics as the input size varies.
- By using asymptotic notations, such as Big O, Big Omega, and Big Theta, we can categorize algorithms based on their worst-case, best-case, or average-case time or space complexities, providing valuable insights into their efficiency.

```md
There are mainly three asymptotic notations:
- Big-O Notation (O-notation)
- Omega Notation (Ω-notation)
- Theta Notation (Θ-notation)
```

### 1. Theta Notation ($Θ$-Notation):
- Theta notation encloses the function from above and below. Since it represents the upper and the lower bound of the running time of an algorithm, it is used for analyzing the **average-case** complexity of an algorithm.
- **Theta (Average Case):** You add the running times for each possible input combination and take the average in the average case.

Let $g$ and $f$ be the function from the set of natural numbers to itself. The function $f$ is said to be $Θ(g)$, if there are constants $c_1$, $c_2$ $>$ $0$ and a natural number $n_0$ such that $c_1 * g(n) ≤ f(n) ≤ c_2 * g(n)$ for all $n ≥ n_0$

<img width="300" height="229" alt="image" src="https://github.com/user-attachments/assets/9954d4a8-79b2-4345-9c60-ea3bda418ae8" />

*Theta notation*

**Mathematical Representation of Theta notation:**

$Θ (g(n))$ $=$ { f(n)$: there exist positive constants $c_1$, $c_2$ and $n_0$ such that $0 ≤ c_1 * g(n) ≤ f(n) ≤ c_2 * g(n)$ for all $n ≥ n_0$ }

**Note:** $Θ(g)$ is a set

The above expression can be described as if $f(n)$ is theta of $g(n)$, then the value $f(n)$ is always between $c_1 * g(n)$ and $c_2 * g(n)$ for large values of $n (n ≥ n_0)$. The definition of theta also requires that $f(n)$ must be non-negative for values of $n$ greater than $n_0$.

**The execution time serves as both a lower and upper bound on the algorithm's time complexity.**

**It exist as both, most, and least boundaries for a given input value.**

A simple way to get the Theta notation of an expression is to drop low-order terms and ignore leading constants. For example, Consider the expression **$3n^3 + 6n^2 + 6000 = Θ(n^3)$**, the dropping lower order terms is always fine because there will always be a number($n$) after which $Θ(n^3)$ has higher values than $Θ(n^2)$ irrespective of the constants involved. For a given function $g(n)$, we denote $Θ(g(n))$ is following set of functions. 

Examples :
```
{ 100 , log (2000) , 10^4 } belongs to Θ(1)
{ (n/4) , (2n+3) , (n/100 + log(n)) } belongs to Θ(n)
{ (n^2+n) , (2n^2) , (n^2+log(n))} belongs to Θ( n2)
Note: Θ provides exact bounds.
```

### 2. Big-O Notation (O-notation):
- Big-O notation represents the upper bound of the running time of an algorithm. Therefore, it gives the worst-case complexity of an algorithm.
- It is the most widely used notation for Asymptotic analysis.
- It specifies the upper bound of a function.
- The maximum time required by an algorithm or the worst-case time complexity.
- It returns the highest possible output value (big-O) for a given input.
- **Big-O(Worst Case):** It is defined as the condition that allows an algorithm to complete statement execution in the longest amount of time possible.

If $f(n)$ describes the running time of an algorithm, $f(n)$ is $O(g(n))$ if there exist a positive constant $C$ and $n_0$ such that, $0 ≤ f(n) ≤ cg(n)$ for all $n ≥ n_0$

**It returns the highest possible output value (big-O) for a given input.**

**The execution time serves as an upper bound on the algorithm's time complexity.**

<img width="252" height="261" alt="image" src="https://github.com/user-attachments/assets/11723212-75f9-4eea-990b-9722b547f245" />

**Mathematical Representation of Big-O Notation:**

$O(g(n))$ $=$ { $f(n)$: there exist positive constants $c$ and $n_0$ such that $0 ≤ f(n) ≤ cg(n)$ for all $n ≥ n_0$ }

For example, Consider the case of Insertion Sort. It takes linear time in the best case and quadratic time in the worst case. We can safely say that the time complexity of the Insertion sort is $O(n^2)$.

**Note:** $O(n^2)$ also covers linear time. 

If we use $Θ$ notation to represent the time complexity of Insertion sort, we have to use two statements for best and worst cases: 
- The worst-case time complexity of Insertion Sort is $Θ(n^2)$.
- The best case time complexity of Insertion Sort is $Θ(n)$.

The Big-O notation is useful when we only have an upper bound on the time complexity of an algorithm. Many times we easily find an upper bound by simply looking at the algorithm.  

**Examples:**
```
{ 100 , log (2000) , 10^4 } belongs to O(1)
U { (n/4) , (2n+3) , (n/100 + log(n)) } belongs to O(n)
U { (n^2+n) , (2n^2) , (n^2+log(n))} belongs to O( n^2) 
Note: Here, U represents union, we can write it in these manner because O provides exact or upper bounds .
```

### 3. Omega Notation (Ω-Notation):
- Omega notation represents the lower bound of the running time of an algorithm. Thus, it provides the best case complexity of an algorithm.

**The execution time serves as a lower bound on the algorithm's time complexity.**
**It is defined as the condition that allows an algorithm to complete statement execution in the shortest amount of time.**

Let $g$ and $f$ be the function from the set of natural numbers to itself. The function $f$ is said to be $Ω(g)$, if there is a constant $c > 0$ and a natural number $n_0$ such that $c*g(n) ≤ f(n)$ for all $n ≥ n_0$

<img width="283" height="261" alt="image" src="https://github.com/user-attachments/assets/57eeea37-5e90-4ec2-b2c5-5dccf0e97b5b" />

**Mathematical Representation of Omega notation:**

$Ω(g(n))$ $=$ { $f(n)$: there exist positive constants $c$ and $n_0$ such that $0 ≤ cg(n) ≤ f(n)$ for all $n ≥ n_0$ }

Let us consider the same Insertion sort example here. The time complexity of Insertion Sort can be written as $Ω(n)$, but it is not very useful information about insertion sort, as we are generally interested in worst-case and sometimes in the average case. 

**Examples:**
```
{ (n^2+n) , (2n^2) , (n^2+log(n))} belongs to Ω( n^2)
U { (n/4) , (2n+3) , (n/100 + log(n)) } belongs to Ω(n)
U { 100 , log (2000) , 10^4 } belongs to Ω(1)
Note: Here, U represents union, we can write it in these manner because Ω provides exact or lower bounds.
```

### Properties of Asymptotic Notations:
**1. General Properties:**

If $f(n)$ is $O(g(n))$ then $a*f(n)$ is also $O(g(n))$, where $a$ is a constant.

**Example:**
```
f(n) = 2n²+5 is O(n²) 
then, 7*f(n) = 7(2n²+5) = 14n²+35 is also O(n²).
Similarly, this property satisfies both Θ and Ω notation.
```
We can say,
```
If f(n) is Θ(g(n)) then a*f(n) is also Θ(g(n)), where a is a constant. 
If f(n) is Ω (g(n)) then a*f(n) is also Ω (g(n)), where a is a constant.
```

**2. Transitive Properties:**

If $f(n)$ is $O(g(n))$ and $g(n)$ is $O(h(n))$ then $f(n) = O(h(n))$.

**Example:**
```
If f(n) = n, g(n) = n² and h(n)=n³
n is O(n²) and n² is O(n³) then, n is O(n³)
Similarly, this property satisfies both Θ and Ω notation.
```
We can say,
```
If f(n) is Θ(g(n)) and g(n) is Θ(h(n)) then f(n) = Θ(h(n)) .
If f(n) is Ω (g(n)) and g(n) is Ω (h(n)) then f(n) = Ω (h(n))
```

**3. Reflexive Properties:**

Reflexive properties are always easy to understand after transitive.
- If $f(n)$ is given then $f(n)$ is $O(f(n))$. Since $MAXIMUM$ $VALUE$ of $f(n)$ will be $f(n)$ ITSELF!
- Hence $x = f(n)$ and $y = O(f(n)$ tie themselves in reflexive relation always.

**Example:**
```
f(n) = n² ; O(n²) i.e O(f(n))
Similarly, this property satisfies both Θ and Ω notation.   
```
We can say that,
```
If f(n) is given then f(n) is Θ(f(n)).
If f(n) is given then f(n) is Ω (f(n)).
```

**4. Symmetric Properties:**

If $f(n)$ is $Θ(g(n))$ then $g(n)$ is $Θ(f(n))$.

**Example:**
```
If(n) = n² and g(n) = n²
then, f(n) = Θ(n²) and g(n) = Θ(n²)
This property only satisfies for Θ notation.
```

**5. Transpose Symmetric Properties:**

If $f(n)$ is $O(g(n))$ then $g(n)$ is $Ω (f(n))$.

**Example:**
```
If(n) = n , g(n) = n²
then n is O(n²) and n² is Ω (n) 
This property only satisfies O and Ω notations.
```

**6. Some More Properties:**

- If $f(n) = O(g(n))$ and $f(n) = Ω(g(n))$ then $f(n) = Θ(g(n))$
- If $f(n) = O(g(n))$ and $d(n)=O(e(n))$ then $f(n) + d(n) = O( max( g(n), e(n) ))$ 

**Example:**
```
f(n) = n i.e O(n) 
d(n) = n² i.e O(n²) 
then f(n) + d(n) = n + n² i.e O(n²)
```

- If $f(n)=O(g(n))$ and $d(n)=O(e(n))$ then $f(n) * d(n) = O(g(n) * e(n))$

**Example:** 
```
f(n) = n i.e O(n) 
d(n) = n² i.e O(n²)
then f(n) * d(n) = n * n² = n³ i.e O(n³)
_______________________________________________________________________________
Note: If  f(n) = O(g(n)) then g(n) = Ω(f(n))
```

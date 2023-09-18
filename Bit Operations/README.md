# Bit Operations

## Bitwise Algorithms Basics 
The Bitwise Algorithms are used to perform operations at bit-level or to manipulate bits in different ways. 
The bitwise operations are found to be much faster and are some times used to improve the efficiency of a program.

**For example:** To check if a number is even or odd. This can be easily done by using ```Bitwise-AND (&)``` operator. 
If the last bit of the operator is $set$ than it is $ODD$ otherwise it is $EVEN$. 
Therefore, if ```num & 1``` not equals to $zero$ then $num$ is $ODD$ otherwise it is $EVEN$.

## Bitwise Operators
The operators that works at Bit level are called bitwise operators. 
In general there are six types of Bitwise Operators as described below:
* ```& (bitwise AND)``` Takes two numbers as operands and does AND on every bit of two numbers.
  The result of $AND$ is $1$ only if both bits are $1$. Suppose $A = 5$ and $B = 3$, therefore ```A & B = 1```.
* ```| (bitwise OR)``` Takes two numbers as operands and does $OR$ on every bit of two numbers.
  The result of $OR$ is $1$ if any of the two bits is $1$. Suppose $A = 5$ and $B = 3$, therefore ```A | B = 7```.
* ```^ (bitwise XOR)``` Takes two numbers as operands and does $XOR$ on every bit of two numbers.
  The result of $XOR$ is $1$ if the two bits are different. Suppose $A = 5$ and $B = 3$, therefore ```A ^ B = 6```.
* ```<< (left shift)``` Takes two numbers, left shifts the bits of the first operand, the second operand decides the number of places to shift.
* ```>> (right shift)``` Takes two numbers, right shifts the bits of the first operand, the second operand decides the number of places to shift.
* ```~ (bitwise NOT)``` Takes one number and $inverts$ all bits of it. Suppose $A = 5$, therefore ```~A = 2```.

### Important Facts about Bitwise Operators:
* The left shift and right shift operators cannot be used with negative numbers.
* The bitwise operators should not be used in place of logical operators.
* The left-shift and right-shift operators are equivalent to multiplication and division by $2$ respectively.
* The & operator can be used to quickly check if a number is odd or even. The value of expression ```(x & 1)``` would be non-zero only if x is odd, otherwise the value would be zero.

## Bit Algorithms | Important Tactics 
Let's look at some of the useful tactics of the Bitwise Operators which can be helpful in solving a lot of problems really easily and quickly.

1. **How to set a bit in the number $num$:** <br>
   If we want to set a bit at $n^{th}$ position in number $num$, it can be done using $OR$ operator ( | ).
   * First we left shift $1$ to $n$ position via $(1 << n)$
   * Then, use $OR$ operator to set bit at that position. $OR$ operator is used because it will set the bit even if the bit is unset previously in binary representation of number $num$.

1. **How to unset/clear a bit at $n^{th}$ position in the number $num$:** <br>
   Suppose we want to unset a bit at nth position in number $num$ then we have to do this with the help of $AND$ ( & ) operator.
   * First we left shift $1$ to $n$ position via $(1 << n)$ than we use $bitwise \space NOT$ operator ( ~ ) to unset this shifted $1$.
   * Now after clearing this left shifted $1$ i.e making it to $0$ we will $AND$ ( & ) with the number $num$ that will unset bit at $n^{th}$ position.

1. **Toggling a bit at $n^{th}$ position:** <br>
   Toggling means to turn bit $on \space (1)$ if it was $off \space (0)$ and to turn $off \space (0)$ if it was $on \space (1)$ previously.
   We will be using $XOR$ operator here which is this '^'. The reason behind $XOR$ operator is because of its properties.
   * Properties of $XOR$ operator.
     * $1$ ^ $1 = 0$
     * $0$ ^ $0 = 0$
     * $1$ ^ $0 = 1$
     * $0$ ^ $1 = 1$
   * If two bits are different then $XOR$ operator returns a set bit $(1)$ else it returns an unset bit $(0)$.

1. **Checking if bit at $n^{th}$ position is set or unset:** <br>
   It is quite easily doable using $AND$ operator.
   * Left shift $1$ to given position and then $AND$ ( & ).
   * If the result of the $AND$ operation is $1$ then the bit at $n*{th}$ position is set otherwise it is unset.

1. **Divide by 2:** <br>
   ```
   x = x >> 1;
   ```
   **Logic:** When we do arithmetic right shift, every bit is shifted to right and blank position is substituted with sign bit of number, $0$ in case of positive and $1$ in case of negative number.
   Since every bit is a power of $2$, with each shift we are reducing the value of each bit by factor of $2$ which is equivalent to division of $x$ by $2$. <br>
   **Example:** <br>
   ```
   x = 18(00010010)
   x >> 1 = 9 (00001001)
   ```
   

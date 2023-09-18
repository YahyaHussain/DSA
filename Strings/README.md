# Introduction to Strings

Strings are defined as a stream of characters. 
Strings are used to represent text and are generally represented by enclosing text within quotes as: 
```
"This is a sample string!"
```

Different programming languages have different ways of declaring and using Strings.

## Strings in C/C++

In C/C++, Strings are defined as an array of characters. 
The difference between a character array and a string is that the string is terminated with a special character '\0'.

**Declaring Strings:** <br>
Declaring a string is as simple as declaring a one-dimensional array. 
Below is the basic syntax for declaring a string.
```cpp
char str_name[size];
```

In the above syntax, *str_name* is any name given to the string variable and size is used to define the length of the string, $i.e.,$ the number of characters strings will store. 
Please keep in mind that there is an extra terminating character which is the Null character '\0' used to indicate the termination of string which differs strings from normal character arrays.

**Initializing a String:** <br>
A string can be initialized in different ways. We will explain this with the help of an example. 
Below is an example to declare a string with the name as *str* and initialize it with *"YahyaHussain"*.
```
1. char str[] = "YahyaHussain";

2. char str[50] = "YahyaHussain";

3. char str[] = {'Y','a','h','y','a','H','u','s','s','a','i','n','\0'};

4. char str[13] = {'Y','a','h','y','a','H','u','s','s','a','i','n','\0'};
```

**Printing a string array:** <br>
Unlike arrays we do not need to print a string, character by character. 
The C/C++ language does not provide an inbuilt data type for strings but it has an access specifier *%s* which can be used to directly print and read strings.

```c
// C/C++ Program to illustrate strings
#include <bits/stdc++.h>
int main()  {
  // declare and initialize string
  char str[] = "YahyaHussain";

  // print string
  printf("%s", str);

  return 0;
}
```
**Output:**
```
YahyaHussain
```

**Passing strings to function:**  <br>
As strings are character arrays, so we can pass strings to function in the same way we pass an array to a function. 
Below is a sample program to do this:
```c
// C/C++ program to illustrate how to pass strings to function
#include <bits/stdc++.h>

void printStr(char str[])  {
  printf("String is: %s", str);
}

int main()  {
  // declare and initialize string
  char str[] = "YahyaHussain";

  // print string by passing string to a different function
  printStr(str);

  return 0;
}
```
**Output:**
```
String is: YahyaHussain
```

### std::string Class in C++

C++ has in its definition a way to represent the sequence of characters as an object of a class. 
This class is called ```std::string```. 
The String class stores the characters as a sequence of bytes with functionality of allowing access to single byte character.

**string Class vs Character array:** <br>
* A character array is simply an array of characters can terminated by a null character. A string is a class which defines objects that be represented as stream of characters.
* Size of the character array has to allocated statically, more memory cannot be allocated at run time if required. Unused allocated memory is wasted in case of character array.
  In case of strings, memory is allocated dynamically. More memory can be allocated at run time on demand. As no memory is preallocated, no memory is wasted.
* Implementation of character array is faster than ```std:: string```. Strings are slower when compared to implementation than character array.
* Character array does not offer much inbuilt functions to manipulate strings. String class defines a number of functionalities which allow manifold operations on strings.

**Declaration Syntax:** <br>
Declaring string using string class is simple and can be done using the string keyword as shown below.
```cpp
string string_name = "Sample String";
```

**Sample Program**
```cpp
// C++ program to illustrate strings
#include <bits/stdc++.h>
using namespace std;

int main()  {
  // declare and initialize string
  string str = "YahyaHussain";

  // print string
  cout << str;

  return 0;
}
```
**Output:**
```
YahyaHussain
```

## Strings in Java
String is a sequence of characters. In java, objects of String are immutable which means a constant and cannot be changed once created. <br>
**Creating a String** <br>
There are two ways to create string in Java: <br>
1. **String literal**
   ```java
   String s = "YahyaHussain";
   ```
1. **Using *new* keyword**
   ```java
   String s = new String (“YahyaHussain”);
   ```

### String Methods
* **int length():** Returns the number of characters in the String.
  ```java
  "YahyaHussain".length();  // returns 12
  ```
* **Char charAt(int i):** Returns the character at ith index.
  ```java
  "YahyaHussain".charAt(3); // returns  'y'
  ```
* **String substring (int i):** Return the substring from the $i^{th}$  index character to end.
  ```java
  "YahyaHussain".substring(5); // returns "Hussain"
  ```
* **String substring (int i, int j):** Returns the substring from $i$ to $j-1$ index.
  ```java
  "YahyaHussain".substring(0, 5); // returns "Yahya"
  ```
* **String concat( String str):** Concatenates specified string to the end of this string.
  ```java
  String s1 = "Yahya";
  String s2 = "Hussain";
  String output = s1.concat(s2); // returns "YahyaHussain"
  ```
* **int indexOf (String s):** Returns the index within the string of the first occurrence of the specified string.
  ```java
  String s = "Learn Share Learn";
  int output = s.indexOf("Share"); // returns 6
  ```
* **int indexOf (String s, int i):** Returns the index within the string of the first occurrence of the specified string, starting at the specified index.
  ```java
  String s = "Learn Share Learn";
  int output = s.indexOf('a',3); // returns 8
  ```
* **Int lastIndexOf( String s)**: Returns the index within the string of the last occurrence of the specified string.
  ```java
  String s = "Learn Share Learn";
  int output = s.lastIndexOf('a'); // returns 14
  ```
* **boolean equals( Object otherObj):** Compares this string to the specified object.
  ```java
  Boolean out = "Yahya".equals("Yahya"); // returns true
  Boolean out = "Yahya".equals("yahya"); // returns false
  ```
* **boolean  equalsIgnoreCase (String anotherString):** Compares string to another string, ignoring case considerations.
  ```java
  Boolean out= "Yahya".equalsIgnoreCase("Yahya"); // returns true
  Boolean out = "Yahya".equalsIgnoreCase("yahya"); // returns true
  ```
* **int compareTo(String anotherString):** Compares two string lexicographically.
  ```java
  int out = s1.compareTo(s2);  // where s1 ans s2 are strings to be compared

  /*
    This returns difference s1-s2. If :
    out < 0  // s1 comes before s2
    out = 0  // s1 and s2 are equal.
    out > 0   // s1 comes after s2.
  */
  ```
* **int compareToIgnoreCase(String anotherString):** Compares two string lexicographically, ignoring case considerations.
  ```java
  int out = s1.compareToIgnoreCase(s2); // where s1 ans s2 are strings to be compared

  /*
    This returns difference s1-s2. If :
    out < 0  // s1 comes before s2
    out = 0   // s1 and s2 are equal.
    out > 0   // s1 comes after s2.
  */
  ```
  *Note-* In this case, it will not consider case of a letter *(it will ignore whether it is uppercase or lowercase)*.
* **String toLowerCase():** Converts all the characters in the String to lower case.
  ```java
  String word1 = “HeLLo”;
  String word3 = word1.toLowerCase(); // returns “hello"
  ```
* **String toUpperCase():** Converts all the characters in the String to upper case.
  ```java
  String word1 = “HeLLo”;
  String word2 = word1.toUpperCase(); // returns “HELLO”
  ```
* **String trim():** Returns the copy of the String, by removing whitespaces at both ends. It does not affect whitespaces in the middle.
  ```java
  String word1 = " Learn Share Learn ";
  String word2 = word1.trim(); // returns : "Learn Share Learn"
  ```
* **String replace (char oldChar, char newChar):** Returns new string by replacing all occurrences of $oldChar$ with $newChar$.
  ```java
  String s1 = "Ilite";
  String s2 = "Ilite".replace('I' ,'E'); // returns "Elite"
  ```
  *Note-* s1 is still Ilite and s2 is Elite

```java
// Java code to illustrate different constructors and methods String class.

import java.io.*;
import java.util.*;
class Test
{
    public static void main (String[] args)
    {
        String s= "YahyaHussain";
        // or String s= new String ("YahyaHussain");

        // Returns the number of characters in the String.
        System.out.println("String length = " + s.length());

        // Returns the character at ith index.
        System.out.println("Character at 3rd position = " + s.charAt(3));

        // Return the substring from the ith index character to end of string
        System.out.println("Substring " + s.substring(3));

        // Returns the substring from i to j-1 index.
        System.out.println("Substring = " + s.substring(0,5));

        // Concatenates string2 to the end of string1.
        String s1 = "Yahya";
        String s2 = "Hussain";
        System.out.println("Concatenated string = " + s1.concat(s2));

        // Returns the index within the string of the first occurrence of the specified string.
        String s4 = "Learn Share Learn";
        System.out.println("Index of Share " + s4.indexOf("Share"));

        // Returns the index within the string of the first occurrence of the specified string, starting at the specified index.
        System.out.println("Index of a = " + s4.indexOf('a',3));

        // Checking equality of Strings
        Boolean out = "Yahya".equals("yahya");
        System.out.println("Checking Equality " + out);
        out = "Yahya".equals("Yahya");
        System.out.println("Checking Equality " + out);

        out = "Yahya".equalsIgnoreCase("yAhYa ");
        System.out.println("Checking Equality " + out);

        int out1 = s1.compareTo(s2);
        System.out.println("If s1 = s2 " + out);

        // Converting cases
        String word1 = "YahyaHussain";
        System.out.println("Changing to lower Case " + word1.toLowerCase());

        // Converting cases
        String word2 = "YahyaHussain";
        System.out.println("Changing to UPPER Case " + word1.toUpperCase());

        // Trimming the word
        String word4 = " Learn Share Learn ";
        System.out.println("Trim the word " + word4.trim());

        // Replacing characters
        String str1 = "Ilite";
        System.out.println("Original String " + str1);
        String str2 = "feeksforfeeks".replace('I' ,'E') ;
        System.out.println("Replaced I with E -> " + str2);
    }
}
```
*Output:*
```
String length = 12
Character at 3rd position = y
Substring Yah
Substring = Yahya
Concatenated string = YahyaHussain
Index of Share 6
Index of a = 8
Checking Equality false
Checking Equality true
Checking Equality false
If s1 = s2 false
Changing to lower Case yahyahussain
Changing to UPPER Case YAHYAHUSSAIN
Trim the word Learn Share Learn
Original String Ilite
Replaced I with E -> Elite
```

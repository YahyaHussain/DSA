# Introduction to Strings

Strings are defined as a stream of characters. 
Strings are used to represent text and are generally represented by enclosing text within quotes as: ```"This is a sample string!"```.

Different programming languages have different ways of declaring and using Strings.

In C/C++, Strings are defined as an array of characters. 
The difference between a character array and a string is that the string is terminated with a special character ‘\0’.

**Declaring Strings:** 
Declaring a string is as simple as declaring a one-dimensional array. 
Below is the basic syntax for declaring a string.
<br>
```char str_name[size];```

In the above syntax, str_name is any name given to the string variable and size is used to define the length of the string, i.e the number of characters strings will store. 
Please keep in mind that there is an extra terminating character which is the Null character ('\0') used to indicate the termination of string which differs strings from normal character arrays.

**Initializing a String:** 
A string can be initialized in different ways. We will explain this with the help of an example. 
Below is an example to declare a string with the name as str and initialize it with “YahyaHussain”.
<br>
```
1. char str[] = "YahyaHussain";

2. char str[50] = "YahyaHussain";

3. char str[] = {'Y','a','h','y','a','H','u','s','s','a','i','n','\0'};

4. char str[13] = {'Y','a','h','y','a','H','u','s','s','a','i','n','\0'};
```

**Printing a string array:** 
Unlike arrays we do not need to print a string, character by character. 
The C/C++ language does not provide an inbuilt data type for strings but it has an access specifier “%s” which can be used to directly print and read strings.

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
<br>
```YahyaHussain```

**Passing strings to function:** 
As strings are character arrays, so we can pass strings to function in the same way we pass an array to a function. 
Below is a sample program to do this:
<br>
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
<br>
```String is: YahyaHussain```









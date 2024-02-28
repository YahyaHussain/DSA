#  Introduction to Arrays 
An array is a collection of items of the same data type stored at contiguous memory locations. This makes it easier to calculate the position of each element by simply adding an offset to a base value, i.e., the memory location of the first element of the array (generally denoted by the name of the array).

For simplicity, we can think of an array as a fleet of stairs where on each step a value is placed (let's say one of your friends). Here, you can identify the location of any of your friends by simply knowing the count of the step that they are on.

**Remember:** "Location of the next index depends on the data type that we use".

![image](https://github.com/YahyaHussain/DSA/assets/91454966/740c33b4-1b77-4907-b4c5-6d217e60d63f)

The above image can be looked at as a top-level view of a staircase where you are at the base of the staircase. Each element can be uniquely identified by their index in the array (in a similar way where you could identify your friends by the step on which they were on in the above example).

## Defining an Array:
Array definition is similar to defining any other variable. There are two things that are needed to be kept in mind, the data type of the array elements and the size of the array. The size of the array is fixed and the memory for an array needs to be allocated before use, the size of an array cannot be increased or decreased dynamically.

Generally, arrays are declared as:
```
dataType arrayName[arraySize];
```

An array is distinguished from a normal variable by brackets $[$ and $]$.

## Accessing array elements:
Arrays allows to access elements randomly. Elements in an array can be accessed using indexes. Suppose an array named arr stores $N$ elements. Indexes in an array are in the range of $0$ to $N-1$, where the first element is present at $0^{th}$ index and consecutive elements are placed at consecutive indexes. Element present at $i^{th}$ index in the array $arr[]$ can be accessed as $arr[i]$.

The below image shows an array $arr[]$ of size $5$:

![image](https://github.com/YahyaHussain/DSA/assets/91454966/7e123801-db12-488e-93aa-537e35804f18)

**Advantages of using arrays:**
* Arrays allow random access of elements. This makes accessing elements by their position faster.
* Arrays have better [cache locality](https://en.wikipedia.org/wiki/Locality_of_reference) that can make a pretty big difference in performance.

**Examples:**
```
// A character array in C/C++/Java
char arr1[] = {'g', 'e', 'e', 'k', 's'};

// An Integer array in C/C++/Java
int arr2[] = {10, 20, 30, 40, 50};

// Item at i'th index in array is typically accessed
// as "arr[i]".  For example arr1[0] gives us 'g'
// and arr2[3] gives us 40.
```

## Searching in an Array
Searching for an element in an array means to check if a given element is present in the array or not. This can be done by accessing elements of the array one by one starting from the first element and checking whether any of the elements matches with the given element.

We can use loops to perform the above operation of array traversal and access the elements, using indexes.

Suppose the array is named $arr[]$ with size $N$ and the element to be searched is referred to as key. Below is the algorithm to perform the search operation in the given array.
```cpp
for (i = 0; i < N; i++)  {
  if (arr[i] == key)  {
    print "Element Found";
  }
  else  {
    print "Element not Found";
  }
}
```

**Time Complexity** of this search operation will be $O(N)$ in the worst case as we are checking every element of the array from $1^{st}$ to $last$, so the number of operations is $N$.

## Insertion and Deletion in Arrays

### Insertion in Arrays
Given an array of a given size. The task is to insert a new element in this array. There are two possible ways of inserting elements in an array:
* Insert elements at the end of the array.
* Insert element at any given index in the array.

**Special Case:**
A special case is needed to be considered is that whether the array is already full or not. If the array is full, then the new element can not be inserted.

Consider the given array is $arr[]$ and the initial size of the array is $N$, that is the array can contain a maximum of $N$ elements and the length of the array is $len$. That is, there are $len$ number of elements already present in this array.

#### Insert an element K at end in arr[]:
The first step is to check if there is any space left in the array for new element. To do this check,
```cpp
if (len < N)
  // space left
else
  // array is full
```

If there is space left for the new element, insert it directly at the end at position $len + 1$ and index $len$:
```
arr[len] = k;
```

**Time Complexity** of this insert operation is constant, i.e. $O(1)$ as we are directly inserting the element in a single operation.

#### Insert an element K at position, pos in arr[]:
The first step is to check if there is any space left in the array for new element. To do this check,
```cpp
if (len < N)
  // space left
else
  // array is full
```

Now, if there is space left, the element can be inserted. The index of the new element will be $idx = pos - 1$.

Now, before inserting the element at the index $idx$, shift all elements from the index $idx$ till end of the array to the right by $1$ place. This can be done as:
```cpp
for (i = len - 1; i >= idx; i--)  {
  arr[i+1] = arr[i];
}
```
After shifting the elements, place the element $K$ at index $idx$.
```
arr[idx] = K;
```
**Time Complexity** in worst case of this insertion operation can be linear i.e. $O(N)$ as we might have to shift all of the elements by one place to the right.

### Deletion in Arrays
To delete a given element from an array, we will have to first search the element in the array. If the element is present in the array then delete operation is performed for the element otherwise the user is notified that the array does not contains the given element.

Consider the given array is $arr[]$ and the initial size of the array is $N$, that is the array can contain a maximum of $N$ elements and the length of the array is $len$. That is, there are $len$ number of elements already present in this array.

#### Deleting an element K from the array arr[]:
Search the element $K$ in the array $arr[]$ to find the index at which it is present.
```cpp
for (i = 0; i < N; i++)  {
  if (arr[i] == K)
    idx = i; return;
  else
    Element not Found;
}
```
Now, to delete the element present at index $idx$, left shift all of the elements present after $idx$ by one place and finally reduce the length of the array by $1$.
```cpp
for (i = idx + 1; i < len; i++)  {
  arr[i - 1] = arr[i];
}
len = len-1;
```
**Time Complexity** in worst case of this insertion operation can be linear i.e. $O(N)$ as we might have to shift all of the elements by one place to the left.

## Array Rotation 
As the term rotation signifies, array rotation means to rotate the elements of an array by given positions.

Consider the below array:

![image](https://github.com/YahyaHussain/DSA/assets/91454966/a7c45442-8a66-4fdf-9f50-fa4f4fd3ad1b)

The above array is rotated counter-clockwise (towards left) by $2$ elements. After rotation, the array will be:

![image](https://github.com/YahyaHussain/DSA/assets/91454966/671f8102-4206-48d2-b882-41e3bc65360a)

Visually, the process of counter clock-wise array rotation (rotated by say $K$ elements) looks like:
* Shift all elements after $K^{th}$ element to the left by $K$ positions.
* Fill the $K$ blank spaces at the end of the array by first $K$ elements from the original array.

**Note:** The similar approach can also be applied for clockwise array rotation.

### Implementations

#### Simple Method: 
The simplest way to rotate an array is to implement the above visually observed approach by using extra space.
* Store the first $K$ elements in a temporary array say $temp[]$.
* Shift all elements after $K^{th}$ element to the left by $K$ positions in the original array.
* Fill the $K$ blank spaces at the end of the original array by the $K$ elements from the temp array.
```
Say, arr[] = [1, 2, 3, 4, 5, 6, 7], K = 2
1) Store first K elements in a temp array
   temp[] = [1, 2]
2) Shift rest of the arr[]
   arr[] = [3, 4, 5, 6, 7, 6, 7]
3) Store back the K elements from temp
   arr[] = [3, 4, 5, 6, 7, 1, 2]
```
**Time Complexity:** $O(N)$, where $N$ is the number of elements in the array. <br>
**Auxiliary Space:** $O(K)$ where $K$ is the number of places by which elements will be rotated.

#### Another Method (Without extra space):
We can also rotate an array by avoiding the use of temporary array. The idea is to rotate the array one by one $K$ times.
```
leftRotate (arr[], d, n)
start
  For i = 0 to i < d
    Left rotate all elements of arr[] by one
end
```
To rotate an array by $1$ position to the left:
* Store the first element in a temporary variable say temp.
* Left shift all elements after the first element by $1$ position. That is, move $arr[1]$ to $arr[0]$, $arr[2]$ to $arr[1]$ and so on.
* Initialize $arr[N-1]$ with $temp$.

**To rotate an array by K position to the left, repeat the above process K times.** <br>
Take the same example,
```
arr[] = [1, 2, 3, 4, 5, 6, 7], K = 2

Rotate arr[] one by one 2 times.

After 1st rotation: [2, 3, 4, 5, 6, 7, 1]
After 2nd rotation: [ 3, 4, 5, 6, 7, 1, 2]
```
**Time Complexity:** $O(N*K)$, where $N$ is the number of elements in the array and $K$ is the number of places by which elements will be rotated. <br>
**Auxiliary Space:** $O(1)$.

#### Juggling Algorithm:
This is an extension of the above method. Instead of moving one by one, divide the array in different sets, where number of sets is equal to GCD of $N$ and $K$ and move the elements within sets.

If GCD is $1$ as is for the above example array $(N = 7 and K = 2)$, then elements will be moved within one set only, we just start with $temp = arr[0]$ and keep moving $arr[I+d]$ to a$rr[I]$ and finally store temp at the right place.

Here is an example for $N = 12$ and $K = 3$. GCD of $N$ and $K$ is $3$:
```
Let arr[] be {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}

a) Elements are first moved in first set – (See below 
   diagram for this movement)
       arr[] after this step --> {4 2 3 7 5 6 10 8 9 1 11 12}
b) Then in second set.
       arr[] after this step --> {4 5 3 7 8 6 10 11 9 1 2 12}
c) Finally in third set.
       arr[] after this step --> {4 5 6 7 8 9 10 11 12 1 2 3}
```
![image](https://github.com/YahyaHussain/DSA/assets/91454966/380dff58-a9cd-4e2a-9036-b29160a423d6)

**Time Complexity:** $O(N)$, where $N$ is the number of elements in the array. <br>
**Auxiliary Space:** $O(1)$.

## Reversing an Array 
Reversing an array means reversing the order of elements in the given array.

### Problem:
Given an array of $N$ elements. The task is to reverse the order of elements in the given array.

**For Example:**
```
Input  : arr[] = {1, 2, 3}
Output : arr[] = {3, 2, 1}

Input :  arr[] = {4, 5, 1, 2}
Output : arr[] = {2, 1, 5, 4}
```

#### Iterative Solution
##### Method 1 (Using Temporary Array):
The idea is to first copy all of the elements of the given array in a temporary array. Then traverse the temporary array from end and replace elements in original array by elements of temp array.

This method will take extra space in order of $O(N)$.

##### Method 2 (Efficient):
This method is efficient then the above method and avoids using extra spaces. The idea is to traverse the array from both ends and keep swapping elements from both ends until middle of the array is reached.
```
1) Initialize start and end indexes as 
   start = 0, end = N-1
2) In a loop, swap arr[start] with arr[end] 
   and change start and end as follows :
       start = start + 1, 
       end = end – 1
```

**For Example:**

![image](https://github.com/YahyaHussain/DSA/assets/91454966/58b604ae-024c-4cf9-b5db-f661f842c170)

**Time Complexity:** $O(N)$, where $N$ is the number of elements in the array.

#### Recursive Solution
The recursive approach is almost similar to that of the method-2 of the iterative solution. Below is the recursive algorithm to reverse an array:
```
1) Initialize start and end indexes as 
   start = 0, end = n-1
2) Swap arr[start] with arr[end]
3) Recursively call reverse for rest of the array.
```
Below is the recursive function to reverse an array:
```cpp
void reverseArray (arr[], start, end)  {
  if (start >= end)
    return;

  // Swap elements at start and end
  temp = arr[start];
  arr[start] = arr[end];
  arr[end] = temp;

  // Recursive Function calling
  reverseArray (arr, start + 1, end - 1);
}
```
**Time Complexity:** $O(N)$, where $N$ is the number of elements in the array.

## Sliding Window Technique 
This technique shows how a nested for loop in few problems can be converted to single for loop and hence reducing the time complexity.

Let’s start with a problem for illustration where we can apply this technique:
```
Given an array of integers of size 'n'.
Our aim is to calculate the maximum sum of 'k' 
consecutive elements in the array.

Input  : arr[] = {100, 200, 300, 400}
         k = 2
Output : 700

Input  : arr[] = {1, 4, 2, 10, 23, 3, 1, 0, 20}
         k = 4 
Output : 39
We get maximum sum by adding subarray {4, 2, 10, 23}
of size 4.

Input  : arr[] = {2, 3}
         k = 3
Output : Invalid
There is no subarray of size 3 as size of whole
array is 2.
```

The Naive Approach to solve this problem is to calculate sum for each of the blocks of $K$ consecutive elements and compare which block has the maximum sum possible. The time complexity of this approach will be $O(n * k)$.

### Window Sliding Technique
The above problem can be solved in Linear Time Complexity by using Window Sliding Technique by avoiding the overhead of calculating sum repeatedly for each block of $k$ elements.

The technique can be best understood with the window pane in bus, consider a window of length $n$ and the pane which is fixed in it of length $k$. Consider, initially the pane is at extreme left i.e., at $0$ units from the left. Now, co-relate the window with array $arr[]$ of size $n$ and plane with $current_sum$ of size $k$ elements. Now, if we apply force on the window such that it moves a unit distance ahead. The pane will cover next $k$ consecutive elements.

Consider an array arr[] = {5 , 2 , -1 , 0 , 3} and value of $k = 3$ and $n = 5$

#### Applying sliding window technique :
* We compute the sum of first $k$ elements out of $n$ terms using a linear loop and store the sum in variable window_sum.
* Then we will graze linearly over the array till it reaches the end and simultaneously keep track of maximum sum.
* To get the current sum of block of $k$ elements just subtract the first element from the previous block and add the last element of the current block.

The below representation will make it clear how the window slides over the array.

This is the initial phase where we have calculated the initial window sum starting from index $0$. At this stage the window sum is $6$. Now, we set the $maximum_sum$ as $current_window$ i.e $6$.

![image](https://github.com/YahyaHussain/DSA/assets/91454966/dabee1a1-6311-4ff7-9aac-9399dcdf8bd4)

Now, we slide our window by a unit index. Therefore, now it discards $5$ from the window and adds $0$ to the window. Hence, we will get our new window sum by subtracting $5$ and then adding $0$ to it. So, our window sum now becomes $1$. Now, we will compare this window sum with the $maximum_sum$. As it is smaller we wont the change the $maximum_sum$.

![image](https://github.com/YahyaHussain/DSA/assets/91454966/fbb5f7c1-9cad-4941-b4c8-89dcaf0270da)

Similarly, now once again we slide our window by a unit index and obtain the new window sum to be $2$. Again we check if this current window sum is greater than the $maximum_sum$ till now. Once, again it is smaller so we don't change the $maximum_sum$.

Therefore, for the above array our $maximum_sum$ is $6$.

![image](https://github.com/YahyaHussain/DSA/assets/91454966/a1602e07-4e16-49ea-a064-ecfe1d57b1a9)


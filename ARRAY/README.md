# ARRAYS

- [Introduction](#introduction)
- [Types](#types)
  1. [One Dimensional](#single-dimensional-arrays)
  2. [Multi Dimensional](#multi-dimensional-arrays)
- [Applications](#applications)
- [Arrays in Various Programming Languages](#support-in-various-languages)
  1. [C](#c-language)
  2. [C++](#c-language-1)
  3. [Python](#python-language)
  4. [Java](#java-language)
- [Questions](#questions)
  1. [Array Rotation](#array-rotation)
  2. [Prefix and Postfix Sums](#prefix-and-postfix-sums)
  3. [Difference Arrays](#difference-array)

## INTRODUCTION

Arrays are one of the most basic data structure. Most programming languages provide built-in support for arrays.

Arrays are a collection of items stored in contigious memory locations.
Each element can be uniquely identified by their index in array.
Array indexing is mostly two ways:

- **0-based indexing**: The first element is at index 0 and then 1, 2, 3 and so on. Most programming language such as _C/C++_, _Python_, _Java_, _JavaScript_ etc supports this type of indexing.
- **1-based indexing**: The first element has index 1.
  Programming languages such as **Fortran**, **SASL**, **Matlab** etc supports this type of indexing.
- **n-based indexing**: The base index can be freely chosen. Usually choosed to allow negative indexes.

## TYPES

### Single Dimensional Arrays

- These are linear data structure which basically looks like a collection in which objects can be appended and deleted.
- Memory address of the base indexed element is called the base address or first address or foundation address.

### Multi Dimensional Arrays

- Multi dimensional array is a array with more than one dimension. It can also be defined as _array of arrays_.
- A two-dimensional array can be viewed as a Matrix.
- Usually an array can be n-dimensional but mostly a array with more than 3 dimensions are hectic to code and maintain for most programmers.

## APPLICATIONS

- Used to implement mathematical vectors and matrices.
- Many databases consists of 1-D array whose elements are records.
- Used to implement other data structures such as lists, heaps, queues, stacks etc.
- One or more large arrays are sometimes use to emulate in program dynamic memory allocation, particularly memory pool allocation. Historically, this has sometimes been the only way to allocate "dynamic memory" portably.
- Can be used for CPU Scheduling.
- Can be used in recursive functions.

## SUPPORT IN VARIOUS LANGUAGES

## C Language

How To Declare An Array?

```c
datatype arrayName[arraySize]
```

Example 1

```c
int array1[100]
char array2[100][100] // Multi Dimensional Array
```

> **NOTE**: The array size cannot be a variable in C language it needs to be a constant.

For Example:

```c
int n = 100;
int array1[n]; // Invalid Declaration

#define size 100
const n = 100;
int array2[n]; // Valid Declaration
int array3[size]; // Valid Declaration
```

How To Initialize An Array?

```c
char a[5] = {'a','f','g','h','r'};

char b[] = {'a','b','c','d'};
```

How To Access Array Elements.

```c
char a[5] = {'a','f','g','h','r'};
a[0] = 'q'; // Access using index value.

int i;
for(i = 0; i < 5; i++){
    printf("%d",a[i]);
}
```

How To Input And Output Array Elements?

```c
scanf("%d",&a[i]); // Input
printf("%d",a[i]); // Output
```

## C++ Language

How To Declare An Array?

```cpp
type arrayName[arraySize];
```

How To Initialize An Array?

```cpp
int arr[100]; // Size should be constant
int n = 100;
int arr[n]; // Since C++ 11 this type of declaration is supported
```

> Array initialization is same in C++ as C language.

How to Access Array Elements?

```cpp
char a[5] ={'a','b','c','d','e'};
a[2]='c' // Access using index value.
```

How To Input Or Output Array Elements?

```cpp
std::cin >> a[i]; // Input
std::cout << a[i]; // Output
```

## Python Language

Array is created in Python by importing array module to the python program.

```python
from array import *
arr = array(data_type, value_list)
arr1 = array('i',[1,2,3]) # Example
```

This type of array holds only homogenous data i.e. data with same datatype.

Arrays in python can also be implemented using lists.

```python
arr = [] # Declaration of empty list.
arr.append(6) # Adding element to arr.
arr2 = [1,'a',"str1",[1,2]] # List Initialization
                            # List within list can be used
                            # to create multi dimensional array
arr.append(5) # to append in the list
arr.pop(i) # to remove ith index element from the list
```

> Lists can store arbitarily heterogenous data. It is very flexible as it providez support for large number of buikt in functions.

How To Access Each Array Element?

```python
arr = [1,3,4,6,65,2]
for i in arr: # Access using for loop
  print(i)
for i in range(len(arr)): # Access using index values
  print(arr[i])
```

## Java Language

How To Declare An Array?

```java
type var_name[];  // Two valid ways of declaring
type[] var_name;  // array in Java
```

> The declaration only creates a variable array but no space is actually allocated. To actually alocate space use **new** operator. In Java all arrays are dynamically allocated.

How To Allocate Memory For New Array?

```java
int[] array1;
array1 = new int[size]; // Allocating Memory to array

int[] array2 = new int[100] // Combining two statements
```

Accessing Array Elements In Java.

```java
for (int i = 0; i < arr.length; i++){
System.out.println("Element at index " + i + " : "+ arr[i]);
} // Accessing each element using for loop.
```

Array Of Objects.

```java
Object array[] = new Object[100] // Same declaration method
                                 // as normal data type.
```

> In Java Array data type is itself an object. It also have various methods.

Creating Multi-Dimensional Arrays?

```java
int[][] arr = new int[2][1] // 2D Array
char[][][] arr2 = new char[2][2][3] // 3D Array
```

Input and Output Array Elements.

```java
import java.Scanner;
Scanner input = new Scanner(System.in);
int[] arr = new int[5];
for(int  i =0; i < 5; i++){
  arr[i] = input.nextInt(); // Input array elements
}

for (int i = 0; i < arr.length; i++){
System.out.println("Element at index " + i + " : "+ arr[i]);
} // Output each element
```

How To Copy An Array?

Java gives an function called **\*clone()** to copy contents of one array to other.

```java
int[] arr = new int[]{1,2,3,4,5};
int[] copyArray = arr.clone(); // Clone an array
```

## QUESTION

### _Array Rotation_

**Question:**

Given an array of integers and an integer d, perform left rotation on array d times.
An example of left rotation is [1,2,3,4,5] -> [2,3,4,5,1].

**Solution:**

If we rotate an array n times then we get same configurartion as original array.

So we need to only rotate **d%n** times.

Pseudocode for single left rotation can be like:

```
temp = a[1] // Store first element in a temporary variable.
for i = 1 : n
  a[i-1] = a[i] // Shift remaining elements left by 1
                // position starting from second element.
a[n] = temp; // Put the temporary variable in last of array.
```

**Similar Concepts:**

1. Right rotation of array: It is same as left rotation just with a small difference. Example: [1,2,3,4,5] -> [5,1,2,3,4]
2. Clockwise rotation is same as Right rotation.
3. Anti-Clockwise rotation is same as Left Rotation.

**Practice:**

1. [Hackerrank - Array's Left Rotation](https://www.hackerrank.com/challenges/ctci-array-left-rotation/problem)
2. [Hackerearth - Monk and Rotation](https://www.hackerearth.com/practice/data-structures/arrays/1-d/practice-problems/algorithm/monk-and-rotation-3/)
3. [CodeChef - Fun With Rotation](https://www.codechef.com/problems/ROTATION)

### _Prefix And Postfix Sums_

What is a Prefix Sum?

Let there be array arr = [1,2,3,6,7,8,9]

The prefix sum of ith element is defined as: sum(arr[0], arr[i])

**The sum of elements from 0 to i index** is defined as prefix sum of array arr of ith element.

The prefix sum array can be defined as array of prefix sums of array indexes.

Let array be arr[] of size n

Let prefix[] be prefix sum array.

So prefix[] array can be created as:

```
prefix[0] = arr[0]
for i = 1 : n-1
  prefix[i] = prefix[i-1] + arr[i]
```

Similarly concept for postfix sum can be said as

**Sum of elements from ith index to last element** can be said as postfix sum of ith index.

postfix[] can be created as follows:

```
postfix[n-1] = arr[n-1]
for i = n-2 : 0
  postfix[i] = postfix[i+1] + arr[i]
```

There are various applications of postfix and prefix sums in various questions.

**Practice Problems:**

1. [Equilibrium Index of Array](https://www.geeksforgeeks.org/equilibrium-index-of-an-array/)
2. [Find subarray with 0 sum](https://www.geeksforgeeks.org/find-if-there-is-a-subarray-with-0-sum/)
3. [Perfect Subarray](https://www.hackerearth.com/ru/practice/data-structures/arrays/1-d/practice-problems/algorithm/perfect-subarray-43560f46/)
4. [Find the Sum](https://www.codechef.com/LTIME76B/problems/PAIRSUM2/)

### _Difference Array_

A difference array can be used when we have to update a particular range of array.

If we are given an array of size **n** and need to update the value of elements in range [l, r] by same amount let it be x. I.E. perform a query of form _l r x_. For example:

Given array: [1,2,3,1,4,6,8,0]

Given Query: l = 2, r = 3, x = 5;

After update operation array would be: [1,2+5,3+5,1+5,4+5,6,8,0]

Suppose we need to perform **q** queries where each query is of form: l r x

And then print the resultant array after q queries we can use difference array.

_What is Difference Array_

A difference array is an array of same size as original array initially all elements initialized to 0.

diff[] - Difference Array

Initially difference array will look like diff = [0: 1, 0: 2, 0: 3, ..,0: l,..,0: r,..., 0: n]

> e: index representation is used.

For query: l r x

Update l'th index as diff[l] = diff[l] + x;

Update r+1'th index as diff[r+1] = diff[r+1] - x;

Now our array looks like diff = [0: 1, 0: 2, 0: 3, ..,x: l,..,-x: r,..., 0: n]

But our array should have looked like [0: 1, ..., x: l, x: l+1,...,x: r-1,x: r,0: r+1,...0: n]

Here's the trick

```
diff[1] = diff[1];
for i = 2:n
  diff[i] = diff[i-1] + diff[i];
```

After above code the arr would be as wanted.

Hence all the **q** queries can be performed as

1. Initialize Difference Array

```
for i = 1:n
  diff[i] = 0
```

2. Perform Queries

```
for p = 1:q
  read l
  read r
  read x
  diff[l] += x
  if(r+1 < n)
    diff[r+1] -= x
```

3. Update difference array to required value

```
for i = 2 : n
  diff[i] = diff[i] + diff[i-1]
```

We get the result of q queries update then at one update in O(n) time. Now update the original array.

**Practice**

1. [Hackerrank - Array Manipulation](https://www.hackerrank.com/challenges/crush/problem)
2. [GeeksForGeeks - Constant Time Array Update](https://www.geeksforgeeks.org/constant-time-range-add-operation-array/)

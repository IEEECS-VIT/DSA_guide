# ARRAYS

- [Introduction](#introduction)
- [Types](#types)
  1. [One Dimensional](#single-dimensional-arrays)
  2. [Multi Dimensional](#multi-dimensional-arrays)
- [Applications](#applications)
- [Arrays in Various Programming Languages](#support-in-various-languages)
  1. [C](#c-language)
  2. [C++](#c-langauge-1)
  3. [Python](#python-language)
  4. [Java](#java-language)
- [Questions](#questions)
  1. jsjjs
  2. sjjsj

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

Array D

Array is created in Python by importing array module to the python program.

```python
from array import *
a
```

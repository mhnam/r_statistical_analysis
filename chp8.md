# Chapter 8 Array

## Contents
1. [Concept of Array](#1-concept-of-array)
2. [Using Array](#2-using-array)
3. [Inter-Function Communication](#3-inter-function-communication)
4. [Two-Dimemsional Array](#4-two-dimensional-array)
5. [Practice] (#5-practice)

## 1. Concept of Array
### Motivation
To manage a number of students grade, which requires many identical variables for each students. 
It would be much convenient to make a set of variables by declare one group of varialbe with same type.

```c
//Inefficient Method
float score1=4.3;
float score2=4.0;
...
float score9=3.3;
float score10=3.0;

//Efficient Method
float score[10]={4.3, 4.0, ..., 3.3, 3.0};
```
### Concept
**Array** is a set of variables with same type. Each content of array can be access through its identifier and index.


_c.f._
1) ```cint A[10]``` has 10 integer variables with A[0] to A[9]
2) String is a array of characters with null character (_i.e._\0) at the end.
3) Array can be compose with many dimension. _i.e._ ```cA[3][3][3]``` has 3*3*3 number of variables in array A.
4) Address of array is assigned with the first memory of first component (_i.e._A[0]), and address of following
components are continuous.

### Classification
* **Fixed-length array** is array whose length is assigned as constant when program is written.

* **Variable-length array** is array whose length can be adjusted while the program is running, using ```cmalloc()``` function.


## 2. Using Array
### Declare and Define
```c
//declare
type-specifier array-name[constant-expression];

//declare and define
type-specifier array-name[constant-expression];
array-name[index]=compoents_i; //note that (index-1)th component would be assigned.
```

_e.g._
```c
#include <stdio.h>

int main(){

  int x[10];
  int t;
  
  for(t=0; t<100; ++t)
    x[t]=t;
  
  printf("x[5]=%d, x[55]=%d\n", x[5], x[55]);
  
  return 0;
}
```

_c.f._
1) 
2) 

_i.e._


### Access
```c
array-name[index];
```

_c.f._
If the index is bigger than declared constant-expression (_i.e._declared number of variables in the array), 
then the value of accessed components would not be spilt-out due to error, but there is also possibility to access 
garbage value.

### Initialization
```c
//Basic Initialization
type-specifier array-name[constant-expression]={component_1, component_2, ..., component_n};

//Initialization without size
type-specifier array-name[]={component_1, component_2, ..., component_n}; //then the array would be declared as n+1 automatically

//Initialization component-wise
type-specifier array-name[constant-expression];
array-name[index]=compoents_i; //note that (index-1)th component would be assigned.
```

_c.f._
1) Initialization is compulsory, because most array has garbage value when they are declared without initialize.

2) Initialization can be occured only when it is defined, and cannot assign whole array to another array. 
However, assigning component-wise is possible.

```c
int hand[5]={1,2,3,4,5}; //right
foot[5]={6,7,8,9,10}; //wrong
foot=hand; //wrong

foot[1]=hand[2]; //right
```

3) If the number of initialized components are less than the declared components, then left components would initialize as 0.

```c
int numbers[5]={3,7}; //then the last three components would be 0
```

4) To initialize all the components as zero, then assign ```{0}```.

```c
int lotsOfNumbers[1000]={0}; //then all the components would be 0
```

5) "Initialization without size" method is not recommendable unless the array is declared for string. If you let compiler to
decide the size of the array, then you should get the number of elements by following logic:

```c
short things[]={1,5,3,8};
int num_elements=sizeof(things)/sizeof(short);
```

### Exchanging Values
```c
temp=numbers[3];
numbers[3]=numbers[1];
numbers[1]=temp;
```

### Example
```c
#include <stdio.h>

int main(){
   int state;
   FILE *file=fopen("Test.txt", "w");
   
   if(file==NULL({
      printf("file open error!\n");
      return 1;
   }
   
   state=fclose(file);
   
   if(state!=0){
      printf("file close error!\n");
      return 1;
   }
   
   return 0;
}
```

## 3. Inter-Function Communication
### fscanf()
**fscanf** is a function used when we get input from the file.

```c
fscanf(FILE *stream, "format string", address list);
```

_e.g._
```c
n=fscanf(fp, "%d %d", &a, &b);
```

_c.f._
1) If we input ```1234 752 a``` as input, then n would have 2 as a return value.
2) If we feed ```1234 f a``` as input, then n would have 1 as a return value.
3) If we input ```<EOF>``` as input, then n would have EOF(==0) as a return value.

### fprintf()
**fprintf** is a function used when we give an output to the file.

```c
fprintf(FILE *stream, "format string", value list);
```

_e.g._
```c
n=fscanf(fp, "...%d...%x...", a, b);
```

_i.e._
1) ```fprintf(spReport, "\nWelcome to calculator.\n");```
2) ```fprintf(spReport, "\nThe answer is %6.2f\n", x);```

### getchar()
**getchar** is a function used when we read(feed an input) one character and return value.

```c
int getchar();
```

### fgetc()
**fgetc** is a function used when we read one character from a file stream and return value.

```c
int fgetc(FILE *stream);
```

_e.g._
```c
n=fgetc(fp);
```

### putchar()

*putchar** is a function used when we write(give an output) one character and return value.

```c
int putchar(int oneChar);
```

### fputc()
**fputc** is a function used when we write(give an output) one character to a file stream and return value.

```c
int fputc(int oneChar, FILE *stream);
```

_e.g._
```c
n=fscanf(oneChar, fp);
```


## 4. Two-Dimemsional Array


## 5. Practice
```c
#include <stdio.h>

int main(){

}
```

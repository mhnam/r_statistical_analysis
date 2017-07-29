# Chapter 4 Functions

## Contents
1. [Preliminaries](#1-preliminaries)
2. [Functions](#2-functions)
3. [User-defined Functions](#3-user-defined-functions)
4. [Standard Functions](#4-standard-functions)
5. [Scope](#5-scope)
6. [Practice](#6-practice)

## 1. Preliminaries
### Top-Down Desgin
**Top-Down Design** is ~

### Structured Programming
**Structured Programming**is ~

## 2. Functions
### Definition

Programs written in C language follows Top-Down Design method, and main function is the most typical function used in C language. Caller controls callee and it gives the result to caller function.

i.e. Main function calls following functions written in the program, and if the main function finishes it is controlled by Operating System (OS).

c.f. There are two types of function
- Standard functions: functions like _printf_ and _scanf_ are standard functions that is given by the library.
- User-defined functions: functions that user defined in the program.

### Pros
- Make problems simple.
- Can reuse the same algorithm.
- Can save the data in the program, because the local variables are only available when the function is called.

## 3. User-defined Functions
### Example
```c
#include <stdio.h>

int sum(int a, int b); //declaration of new function. the type of function and variable should be identical through the program, but the variable name can be different

int main()
{
     int x, y, s;
     x=2;
     y=3;
     s=sum(x,y); //function call
     printf("%d + %d = %d", x, y, s);
     
     return 0;
}

//function definition
int sum(int a, int b) //the shape of the function should be same as declaration stage
{
     return a+b; //return a+b to the sum(a,b) function, note that only one value can be returned.
}
```

### How to use
1) Declare: Write in the header of the program. Inform some informations - name; type of variables (the identifier can be different but the number and its type should be the same); return type - to the compiler.

```c
int sum(int a, int b);
```

2) Define: Write the tasks that the function need to do. Return statement can be empty if the return value is void.

c.f. Each function must be defined seperately.

```c
int sum(int a, int b)
{
     return a+b;
}
```

3) Call: Use the function, but note that the number and the type of calling parameter must be followed as it defined.

```c
s=sum(x,y);;
```

c.f. There are two types of calling methods - Pass by Value, Pass by Reference.
- Pass by Value: Give the real value to the function, usally used when the returned value is just one.

- Pass by Reference: Give the address of the refered value, usally used when the number of returned value is more than one.

## 4. Standard Functions
### Example: rand()
```c
#include <stdio.h>
#include 

int sum(int a, int b); //declaration of new function. the type of function and variable should be identical through the program, but the variable name can be different

int main()
{
     int x, y, s;
     x=2;
     y=3;
     s=sum(x,y); //function call
     printf("%d + %d = %d", x, y, s);
     
     return 0;
}

//function definition
int sum(int a, int b) //the shape of the function should be same as declaration stage
{
     return a+b; //return a+b to the sum(a,b) function, note that only one value can be returned.
}
```

### How to use
1) Include header files (library of functions): Must include header files to use the standard functions that are already defined by langauge developers, if not the compiler would not know what the functions are.

```c
#include <stdio.h> //std. input and output
#include <string.h> //regarding strings
#include <ctype.h> //regarding characters
#include <stdlib.h> //some utilities, e.g. system pause, randomization etc.
#include <time.h> //regarding time and dates
#include <math.h> //regarding maths, e.g. sqrt, pi etc.
```

2) Call: Use the function

```c
printf("%d", a)
```

### Standard Functions
1) <stdio.h> 

```c
printf();
scanf();
```

2) <math.h>

```c
double abs(double number);
double ceil(double number); //most smallest integer bigger or equal to the given number
double floor(double number); //most biggest integer smaller or equal to the given number
double pow(double x, double y); //power of x to the y
double sqrt(double number); //square root
```

3) <stdlib.h>

```c
int abs();
long labs();
void srand(unsigned int seed); //randome number from the given seed number
int rand(void); //random numbers from 0 to RAND_MAX
```

## 5. Scope
### Definition

**Scope** is a expression that consist of one operand without any operator

### Examples (1)
```c
x= ++a // increase a as 'a=a+1' then give the value to the variable x
```

### Examples (2)
```c
x= a++ // give the value to the variable x then increase a as 'a=a+1'
```

## 6. Practice
```c
#include <stdio.h>

int main()
{
     printf("size of character: %d", sizeof(char));
     printf("size of integer: %d", sizeof(int));
     printf("size of float: %d", sizeof(float));
     
     return 0;  
}
```

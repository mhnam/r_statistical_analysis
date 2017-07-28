# Chapter 2 Introduction to the C Language

## Contents
1. [Preliminaries](#1-preliminaries)
2. [Formatting](#2-formatting)
3. [Practice](#3-practice)

## 1. Preliminaries
### Identifier
**Identifier** is a name we give to each variables.

c.f.
- Start with english or underscore(_; usually for system variables)
- Use only english, numbers and under score
- Can be consist maximum 63 characters
- Can not use _keywords_ such as double, int, switch, if, else, return, static etc.

### Types
**Type** is a set of values and a set of operations that can be applied on those values.

i.e. There are mainly four types.

- void: literally _empty_ type, meaning _undefined_.
- integral
     - boolean: gets only two values - 0,1 - which represents true and false.
     - character: gets only one character as ASCII code (i.e. 1 byte; 0~255(2^8))
     - integer: gets integer numbers and this varies from short to long long integer. Each type varies in the size(size can be checked with the function '_sizeof( )_') of the memory.
- floating-point
     - real: varies from float to long double with different size.
     - imaginary
     - complex
- derived

### Variables and Constants

**Variables** are the space that gets value, while **constant** is the number that does not alter along the program.
```c
const float pi=3.141592 //constants
bool fact;
short maxItems;
long long national_debt;
float payRate=0; //variable initialization (this stage is indispensable if we use the same variable repeatedly) 
char code, kind;
int a, b;
```

### Others

There are three more things to note-Literal Constants, Defined Constants, Memory Contstants.

i.e. There are three types of constant

- Literal Constant: Non-named constants. This is generated if we just type a number.

```c
a=b*5; \\5 is literal constant
```

- Defined Constant: The constant that does not varies alond the program; Defined before the main function starts.

```c
#define SALES_TAX_RATE .0825
```

- Memory Constant: The constant that does not varies alond the program; Defined after the main function.

```c
const float Pi=3.141592;
```


## 2. Formatting
### Output Formatting
#### Printf
This is a function to print out the formatted variables.

```c
printf("...%d...%f...", int var, float var);
```

c.f. 

- Can be aligned by assigning the space for format
```c
printf("|%5d|",30); //30 will appear as | _ _ _ 3 0 |
printf("|%+5d|",30); //30 will appear as | _ _ + 3 0 |
```
- Printing format can be determined, i.e. how many decimals to presents
```c
printf("|%f|"3.1); //3.1 will appear as |3.100000|, i.e. six decimals are default
printf("|%10f|",3.1); //3.1 will appear as |_ _ 3.100000|, i.e. right alignment is default
printf("|%10.5f|",3.1); //3.1 will appear as |_ _ _ 3.10000|
printf("|%-10.5f|", 3.1); //3.1 will appear as |3.10000 _ _ _|, i.e. alignment can be changed by putting '-' sign
printf("|%5.3f|", 3.1); //if the space is less than decimal, the space number would be ignored; |3.100|
```
- Following examples are wrong:
```c
printf("%d %d %d\n", 44, 55); //would appear as 44, 55, 134513316 because the last format is not determined
printf("%d %d\n", 44, 55, 66); //would appear as 44, 55 because the last format is not assigned
float x=123.45;
printf("%d", x); //would appear as -1073741824 because x is not decimal number(integer)
```

### Input Formatting
#### Scanf
This is a function to get the values from user to the formatted variables.

```c
scanf("%d %f", &int var, &float var); //& represent the address of the variable
```

c.f. 

- The format inside the quotation mark "~" must be followed
```c
scanf("%d %d %d", &day, &month, &year); //the input should be feeded as '28 7 2017'
scanf("%d-%d-%d", %day, %month, &year); //the input should be feeded as '28-7-2017'
```

## 3. Practice
```c
#include <stdio.h>
#include<stdlib.h>

int main()
{
     int year, month, day;
     
     printf("\nPlease enter the date as day-month-year format:");
     scanf("%d-%d-%d", &day, %month, &year);
     printf("\t The date is %d-%d-%d", day, month, year);
     
     system("PAUSE");
     return 0;  
}
```


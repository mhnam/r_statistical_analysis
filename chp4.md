# Chapter 4 Functions

## Contents
1. [Preliminaries](#1-preliminaries)
2. [Expressions](#2-expressions)
3. [Precedence and Associativity](#3-precedence-and-associativity)
4. [Type Conversion](#4-type-conversion)
5. [Statements](#5-statements)
6. [Practice](#6-practice)

## 1. Preliminaries
### Top-Down Desgin
**Top-Down Design** is ~

### Structured Programming
**Structured Programming**is ~

## 2. Functions

Expression is a statement consist of variables, constants and operators.

i.e. There are six types of expression

### Primary Expression

**Primary Expression** is a expression that consist of one operand without any operator

- Idenrifier
```c
a
```

- Constants
```c
5, 'A', "Hello" //"Hello" is one string operand
```

- Parenthetical Expression
```c
(2+a-3) //There are several operators and operands but it is just one componet with respect to the parenthesis
```

### Postfix Expression
**Postfix Expression** is a expression that operator comes before operand. Calculation comes first before variable is refered.

```c
x= ++a // increase a as 'a=a+1' then give the value to the variable x
```

### Prefix Expression
**Prefix Expression** is a expression that operator comes after operand. The variable is refered before calculation

```c
x= a++ // give the value to the variable x then increase a as 'a=a+1'
```

```c
#include <stdio.h>

int main()
{
     int x=10;
     
     printf("%d, ", x++);
     printf("%d, ", x);
     printf("%d, ", --x);
     printf("%d", x);
     
     return 0;
}
```

Then the result would appear as 10, 11, 10, 10 while x would be 10, 11, 11, 10, 10

```c
#inclue <stdio.h>

int main()
{
     int x=10;
     
     printf("%d, ", x+1);
     printf("%d, ", x);
     printf("%d, ", x-1);
     printf("%d", x);
     
     return 0;
}
```

Then the result would appear as 11, 10, 9, 10 while x would be always 10 regardless of stages.

**_Note that prefix and postfix operator would give the expression much shorter and faster_**

### Unary Expression

### Binary Expression
**Binary Expression** is a expression that operator comes between two operand.

```c
a+7, 3+4, b-11 //additive expression (+, -)
10*12, a/4, 5%2 //multiplicative expression (*, /, %)
```

### Ternary Expression
**Ternary Expression** is a expression that has conditional operator.

```c
if a>b:
     max=a;
else:
     max=b;
```

### Assignment Expression
**Assignment Expression** is a expression that assign a value to a variable.

```c
a=7 //assign a value to variable a
a+=1 //called compound assignment; a=a+1
a=b=c=0 //assign 0 to c then assign c to b, b to a, and hence a, b and c are all 0
```

## 3. Precedence and Associativity
### Precedence
There is a order among operators

```c
2+3*4 //2+(3*4)
-b++ //-(b+1)
```

### Associativity
The direction of the operation among same precedence operator, _i.e._ multiplication and divide operator calculates from left to right, while assignment happens from right to left.

```c
3*8/4%4*5 //(((3*8)/4)%4)/5=((24/4)%4)/5=(6%4)/5=1/5=0.2
a+=b*c-=5 //c=c-5; b=b*(c-5); a=a+(b*(c-5))
```

## 4. Type Conversion
### Explicit Type Conversion
Convert variable type using cast operator.

```c
int a=7; //a would be considered as 7
a=(double)a; //a would be considered as 7.000000 from here
```

### Implicit Type Conversion
Variable is converted by the compiler automatically during operation followed by the type of assigned variable.

_c.f._ the rank of the conversion

bool > char > short > int > long > long long > float > double > long double

```c
int a=7;
float b=3.2;
double result1;
char result2;

result1=b*a; //'a' would be converted into float (7.000000) to be calculated with 'b'; then a*b would be converted from float to double to assigned into 'result1' because the type of result is bigger than float

result2=b*a //'a' would be converted into float (7.000000) to be calculated with 'b'; then a*b would be converted from float to integer to assigned into 'result2' because the type of result is smaller than float then the decimals below 10^(-1) would be lost with its precision
```

### NOTE
To check a size of each type can be checked from '_sizeof()_' function, and it can be used as follow:

```c
printf("size of character: %d", sizeof(char))
printf("size of integer: %d", sizeof(int))
printf("size of float: %d", sizeof(float))
```

## 5. Statements
**Statement** is an action that occurs in a program.

_c.f._

- Null: Statement that none of the action is needed; _e.g._ for(;;)
- Expression: Statement that written action is required; _i.e._ end with ;
- Return: Statement that returns a value to the function; _e.g._ return 0;
- Compound: Statement that ';' is not used; _e.g._ main()
- Conditional: for, if, else, while
- Labeled
- Switch
- Iterative
- Break: Used to get out from the loop
- Continue: Used when following stage is unnecessary
- Goto


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

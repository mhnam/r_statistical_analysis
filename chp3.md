# Chapter 3 Structure of a Program

## Contents
1. [More types](#1-more-types)
2. [Formatting](#2-formatting)
3. [Practice](#3-practice)

## 1. More types
### Decimal Integer
**Decimal Integer** is a default number bases that we have used in the previous chapter.

```c
0, 237, 18567, -789
```

### Octal Integer
**Octal Integer** is a number bases that start with '0' which number varies from 0 to 7 rather 0 to 9 in decimal integer.
This can be converted 3 bits of binary number. (i.e. 1111 > 1 / 111 > 1 / 7 > 017)

```c
017 /*1*8^1+7*8^0=15*/, 05643, 0234
```

### Hexadecimal Integer
**Hexadecimal Integer** is a number base that starts with '0x' which number varies from 0 to F (i.e. 0~9 and A, B, C, D, E, F)
This can be converted 4 bits of binary number. (i.e. 11111 > 1 / 1111 > 1 / 15 > 1 / F > 0x1F)

```c
0x12FF /* 1*16^3+2*16^2+15*16^1+15*16^0=4096+512+240+15=4863 */, 0x56ABC, 0x89A345
```

## 2. Expression

Expression is a statement consist of variables, constants and operators.

i.e. There are six types of expression

### Primary Expression

### Postfix Expression

### Prefix Expression

### Unary Expression

### Binary Expression

### Ternary Expression


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

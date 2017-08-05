# Chapter 5 Selection Making Decisions

## Contents
1. [Logical Data and Operator](#1-logical-data-and-operator)
2. [Two-Way Selection](#2-two-way-selection)
3. [Multiple Selection](#3-multiple-selection)
4. [Practice](#4-practice)

## 1. Logical Data and Operator
### Logical Data
**Logical Data** is used to represent the result of the decision which is mandatory for selection statement.

_c.f._

1) **Selection** is a method to switch the flow of the situation depending on decision.
2) C-programming does not have logical type which represent the result of the decision, while just use boolean type. 
(_i.e._0 for 'FALSE', otherwise for 'TRUE', note that \0 for string data)

### Operators
#### Logical Operator
Operator|Comments|Usage
--------|--------|-----
and|'TRUE' if both 'TRUE'|A&&B
or|'TRUE' if one of data is 'TRUE'|A\|\|B
not|'FALSE' if not is applied to 'TRUE', vice versa|!A


_i.e._

x|y|x&&y|x\|\|y|!x
-|-|----|------|--
0(FALSE)|0|0|0|1
0|1(TRUE)|0|1|1
1|0|0|1|0
1|1|1|1|0


_e.g._

```c
#include <stdio.h>

int main(){
  bool a=true;
  bool b=true;
  bool c=false;
  
  printf(" %2d AND %2d = %2d, \t", a, b, a&&b);
  printf(" %2d AND %2d = %2d, \t", a, c, a&&c);
  printf(" %2d AND %2d = %2d, \n", c, a, c&&a);
  printf(" %2d OR %2d = %2d, \t", a, b, a||b);
  printf(" %2d OR %2d = %2d, \t", a, c, a||c);
  printf(" %2d OR %2d = %2d, \n", c, c, c||c);
  
  printf(" NOT %2d AND %2d = %2d, \t", a, c, !a&&c);
  printf(" %2d AND NOT %2d = %2d, \n", a, c, a&&!c);
  
  return 0;
}
```

The result must look like as follows:

```c
1 AND 1 = 1,  1 AND 0 = 0,  0 AND 1 = 0,
1 OR 1 = 1,  1 OR 0 = 1,  0 OR 0 = 0,
NOT 1 AND 0 = 0,  1 AND NOT 0 = 1
```

#### Relation Operator

Operator|Comments|Usage
--------|--------|-----
\>|LHS is greater than RHS|A>B
<|LHS is less than RHS|A<B
\>=|LHS is great or equal to RHS|A\>=B
<=|LHS is less or equal to RHS|A<=B
==|LHS is equal to RHS|A==B
!=|LHS is not equal to RHS|A!=B

## 2. Two-Way Selection
### Two-Way Selection
**Two-Way Selection** is a basic decision statement which acts true action if the condition is true, otherwise acts false action.

### if-else

The grammar is as follows:

```c
if (conditional expression)
  TRUE ACTION;
else
  FALSE ACTION;
```

If there is more than two actions to take, use {}:

```c
if (conditional expression)
  {TRUE ACTIONS};
else
  FALSE ACTION;
```

If there is no actions required for else, SKIP IT or use NULL STATEMENT!:

```c
if (conditional expression)
  TRUE ACTION;
```

```c
if (conditional expression)
  TRUE ACTION;
else
  ;
```

_e.g._

```c
#include <stdio.h>

int main(){
  int a, b;
  printf("Please enter two integers:");
  scanf("%d %d", &a, &b);
  
  if (a<=b)
    printf("%d <= %d", a, b);
  else
    printf("%d > %d", a, b);
    
  return 0;
}
```

### nested-if
**Nested-if** statement is used when there is multiple conditions to check under if-else statement.

The grammar is as follows:
```c
if (conditional expression 1)
  if (conditional expression 2)
    TRUE ACITION;
  else
    FALSE ACTION 1;
else
  FALSE ACTION 2;
```

You can **_not_** skip _else_ statement when you use multiple _if_ selections:
```c
if (conditional expression 1)
  if (conditional expression 2)
    TRUE ACITION;
else
  FALSE ACTION 2;
```

Then FALSE ACTION 2 happens if the conditional expression 1 is _TRUE_ and conditional expression 2 is _FALSE_ rather just conditional expression 1 is _FALSE_ as intended.


For this case (_i.e._ when just conditional expression 1 is _FALSE_), nothing happens, because computer recognize the final else statement is _NULL_.


This happens because computer recognize the if-else as a pair with the nearest one unless using {}. Hence we can solve the problem as follows:
```c
if (conditional expression 1)
  {if (conditional expression 2)
    TRUE ACITION;}
else
  FALSE ACTION 2;
```


_c.f._ Note that FALSE ACTION 1 and FALSE ACTION 2 does not happens at the same time.


_e.g._

```c
#include <stdio.h>

int main(){
  int a, b;
  printf("Please enter two integers:");
  scanf("%d %d", &a, &b);
  
  if (a<=b)
    if (a<b)
      printf("%d <= %d", a, b);
    else
      printf("%d == %d", a, b);
  else
    printf("%d > %d", a, b);
    
  return 0;
}
```


## 3. Multiple Selection
### switch
**switch** statement is used when each case can be classified into some integer numbers.

The grammar as is follows:
```c
switch(expression){ //expression is the variable that make
  case CONSTANT 1: STATEMENT 1; break; //"break" statement is not mandatory thing but if there is 
  case CONSTANT 2: STATEMENT 2; break;
  case CONSTANT 3: STATEMENT 3; break;
  ...
  default: STATEMENT n; //not compulsary but all case must be classified above 
}
```


_e.g._
```c
#include <stdio.h>

char score_to_grade(int score);

int main(){
  int score;
  char grade;
  
  printf("Enter the test score(0-100):");
  scanf("%d", &score);
  
  grade=score_to_grade(score);
  printf("The grade is: %c\n", grade);
  
  return 0;
}

char score_to_grade(int score){
  char grade;
  int temp;
  
  temp=score/10;
  switch(temp){
    case 10:
    case 9: grade='A'; break;
    case 8: grade='B'; break;
    case 7: grade='C'; break;
    case 6: grade='D'; break;
    default: grade='F'; //if the case does not belong to anyother above, than the default value is 'F'
  }
  
  return grade;
}
```

### else if

## 4. Practice

---NOT COMPLETED BELOW THIS LINE---

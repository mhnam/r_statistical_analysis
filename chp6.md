# Chapter 6 Repetition

## Contents
1. [What is Loop?](#1-what-is-loop?)
2. [While Loop](#2-while-loop)
3. [For Loop](#3-for-loop)
4. [Do while Loop](#4-do-while-loop)
5. [Practice](#5-practice)

## 1. What is Loop?
### Loop
**Loop** is a logic that helps to repeat til the condition holds.

### Classifications
#### Pretest vs. Post-test Loops
* **Pretest Loop** is a loop that check the condition first before practicing the loop. Hence, if the condition does not hold at
the first, then the loop never occurs.


* **Post-test Loop** is a loop that check the condition after practicing the loop. Hence, even the condition does not hold at
the first, the loop occurs at least once.

#### Event vs. Count controlled Loops
* **Event controlled Loop** is a loop whose condition is depend on whether some event is happened or not.


* **Count controlled Loop** is a loop whose condition is depend on whether the number of loop occurance is greater or less than some number.

### Preliminaries
#### Initialization
Since the loop is a logic that repeats the same actions, the value in the variable may mixed up. Hence, we need to initialize the variable to some value (_e.g._ 0 or 1) to clean the variable.

#### Updating
To prevent infinite loop, we need to control the loop occurance with some methods - event or count control. If the loop is
controlled by counting the number of loop occurance, we need to update some variable - so called counter - each time whenever
the loop occured.

## 2. While Loop
**while loop** is used when each case can be classified into some integer numbers.

The grammar as is follows:
```c
switch(expression){
  case CONSTANT 1: STATEMENT 1; break;
  case CONSTANT 2: STATEMENT 2; break;
  case CONSTANT 3: STATEMENT 3; break;
  ...
  default: STATEMENT n; //not compulsary but all case must be classified above 
}
```


_c.f._
1) _expression_ is the variable that referred to classified into each case.
2) _break_ statement is not mandatory but if there is not, then the statement would keep continue even the program should be ended. However you can use this property to determine the starting point of the program and keep the program to work on.
3) Can not use relation expression (_e.g._ >, <, >=, <=, ==, !=)


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


## 3. For Loop
**switch** statement is used when each case can be classified into some integer numbers.

The grammar as is follows:
```c
switch(expression){
  case CONSTANT 1: STATEMENT 1; break;
  case CONSTANT 2: STATEMENT 2; break;
  case CONSTANT 3: STATEMENT 3; break;
  ...
  default: STATEMENT n; //not compulsary but all case must be classified above 
}
```


_c.f._
1) _expression_ is the variable that referred to classified into each case.
2) _break_ statement is not mandatory but if there is not, then the statement would keep continue even the program should be ended. However you can use this property to determine the starting point of the program and keep the program to work on.
3) Can not use relation expression (_e.g._ >, <, >=, <=, ==, !=)


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

## 4. Do while Loop
**switch** statement is used when each case can be classified into some integer numbers.

The grammar as is follows:
```c
switch(expression){
  case CONSTANT 1: STATEMENT 1; break;
  case CONSTANT 2: STATEMENT 2; break;
  case CONSTANT 3: STATEMENT 3; break;
  ...
  default: STATEMENT n; //not compulsary but all case must be classified above 
}
```


_c.f._
1) _expression_ is the variable that referred to classified into each case.
2) _break_ statement is not mandatory but if there is not, then the statement would keep continue even the program should be ended. However you can use this property to determine the starting point of the program and keep the program to work on.
3) Can not use relation expression (_e.g._ >, <, >=, <=, ==, !=)


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

## 5. Practice
This section is yet to be completed.

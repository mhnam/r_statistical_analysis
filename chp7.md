# Chapter 7 File IO

## Contents
1. [What is Loop?](#1-what-is-loop)
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
**while loop** is loop that repeats until condition holds.


The grammar as is follows:
```c
while(conditional expression){
  STATEMENTS;
}
```


_e.g._
```c
#include <stdio.h>

int main(){
  int height=0;
  int days=0;
  int depth;
  
  printf("Inputthe depth of well(cm): ");
  scanf("%d", &depth);
  
  while(height<depth){
    height=height+50;
    days=days+1;
  }
  
  printf("Total days: %d\n", days);
  
  return 0;
}
```


## 3. For Loop
**for loop** is loop that repeats until counter reach a certain value.

The grammar as is follows:
```c
for(initializaiton; limit-test expression; updating expression){
  STATEMENTS;
}

```

For loop can be used inside the loop as follows:
```c
#include <stdio.h>

int main(){
  int i, j;

  for (i=2; i<3; i++){
    for(k=1; j<10; j++)
      printf("%d * %d = %d\n, i, j, i*j);
  }
  
  return 0;
}
```

_c.f._
1) some part of expression in paranthesis can be skipped at least the number of semi colon.
2) {} can be skipped if there is only one statement.
3) For loop can be used inside the loop

_e.g._
```c
#include <stdio.h>

int main(){
  int i;
  int sum=0; //initialization
  
  for(i=0; i<=10; i++)
    sum+=i;
    
  printf("sum= %d\n", sum);
  
  return 0;
}
```

### For vs. While Loop
Every _for loop_ can be changed into _while loop_, and viceversa

_e.g._ For Loop
```c
#include <stdio.h>

int main(){
  int i=1, sum=0;
  
  for(i=1; i<20; i++){
    scanf("%d", &a);
    sum+=a;
  }
  
  printf("Total: %d", &sum);
  
  return 0;
}
```

_e.g._ While Loop
```c
#include <stdio.h>

int main(){
  int i, sum=0;
  
  while(i<20){
    scanf("%d", &a);
    sum+=a;
    i++;
  }
  
  printf("Total: %d", &sum);
  
  return 0;
}
```
```c

## 4. Do while Loop
**do while loop** is loop that repeats until condition holds as while loop, but actions occur before checking the condition. (_i.e._ Post-test Loop)

The grammar as is follows:
```c
do{
  STATEMENTS;
}while(conditional expression);

```

_c.f._
1) The loop occurs at least once, even the condition does not holds.
2) There must be a semi-colon after _while_ statement.


_e.g._
```c
#include <stdio.h>

int main(){
  int total=0;
  int val=0;
  
  do{
    printf("Input number(Quit:0): "); //To give an opportunity to quit the program at the begining, we use "do-while loop"
    scanf("%d", &val);
    total+=val;
  }while(val!=0);
 
  printf("Total: %d\n", total);
  
  return 0;
}
```


### Related Statements
* **break** is a statement which is used to quit the most inner loop.

* **continue** is a statement which is used to skip the latter parts of the loop, and go to the conditional expression.


_e.g._
```c
#include <stdio.h>

int main(){
  int i, sum=0;
  
  for(i=0;;i++){
    if(i>=100) //add until the number is less than 100
      break;
    else if(i%4==0) //do not add multiples of 4
      continue;
    sum+=i; //if the condition does not holds, add to "sum"
  }
  printf("sum=%d\n", sum);
}
```


## 5. Practice
This section is yet to be completed.

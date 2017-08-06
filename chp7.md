# Chapter 7 File IO

## Contents
1. [Preliminaries](#1-preliminaries)
2. [Open and Close](#2-open-and-close)
3. [Functions](#3-functions)
4. [Practice](#4-practice)

## 1. Preliminaries
### Files
**File** is a unit of external data such as internal hard disk, keyboard, monitor, disk file and paper file.

### Streams
Data is given and written by **Stream** while all its source and destination is **File**.

#### Classification of Streams
* **Text Stream** is consist of continuous characters and line is seperated by "\n"

* **Binary Stream** is consist of continuous integer and real numbers. Since it does not need to be converted as Text Stream, its speed is much faster.

#### Handling Stream and File
1) Create a Stream

This stage is declaring a stream name (_i.e._ spData in this caes) what we are going to use whenever we need to access the file. 

```c
FILE* spData; //FILE is a structure type to read and write on file, and *(asterisk) represent that spData is a pointer type which has a address of stream.
```

2) Open a File

By using ```c fopen() ``` function, we can open the file we are using

```c
FILE* fopen(const char* filename, const char* mode); //fopen is a function to open a file, whose inputs are file name and opening mode.
```

3) Use the Stream name

We can use pointer ```c *spData ``` to access the file using all functions

4) Close the Stream

By using ```c fclose() ``` function, we can break the connection between the file and the stream.

```c
fclose(FILE* stream)
```

#### System-Created Streams
C provides **System-Created Streams** to communicate with turminal (_i.e._ Keyboard or monitor). Hence, we do not need to close (_c.f._ Operating System will do it for you)

_e.g._
```c
//<stdio.h> has following streams:

stdin(standard input)
stdout(standard output)
stderr(standard error)
```

## 2. Open and Close
### File Opening
```c
fopen("filename", "mode");
```

_c.f._
1) **filename** is a string that consit of file name and file location.
2) **mode** is a string information that determines the usage of the file.
    * read mode: Open existing file for reading, while file marker would be positioned at the begining of the file
    * writing mode: Open new file for writing, even there are something in the file, file marker would position at the begining of file
    * append mode: Open existing file for writing or create new file if there is no file exists. The file marker would position at the end of the file.

_i.e._
```c
fpTempData=fopen("TEMPS.DAT", "w"); //open "TEMPS.DAT" in the working directory in 'writing' mode
fpTempData=fopen("A:\\TEMPS.DAT", "w"); //open "TEMPS.DAT" in a A drive in 'writing' mode
```

_e.g._
```c
#include <stdio.h>
...
{
int main()
  FILE* spData;
  ...
  //spData would point (inform the address of) the opened file "MYDATA.DAT" with 'writing' mode
  spData=fopen("MYDATA.DAT", "w"); 
  ...
}//main

### File Closing
```c
fopen("filename", "mode");
```

_c.f._
1) **filename** is a string that consit of file name and file location.
2) **mode** is a string information that determines the usage of the file.

_i.e._
```c
fpTempData=fopen("TEMPS.DAT", "w"); //open "TEMPS.DAT" in the working directory in 'writing' mode
fpTempData=fopen("A:\\TEMPS.DAT", "w"); //open "TEMPS.DAT" in a A drive in 'writing' mode
```

_e.g._
```c
#include <stdio.h>
...
{
int main()
  FILE* spData;
  ...
  //spData would point (inform the address of) the opened file "MYDATA.DAT" with 'writing' mode
  spData=fopen("MYDATA.DAT", "w"); 
  ...
}//main

```

## 3. Functions
###
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

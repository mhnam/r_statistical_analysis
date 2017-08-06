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

We can use pointer ```*spData``` to access the file using all functions

4) Close the Stream

By using ```fclose()``` function, we can break the connection between the file and the stream.

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
    * read mode (r): Open existing file for reading, while file marker would be positioned at the begining of the file
    * writing mode (w): Open new file for writing, even there are something in the file, file marker would position at the begining of file
    * append mode (a): Open existing file for writing or create new file if there is no file exists. The file marker would position at the end of the file.

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

### File Closing
```c
fclose(FILE* stream);
```

_i.e._
```c
res=fclose(fpTempData); //sever the connection between fpTempData with "TEMPS.DAT"
```

_e.g._
```c
#include <stdio.h>
...
{
int main()
  FILE* spData;
  int res
  ...
  spData=fopen("MYDATA.DAT", "w"); 
  ...
  //Give the result to variabe 'res' whether the file is properly closed. (i.e. 0 for success)
  res=fclose(spData);
  if(res!=0){
   printf("The file does not closed\n");
   return 1;
  }
}//main

```

### Error on File Opening and Closing
#### Opening
Opening fails:

1) When there is no identical filename

2) When there is no disk storage for create new file

_c.f._ The ```FILE* stream``` would have NULL if the opening procedure failed

#### Closing
If closing fails, fclose function would give EOF(_i.e._ 1) to the variable.

_c.f._ Use if logic to inform user whether the file is properly closed.

_e.g._


## 3. Functions
### fscanf()

### fprintf()

### Others

## 4. Practice
This section is yet to be completed.

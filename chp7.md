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
FILE *spData; //FILE is a structure type to read and write on file, and *(asterisk) represent that spData is a pointer type which has a address of stream.
```

2) Open a File

By using ```c fopen() ``` function, we can open the file we are using

```c
FILE *fopen(const char *filename, const char *mode); //fopen is a function to open a file, whose inputs are file name and opening mode.
```

3) Use the Stream name

We can use pointer ```*spData``` to access the file using all functions

4) Close the Stream

By using ```fclose()``` function, we can break the connection between the file and the stream.

```c
fclose(FILE *stream);
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
  FILE *spData;
  ...
  //spData would point (inform the address of) the opened file "MYDATA.DAT" with 'writing' mode
  spData=fopen("MYDATA.DAT", "w"); 
  ...
}//main
```

### File Closing
```c
fclose(FILE *stream);
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
  FILE *spData;
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
Opening fails when there is:

1) no identical filename in your storage.

2) no disk storage available to create new file.

_c.f._ The ```FILE *stream``` would have NULL if the opening procedure failed

#### Closing
If closing fails, fclose function would give EOF(_i.e._ 1) to the variable.

_c.f._ Use if logic to inform user whether the file is properly closed.

_e.g._
```C
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

## 3. Functions
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

### Summary

Usage  | Keyboard/Monitor | File
----- | ---------------- | ----
output char | ```int putchar(int c)``` | ```int fputc(int c, FILE *stream)```
input char | ```int getchar(void)``` | ```int fgetc(FILE *stream)```
output string | ```int puts(const char* s)``` | ```int fputs(const char* s, FILE *stream)```
input string | ```char* gets(int c)``` | ```char* fgets(char* s, int n, FILE *stream)```
output formatted | ```int printf(const* format, ...)``` | ```int fprintf(FILE *stream, const char *format, ...)```
input formatted | ```int scanf(const char* format, ...)``` | ```int fscanf(FILE *stream, const char *format, ...)```

## 4. Practice
```c
#include <stdio.h>

int main(){
   FILE *ifp, *ofp;
   char name[20];
   int age;
   double height;
   int res;
   
   ifp=fopen("s.txt", "r");
   if(ifp==NULL){
      prinf("input file open error!\n");
      return 1;
   }
   
   ofp=fopen("b.txt", "w");
   if(ofp==NULL){
      prinf("output file open error!\n");
      return 1;
   }
   
   while(1){
      res=fscanf(ifp, "%s%d%lf", name, &age, &height);
      if(res==EOF) break;
      fprintf(ofp, %.1lf %d %s\n", height, age, name);
   }
   
   fclose(ifp);
   fclose(ofp);
}
```

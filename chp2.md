# Chapter 2
Introduction to the C Language

## Contents
1. [Preliminaries](#1-preliminaries)
2. [Formatting](#2-formatting)
3. [Void](#3-void)
4. [Void](#4-void)

## 1. Preliminaries
1) Identifier: Identifier is a name we give to each variables.
c.f. Start with english or underscore(_; usually for system variables); Use only english, numbers and under score

2) Types: Type is a set of values and a set of operations that can be applied on those values.
i.e. There are mainly four types; void, integral(boolean, character, integer), floating-point(real, imaginary, complex) and derived.

c.f. Boolean: gets only two values-0,1 which represents true and false.
     Character: gets only one character as ASCII code (i.e. 0~255)
     Integer: gets integer numbers and this varies from short integer to long long integer. Each type varies in the size of the memory.
     Floating-Point: gets floating numbers and this varies from real, imaginary and complex number.

3) Variables and Constants: Variables are the space that gets value, while constant is the number that does not varies along the program.
e.g.
> const float pi=3.141592 //constants
> bool fact;
> short maxItems;
> longlong national_debt;
> float payRate=0; //variable initialization
> char code, kind;
> int a, b;

4) Others: There are three more things to note-Literal Constants, Defined Constants, Memory Contstants.
i.e. Literal Constant: Non-named constants. This is generated if we just type a number.
     Defined Constant: The constant that does not varies alond the program; Defined before the main function starts.
     Memory Constant: The constant that does not varies alond the program; Defined after the main function.

## 2. Formatting
### Output Formatting
#### Printf
This is a function to print out the formatted variables.

> printf("...%d...%f...", int var, float var)

c.f. Can be aligned 

c.f.Can be 

c.f. Caution

### Input Formatting
#### Scanf


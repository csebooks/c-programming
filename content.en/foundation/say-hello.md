
---
title: 'Say Hello'
weight: 2
references:
    videos:
        - youtube:WXY-r9s0_Rg
        - youtube:o8XEzZBjQTs
    links:
        - https://www.w3schools.com/c/
        - https://www.programiz.com/c-programming
    books:
        - b1:
            title: Let Us C By Kanetkar Yashavant 
            url: https://www.google.co.in/books/edition/Let_Us_C/HrlIEAAAQBAJ?hl=en&gbpv=1

---


# The First C Program

Once armed with the knowledge of variables, constants & keywords, the next logical step would be to combine them to form instructions. However, instead of this, we would write our first C program now. Once we have done that we would see in detail the instructions that it made use of. The first program is very simple. It calculates simple interest for a set of values representing principal, number of years and rate of interest.
```c
/* Calculation of simple interest */
/* Author: gekay Date: 25/06/2016 */
 
 #include <stdio.h>

int main() {
    int p, n;
    float r, si;
    
    p = 1000;
    n = 3;
    r = 8.5;
    
    /* formula for simple interest */
    si = p * n * r / 100;
    
    printf("%f\n", si);
    
    return 0;
}

```
Let us now understand this program in detail.

## Form of a C Program

Form of a C program indicates how it has to be written/typed. There are certain rules about the form of a C program that are applicable to all C programs. These are as under:
- Each instruction in a C program is written as a separate statement.
- The statements in a program must appear in the same order in which we wish them to be executed.
- Blank spaces may be inserted between two words to improve the readability of the statement.
- All statements should be in lower case letters.
- C has no specific rules for the position at which a statement is to be written in a given line. That’s why it is often called a free-form language.
- Every C statement must end with a semicolon ( **; )**. Thus **;** acts as a statement terminator.

## Comments in a C Program

Comments are used in a C program to clarify either the purpose of the program or the purpose of some statement in the program. It is a good practice to begin a program with a comment indicating the purpose of the program, its author and the date on which the program was written.

Here are a few things that you must remember while writing comments in a C program:
- Comment about the program should be enclosed within /* */. Thus, the first two statements in our program are comments.
- Sometimes it is not very obvious as to what a particular statement in a program accomplishes. At such times it is worthwhile mentioning the purpose of the statement (or a set of statements) using a comment. For example:
```c
/* formula for simple interest */
si = p * n * r / 100 ;
```
- Any number of comments can be written at any place in the program. For example, a comment can be written before the

statement, after the statement or within the statement as shown below.
```c
/* formula */si = p * n * r / 100;
 si = p * n * r / 100; /* formula */
 si = p * n * r / /* formula */ 100 ;
```
- The normal language rules do not apply to text written within **/* .. */**. Thus we can type this text in small case, capital or a combination. This is because the comments are solely given for the understanding of the programmer or the fellow programmers and are completely ignored by the compiler.
- Comments cannot be nested. This means one comment cannot be written inside another comment. For example,
```c
/* Cal of SI /* Author: gekay date: 25/06/2016 */*/
```

is invalid.
- A comment can be split over more than one line, as in,
```c
/* This comment has three lines in it */
```

Such a comment is often called a multi-line comment.
- ANSI C permits comments to be written in the following way:
```c
// Calculation of simple interest // Formula
```
## What is main() ?


**main( )** forms a crucial part of any C program. Let us understand its purpose as well as its intricacies.
- **main( )** is a function. A function is nothing but a container for a set of statements. In a C program there can be multiple functions. To begin with, we would concentrate only on those programs which have only one function. The name of this function has to be **main( )**, it cannot be anything else. All statements that belong to **main( )** are enclosed within a pair of braces { } as shown below.

int main( ) { statement 1 ; statement 2 ; statement 3 ; }
- The way functions in a calculator return a value, similarly, functions in C also return a value. **main( )** function always returns an integer value, hence there is an **int** before **main( )**. The integer value that we are returning is 0. 0 indicates success. If for any reason the statements in **main( )** fail to do their intended work we can return a non-zero number from **main( )**. This would indicate failure.
- Some compilers like Turbo C/C++ even permit us to return nothing from **main( )**. In such a case we should precede it with the keyword **void**. But this is non-standard way of writing the **main( )** function. We would discuss functions and their working in great detail in Chapter 8.

## Variables and their Usage

We have learnt constants and variables in isolation. Let us understand their significance with reference to our first C program.
- Any variable used in the program must be declared before using it. For example,
```c
int p, n ;/* declaration */
float r, si ;/* declaration */
si = p * n * r / 100 ; /* usage */
```
- In the statement,
```c
si = p * n * r / 100 ;
```
***** and **/** are the arithmetic operators. The arithmetic operators available in C are **+**, **\-**, ***** and **/**. C is very rich in operators. There are as many as 45 operators available in C.

Surprisingly there is no operator for exponentiation... a slip, which can be forgiven considering the fact that C has been developed by an individual, not by a committee.

## printf( ) and its Purpose

C does not contain any instruction to display output on the screen. All output to screen is achieved using readymade library functions. One such function is **printf(** **)**. Let us understand this function with respect to our program.
- Once the value of **si** is calculated it needs to be displayed on the screen. We have used **printf( )** to do so.
- For us to be able to use the **printf( )** function, it is necessary to use **#include <stdio.h>** at the beginning of the program. **#include** is a preprocessor directive. Its purpose will be clarified in Chapter 8. For now, use it whenever you use **printf( )**.
- The general form of **printf( )** function is,
```c
printf ( "<format string>", <list of variables> ) ;

<format string> can contain,
```
**%f** for printing real values **%d** for printing integer values **%c** for printing character values

In addition to format specifiers like **%f**, **%d** and **%c**, the format string may also contain any other characters. These characters are printed as they are when **printf( )** is executed.
- Given below are some more examples of usage of **printf( )** function:
```c
    printf("%f\n", si);
    printf("%d %d %f %f\n", p, n, r, si);
    printf("Simple interest = Rs. %f\n", si);
    printf("Principal = %d\nRate = %f\n", p, r);
```
The output of the last statement would look like this...
```c
Principal = 1000 Rate = 8.500000
```
What is ‘\\n’ doing in this statement? It is called newline and it takes the cursor to the next line. Therefore, you get the output split over two lines. ‘\\n’ is one of the several Escape Sequences available in C. These are discussed in detail in Chapter 18. Right now, all that we

can say is ‘\\n’ comes in handy when we want to format the output properly on separate lines.
- **printf(** **)** can not only print values of variables, it can also print the result of an expression. An expression is nothing but a valid combination of constants, variables and operators. Thus, 3, 3 + 2, c and a + b * c – d all are valid expressions. The results of these expressions can be printed as shown below.
```c
printf ( "%d %d %d %d", 3, 3 + 2, c, a + b * c – d ) ;
```
Note that **3** and **c** also represent valid expressions.

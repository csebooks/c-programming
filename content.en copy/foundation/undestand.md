
---
title: 'Lets understand C'
weight: 3

---

# Compilation and Execution

Once you have written the program you need to type it and instruct the machine to execute it. To type your C program you need another program called Editor. Once the program has been typed it needs to be converted to machine language instructions before the machine can execute it. To carry out this conversion we need another program called Compiler. Compiler vendors provide an Integrated Development Environment (IDE) which consists of an Editor as well as the Compiler.

There are several IDEs available in the market targeted towards different operating systems and microprocessors. Details of which IDE to use, how to procure, install and use it are given in Appendix A. Please go through this appendix and install the right IDE on your machine before you try rest of the programs in this book.

{{< diagram "Exucution of C program" "w-75" >}}
```goat
     
  ┌─────────────────┐ 
  │source code in c │  Preprocessing
  └────────┬────────┘ 
┌──────────▽─────────┐
|Expanded Source code|  Compiling
└──────────┬─────────┘
    ┌──────▽───────┐    
    │Assembly code │ Assembling    
    └──────┬───────┘   
    ┌──────▽─────┐    
    │Object code │ Assembling    
    └──────┬─────┘    
    ┌──────▽────────┐      
    │Exucutable file│ Linking     
    └───────────────┘  


```
{{< /diagram >}}


# Receiving Input
In the program discussed above we assumed the values of **p**, **n** and **r** to be 1000, 3 and 8.5. Every time we run the program we would get the same value for simple interest. If we want to calculate simple interest for some other set of values then we are required to make the relevant changes in the program, and again compile and execute it. Thus the program is not general enough to calculate simple interest for any set of values without being required to make a change in the program. Moreover, if you distribute the EXE file of this program to somebody he would not even be able to make changes in the program. Hence it is a good practice to create a program that is general enough to work for any set of values.

To make the program general, the program itself should ask the user to supply the values of **p**, **n** and **r** through the keyboard during execution. This can be achieved using a function called **scanf( )**. This function is a counter-part of the **printf( )** function. **printf( )** outputs the values to the screen whereas **scanf( )** receives them from the keyboard. This is illustrated in the program given below.
```c
/* Calculation of simple interest */
/* Author: gekay Date: 25/06/2016 */
#include <stdio.h>

int main() {
    int p, n;
    float r, si;
    
    printf("Enter values of p, n, r: ");
    scanf("%d %d %f", &p, &n, &r);
    
    si = p * n * r / 100;
    
    printf("%f\n", si);
    
    return 0;
}

```
The first **printf(** **)** outputs the message ‘Enter values of p, n, r’ on the screen. Here we have not used any expression in **printf( )** which means that using expressions in **printf( )** is optional.

Note the use of ampersand (**&**) before the variables in the **scanf(** **)** function is a must. **&** is an ‘Address of’ operator. It gives the location number (address) used by the variable in memory. When we say **&a**, we are telling **scanf( )** at which memory location should it store the value supplied by the user from the keyboard. The detailed working of the **&** operator would be taken up in Chapter 6.

Note that a blank, a tab or a new line must separate the values supplied to **scanf( )**. A blank is created using a spacebar, tab using the Tab key and new line using the Enter key. This is shown below.


Ex.:  The three values separated by blank:
```c
1000 5 15.5
```
Ex.:  The three values separated by tab:
```c
1000 5 15.5
```
Ex.:  The three values separated by newline:
```c
1000 5 15.5
```
So much for the tips. How about writing another program to give you a feel of things. Here it is...
```c
/* Just for fun. Author: Bozo */
#include <stdio.h>

int main() {
    int num;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    printf("Now I am letting you in on a secret...\n");
    printf("You have just entered the number %d\n", num);
    
    return 0;
}

```
## Summary 
- Constant is an entity whose value remains fixed.
- Variable is an entity whose value can change during course of execution of the program.
- Keywords are special words whose meaning is known to the Compiler.
- There are certain rules that must be followed while building constants or variables.
- The three primary constants and variable types in C are integer, float and character.
- We should not use a keyword as a variable name.
- Comments should be used to indicate the purpose of the program or statements in a program.
- Comments can be single line or multi-line.
- Input/output in C can be achieved using scanf( ) and printf( ) functions.

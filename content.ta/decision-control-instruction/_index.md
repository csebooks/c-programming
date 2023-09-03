---
title: " Decision Control Instruction"
weight: 3
references:
    videos:
        - youtube:hjoHjnAUs4s
---

# Contents

We all need to alter our actions in the face of changing circumstances. If the weather is fine, then I will go for a stroll. If the highway is busy, I would take a diversion. If the pitch takes spin, we would win the match. If you join our WhatsApp group, I would send you interesting videos. If you like this book, I would write the next edition. You can notice that all these decisions depend on some condition being met.

C language too must be able to perform different sets of actions depending on the circumstances. In the programs written in Chapters 1 and 2, we used sequence control instruction in which the various statements are executed sequentially, i.e., in the same order in which they appear in the program. In many Programming situations, we want one set of instructions to be executed in one situation, and a different set in another situation. In C Programming, such situations are dealt with using a decision control instruction.

## The if - else Statement
C uses the keywords if and else to implement the decision control instruction. The general form of this statement looks like this:

```c
{
if (this condition is true)
statement1;
else
statement2;
}
```

The condition following the keyword if is always enclosed within a pair of parentheses. If the condition is true, then statement1 is executed. If the
condition is not true, then statement2 is executed. The condition is expressed using ‘relational’ operators in C. These operators allow us to
compare two values. Figure 3.1 shows how they look and how they are evaluated in C


| this expression | is true of |
| ----------- | ----------- |
|  x == y  | x is equal to y |
|  x != y  | x is not equal to y |
|  x < y   | x is less then y |
|  x > y   | x is greater then y |
|  x <= y   | x is less then or equal to y |
|  x >= y   | x is greater then or equal to y |


Here == is the equality operator and != the inequality operator. Note that = is used for assignment, whereas, == is used for comparison of two
quantities. Let us now understand with the help of an example how if - else and the relational operators are used in a program.

Example 3.1: While purchasing certain items, a discount of 10% is offered if the quantity purchased is more than 1000. If quantity and price per
item are input through the keyboard, write a program to calculate the total expenses.

Given below is a program that implements this logic.

```c
/* Calculation of total expenses */

#include <stdio.h>

int main()
{
int qty, dis;
float rate, tot;
printf (“Enter quantity and rate”);
scanf (“%d %f”, &qty, &rate);
if (qty > 1000)
dis = 10;
else
dis = 0;
tot = (qty * rate) - (qty * rate * dis / 100);
printf (“Total expenses = Rs. %f\n”, tot);
return 0;
}
```

Here is some sample interaction with the program.

Enter quantity and rate 1200 15.50 

Total expenses = Rs. 16740.000000

Enter quantity and rate 200 15.50 

Total expenses = Rs. 3100.000000

In the first run of the program, the condition evaluates to true, as 1200 (value of qty) is greater than 1000. Therefore, the variable dis, which was earlier set to 0, now gets a new value 10. Using this new value, total expenses are calculated and printed.

In the second run, the condition evaluates to false, as 200 (the value of qty) isn’t greater than 1000. Thus, dis, which is earlier set to 0, remains 0, and hence the expression after the minus sign evaluates to zero, thereby offering no discount.


Note how the statements after if and after else are indented using tab. We would adopt this style throughout this book. Also note that if we do not
wish to do anything when the condition fails, we can drop the else and the statement belonging to it.

## Multiple Statements within if - else

It may so happen that in a program we want more than one statement to be executed when the expression following if is satisfied. If such multiple
statements are to be executed, then they must be placed within a pair of braces, as illustrated in the following example:

Example 3.2: In a company an employee is paid as under:

If his basic salary is less than Rs. 1500, then HRA = 10% of basic salary and DA = 90% of basic salary. If his salary is either equal to or above Rs.
1500, then HRA = Rs. 500 and DA = 98% of basic salary. If the employee’s salary is input through the keyboard write a program to find his gross
salary.
The program that implements this logic is given below.
```c
/* Calculation of gross salary */

#include <stdio.h>

int main()
{
float bs, gs, da, hra;
printf (“Enter basic salary”);
scanf (“%f”, &bs);
if (bs < 1500)
{
hra = bs * 10 / 100;
da = bs * 90 / 100;
}
else
{
hra = 500;
da = bs * 98 / 100;
}
gs = bs + hra + da;
printf (“gross salary = Rs. %f\n”, gs);
return 0;
}
```
Figure 3.2 would help you understand the flow of control in the program.


Figure 3.2

A few points worth noting about the program…

(a) The group of statements after the if up to and not including the else is called an ‘if block’. Similarly, the statements after the else form the ‘else block’.

(b) Notice that the else is written exactly below the if . The statements in the if block and those in the else block have been indented to the right. This formatting convention is followed throughout the book to enable you to understand the working of the program better.

(c) Had there been only one statement to be executed in the if block and only one statement in the else block, we could have dropped the pair of braces.

(d) The default scope of if as well as else is the statement immediately after them. To override this default scope, a pair of braces, as shown in the above example, must be used.

## Nested if-else s

It is perfectly alright if we write another if-else construct within either the if block or the else block. This is called ‘nesting’ and is shown in the following code fragment:

```c
if (i == 1)
printf (“You would go to heaven !\n”);
else
{
if (i == 2)
printf (“Hell was created with you in mind\n”);
else
printf (“How about mother earth !\n”);
}
```


Note that the second if-else construct is nested in the first else block. If the condition in the first if is false, then the condition in the second if ischecked. If it is false as well, then the second else is executed.

You can observe how each time a if-else construct is nested within another if-else construct, it is also indented to add clarity to the program.Inculcate this habit of indentation; otherwise you would end up writing programs which nobody (you included) can understand easily at a later date.Note that whether we indent or do not indent the program, it doesn't alter the flow of execution of instructions in the program.

In the above program, an if-else occurs within the ‘ else block’ of the first if statement. Similarly, in some other program, an if-else may occur in the ‘
if block’ as well. There is no limit on how deeply the if s and the else s can be nested.

## A Word of Caution

Though usually a condition is used in if statement, any valid expression will also do. Thus all the following if statements are valid.


```c
if (3 + 2 % 5)
printf (“This works”);
if (a = 10)
printf (“Even this works”);
if (-5)
printf (“Surprisingly even this works”);
```


Note that in C a non-zero value is considered to be true, whereas a 0 is considered to be false. In the first if , the expression evaluates to 5 and since 5 is non-zero it is considered to be true. Hence the printf() gets executed.

In the second if , 10 gets assigned to a so the if is now reduced to if (a) or if (10) . Since 10 is non-zero, it is true hence again printf() goes to work.

In the third if , -5 is a non-zero number, hence true. So again printf() goes to work. In place of -5 even if a float like 3.14 were used, it would becon sidered to be true. So the issue is not whether the number is integer or float, or whether it is positive or negative. Issue is whether it is zero or non-zero.

Another common mistake while using the if statement is to write a semicolon ( ; ) after the condition, as shown below.

```c
scanf (“%d”, &i);
if (i == 5);
printf (“You entered 5\n”);
The; makes the compiler to interpret the statement as if you have written it in following manner:
if (i == 5);
printf (“You entered 5\n”);
```

Here, if the condition evaluates to true, the; (null statement, which does nothing on execution) gets executed, following which the printf() gets executed. If the condition fails, then straightaway the printf() gets executed. So irrespective of whether the condition evaluates to true or false, printf() is bound to get executed. Remember that compiler would not point out this as an error, since as far as the syntax is concerned, nothing has gone wrong but the logic has certainly gone awry.

## Programs

Problem 3.1

If cost price and selling price of an item is input through the keyboard, write a program to determine whether the seller has made profit or incurred loss. Also determine how much profit he made or loss he incurred.

Program

```c
/* Calculate profit or loss */

#include <stdio.h>

int main()
{
float cp, sp, p, l;
printf (“\nEnter cost price and selling price:”);
scanf (“%f %f”, &cp, &sp);
p = sp - cp;
l = cp - sp;
if (p > 0)
printf (“The seller made a profit of Rs. %f\n”, p);
if (l > 0)
printf (“The seller incurred loss of Rs. %f\n”, l);
if (p == 0)
printf (“There is no loss, no profit\n”);
return 0;
}
```
Output
Enter cost price and selling price: 25 15

The seller incurred loss of Rs. 10.000000


Problem 3.2
Any integer is input through the keyboard. Write a program to find out whether it is an odd number or even number.

Program
```c
/* Check whether a number is even or odd */

#include <stdio.h>

int main()
{
int n;
printf (“\nEnter any number:”);
scanf (“%d”, &n);
if (n % 2 == 0)
printf (“The number is even\n”);
else
printf (“The number is odd\n”);
return 0;
}
```
Output

Enter any number: 45

The number is odd

Problem 3.3

Any year is input through the keyboard. Write a program to determine whether the year is a leap year or not.

Program
```c
/* Check whether a year is leap or not */

#include <stdio.h>

int main()
{
int yr;
printf (“\nEnter a year:”);
scanf (“%d”, &yr);
if (yr % 100 == 0)
{
if (yr % 400 == 0)
printf (“Leap year\n”);
else
printf (“Not a Leap year\n”);
}
else
{
if (yr % 4 == 0)
printf (“Leap year\n”);
else
printf (“Not a leap year\n”);
}
return 0;
}
```
Output

Enter a year: 2020

Leap year

## Exercises

[A] What will be the output of the following programs:

(a)
 ```c
#include <stdio.h>
int main()
{
int a = 300, b, c;
if (a >= 400)
b = 300; c = 200;
printf (“%d %d\n”, b, c);
return 0;
}
```
(b) 
```c
#include <stdio.h>
int main()
{
int x = 10, y = 20;
if (x == y);
printf (“%d %d\n”, x, y);
return 0;
}
```
(c) 
```c
#include <stdio.h>
int main()
{
int x = 3;
float y = 3.0;
if (x == y)
printf (“x and y are equal\n”);
else
printf (“x and y are not equal\n”);
return 0;
}
```
(d) 
```c
#include <stdio.h>
int main()
{
int x = 3, y, z;
y = x = 10;
z = x < 10;
printf (“x = %d y = %d z = %d\n”, x, y, z);
return 0;
}
```
(e)
```c
#include <stdio.h>
int main()
{
int i = 65;
char j = ‘A’;
if (i == j)
printf (“C is WOW\n”);
else
printf (“C is a headache\n”); return 0;
}
```

[B] Point out the errors, if any, in the following programs:

(a) 
```c
#include <stdio.h>
int main()
{
float a = 12.25, b = 12.52;
if (a = b)
printf (“a and b are equal\n”);
return 0;
}
```
(b) 
```c
#include <stdio.h>
int main()
{
int j = 10, k = 12;
if (k >= j)
{
{
k = j;
j = k;
}
}
return 0;
}
```
(c) 
```c
#include <stdio.h>
int main()
{
if (’X’ < ’x’)
printf (“ascii value of X is smaller than that of x\n”);
}
```
(d)
```c
#include <stdio.h>
int main()
{
int x = 10;
if (x >= 2) then
printf (“%d\n”, x);
return 0;
}
```
(e) 
```c
#include <stdio.h>
int main()
{
int x = 10, y = 15;
if (x % 2 = y % 3)
printf (“Carpathians\n”);
}
```
(f) 
```c
#include <stdio.h>
int main()
{
int a, b;
scanf (“%d %d”, a, b);
if (a > b);
printf (“This is a game\n”);
else
printf (“You have to play it\n”);
return 0;
}
```

[C] State whether the following statements are True or False:

(a); is a valid statement.

(b) Ifs can be nested.

(c) If there are multiple statements in if or else block they should be enclosed within a pair of {}.

(d) If can occur within an if block but not in the else block.

(e) By default there is only one statement in if block and only one in the else block.

(f) Nothing happens on execution of a null statement.

[D] Match the following pairs:

[E] Which of the following are valid ifs:

(a) if (-25) 

(b) if (3.14)

(c) if (a)

(d) if (a + b)

(e) if (a >= b)

[F] Attempt the following questions:

(a) A five-digit number is entered through the keyboard. Write a program to obtain the reversed number and to determine whether the original andreversed numbers are equal or not.

(b) If ages of Ram, Shyam and Ajay are input through the keyboard, write a program to determine the youngest of the three.

(c) Write a program to check whether a triangle is valid or not, when the three angles of the triangle are entered through the keyboard. A triangle is valid if the sum of all the three angles is equal to 180 degrees.

(d) Write a program to find the absolute value of a number entered through the keyboard.

(e) Given the length and breadth of a rectangle, write a program to find whether the area of the rectangle is greater than its perimeter. For example, the area of the rectangle with length = 5 and breadth = 4 is greater than its perimeter.

(f) Given three points (x1, y1) , (x2, y2) and (x3, y3) , write a program to check if all the three points fall on one straight line.

(g) Given the coordinates (x, y) of center of a circle and its radius, write a program that will determine whether a point lies inside the circle, on the circle or outside the circle. (Hint: Use sqrt() and pow() functions) (h) Given a point (x, y) , write a program to find out if it lies on the X-axis, Y-axis or on the origin.

(i) According to Gregorian calendar, it was Monday on the date 01/01/01. If any year is input through the keyboard write a program to find out what
is the day on 1st January of this year.

**Kannotes**

1.Using if-else statement

2.Using conditional operators

3.Using the switch statement

General forms of decision control instruction:
The default scope of if and else statement is only the next statement. So, to execute multiple statements they must be written in a pair of braces.

Condition is built using relation operators <, >, <=, >=, ==, != An if need not always be associated with an else. However, an else must always be associated with an if An if-else statement can be nested inside another if-else statement a = b is assignment. a == b is comparison In if (a == b == c) result of a == b is compared with c If a condition is true it is replaced by 1, if it false it is replaced by 0 Any non-zero number is true, 0 is false; is a null statement. It doesn't do anything on execution

---
title: 'What is C'
weight: 1

---

# What is C?

C is a programming language developed at AT & T’s Bell Laboratories of USA in 1972. It was designed and written by a man named Dennis Ritchie. In the late seventies C began to replace the more familiar languages of that time like PL/I, ALGOL, etc. No one pushed C. It wasn’t made the ‘official’ Bell Labs language. Thus, without any advertisement, C’s reputation spread and its pool of users grew. Ritchie seems to have been rather surprised that so many programmers preferred C to older languages like FORTRAN or PL/I, or the newer ones like Pascal and APL. But, that’s what happened.

Possibly why C seems so popular is because it is reliable, simple and easy to use. Moreover, in an industry where newer languages, tools and technologies emerge and vanish day in and day out, a language that has survived for more than three decades has to be _really_ good.

An opinion that is often heard today is C has been already superseded by languages like C++, C# and Java, so why bother to learn C today

I seriously beg to differ with this opinion. There are several reasons for this. These are as follows:

![Realworld Applications of C](applications-of-c.png)


- C++, C# or Java make use of a principle called Object Oriented Programming (OOP) to organize the program. This organizing principle has lots of advantages to offer. But even while using this organizing principle you would still need a good hold over the language elements of C and the basic programming skills. So it makes more sense to first learn C and then migrate to C++, C# and Java. Though this two-step learning process may take more time, but at the end of it you will definitely find it worth the trouble.
- Major parts of popular operating systems like Windows, UNIX, Linux and Android are written in C. This is because even today when it comes to performance (speed of execution) nothing beats C. Moreover, if one is to extend the operating system to work with new devices one needs to write device driver programs. These programs are exclusively written in C.
- Mobile devices like Smartphones and Tablets have become rage of today. Also, common consumer devices like microwave ovens, washing machines and digital cameras are getting smarter by the day. This smartness comes from a microprocessor, an operating system and a program embedded in these devices. These programs not only have to run fast but also have to work in limited amount of memory. No wonder that such programs are written in C. With these constraints on time and space, C is the language of choice while building such operating systems and programs.
- You must have seen several professional 3D computer games where the user navigates some object, like say a spaceship and fires bullets at the invaders. The essence of all such games is speed. Needless to say, such games won’t become popular if they take a long time to move the spaceship or to fire a bullet. To match the expectations of the player the game has to react fast to the user inputs. This is where C language scores over other languages. Many popular gaming frameworks (like DirectX) have been built using C language.
- At times one is required to very closely interact with the hardware devices. Since C provides several language elements that make this interaction feasible without compromising the performance, it is the preferred choice of the programmer.

I hope that these are very convincing reasons why you should adopt C as the first, and a very important step, in your quest for learning programming.

# Getting Started with C

Communicating with a computer involves speaking the language the computer understands, which immediately rules out English as the language of communication with computer. However, there is a close analogy between learning English language and learning C language. The classical method of learning English is to first learn the alphabets used in the language, then learn to combine these alphabets to form words, which, in turn, are combined to form sentences and sentences are combined to form paragraphs.

Learning C is similar and easier. Instead of straight-away learning how to write programs, we must first know what alphabets, numbers and special symbols are used in C, then how using them, constants, variables and keywords are constructed, and finally, how are these combined to form an instruction. A group of instructions would be combined later on to form a program. This is illustrated in the Figure 1.1.


{{< diagram "Steps in learning C Language" "w-50" >}}
```goat
  ┌─────────────────┐ 
  │Alphabets,Digits,│ 
  │Special symbols  │ 
  └────────┬────────┘ 
┌──────────▽─────────┐
│Constants,Variables,│
│Keywords            │
└──────────┬─────────┘
    ┌──────▽─────┐    
    │Instructions│    
    └──────┬─────┘    
       ┌───▽───┐      
       │Program│      
       └───────┘      

```
{{< /diagram >}}

## The C Character Set

A character denotes any alphabet, digit or special symbol used to represent information. 
| Character | Range |
| ----------- | ----------- |
| Alphabets          | A, B, ….., Y, Z a, b, ….., y, z |
| Digits             | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9    |
| Special symbols    | ~ ‘ ! @ # % ^ & * ( ) \_ - + = | \\ { } [ ] : ; " ' < > , . ? / $ |

## Constants, Variables and Keywords

The alphabets, digits and special symbols when properly combined form constants, variables and keywords. Let us now understand the meaning of each of them. A constant is an entity that doesn’t change, whereas, a variable is an entity that may change. A keyword is a word that carries special meaning.

In any C program we typically do lots of calculations. The results of these calculations are stored in computer’s memory. Like human memory, the computer’s memory also consists of millions of cells. The calculated values are stored in these memory cells. To make the retrieval and usage of these values easy, these memory cells (also called memory locations) are given names. Since the value stored in each location may change, the names given to these locations are called variable names. Let us understand this with the help of an example.

Consider the memory locations shown in Figure 1.3. Here 3 is stored in a memory location and a name **x** is given to it. Then we have assigned a new value 5 to the same memory location **x**. This would overwrite the earlier value 3, since a memory location can hold only one value at a time.

Since the location whose name is **x** can hold different values at different times **x** is known as a variable (or a variable name). As against this, 3 or 5 do not change, hence are known as constants.

In programming languages, constants are often called literals, whereas, variables are called identifiers.

Now that we understand the constants and the variables, let us see what different types of constants and variables exist in C.

## Types of C Constants

C constants can be divided into two major categories:

{{< diagram "Types of C Constants" >}}
```goat
                                          +-------------+                                                          
                             +----------- |  Constants  |-------------+                                            
                             |            +-------------+             |                                            
                             |                                        |                                            
                      +-------------+                          +-------------+                                     
                      |  Primary    |                          |  Secondary  |                                     
                      +-------------+                          +-------------+           
                             |                                        |
                             |                                        |                                            
                             |                                        |                                            
                             |                                        |                                            
                      +-------------+                           +-------------+                                    
                      |  Integer    |                           | Array       |                                    
                      |  Charactor  |                           | Pointer     |                                    
                      |  Real       |                           | Structure   |                                    
                      +-------------+                           | Union,      |                                    
                                                                | Enum etc    |                                    
                                                                +-------------+                                   -
                                                                                    
```
{{< /diagram >}}

At this stage, we would restrict our discussion to only Primary constants, namely, Integer, Real and Character constants. Let us see the details of each of these constants. For constructing these different types of constants, certain rules have been laid down. These rules are as under:

## Rules for Constructing Integer Constants
- An integer constant must have at least one digit.
- It must not have a decimal point.
- It can be either positive or negative.
- If no sign precedes an integer constant, it is assumed to be positive.
- No commas or blanks are allowed within an integer constant.
- The allowable range for integer constants is -2147483648 to +2147483647.

Truly speaking, the range of an Integer constant depends upon the compiler. For compilers like Visual Studio, gcc, it is -2147483648 to +214748364, whereas for compilers like Turbo C or Turbo C++ the range is -32768 to +32767.

```c
Ex:  426
+782
-8000
-7605
```
## Rules for Constructing Real Constants

Real constants are often called Floating Point constants. The real constants could be written in two forms—Fractional form and Exponential form.

Following rules must be observed while constructing real constants expressed in fractional form:

- A real constant must have at least one digit.
- It must have a decimal point.
- It could be either positive or negative.
- Default sign is positive.
- No commas or blanks are allowed within a real constant.

```c
Ex.:  +325.34
426.0 
-32.76
-48.5792
```
The exponential form is usually used if the value of the constant is either too small or too large. It, however, doesn’t restrict us in any way from using exponential form for other real constants.

In exponential form the real constant is represented in two parts. The part appearing before ‘e’ is called mantissa, whereas the part following ‘e’ is called exponent. Thus 0.000342 can be written in exponential form as 3.42e-4 (which in normal arithmetic means 3.42 x 10-4).

Following rules must be observed while constructing real constants expressed in exponential form:
- The mantissa part and the exponential part should be separated by a letter e or E.
- The mantissa part may have a positive or negative sign.
- Default sign of mantissa part is positive.
- The exponent must have at least one digit, which must be a positive or negative integer. Default sign is positive.
- Range of real constants expressed in exponential form is -3.4e38 to 3.4e38.

```c
Ex: 
+3.2e-5
4.1e8
-0.2E+3
-3.2e-5
```
## Rules for Constructing Character Constants
- A character constant is a _single_ alphabet, a single digit or a single special symbol enclosed within single inverted commas.
- Both the inverted commas should point to the left. For example, ’A’ is a valid character constant whereas ‘A’ is not.

```c
Ex.:  'A'
'I'
'5'
'='
```
## Types of C Variables

A particular type of variable can hold only the same type of constant. For example, an integer variable can hold only an integer constant, a real variable can hold only a real constant and a character variable can hold only a character constant. The rules for constructing different types of constants are different. However, for constructing variable names of all types, the same set of rules applies. These rules are given below.

## Rules for Constructing Variable Names
- A variable name is any combination of 1 to 31 alphabets, digits or underscores. Some compilers allow variable names whose length could be up to 247 characters. Still, it would be safer to stick to the rule of 31 characters. Do not create unnecessarily long variable names as it adds to your typing effort.
- The first character in the variable name must be an alphabet or underscore ( _ ).
- No commas or blanks are allowed within a variable name.
- No special symbol other than an underscore (as in **gross_sal**) can be used in a variable name.

```c
Ex.:  si_int 
pop_e_89
```
Since, the maximum allowable length of a variable name is 31 characters, an enormous number of variable names can be constructed using the above-mentioned rules. It is a good practice to exploit this abundant choice in naming variables by using meaningful variable names.

Thus, if we want to calculate simple interest, it is always advisable to construct meaningful variable names like **prin**, **roi**, **noy** to represent Principle, Rate of interest and Number of years rather than using the variables **a**, **b**, **c**.

The rules for creating variable names remain same for all the types of primary and secondary variables. Naturally, the question follows... how is C able to differentiate between these variables? This is a rather simple matter. C compiler is able to distinguish between the variable names by making it compulsory for you to declare the type of any variable name that you wish to use in a program. This type declaration is done at the beginning of the program. Examples of type declaration statements are given below.

```c
Ex.:  int si, m_hra;
float bassal;
char code ;
```
## C Keywords

Keywords are the words whose meaning has already been explained to the C compiler (or in a broad sense to the computer). There are only 32 keywords available in C. Figure 1.5 gives a list of these keywords for your ready reference. A detailed discussion of each of these keywords would be taken up in later chapters wherever their use is relevant.

auto double int struct break else long switch case enum register typedef char extern return union const float short unsigned continue for signed void default goto sizeof volatile do if static while Figure 1.5 The keywords **cannot** be used as variable names because if we do so, we are trying to assign a new meaning to the keyword, which is not allowed. Some C compilers allow you to construct variable names that exactly resemble the keywords. However, it would be safer not to mix up the variable names and the keywords.

Note that compiler vendors (like Microsoft, Borland, etc.) provide their own keywords apart from the ones mentioned in Figure 1.5. These include extended keywords like **near**, **far**, **asm**, etc. Though it has been suggested by the ANSI committee that every such compiler-specific keyword should be preceded by two underscores (as in **__asm** ), not every vendor follows this rule.

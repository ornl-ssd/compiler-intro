---
layout: lesson
root: .
---
In [Introduction to Python](http://swcarpentry.github.io/python-novice-inflammation/) we saw how to run a Python program using the `python`
command. This is known as an interpreted implementation of Python (or *interpreter* for short). This is a process whereby the source code is 
translated into an intermediate representation and then executed by the interpreter, not directly by the target machine. 
The interpreter is usually written specifically for the native machine. As an example, you could consider the multiplier operation – the “*”. 
If the interpreter sees this in your code, then at run time it would call its own definition of the multiplier function – maybe something called 
“multiply(x,y)”. And then that “multiply(x,y)” would execute the machine code’s equivalent of the multiply instruction.

Although interpreted implementations offer many benefits, such as fast prototyping, object introspection, and ..., they are also typically much
slower to execute than compiled implementations. This is one of the main reasons why languages such as C, C++, and Fortran are typically compiled 
(although interpreters do exist).

In a compiled implementation of a language, a program called a compiler will translate the program directly into code that is specific to the 
target machine, which is also known as machine code – basically code that is specific to a given processor and operating system. Then the computer 
will run the machine code directly.

The disadvantage of compilers is that they take time to translate the source code into machine code. This can slow down the development cycle since
the developer must wait for the compiler to complete after changing code. The other main disadvantage is that the compiled programs are specific
to a particular architecture and operating system, so are less portable. For large projects with many source files, the process of invoking the 
correctly can be a complicated task.

> ## Prerequisites
>
> In this lesson we use commands from the Unix Shell. Some previous
> experience with using the shell to list directories, create, copy,
> remove and list files and directories, and run simple scripts is
> necessary.
{: .prereq}

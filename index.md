---
layout: lesson
root: .
---
In [Introduction to Python](http://swcarpentry.github.io/python-novice-inflammation/) we saw how to run a Python program using the `python`
command. This is known as an interpreted implementation of Python (or *interpreter* for short). An interpreter translates the source code 
into an intermediate representation and then executes it, rather than being executed directly by the target machine. 
The interpreter itself is usually written specifically for the target machine. 

As an example, you could consider the multiplier operation – the “*”. 
If the interpreter sees this in your code, then at run time it would call its own definition of the multiplier function – maybe something called 
“multiply(x,y)”  - and then that “multiply(x,y)” would execute the target machine’s equivalent of the multiply instruction.

Although interpreted implementations offer many benefits, such as fast prototyping, object introspection, and interactive development, they 
also typically execute programs much more slowly than compiled versions. This is one of the main reasons why languages such as C, C++, and Fortran 
are typically compiled (although interpreters for these do exist).

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

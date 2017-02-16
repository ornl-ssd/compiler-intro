---
title: "Introduction"
teaching: 15
exercises: 15
questions:
- "How can I compile a C++ program?"
- "How do I run a C++ program?"
objectives:
- "Learn how to use the C++ compiler, and the some of its options"
- "Learn about running user-created programs"
keypoints:
- ""
---
As mentioned, a compiler converts source code into machine code that can execute on a target computer. Let's start with a simple example. Download the
`hello_world.cpp` file and place it in a directory. This file contains the source code to a very simple program that prints "Hello World!" and exits. 
If this was Python, we would just run it using the `python` command. However, for C++, we must first create an *executable* version of the program
using the C++ compiler. To do this, open a shell and change to the same directory that you placed the source file in. Then run the command:

~~~
$ c++ -o hello_world hello_world.cpp
$
~~~
{: .bash}

The effect of this comman is to compile the source file `hello_world.cpp`. The `-o` option instructs the compiler to generate an executable version 
of the program called `hello_world`. Now you should be able to run the program:
~~~
$ ./hello_world
Hello World!
$
~~~
{: .bash}

> ## The PATH environment variable
>
> We need to prefix the command by `./` so that the shell can find it. By default, the shell does not include the current
> directory (`.`) in the PATH as this can present a security risk.
{: .callout}


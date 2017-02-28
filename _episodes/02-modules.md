---
title: "Multipe Source Files"
teaching: 15
exercises: 15
questions:
objectives:
keypoints:
---
Like Python, C++ programs can be comprised of multiple modules. Modules in C++ are not imported the same way they are for Python, however. Instead, 
the modules must be combined together into a single executable.

Let's try it. First, create a new source file called `func.cpp` and put the following code in it:

~~~
// A function to increment its argument
int func(int a) {
	return a+1;
}
~~~
{: .code}

Next we need to modify the `hello_world.cpp	 program to use the function. Edit `hello_world.cpp` and change it to:

~~~
#include <iostream>

extern int func(int); // Declare the interface we want to use

int
main (int argc, char *argv[]) 
{
	int a = 1;
	std::cout << "Hello World!\n";
	std::cout << "func is " << func(a) << "\n";
	exit(0);
}
~~~
{: .code}

Now lets try the same command to compile `hello_world.cpp` we tried before.

~~~
$ c++ -o hello_world hello_world.cpp
~~~
{: .bash}

This time, however, we get an error similar to this:

~~~
Undefined symbols for architecture x86_64:
  "func(int)", referenced from:
      _main in hello_world-76e383.o
ld: symbol(s) not found for architecture x86_64
clang: error: linker command failed with exit code 1 (use -v to see invocation)
~~~
{: .output}

The reason for this error is that we're trying to call `func(a)` in the program, but the *symbol* (or name) `func` can't be found. In order to
resolve this, we need to add the `func.cpp` file to the compile command:

~~~
$ c++ -o hello_world hello_world.cpp func.cpp
~~~
{: .bash}

This time the program compiles without error and we can again run the program:

~~~
$ ./hello_world
Hello World!
func is 2
$
~~~
{: .bash}

> ## Challenge
> In C++, you must first declare the interface of the function you want to use. We did this by adding a line to `hello_world.cpp`.
> However the more usual approach is to put these declarations into a *header* file, which by convention has the same name as the
> source file, but ends in `.h`. These header files are then *included* using the `#include` statement in order to use them.
>
> Move the declaration of `extern int func(int);` in `hello_world.cpp` into a file called `func.h`. Then replace the declaration with the line
> `#include "func.h"` and try compiling the program again using the same command as last time. Did you get it to work?
{: .challenge}

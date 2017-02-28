---
title: "Object Files"
teaching: 15
exercises: 5
questions:
- "How do I avoid recompiling every source file when only one is changed?"
objectives:
- "Understand the process of compiling and linking a program."
- "Learn how to generate object file versions of source files."
- "Learn how to combine object files into an executable."
keypoints:
- "Object files are compiled versions of source files."
- "Object files can be combined together to form an executable using a linker."
---
We've seen how to compile multiple source files into a single executable. However, the disadvantage of doing it this way is that
if we make a change to one source file, every source file needs to be recompiled. Since compiling is a relatively time consuming
process, it would be better if we only had to recompile the file that was changed.

Fortunately there is a way to do this using *object files*. An object file is a compiled version of one or more source files. Object files 
are combined together, along with other information, in order to produce an executable, using a process called *linking*. 
It is the job of the *linker* to do this. In fact, when you compiled `hello_world.cpp` and `func.cpp` previously, you were 
actually creating object file versions, and linking these together to produce the executable. The `c++` command was just doing 
this without you realizing it.

The diagram below shows the process of creating an executable from multiple source files.

![creating an executable]({{ page.root }}/fig/03-compiling.png "creating an executable")

Although this diagram shows that multiple source files can be used to generate a single object file, we're going to create one object 
file for each source file. This is the more usual way to do it. Also, we haven't talked about libraries yet, but as you can see, the
linking step is where external functionality is added to the program.

The simplest way to create an object file from a source file is to use the `-c` argument as follows:

~~~
$ c++ -c hello_world.cpp
$ c++ -c func.cpp
~~~
{: .bash}

After running these commands, you will see two new files called `hello_world.o` and `func.o`. The `.o` stands for "object file". We can
combine these together to produce the executable using the `c++` command:

~~~
$ c++ -o hello_world hello_world.o func.o
~~~
{: .bash}

Notice that this looks very like our original compile command, except that we're using the object files instead of the source files. Using this
approach, we can make a modification to one of the source files without having to recompile the others.

Let's change `func.cpp` to add 2 instead of 1:

~~~
// A function to increment its argument
int func(int a) {
	return a+2;
}
~~~
{: .code}

Now we can simply recompile `func.cpp` and combine the object files again:

~~~
$ c++ -c func.cpp
$ c++ -o hello_world hello_world.o func.o
~~~
{: .bash}

Running the program now results in:

~~~
$ ./hello_world
Hello World!
func is 3
~~~
{: .bash}

> ## Challenge
>
> Create a third file called `func2.cpp` with a function that multiplies its argument with itself (e.g. `a * a`). Add a declaration of the
> function to the `func.h` file and call the function from `hello_world.cpp`. Which files do you need to compile? Comple these to object
> files, then combine `hello_world.o`, `func.o`, and `func2.o` to create a new executable. Did it work?

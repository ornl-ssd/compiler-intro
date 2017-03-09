---
title: "Introduction"
teaching: 15
exercises: 0
questions:
- "How can I compile a C++ program?"
- "How do I run a C++ program?"
objectives:
- "Learn how to use the C++ compiler, and the some of its options"
- "Learn about running user-created programs"
keypoints:
- "A compiler is used to create an executable version of a program from its source code."
---
As mentioned, a compiler converts source code into machine code that can execute on a target computer. Let's start with a simple example. Download the
[`hello_world.cpp`]({{ page.root }}/code/hello_world.cpp) file and place it in a directory. This file contains the source code to a very simple program that prints "Hello World!" and exits. 
If this was Python, we would just run it using the `python` command. However, for C++, we must first create an *executable* version of the program
using the C++ compiler. To do this, open a shell and change to the same directory in which you placed the source file. Then enter the following
command at the shell prompt:

~~~
$ c++ -o hello_world hello_world.cpp
~~~
{: .bash}

The effect of this command is to compile the source file `hello_world.cpp`. The `-o` option instructs the compiler to generate an *executable* version 
of the program (or simply "executable") called `hello_world`. Now you should be able to run the program:

~~~
$ ./hello_world
Hello World!
~~~
{: .bash}

We did it! We ran our first C++ program.

> ## The PATH environment variable
>
> We need to prefix the command by `./` so that the shell can find it. By default, the shell does not include the current
> directory (`.`) in the list of directories to search (the `PATH` environment variable) as this can present a security risk.
{: .callout}

The `c++` command has many options, and these will depend on your operating system and the version of the compiler you have installed. On Linux,
the most common compiler is the GNU compiler. This is also the version you'll be using on Windows. On Mac OS X, the compiler is known as `clang`.

To see the options available, use the command `c++ --help`. A portion of the output from `clang` is shown below.

~~~
$ c++ --help
OVERVIEW: clang LLVM compiler

USAGE: clang [options] <inputs>

OPTIONS:
  -###                    Print (but do not run) the commands to run for this compilation
  --analyze               Run the static analyzer
  -arcmt-migrate-emit-errors
                          Emit ARC errors even if the migrator can fix them
  -arcmt-migrate-report-output <value>
                          Output path for the plist report
  --cuda-device-only      Do device-side CUDA compilation only
  --cuda-host-only        Do host-side CUDA compilation only
  --cuda-path=<value>     CUDA installation path
  -cxx-isystem <directory>
                          Add directory to the C++ SYSTEM include search path
  -c                      Only run preprocess, compile, and assemble steps
  -dD                     Print macro definitions in -E mode in addition to normal output
  -dependency-dot <value> Filename to write DOT-formatted header dependencies to
  -dependency-file <value>
                          Filename (or -) to write dependency output to
  -dM                     Print macro definitions in -E mode instead of normal output
  -emit-ast               Emit Clang AST files for source inputs
  -emit-llvm              Use the LLVM representation for assembler and object files
  -E                      Only run the preprocessor
  -faltivec               Enable AltiVec vector initializer syntax
  -fansi-escape-codes     Use ANSI escape codes for diagnostics
  -fapinotes-cache-path=<directory>
                          Specify the API notes cache path
  -fapinotes              Enable external API notes support
  -fapple-kext            Use Apple's kernel extensions ABI
  -fapple-pragma-pack     Enable Apple gcc-compatible #pragma pack handling
  -fapplication-extension Restrict code to those available for App Extensions
  -fblocks                Enable the 'blocks' language feature
  -fborland-extensions    Accept non-standard constructs supported by the Borland compiler
  -fbuild-session-file=<file>
                          Use the last modification time of <file> as the build 
...
~~~
{: .output}

Some of the more useful options include:

-o *file*
: Write output to *file*

-I *dir*
: Add *dir* to the include search path

-w
: Suppress all warnings

-g
: Generate source-level debug information

-c
: Only run preprocess, compile, and assemble steps

-std=*language*
: Specify the *language* standard to compile for

-O*N*
: Specify which optimization level to use (*N*=0,1,2,3,4)

We will be looking at how to use some of these in later lessons.
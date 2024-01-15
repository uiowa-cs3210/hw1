# Problem 3

## C++
The *what* of C++ will be continuously covered during this course. Here, we get started with the *how*. A C++
program is written in a file with a `.cpp` extension. This file is said to contain the *source code* of the
C++ program. C++ is a *compiled language*, so a compiler compiles the source code into an object file
which usually has a `.o` extension. This is then *linked* with possibly additional object files and library files
by a linker, which produces then produces an executable file corresponding to the source code, that can now be run.
The GCC compiler that we will use can handle compiling and linking in one step.

## First C++ Program
`helloworld.cpp` contains a C++ program that simply prints "Hello, world" on to the screen.
```
#include <iostream>

int main() {
    std::cout << "Hello, world\n";
    return 0;
}
```
Libraries can be imported in C++ using `#include`. In the first line here, we ask C++ to include the 
library called `iostream` that provides functions for user input/output (so this will need to be linked
along with the object file, once compiled).

A function inputs values, processes them in some way, and returns a value. Every C++ program has a `main` function
which is where program execution begins. `int main ()` specifies that the `main` function returns an integer
and that it takes no arguments (since nothing goes between the parentheses). The body of the `main` function, 
that describes how it processes its inputs, is contained within the braces (`{ ... }`). Within the `main` function
above, we call the `cout` function (from the `iostream` library) that allows us to print strings to the user output 
during execution. In this case, we print "Hello, world\n" on to the screen. Since there are no inputs that are being 
processed, we return a default integer value `0`.

We use the GCC compiler to compile and link the source code. In the command-line, run the following in the current
directory:
```
g++ helloworld.cpp -o helloworld
```
If everything goes well, it should compile (and link) it into an executable `helloworld` that can simply be run:
TODO what is the conventional extension of C++ executables in linux?
```
./helloworld
#Hello, world
```
Notice that simply running `helloworld` in the command line will not work. By using `./a.out`, we are telling the 
TODO

The `\n` at the end of `Hello, world` in the code inserts a new line at the end of the string while printing it
onto the output. To see its effect, make a copy of `helloworld.cpp`, called `helloworld2.cpp`;
remove the new line character from the string in  `helloworld2.cpp`, and compile it to see how the output
changes. **Don't** make changes to `helloworld.cpp`, but instead do it to a copy since we want the specification
files to be unchanged in your repositories. You don't need to push `helloworld.cpp`, this is just for you to play with 
the code and see what happens to the output when you make changes to the code. You can either delete this file when 
you're done, or make sure you don't add it to your remote repository when you push your changes.
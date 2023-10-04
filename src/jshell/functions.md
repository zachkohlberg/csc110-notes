# Functions

Functions were briefly mentioned in the quickstart chapter, and you've been
using several functions for a while: `println`, `nextLine`, and the other I/O
commands are all functions.

We could technically write our programs without using functions, but in reality
this would be impractical. Functions offer many benefits, including:
- Abstraction: it's often convenient to tell the computer to perform a task and
not worry about the details. If we had to look at each step of every task the
computer performed, down to the low-level instructions executed by the CPU, then
we would be overwhelmed with information and find it difficult to write any code.
Consider printing to the terminal: do you know how your program takes a string
and makes it appear on the terminal? It's a much more complicated process than
you might expect, but because Java includes a `println` function to handle this
for you, you can tell your program to produce output without worrying about
every little detail.
- Organization: we can define functions for different parts of our program,
breaking it into smaller parts that we can write one at a time. The larger
a program is, the more important it is to keep code organized.
- Testing: when we want to test our program, it's much easier to test individual
functions than it is to test the entire program at once. This type of test is
called a **unit test**, and it's heavily used in most software projects to
ensure code works as intended.
- Avoid Repetition: when we copy-paste or write the same code in multiple
places, we make our code longer and add opportunities to make mistakes. Longer
code takes more effort to read and modify, and if we change code that appears in
several places then we can easily forget to update every occurrence of that
code. It's usually better to write the code once as a function and call the
function when we need to use that code.

We've already benefitted from the abstractions provided by Java's built-in
functions, but to fully benefit from functions we need to know how to write our
own. This chapter will cover how to do this in a Jshell script.

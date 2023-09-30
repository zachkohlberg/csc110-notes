# Functions

A function is a series of instructions (lines of code) that can be **called**
from another part of the program.
We'll learn more about functions and how to write our own functions later, but
for now we'll only look at how to call them.
We've already used several functions in our code, such as `println` and
`nextLine`.

## Function Call Syntax

A **function call** in Java follows the format `FUNCTION_NAME(ARGUMENTS)`.
Function names follow the same rules as variable names, and like variables they
*should* use camelCase and be descriptive.

Some functions require **arguments**, much like programs on the terminal.
An argument is addtional information that the function must have in order to
work, and the arguments for a function call always appear in a comma-separated
list between parenthesis (`(` and `)`) after the function's name.
Sometimes these arguments are optional (technically there are two functions with
the same name, one that requires arguments and one that doesn't), but the
parenthesis are always required, even if the function never has arguments.
An example would be the `println` function, which can be called with no
arguments (`println()` only prints a blank line), but it otherwise needs an
argument to tell it what text to print (`println("Hello, World!");` prints the
message `Hello, World!`).

## Return Value

Some function calls **return** information after they finish, and this
information can be used an part of an expression.
All of the input functions return the information they read from the terminal.
If you call a function that returns something, you should almost always use
the result for something or store it in a variable for later.
Calling `readInt` on its own isn't very useful because the integer isn't saved
anywhere.
Calling `readInt` **and** assigning the result to a variable
(`int x = readInt();`) lets you use the number you read in other parts of your
code.

## Methods

You may see the term "method" used to refer to functions. A **method** is a
concept from object-oriented programming, and it refers to a function attached
to an **object**.
Technically, most functions in Java are methods, including all of the functions
we've used so far.
For now, I'll use the term function for anything that is presented to you as a
standalone function.

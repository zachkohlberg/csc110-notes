# Syntax Changes

## Output

The `PRINTING` script we added to our jshell startup created shorter print
functions for our jshell scripts to use. This is why we could type `println`
instead of `System.out.println`. In a Java program, we need to specify an output
stream when we want to print something. `System.out` is an output stream
connected to standard out, and `System.err` is an output stream connected to
standard err (which is used for printing error messages). All of the print
functions we used in jshell still work in Java as long as you begin them with
`System.out.`.

## Input

The `INPUT.jsh` script we added to our jshell startup created a `Scanner` and
some shorter input functions (`nextInt`, `nextLine`, etc.) for our jshell
scripts to use. To do the same thing in a Java program, we need to create a
scanner connected to an input stream (`System.in` is what we'll normally use),
then we can call that scanner's input methods. The same input functions will
work as long as we call them as methods on our `System.in` scanner.

We also need to import the scanner class before we can use it in our program. An
`import` statement normally goes at the beginning of our program, before the
start of our class. See the code below for a complete example of creating and
using a `System.in` scanner.


```java
// Import the scanner at the beginning of the file
import java.util.Scanner;

// Remember to name this file InputExample.java so it can compile
class InputExample
{
    public static void main(String[] args)
    {
        // Create a new scanner to read from the System.in input stream
        // NOTE: We should only create the System.in scanner once in our entire
        // program! We should only have one scanner reading from a particular
        // input stream.
        Scanner input = new Scanner(System.in);

        // The usual prompt for input pattern, but with a scanner!
        System.out.println("Please enter your first name.");
        String firstName = input.nextLine();

        System.out.println("Please enter your last name.");
        String lastName = input.nextLine();

        // Don't forget we have printf as well as println
        System.out.printf("Your full name is %s %s.\n", firstName, lastName);
    }
}
```

## Functions

Functions have to be formatted slightly differently in a Java program compared
to a jshell script. They're also referred to as methods (although the term
function is still accurate, just less specific). All of our functions will need
to include the `static` keyword before their return type (just like main). This
marks them as a standalone function that can be called from the class. When we
learn how to instantiate our classes later on, we'll be able to write non-static
methods.

We also cannot define methods inside of other methods. Jshell didn't allow this
either, but if you copy a jshell script into your `main` method, then you'll end
up with all of your functions defined inside of the `main` method.

Finally, we don't have to worry about the order of our method definitions in a
Java program! You can define all of your other methods after the main method,
and Java won't have a problem with this.

## Semicolons

Jshell did not require semicolons at the end of statements outside of code
blocks. In Java, statements typically need to end with a semicolon. There are
some lines of code where we should never use semicolons, and we've covered many
of these before. However, let's go over them all again right here:
- Never put a semicolon at the end of an `if` statement, `while` loop, or `for`
loop. The chapters about if statements and loops goes into more detail about
why.
    - One small exception is the do-while loop: you must put a semicolon at the
    end of the `while` line in a do-while loop, but you should **never** do this
    to a regular while loop!
- Never put a semicolon at the end of a function signature or class declaration.
- We rarely need to put semicolons after curly braces, at least not when they're
marking a code block.

All of the code examples in this book will show examples of where to use
semicolons and where not to use them. You're probably somewhat used to this
already from writing code in code blocks for jshell scripts. The only difference
when switching to Java programs is that they're no longer optional in the main
body of your program.

## Code Blocks

One other small change is the structure of code blocks. Jshell's interpreter
doesn't allow you to write the opening brace for the body of an if statement or
a loop on the line after the if statement or loop. A Java program has no problem
with this, as you can see in the example programs. It doesn't matter which style
you use when writing code blocks, but you should always be consistent. Don't
switch styles in the middle of a program.

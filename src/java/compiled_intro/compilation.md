# Compile and Run

There are two steps to running a Java program on the terminal:
1. Compile the program if you made any changes to the code since the last time
you compiled it. This uses the command `javac Filename`.
2. Run the compiled program with the command `java ClassName`.

For practice, try using the following commands to compile and run the hello
world program from the previous section: `javac HelloWorld.java`, then
`java HelloWorld`.

A few notes about compiling and running Java programs this way:
- You need to be in the folder containing the source code (the `.java`
file(s)).
- The `javac` command uses the program's file name, which ends in `.java`.
- The `javac` command will generate a `.class` file for each `.java` file it
compiles. These `.class` files are your compiled program.
- The `java` command uses the class name, which **does not** end in `.java`.
- You can include additional arguments after the class name when using the
`java` command. These arguments will end up in your `main` method's `args`
parameter.

## Example of Program Arguments

Try running the following program with different sets of command line arguments:

```java
class ArgsProgram
{
    public static void main(String[] args)
    {
        System.out.println("Printing all program args:");
        for (int i = 0; i < args.length; ++i)
        {
            System.out.printf("\targs[%d] = %s\n", i, args[i]);
        }
    }
}
```

Try using each of the commands below (don't include the `$`, it just marks the
start of a terminal prompt) and predicting what the output will be before you
run the command. Are any of the results surprising? What can you learn about
command line arguments from the results?

```
$ java ArgsProgram a b c
$ java ArgsProgram a,b,c
$ java ArgsProgram a, b, c
$ java ArgsProgram "a b c"
$ java ArgsProgram a\ b c
$ java ArgsProgram Hello, World
$ java ArgsProgram "Hello, World"
```

## Compiler Errors and Runtime Errors

Our jshell scripts were **interpreted** by the jshell program. This means it
looked at one line or code block at a time and tried to run that piece of code
before looking at the next piece. If we typed some invalid code, then we would
see an error when it tried to run that code and it would continue trying to run
the rest of our script.

A Java program is **compiled**. This means the compiler checks the code to make
sure it follows Java's syntax rules, then it converts the code into Java
**bytecode**, which can be executed by the **Java Virtual Machine**. Certain
types of errors will prevent our code from compiling, which means we can't even
try to run the program. These are called **compiler errors** or **syntax
errors**. If our code doesn't follow Java's syntax (grammar) rules, then it
isn't valid Java code and will be rejected by the compiler.

Syntax errors can be annoying, especially as a beginner who makes this type of
error frequently. However, these is the best kind of error to have in your
program. A syntax error will be caught immediately when you compile your
program, and some editors will warn you about syntax errors as you are editing
your code, before you even try to compile. Your editor or compiler can tell you
exactly where the syntax error is located, and the error message will often be
helpful when you try to figure out the problem.

Runtime errors, on the other hand, cannot be caught by the compiler. A runtime
error occurs while your program is running when the program tries to do
something that it isn't allowed to do (such as index an array with a negative
number or divide an integer by zero). A runtime error will immediately crash
your program and show an error message. This type of error can be harder to
diagnose, because it may only happen with certain inputs, and you won't get a
warning from your editor or compiler about it. You'll usually have to spend a
little bit of time investigating a runtime error before you'll know how to fix
it.

### Semantic Errors

It's also worth mentioning a third type of error, called a **logic error** or a
**semantic error**. This type of error is usually the most difficult to fix,
because it often won't crash your program and provide an error message to show
you what went wrong. A logic error occurs when you make a mistake in your
program's logic that causes it to run but produce incorrect output or otherwise
behave incorrectly. Sometimes this can lead to an infinite loop, or maybe your
program will print the wrong answer to a question five percent of the time. You
can catch logic errors by manually testing your program or by writing automated
tests, like the test scripts included with some of the projects.

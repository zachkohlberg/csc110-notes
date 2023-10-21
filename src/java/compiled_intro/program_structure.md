# Java Program Structure

Java programs have to follow a specific structure. For now, we're just going to
look at programs that fit into a single `.java` file, but later we'll see longer
programs that span two or more files.

We'll be using the hello world program below as an example to explain the
structure of a Java program:

```java
// The body of the HelloWorld class contains our program
// - the class keyword is new
// - HelloWorld is an identifier (the class's name)
class HelloWorld
{
    // The main method (a function attached to the HelloWorld class) is the
    // entry point for our program
    //
    // There aren't many new concepts here:
    // - the public and static keywords
    //
    // We've seen everything else before
    // - the void keyword tells us that the main method returns nothing
    // - main is an identifier (the method's name)
    // - the parenthesis after main contain the method's parameter list
    // - the String[] type is an array of strings
    // - args is an identifier (the parameter's name)
    public static void main(String[] args)
    {
        // This print statement prints the string "Hello World" to standard out
        // - System.out is new
        // - we've been using the println method since the quickstart chapter
        System.out.println("Hello World");
    }
}
```

## Classes

The first new concept we have to cover is a **class**. We're not going to fully
explore classes right away, so we'll start with a simplified definition for a
class: a class is a container for our program and its methods (functions). This
is an incomplete and misleading definition, but it's good enough for now.

There are a few other things you should know about classes:
- A class will usually start with the `public` keyword (`public class ClassName`
instead of `class ClassName`). You're likely to see this in other examples, but
for now it's unnecessary.
- A class's name follows the usual rules for an identifier, but unlike variable
and function names, class names should always start with a capital letter.
- The class's name must match the filename. The hello world example must be in a
file named `HelloWorld.java`, with the same exact capitalization.
- The body of our class goes in a code block after the class name. This will
include *all* of the code in our program for now.

## The Entry Point

A Java program can consist of many classes, and each class can contain many
methods. Most of the code in a class (for now, *all* of the code) has to be
inside of the class's methods. However, if we compile and run our program, it
needs to know which method to call when the program starts. This is the
program's entry point, and it's always going to be a method with the name
`main` and an array of strings as its only parameter.

With a few changes, most of your jshell scripts can be converted into Java
programs by placing all of their code into a class's main method.

### Program Arguments

When you enter a command on the terminal, you can include one or more arguments
after the name of the command. For example, the `cd` command is usually followed
by an argument to specify which directory you want to move to. This is very
similar to how a function call in Java can accept arguments.

When you run a Java program, you can include arguments for the program on the
terminal. These arguments will be parsed as strings and placed in your `main`
method's `args` parameter.

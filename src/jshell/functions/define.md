# Defining Functions in Jshell

A function definition has the following parts:
- If the function returns a value, then it should begin with a return type,
which tells us what type of value it returns. If a function doesn't return a
value, then it should begin with the keyword `void`.
- The function has a name after the return type. Function names follow the
standard rules for [Java identifiers](../../variables/names.md) that we learned
for variable names.
- If the function has any parameters, then these are listed in parenthesis after
the function name. If the function has no parameters, then we must still include
a set of empty parenthesis after the name.
- The function's body (the code it will execute) goes inside a code block after
the parameter list.

```
<return type> <function name>(<parameter list>) {
    <function body>
}
```

A function's parameters tell the program what information the function needs to
receive from the code that calls it. A parameter acts like a variable, but its
initial value is supplied when we call it. The parameter list just looks like a
comma-separated list of variable declarations. For example, if a function needed
two parameters, a double and a boolean, then its parameter list might look like
this: `functionName(double x, boolean y)`. Like variable names, function and
parameter names should be descriptive whenever possible. I've used generic names
here because we have no further context for what these parameters mean. If they
referred to a distance and whether that distance was in metric units, then we
might instead write `functionName(double distance, boolean isMetric)`.

## Return Values

If a function is meant to create information for another part of the program to
use, then it should **return** that information to the code that called it. You
have already used functions with return values: all of the input functions (
`nextLine`, `nextInt`, etc.) return the value they read from the user, and all
of the `Math` functions (`abs`, `min`, `sqrt`, etc.) return the number they
calculated.

If we want our function to return a value, then we need to include the value's
type before the name. We also need to give our function a **return statement**
that includes the value it returns. A return statement is the `return` keyword
followed by an expression whose type matches the function's return type. For
example, if we had a function that adds two `double` values, then its return
statement might look like this: `return x + y;`, where `x` and `y` are the
function's parameters. The entire function would look like this:

```java
double add(double x, double y) {
    return x + y;
}
```

This isn't a useful function because it's easier to add by writing `2 + 3` than
by calling our function with `add(2, 3)`. This is just a short function that
demonstrates what a return statement looks like.

If our function has a return type, then it must *always* return a value of that
type. It should not be possible for such a function to end without returning.
For example, take a look at the following `divide` function:

```java
int divide(int x, int y) {
    if (y != 0) {
        return x / y;
    }
}
```

This is not a valid function because when `y` is equal to `0`, the function does
not return a value. It must either always return a value or never return a
value. There are exceptions (and they're literally called [exceptions](
https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)), but
for now all of our functions must return something if they have a return type.
We don't have a good way to handle errors yet, so the best we can do for now is
let our `divide` function attempt the division and crash if it divides by zero:

```java
int divide(int x, int y) {
    return x / y;
}
```

When new programmers are using if statements or loops in a function and have
multiple return statements, it's common to accidentally write functions like the
first version of divide that aren't guaranteed to return a value. A few tips for
avoiding this:
- If your return statement is inside an if statement, make sure that if
statement has an `else` clause with its own return statement.
- If you have an else-if chain with return statements inside the bodies of the
ifs/else-ifs, then make sure the chain ends with an `else` and that this `else`
contains a return statement.
- If you have a return statement inside of a loop, then you should probably have
a default return statement at the end of the function body in case the loop is
never executed or the return statement inside the loop is never triggered.

Finally, note that as soon as a function reaches a return statement, the
function will stop executing. If you put code after a return statement, it will
never execute:

```java
int divide(int x, int y) {
    return x / y;
    println("This will never be printed!");
}
```

## Practice

Here are a few descriptions of small functions we could write. Try writing a few
of them yourself before looking at the solutions.

Before you write a function definition, it may help to answer two questions:
- Does this function require any parameters? If it always does the same thing,
or it doesn't rely on input from other parts of the program, then it probably
doesn't need parameters.
- Does this function return anything? If another part of the program would want
to use a value created by the function, then it should return that value.
Printing a value is not the same as returning it, and if the function's only job
is to print something then it probably doesn't return a value.

The function descriptions:
1. A function named `sayHello` that prints the message "Hello, World!".
2. A function named `greetPerson` that takes a name and prints a greeting in the
form of "Hello \<name\>, how are you doing today?".
3. A function named `square` that calculates (but does not print) the square of
an integer.

Solution code:

```java
void sayHello() {
    println("Hello, World!");
}

void greetPerson(String name) {
    println("Hello " + name + ", how are you doing today?");
}

int square(int x) {
    return x * x;
}
```

Solution explanations:
1. The `sayHello` function does not require any parameter input because it
always does the same thing. No part of the function's behavior needs to change,
and it doesn't need additional information to print "Hello, World!". The
function is printing rather than producing information for another part of the
program, so it also doesn't need to return anything. This is why its return type
is `void`.
2. The `greetPerson` function is supposed to greet someone by name, but the
description does not say what name we're supposed to use. Instead, it's supposed
to take any name and insert it into a message, which means it needs us to tell
it what name to print. This is why we have a `name` parameter. As with the
`sayHello` function, we're not producing information to use in other parts of
the program, we're sending information outside of the program with `println`.
This means we don't need to return anything, and our return type is `void`.
3. The `square` function needs to know what number it's squaring, and the number
is supposed to be an `int` according to the description, so we need a single
parameter with the type `int`. This parameter doesn't mean anything beyond the
fact that it's a number, so an arbitrary name like `x` or `a` is fine here. The
function is supposed to calculate something, not print it, so in order for this
to be useful we'll have to return the resulting value so another part of the
program can make use of it. The calculation produces an `int`, so our return
type should be `int`.

# Variables

Sometimes we want our program to remember information and reuse the information
later.
We tell our program to remember something by creating a variable and
**assigning** the information to that variable.

## The `var` Keyword

We can use the `var` keyword followed by a name and initial value to create a
new variable.
This follows the format: `var VARIABLE_NAME = INITIAL_VALUE;`.
For example, `var x = 5;` will create a variable named `x` with an initial value
of the number `5`.
`var message = "Hello, World!";` will create a variable named `message` with an
initial value of the text `Hello, World!`.
You can create many types of variables, but for now we'll stick with numbers
and text.

## The Assignment Operator

The equals sign (`=`) can be confusing to new programmers.
You've likely seen it used in math to establish a relationship between two
expressions.
For example, we might say "x = y + z" to establish that the variable x is the
sum of the variables y and z.
We might also make simpler statements, such as "x = 5".
However, if we follow "x = 5" with the statement "x = 6", then we've created a
contradiction because the variable x cannot equal 5 and 6 at the same time.

In programming, the equals sign means something different.
If our code says `x = 5;`, we are not stating a fact about `x` as we would be in
mathematics.
What we're really doing is telling the computer to change the value associated
with the variable `x` to the number 5.
This is called an **assignment**, and the equals sign is the **assignment
operator**.
An assignment follows the pattern `VARIABLE_NAME = EXPRESSION;`.
In our `x = 5;` example, `x` is the variable name and `5` is the **expression**.
An expression can be a lone number or a single variable name, but it could also
be a more complex calculation involving multiple numbers and variables.
Expressions are also not restricted to numbers.
`"Hello, World!"` is also an expression.

What does this mean? While the statement `x = 5;` followed by `x = 6;` would
normally be a contradiction in mathematics, in programming these statements
mean "set the value of `x` to `5`" and "set the value of `x` to `6`".
They are instructions for the computer to change the value of `x` rather than
declarations about the value of `x`.
If our program follows both of these instructions, the result will be that our
variable named `x` stores the number `6`.

## Outputting Variables

You can a variable with `println` to output the information stored in the
variable.
Copy the following code into a jshell script named `variableOutput.jsh` and run
it with jshell:

```java
{{#include variableOutput.jsh}}
```

A couple of notes about the above program:
- The variable `x` can be used in an assignment statement's expression to
calculate a new value for itself. The calculation uses the old value of `x`,
and the result of this calculation becomes the new value of `x`.
- We only use the `var` keyword when we first create the variable. After it
exists we only refer to it by its name, even if we assign a new value to it.

## Names

Variable names must consist of letters, numbers, and the underscore (`_`)
character, and they cannot start with a number. Among other things, this means
they **cannot include spaces**. Java also has certain [reserved words]
(https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)
that cannot be used as variable names.

## Types

We'll learn more about types later. For now, keep in mind that a variable's
type is set with its initial value and cannot be changed. If you make a
variable that stores text, you cannot reassign it to hold a number. Try running
the following code in jshell and you'll see an error message:

```java
var x = "hello";
x = 5;
```

## Good Variable Names

Variable names in Java *should* follow the "camelCase" naming convention. The
name should start with a lowercase letter, and the first letter of each word
after the first should be capitalized. All other letters are lowercase, and we
usually don't use underscores.

Variable names *should also* be descriptive. If you make a variable to store
somebody's age, then the name `age` describes what is in the variable and makes
our code easier to understand. Don't name your variables arbitrary letters like
`a` or `x` unless those names make sense in context. For example, `x` would be
an appropriate name for an x-coordinate on a graph, and a single arbitrary
letter is fine if the information in the variable is only a number with no
further meaning in the context of the program.

Your program can still work if you do not follow these rules, but your code
will be harder for a human to read. A human has to understand the code in order
to use and maintain it, so writing readable code is very important.

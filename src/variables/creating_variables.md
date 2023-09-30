# Creating Variables

There are a few terms that are helpful to cover. The [templates chapter](
../templates.md#declare-and-initialize-a-variable) has some examples to
illustrate declaring, initializing, and reassigning variables.
- **Type**: a variable's type tells us what kind of information it contains. A
computer stores everything as a series of 0's and 1's (bits), and the type tells
it how to interpret those bits. Two identical sequences of bits can each mean
something completely different depending on their types.
- **Value**: a variable's value is the information stored in it.
- **Declare**: creating a new variable is called declaring a variable, and we
might refer to a line of code that declares a variable as a "variable
declaration". This is also when the variable's type is set.
- **Initialize**: when we set a variable's initial value, this is called
"initialization," or initializing the variable. This usually happens in the same
line of code that declares the variable, but we are allowed to declare a
variable without initializing it (this is usually a bad idea, so don't do it
unless you have a good reason).
- **Identifier**: the term "identifier" refers to the name by which we identify
a variable (as well as other constructs, such as functions and classes, which
we'll cover later). There are rules for what is and isn't a valid identifier,
and with a few exceptions we cannot use the same identifier for multiple
variables (when this *is* allowed, it's called "shadowing", but you should avoid
doing this most of the time).

## Variable Declaration

There are two ways to declare a new variable: using the `var` keyword and
allowing Java to infer the type, or explicitly stating the type before the
variable's name. Here are two examples:

```java
var x = 5; // type is inferred to be int
int y = 5; // type is explicitly stated as int
```

In Java, we usually state the type explicitly. The `var` keyword is sometimes
used, but I recommend you stick to explicitly typed variables and avoid using
`var`. When the type appears before the name, this can make it easier for you to
determine a variable's type when reading the code.

## Variable Initialization

In the previous example, both variables were initialized at the same time they
were declared (the `= 5` sets their initial value to `5`). However, if we state
the type of a variable, we are allowed to initialize it later:

```java
int x; // declared, but not initialized
println("We've not yet set a value for x.");
x = 5; // this is the first time we set x's value, so it's now initialized
println("Now x is initialized to " + x + ".");
```

If you have an uninitialized variable, it is an error to try to access the data
stored inside that variable. If we try to print the value of `x` before it's
been initialized, then we'll get an error message:

```java
int x;
println("I'd tell you that x is equal to " + x + ", but that's not allowed yet!");
x = 10;
println("Now we can safely print that x is equal to " + x + ".");
```

Usually you won't have a reason to declare a variable without initilizing it.
We'll see some examples later on where it makes sense to do this, but for now
you should always initialize your variables when you declare them.

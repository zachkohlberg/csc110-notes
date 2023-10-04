# Calling Functions

A **function call** is how we tell our program to execute the code in a
function's body. We've already written plenty of function calls: the statements
`println("Hello, World!");` and `String name = nextLine();` both contain
function calls. A function call has two parts:
- A function call begins with the function's name.
- A function call includes a list of **argument** in parenthesis after the
function name, or a set of empty parenthesis if the function requires no
arguments.

The argument list in a function call is a list of values to use when
initializing the function's parameters. Let's consider the `add` function
defined in the previous section:

```java
double add(double x, double y) {
    return x + y;
}
```

We can't run the code `x * y` without first initializing `x` and `y`. If we call
`add`, then we need to provide an initial value for each parameter: `add(2, 3)`.
The first argument is used to initialize the first parameter (`x`), the second
argument initializes the second parameter, and so on. You may hear the terms
"argument" and "parameter" used interchangeably because they're both referring
to a function's inputs. It's usually clear from context
what we mean when we say "argument" or "parameter", so don't worry about getting
them mixed up. You may also see the term "formal parameter" used to
refer to the parameters in the function's definition and the term "actual
parameter" used for the values supplied with a function call.

## Examples

If we want to call the functions defined in the examples from the previous
section, we would write:

```java
// will print "Hello, World!"
sayHello();

// will print "Hello Zach, how are you doing today?"
greetPerson("Zach");

// will set x equal to 16
int x = square(4);

// will print 16
println(x);

// combines the previous two statements into one step; will also print 16
println(square(4));
```

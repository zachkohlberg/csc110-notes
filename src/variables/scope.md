# Variable Scope and Shadowing

## Scope

Once we start using code blocks, we can have variables with different **scopes**
in our programs. A variable's scope is the portion of the program where it
exists. If we try to refer to a variable outside of its scope, we'll get an
error because it doesn't exist.

When you declare a variable inside of a code block, that variable's scope is
limited to the inside of that code block. Once the code block ends, the variable
no longer exists. Try running the following example:

```java
if (true) {
    int text = "Hello";
    println(text);
}
println(text);
```

We'll get an error when we try to print `text` a second time because it only
exists inside the code block.

## Shadowing

Shadowing occurs when we have two variables with the same name. The newer
variable "shadows" the older variable, taking its place until the newer
variable goes out of scope. Jshell will allow shadowing within the same scope,
which permanently replaces the old variable, but in compiled Java we can only
shadow when the new variable has a different scope from the original.

```java
// this will work fine in jshell, but it won't compile as part of a Java program
int x = 5;
int x = 10; // stating the type declares a new variable named x

// the correct way to change the value of a variable from 5 to 10 is to reassign
// it, not declare the variable a second time
int y = 5;
y = 10; // reassigns the variable instead of redeclaring it
```

Usually it's best to avoid this, but in my experience it's common for new
programmers to unnecessarily declare the same variable multiple times until
they learn the difference between [declaring and initializing](
../variables/creating_variables.md) a variable and [reassigning](
../variables/assignment.md) a variable. Jshell makes this bad habit easier to
form because it allows shadowing within the same scope, as shown above. Compiled
Java will still allow shadowing when the scopes differ:

```java
// shadowing
int x = 5;
if (true) {
    // this is a new variable named x, and it will cease to exist at the end of
    // this block of code
    int x = 10;
}
// this prints the original x value of 5 because we made a new temporary x
// instead of reassigning x
println(x);

// no shadowing
int y = 5;
if (true) {
    // we reassign y instead of declaring a new y with `int y = ...`
    y = 10;
}
// the original y was reassigned to 10, so this will print 10
println(y);
```

In general, I recommend that you avoid shadowing because of the errors that it
enables you to make.

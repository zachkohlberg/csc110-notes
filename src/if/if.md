# If

On its own, an if statement lets the program decide whether or not to run a
block of code. This means the code inside the if block can be skipped. For
example:

```java
println("Please enter a number less than 100.");
int number = nextInt();

if (number < 100) {
    println("Thanks for following directions!");
}
```

This program only prints its second message if the user types a number less
than 100. If the user types a number greater than or equal to 100, then the
program will skip the second print statement.

An if statement [has several parts](../templates.md#if-statement):
- The `if` keyword
- A **condition** in parenthesis after the `if`, which is always a
[boolean expression](../boolean.md)
- An opening curly brace (`{`) to begin a code block; this code block and its
contents are the **body** of the if statement
- Some code indented within the code block
- A closing curly brace (`}`) to end the code block

When an if statement is executed, the condition is first evaluated. This will
result in either `true` or `false`. If the condition is `true`, then the body
of the if statement will execute. If the condition is `false`, then the program
skips the body and continues executing the rest of the program.

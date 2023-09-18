# Syntax Templates and Common Patterns

This section contains examples of patterns you'll see and use frequently while
learning Java. Each entry will have a label to describe the pattern's
purpose, one or more versions of the pattern with placeholders written between
arrow brackets `<like this>`, and one or more examples of code that follows the
pattern. If code is left out of the middle of a pattern or example (usually
because that part isn't relevant to the pattern), it will be replaced with an
ellipsis (`...`).

### Print to standard out (jshell simplified I/O)

Pattern:
```
// Print a string literal
println(<string literal>);

// Print a variable
println(<variable name>);

// Print a concatenated string
println(<string concatenation expression>);
```

Examples:
```java
// Print a string literal
println("Hello, world!");
println("I'm a string literal!");

// Print a variable
println(name);
println(iAmAVeryLongVariableName);

// Print a concatenated string
println("Your name is: " + name + ".");
println("The value of x is " + x + ", and the value of y is " + y + ".");
```

### Declare and initialize a variable

Pattern:
```
// Infer the variable's type
var <variable name> = <initial value expression>;

// Explicitly state the variable's type
<type> <variable name> = <initial value expression>;
```

Examples:
```java
// Infer the variable's type
var mailingAddress = "123 Fake Ln";
var accountBalance = 5 - 3;

// Explicitly state the variable's type
String mailingAddress = "123 Fake Ln";
int accountBalance = 5 - 3;
```

### Declare a variable without initializing

Pattern:
```
<type> <variable name>;
```

Examples:
```java
double area;
String userName;
```

### Read user input to a variable (jshell simplified I/O)

Pattern:
```
// Declare & initialize a new variable with inferred type
var <variable name> = <input function call>;

// Declare & initialize a new variable with explicit type
<type> <variable name> = <input function call>;

// Reassign existing variable
<variable name> = <input function call>;
```

Examples:
```java
// Declare & initialize a new variable with inferred type
var year = nextInt();
var initial = nextChar();

// Declare & initialize a new variable with explicit type
int year = nextInt();
char initial = nextChar();

// Reassign existing variable
year = nextInt();
initial = nextChar();
```

### If statement

Pattern:
```
if (<condition>) {
    <statement(s)>;
}
```

Examples:
```java
if (x % 2 != 0) {
    println("X is odd.");
}
if (numberOfDays < 365) {
    println("The first year isn't over yet.");
    println("There are " + (365 - numberOfDays) + " left in the year.");
}
```

### If statement with else

Pattern:
```
if (<condition>) {
    <statement(s)>;
} else {
    <statement(s)>;
}
```

Examples:
```java
if (x % 2 == 0) {
    println("X is even.");
} else {
    println("X is odd.");
}
if (numberOfDays < 365) {
    println("The first year isn't over yet.");
    println("There are " + (365 - numberOfDays) + " left in the year.");
} else {
    println("The first year has ended.");
    println("It's been " + (numberOfDays - 365) + " since the end of the first year.");
}
```

### Check if value is in a range

Pattern:
```
// Boolean expression, exclusive range
<lower bound> < <value> && <value> < <upper bound>

// Boolean expression, inclusive range
<lower bound> <= <value> && <value> <= <upper bound>

// If statement, exclusive range
if (<lower bound> < <value> && <value> < <upper bound>) {
    ...
}

// If statement, inclusive range
if (<lower bound> <= <value> && <value> <= <upper bound>) {
    ...
}
```

Examples:
```java
// Boolean expression, exclusive range
0 < x && x < 11

// Boolean expression, inclusive range
1 <= x && x <= 10
minimumHeight <= height && height <= maximumHeight

// If statement, exclusive range
if (0 < x && x < 11) {
    println("x is a number from 1 to 10");
}

// If statement, inclusive range
if (1 <= x && x <= 10) {
    println("x is a number from 1 to 10");
}
if (minimumHeight <= height && height <= maximumHeight) {
    ...
}
```

# Numeric Conversions

You can convert between different numeric types. Some of these conversions must
be explicitly stated in your code, and others can be performed implicitly. In
general, conversions from a smaller type to a larger type (widening conversions)
can happen automatically because they shouldn't cause a loss of information.
Conversions from a larger type to a smaller type will result in an error unless
you explicitly tell the program to perform the conversion because these risk
losing information and causing other errors that are much more difficult to fix.

## Implicit Conversions

Java can implicitly convert from any type earlier in this list to a type later
in the list:
- `byte`
- `short`
- `int`
- `long`
- `float`
- `double`

Java will also implicitly convert from a `char` to `int` or any type below `int`
on the list, but it will not implicitly convert any type to a `char`.

The following code demonstrates a few implicit conversions.

```java
byte a = 10
short b = a
int c = b
long d = c
float e = d
double f = e

println(a + ", " + b + ", " + c + ", " + d + ", " + e + ", " + f)
```

## Explicit Conversions

Any other conversions between numeric types must be explicitly stated in your
code. If we don't do this, then we'll get a syntax error. If we reverse the
order of the types in the last example, we'll see this happen with every line
but the first. Try running the following script in jshell:

```java
double a = 10
float b = a
long c = a
int d = a
short e = a
byte f = a
```

To make this work, we need to state the type we want to convert to in
parenthesis before the expression we wish to convert:

```java
double a = 10
float b = (float)a
long c = (long)a
int d = (int)a
short e = (short)a
byte f = (byte)a

println(a + ", " + b + ", " + c + ", " + d + ", " + e + ", " + f)
```

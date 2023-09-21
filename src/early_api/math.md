# Math

Java's `Math` class is a collection of functions and constants that are used in
many programs. We'll cover a few that may be relevant to you in the near future,
but you can always view the [online documentation](
https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Math.html)
if you want to see what else is available.

We've not yet explained the term **class**, and it won't be that relevant until
we switch to compiled Java. For now, think of a class as a container for other
code, such as the constants and functions described below.

## Using the Math API

You can access any of the functions or constants in the `Math` class by typing
`Math.` followed by the name of that constant or function:

```java
// prints the value of PI
println(Math.PI);

int a = nextInt();
int b = nextInt();
// prints the larger of the two numbers entered by the user
println(Math.max(a, b));
```

## Constants

There are only a few constants in the `Math` class, but they are frequently
used in mathematics and may be relevant to some of your programs:
- `Math.PI` is an approximation of [pi](https://en.wikipedia.org/wiki/Pi)
- `Math.TAU` is an approximation of pi doubled
- `Math.E` is an approximation of [e](
https://en.wikipedia.org/wiki/E_(mathematical_constant))

## Functions

The functions shown below will use placeholder variable names, which you should
replace with the appropriate variables or literals from your program when you
use these functions.

Some of the functions in `Math`:
- `Math.abs(x)` takes the [absolute value](
https://en.wikipedia.org/wiki/Absolute_value) of `x`
- `Math.ceil(x)`, `Math.floor(x)`, and `Math.round(x)` all round `x` (ceil
always rounds up, floor always rounds down, and round follows standard rounding
rules)
- `Math.max(x, y)` and `Math.min(x, y)` returns the largest (max) or smallest
(min) of `x` and `y`
- `Math.pow(x, y)` raises `x` to the power of `y`
- `Math.sqrt(x)` returns the square root of `x`
- `Math.random()` generates a random number from 0.0 to 1.0 (excluding 1.0)
- `Math.toDegrees(x)` and `Math.toRadians(x)` convert the angle `x` from radians
to degrees or from degrees to radians
- Many [trigonometric](https://en.wikipedia.org/wiki/Trigonometry) functions,
such as `Math.sin(x)`, `Math.cos(x)`, and `Math.tan(x)`, are included in the
`Math` class

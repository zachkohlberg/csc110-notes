# Integers

Integer types can represent positive and negative whole numbers, as well as the
number zero. Java's integer types are `long`, `int`, `short`, and `byte`.

`int` is Java's default integer type. Most of our integers will use the `int`
type, but `long` will be necessary if we're dealing with numbers too large to
represent with `int`.

## Integer Division

We can add, subtract, multiply, and divide integers, but division may not work
the way you expect. Dividing one integer by another always results in an
integer. If there is a remainder, the result is **truncated**, which means the
remainder is dropped. This causes integer division to always round towards
zero (negative numbers round up and positive numbers round down).

The [modulo](./modulo.md) operator can be used if you would like the remainder
from dividing two integers *instead* of the quotient.

## Overflow

Each integer type can only represent values within [a set range](
../primitives.md), and if an integer exceeds this value it will **overflow**.
When an integer overflows, it wraps around to the opposite end of its range of
possible values. To see this in action, try running the jshell script below.
Before you run it, write down what number you think each print statement will
output.

```java
byte a = 255
byte b = -256
byte c = 200
int d = 2147483647

println(a + 1)
println(a + 5)
println(b - 1)
println(b + 1)
println(c + 55)
println(c + 56)
println(c + 100)
println(d + 1)
```

We'll see exactly why this happens when we learn how binary numbers work.

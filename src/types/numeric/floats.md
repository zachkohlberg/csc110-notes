# Floating-Point Numbers

Floating-point types can represent real numbers, which includes integers,
fractions, and numbers like \\( \pi \\) that cannot be represented as a
fraction. Java's floating-point types are `float` (single precision
floating-point number) and `double` (double-precision floating-point number).

`double` is Java's default floating-point type, and we will not normally have a
reason to use the less precise `float` type.

## Precision

Floating-point numbers do not represent exact values. You may have noticed that
they can store a far larger range of values than integer types that use the
same amount of memory, and this is only possible because they have a limited
precision. For now, it's best to think of a floating-point number as a close
approximation or a small range of possible values rather than a precise value.

Due to this limited precision, you will sometimes see floating-point
calculations that result in values that are slightly off from what you would
expect if you were working with exact numbers. For example, `0.1 + 0.2` will
result in `0.30000000000000004` instead of the expected `0.3`. As you'll be
reminded in the chapters on [if statements](../../if.md) and [boolean logic](
../../boolean.md), this lack of precision makes it a bad idea to try checking
whether two floating-point values are exactly the same.

## Overflow

Floating-point numbers do not overflow like integers. If you exceed the minimum
or maximum value that a floating-point format can represent, you'll end up with
`Infinity` or `-Infinity`.

## Underflow

Floating-point numbers can experience underflow. This can happen if you add or
subtract a small number from a much larger number, such as subtracting `1` from
`1000000000000000000000.0`. The limited precision of floating-point numbers
means it can only represent the first 17 or so digits of the number (the
**significant digits**, if you're used to scientific notation), and changes to
the later digits are too small to affect these significant digits. This is why,
in Java, `1000000000000000000000.0 + 1.0` will equal `1000000000000000000000.0`.

## Why

Like some of the quirks of integers, for now it's most important to understand
that they exist and that they are supposed to function this way. We'll learn
more about how they work when we learn about binary numbers.

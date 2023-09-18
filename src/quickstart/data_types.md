# Data Types

So far we've simplified the different types of information you can put in a
variable. Now we'll go over some of Java's basic types in more detail.

We won't go into detail about binary right now, but it's worth mentioning that
every piece of information in your computer is represented as a series of ones
and zeroes, called bits (binary digits).
These bits form a **binary number**.
Even though everything is a binary number when you look at the computer's
memory, different types specify different rules for interpreting these binary
numbers.
These rules let us decode binary into text, integers, real numbers, and more
complex forms of data.

Most of the types we cover in this section have a limited size, and they always
use the exact same number of bits no matter what value they represent.
Rather than bits, we measure the space taken up by data in bytes, which are
chunks of 8 bits.

## Numbers

There are two categories of numbers: integers and floating-point numbers.
Integers can only represent zero and positive or negative whole numbers.
Floating-point numbers can represent real numbers (fractions, irrational
numbers like pi, and other numbers that require a decimal), as well as
zero and whole numbers.

The integer types are:
- `byte`: 1-byte (8-bit) integer value; stores any integer from -128 to 127
- `short`: 2-byte (16-bit) integer value; stores any integer from -32768 to 32767
- `int`: 4-byte (32-bit) integer value and the default type for integers in Java;
stores any integer from about -2 billion to about 2 billion
- `long`: 8-byte (64-bit) integer value; stores any integer from about -9
quintilion to about 9 quintillion

The floating-point types are:
- `float`: 4-byte (32-bit) floating-point value; stores numbers from about
[-3E38](https://en.wikipedia.org/wiki/Scientific_notation#E_notation) to about
3E38
- `double`: 8-byte (64-bit) floating-point value and the default type for
floating-point numbers in Java; stores numbers from about -1.7E308 to about
1.7E308

The differences in ranges may be surprising, and there is a significant
drawback to floating-point numbers, but we'll cover that later when we take a
closer look at binary and how numbers are represented in memory.

You can perform basic arithmetic with integers and floating-point numbers.
If you use numbers of different types, then they will be converted to the type
that can represent a greater range of numbers.
The symbols to use for arithmetic are `+`, `-`, `*` (multiplication for), and
`/` (for division).

## Text

There are two types commonly used for representing text:
- `char`: a single character encoded as a 2-byte integer
- `String`: a sequence of characters; the size of a `String` depends on the
number of characters in the `String`

The text we've been putting in quotations are `String` values. If we want
a `char`, we need to use single quotes (`'`) instead. For example, `"A"` is a
`String` and `'A'` is a `char`.

We can combine strings with other values using **concatenation**.
This uses the `+` symbol, and at least one of the values must be a `String`.
If one of the values is not a `String`, it will be converted to one, and then
the second value will be appended to the first value.
For example, `"10" + 5` is equal to `"105"` because the `5` is converted to a
`String` and appended to the `"10"`.
`10 + 5` without any quotes will perform regular addition and give us `15`.

If you try to add a `char` and a number, the `char` will be converted to its
numeric representation and treated as an `int` value, then regular addition
will be performed.
For example, `'a' + 5` is `102` because the character `'a'` is internally
represented by the number 97 (look up an ASCII table if you're curious about
why).
This may seem counter-intuitive, but as we'll see later it can actually be
quite useful.
If we use a `String` instead of a `char`, we'll go back to concatenation:
`"a" + 5` is `"a5"`.

## Booleans

We likely won't use booleans for a while, but they're briefly explained here
for the sake of completeness.
A `boolean` value is either `true` or `false`.
`boolean`s are used in **Boolean Logic**, which allows our programs to make
decisions based on input instead of always doing the same thing.
We'll talk more about the `boolean` type when we introduce if statements.

## Explicit and Inferred Types

The `var` keyword has Java infer the type of a variable based on the initial
value.
If we assign an initial value of `5`, for example, then it will infer
that the type is `int`.
However, it is standard practice in Java to specify the type of a variable
rather than using the `var` keyword in most situations.
Instead of `var x = 5`, we would write `int x = 5`, putting the type before the
variable name instead of `var`.
This makes it easier to specify types other than the default `int` and `double`
for numbers, and it makes it easier to tell what type a variable is when looking
at the code.
From now on, most examples will use explicit types rather than inferred types.

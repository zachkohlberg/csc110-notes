# Comparisons

In order to write a condition, you need to be able to write a boolean
expression. One common type of boolean expression is a comparison between two
values. Here are the comparison operators that Java supports:
- `<`: less than
- `<=`: less than or equal to
- `>`: greater than
- `>=`: greater than or equal to
- `==`: equal to (a single `=`
[is an assignment, not a comparison](../variables/assignment.md))
- `!=`: not equal to

Here are a few examples of boolean expressions using these comparison operators
along with the equivalent English statement:
- `a >= b`: `a` is greater than or equal to `b`
- `year != 2022`: `year` is not equal to `2022`
- `2 + 2 == 5`: `2 + 2` is equal to `5`

These will result in `true` if the comparison is making a true statement, and
`false` if it is not. For example, `a >= b` will be true whenever `a` is greater
than or equal to `b`, and `false` when `a` is less than `b`. This comparison
contains variables, so its value will depend on those variables. A comparison
between two constant values, such as `2 + 2 == 5`, will always result in the
same value (in this case, `false`, because `2 + 2` is equal to `4` and not `5`).

## String Comparisons

The comparison operators above are only meant to be used with [primitive types](
../types/primitives.md). If you use them to compare `String`s or other reference
types, then your code will usually not work correctly.

If you want to compare two strings, you'll need to use the `.equals()` [method](
../quickstart/functions.md#methods):

```java
println("Please enter your name.");
String name = nextLine();

if (name.equals("Zach")) {
    println("Hello, Professor Kohlberg!");
} else {
    println("Hello, " + name + "!");
}
```

## Common Mistakes

A few mistakes to avoid with comparisons:
- The `=` operator does not check for equality; do not use it in a boolean
expression
- Do not check floating-point values for equality with `==` or `!=`; the lack of
precision inherent to floating-point numbers will cause false positives and
false negatives

## Ranges

You cannot combine comparisons like this: `1 <= x <= 10`.
This would be a perfectly natural way to state that x is a number from 1 to 10,
and this *is* how you'd write such a statement in algebra, but your program will
not interpret it the way we might hope. Let's look at how a program will
evaluate the boolean expression `1 <= x <= 10` while `x` stores the value `7`:
- First, we'll substitute the value of `x`: `1 <= 7 <= 10`.
- Now, `1 <= 7 <= 10` contains three known values (`1`, `7`, and `10`) and two
operators (the two `<=` operators). The operators are identical, so we have to
start with the one on the left: `1 <= 7` is `true`, because `1` is less than
`7`. Therefore, we'll replace `1 <= 7` with `true`: `true <= 10`.
- How do we evaluate `true <= 10`? We can't! This is why you'll see an error if
you try to write a comparison this way.

If we want to ask whether `x` is between `1` and `10`, we'll need to write two
separate comparisons and join them with the `&&` operator to require both to be
`true` for the whole expression to result in `true`. `&&` and other boolean
operations are covered in [the next chapter](../boolean.md).

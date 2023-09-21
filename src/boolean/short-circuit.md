# Short-Circuiting

Sometimes, a boolean expression involving the `&&` or `||` operator can be fully
evaluated without checking the second operand. In these situations, the computer
will skip evaluating the second operand, and this is called "short-circuiting".

## When Do We Short-Circuit?

There are two situations where we can short-circuit a boolean expression:
- When we are ANDing two values (`&&`) and we see that the first value is
`false`, we don't need to check the second value to know that the result is
`false`. This is because an AND results in `false` unless both operands are
`true`.
- When we are ORing two values (`||`) and we see that the first value is `true`,
we don't need to check the second value to know that the result is `true`. This
is because an OR results in `true` unless both operands are `false`.

You can see this if you check the [truth table](./operators.md#truth-table)
shown in the operators section. Both rows where `a` is `false` result in `false`
for `a && b`, and both rows where `a` is `true` result in `true` for `a || b`.
You don't need to know what's in column `b` in either of those situations to
tell me what's going to be in the column for `&&` or `||`. This is why we can
"short-circuit" and skip looking in column `b`.

On the other hand, if `a` is `true`, then you still need to check `b` to
determine what's under `a && b`, and if `a` is `false`, then you still need to
check `b` to determine what's under `a || b`. In these situations, we need to
evaluate `b` before we know the result of the expression. This means we cannot
short-circuit.

## Uses

Short-circuiting can be useful when we want to evaluate two boolean expressions,
but one of them will cause an error in certain situations. For example, we're
not allowed to divide integers by zero. If we want to divide two unknown
integers, we need to make sure they aren't zero first:

```java
int x = nextInt();
int y = nextInt();

if (y != 0) {
    println(x / y);
} else {
    println("We can't divide by zero!");
}
```

Let's say we want to know whether `x / y` is an even number. We could write our
code like this:

```java
int x = nextInt();
int y = nextInt();

if (y != 0) {
    if ((x / y) % 2 == 0) {
        println("x / y is even");
    } else {
        println("x / y is not even");
    }
} else {
    println("x / y is not even"); // if we can't divide x / y, then it's not even
}
```

However, that's long and repetitive. We can simplify this code by taking
advantage of short-circuiting:

```java
int x = nextInt();
int y = nextInt();

if (y != 0 && (x / y) % 2 == 0) {
    println("x / y is even");
} else {
    println("x / y is not even");
}
```

If the first part, `y != 0`, is false, then `y` *is* zero and dividing will
cause an error. However, if we have `false` followed by `&&`, then we don't need
to evaluate the part after the `&&` to know that the `&&` results in `false`.
Java will use this fact to skip evaluating the `(x / y) % 2 == 0`, and we won't
divide by zero and cause an error.

We can use `||` to ask the same question with short-circuiting if we change the
comparisons:

```java
int x = nextInt();
int y = nextInt();

if (y == 0 || (x / y) % 2 != 0) {
    println("x / y is not even");
} else {
    println("x / y is even");
}
```

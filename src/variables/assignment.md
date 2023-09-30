# Assignment Operator

The assignment operator (`=`) can cause some confusion. When you start writing
[comparisons](../if/comparisons.md) and using the equality operator (`==`), it's
easy to mix up what each of these mean. One of the reasons this can be confusing
is the difference between imperative programming (the style of programming that
Java primarily supports and that we will be using) treats variables differently
from mathematics.

## Variables in Math

If this were an algebra class and I gave you the following statements, you would
probably be confused:

```
x = 5
x = 6
x = x + 3
```

The first two statements, `x = 5` and `x = 6` contradict one another and imply
that `5 = 6`, which we know is not true. The third statement contradicts itself,
because a number cannot equal itself plus 3 (this would imply that `0 = 3` if we
subtract an `x` from both sides). In math, we would view the above statements as
factual statements about the variable `x`, and because of the contradictions
they cannot be true statements (the first or second would be fine on their own).

## Variables in Imperative Programming

In Java, the previous statements are perfectly fine and do not contradict one
another. This is because the `=` sign does not have the same meaning in Java
that it has in algebra. In Java, the `=` sign is the **assignment operator**,
and it is instructing the computer to change the value associated with `x`.
The value of `x` is allowed to change over time, and it will be different after
each instruction that **assigns** a value to `x`. After the first statement,
`x` will be equal to 5. After the second, it will be equal to 6. After the
third, it will be equal to 9, because it uses the previous value (6) in the
calculation before it assigns the new value. We can see this if we add a
declaration and several print statements to the program and run it in Jshell:

```java
int x;
x = 5;
println("x is " + x);
x = 6;
println("x is " + x);
x = x + 3;
println("x is " + x);
```

The equality operator (`==`) has a meaning closer to how we would interpret an
equals sign in mathematics. It is stating that two values are the same, but it
is still valid to make false or contradictory statements with `==` in Java. If
we do, then the result will be `false` instead of `true`. This is because the
equality operator is asking a question rather than asserting that something must
be true, and both yes (`true`) and no (`false`) are valid answers to that
question. We can demonstrate this with the following program:

```java
int x = 10;
int y = 13;
boolean xEqualsItself = (x == x);
boolean xEqualsY = (x == y);
boolean xEqualsFive = (x == 5);
boolean xEqualsTen = (x == 10);
boolean xEqualsItselfPlus1 = (x == x + 1);
println("The value of x is " + x);
println("The value of y is " + y);
println("Does x equal itself? " + xEqualsItself);
println("Does x equal y? " + xEqualsY);
println("Does x equal five? " + xEqualsFive);
println("Does x equal ten? " + xEqualsTen);
println("Does x equal itself plus one? " + xEqualsItselfPlus1);
```

The parenthesis around the equality checks on lines 2-5 are not necessary, but
I've included them to make it clear what the order of operations will be. First
we evaluate whether `x` is equal to the value to the right of the `==`, which
results in `true` or `false`, and then we assign the result to the variable on
the left of the `=`. Try running this, and note that despite some of the answers
being false, we don't actually get an error from those false statements. Again,
this is because they are questions rather than statements of fact.

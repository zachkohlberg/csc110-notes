# Pen & Paper Analogy

Many new programmers have difficulty learning to think it terms of variables,
but this is a fundamental skill for writing code. It may be helpful to think
about variables in terms of writing information down by hand on a piece of paper
or a whiteboard. Everything we can do with a variable can be represented this
way, which lets you simulate small amounts of code by hand or think through the
process in your head to better understand what's going on.

## Declare and Initialize

If we declare a variable in a program (`int x`), this is equivalent to writing
the label `x` on our paper. When we initialize that variable in code (`x = 5`), 
we would write the initial value on the paper beneath or next to `x`.

Example:

```java
int x;
x = 5;
int y = 10;
```

> x -> 5
>
> y -> 10

## Reassign

Reassigning the variable in code (`x = 10`) is equivalent to crossing out the
old value of `x` and replacing it with the new value.

```java
x = 11;
y = -4;
x = 3;
```

> x -> ~~5~~ ~~11~~ 3
>
> y -> ~~10~~ -4

## Print

Printing the variable (`println(x)`) means we're communicating it to someone
else. We could write it down on a separate piece of paper, or we could read the
text out loud to the other person.

```java
println(x);
println(y);
```

Variable record
> x -> ~~5~~ ~~11~~ 3
>
> y -> ~~10~~ -4

Output paper
> 3
>
> -4

## Use in a Calculation

If we use our variable in a calculation, we would write the expression with our
variable, then substitute the variable's value as we simplify the expression
one step at a time.

```java
x = 10;
y = 5;
x = x + y;
y = x * 2 - 4;
println("x = " + x + " and y = " + y);
```

Variable record
> x -> ~~5~~ ~~11~~ ~~3~~ ~~10~~ 15
>
> y -> ~~10~~ ~~-4~~ ~~5~~ 26

Scratch paper for calculations
> Calculate x + y
>
> x + y
>
> 10 + y
>
> 10 + 5
>
> 15
>
> **set x equal to 15**
>
> Calculate x * 2 - 4
>
> x * 2 - 4
>
> 15 * 2 - 4
>
> 30 - 4
>
> 26
>
> **set y equal to 26**
>
> Calculate "x = " + x + " and y = " + y
>
> "x = " + x + " and y = " + y
>
> "x = " + 15 + " and y = " + y
>
> "x = 15" + " and y = " + y
>
> "x = 15 and y = " + y
>
> "x = 15 and y = " + 26
>
> "x = 15 and y = 26"
>
> **write "x = 15 and y = 26" to the output paper**

Output paper
> 3
>
> -4
>
> x = 15 and y = 26

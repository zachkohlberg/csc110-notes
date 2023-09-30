# For Loop

The for loop exists to make it easier to code certain types of loops, such as
counting loops. With a while loop, we need to declare and initialize the
counting variable before the loop, check the value in the loop's condition, and
update the counting variable's value in the loop's body:

```java
int i = 0; // init

while (i < 100) { // condition
    println(i);

    i = i + 1; // update
}
```

A for loop lets us combine all three of these steps in the parenthesis after the
`for` keyword:

```java
for (int i = 0 /*init*/; i < 100 /*condition*/; i = i + 1 /*update*/) {
    println(i);
}
```

The for loop is an example of [syntactic sugar](
https://en.wikipedia.org/wiki/Syntactic_sugar), or something that isn't strictly
necessary, but that makes it easier or clearer to write some kind of code. The
for loop is generally going to be more concise than a counting while loop, and
putting all of the counting logic in the same place can make it easier to read.
Any loop that can be written as a while loop can be written as a for loop, and
any loop that can be written as a for loop can be written as a while loop. You
should use whichever one seems best suited to the problem you are solving.

## Abbreviations for Incrementing Variables

You may or may not have seen the `+=`, `++`, `-=`, and `--` operators before,
but they're commonly used with for loops. These operators allow you to more
concisely increment (increase the value of) or decrement (decrease the value of)
a variable:

```java
int i = 0;

// the following lines of code all increase the value of i by 1
i = i + 1;
i += 1;
i++;
++i;

// the following lines of code all decrease the value of i by 1
i = i - 1;
i -= 1;
i--;
--i;
```

There is technically a small difference between putting the `++` and `--`
operator before or after a variable, but this only matters if you are using it
in an expression: `int x = i++` and `int x = ++i` will result in different
values for `x`. Otherwise, it isn't going to matter which way you write these
operators, so go with the style you prefer. I also tend to avoid using them in
situations where they behave differently because it can make the code harder to
read.

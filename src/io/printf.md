# Formatting with printf

String [concatenation](../types/strings.md#concatenation) works well for
combining sever string literals and variables when no additional formatting is
required, but it can be cumbersome when there are many variables and doesn't
offer any tools for controlling how values are formatted. You can write your own
code to control formatting, but this can get repetitive and tedious. The
`printf` function offers a better solution in these situations.

Look at the following code that prints the time for a 12-hour clock using
concatenation:

```java
String amOrPm = nextLine();
int hour = nextInt();
int minute = nextInt();
int second = nextInt();

String minuteFormatted;
if (minute < 10) {
    minuteFormatted = "0" + minute;
} else {
    minuteFormatted = "" + minute;
}
String secondFormatted;
if (second < 10) {
    secondFormatted = "0" + second;
} else {
    secondFormatted = "" + second;
}

String time = hour + ":" + minuteFormatted + ":" + secondFormatted + " " + amOrPm;
println(time);
```

This code works, but it has the drawbacks we just mentioned: the concatenated
string expression is long and hard to read due to all of the breaks in the
string literals and `+` symbols joining the different parts, and we have to
write additional code to control how some of the numbers are formatted.

Compare this to using the `printf` function:

```java
String amOrPm = nextLine();
int hour = nextInt();
int minute = nextInt();
int second = nextInt();

printf("%d:%02d:%02d %s\n", hour, minute, second, amOrPm);
```

This produces the same output, but with far less code. The downside is that we
may not know how to read the format string at the beginning. Let's fix that!

## Format Strings and Args

The `printf` function takes a format string that includes placeholder values for
any variables that we want to insert into the string. After this format string,
we include a list of arguments (the values we want to insert) in the same order
that their placeholders appear in the string.

It's also important to note that `printf`, unlike `println`, does not
automatically add a line break to the end of its output. If we want a line
break, and we usually do, then we need to include the `\n` [escape sequence](
../types/numeric/chars.md#escape-sequences) in the format string.

## Formatting Specifiers

The placeholders are "formatting specifiers," and their job is to convey the
type of value to insert into the string as well as how we want to format that
value. A formatting specifier has two or three parts:
- They begin with a percent sign `%`
- They can (but don't have to) include some formatting information in the
middle, such as the `02` in our time example
- They end in a character that represents the type of value we're going to
insert at that point in the string, such as `d` (decimal, as in "base-10",
integer) or `s` (string)

## Interpreting Our Example

With all this in mind, how do we interpret the `"%d:%02d:%02d %s"` from our
time example?
- Each `%d` represents an integer
- A `%02d` is an integer with additional formatting: if it's shorter than `2`
characters then it should be padded with `0`s so that it takes up `2` characters
of space
- A `%s` is a string (the "AM"/"PM" value)
- The colons (`:`) and space are not part of any placeholder values, so they'll
be printed as they appear in the string

Let's apply these rules and see what our string looks like if `hour` is `9`,
`minute` is `5`, `second` is `30`, and `amOrPm` is `"AM"`:
- `hour` is the first argument, so it takes the place of the `%d`:
`"9:%02d:%02d %s"`
- `minute` is the second argument, so it takes the place of the first `%02d`,
and because `%02d` specifies that we pad with `0` to ensure our number is at
least `2` characters long, we change the `5` to `05`:
`"9:05:%02d %s"`
- `second` is the third argument, so it takes the place of the second `%02d`:
`"9:05:30 %s"`
- `amOrPm` is the last argument, so it takes the place of the `%s` at the end of
the format string: `"9:05:30 AM"`

## Documentation

This example showed a few of the many types and methods for formatting those
types that `printf` supports. Java has [detailed documentation](
https://docs.oracle.com/javase/8/docs/api/java/util/Formatter.html) for
formatting strings, and there are also some [tutorials](
https://docs.oracle.com/javase/tutorial/java/data/numberformat.html)
that you may find [helpful](
https://docs.oracle.com/javase/tutorial/essential/io/formatting.html). Not all
of this documentation is going to make sense early on, but the more you use
`printf` and check the documentation, the better you'll be able to use Java's
documentation to find the information you need.

# Strings

Strings are sequences of characters. They have many applications and come with
useful built-in [methods](../quickstart/functions.md#methods), but to begin
we'll mostly use them for producing output. We'll revisit this chapter later to
learn about more advanced string manipulation.

## String Literals

A string literal is text enclosed within double-quotes (`"`). You can use
[escape sequences](./numeric/chars.md#escape-sequences) in string literals just
like `char` literals.

## Concatenation

Anything can be concatenated with a string. The plus sign `+` performs string
concatenation instead of addition whenever one of the operands is a string.

If one of the operands is a string and the other is a different type, Java will
convert the other operand to a string before concatenating them. The second
operand is then appended to the first operand, forming a new string. For
example, if we concatenated `"Hello"` with `"World"` (`"Hello" + "World"`), we
would get `"HelloWorld"` (if you want a space, make sure to include it in one of
the operands!).

You can concatenate multiple values together, but remember that the
concatenation will be evaluated left to right. If you want to perform any
arithmetic with numeric values before they are concatenated, you may need to
surround them with parenthesis to ensure the arithmetic happens first. For
example, `"sum: " + 2 + 3` will result in `"sum: 23"`. If we wanted to add 2
and 3 before concatenating, we can add parenthesis: `"sum: " + (2 + 3)` will
result in `"sum: 5"`.

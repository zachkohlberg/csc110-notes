# Chars

The `char` type represents a text character, but internally it is an **unsigned
integer**. [Strings](../strings.md) are made up of `char`s, and the fact that
a `char` is a number allows us to manipulate it in some interesting ways.

## ASCII and Numeric Representation

If you look up an [ASCII table](https://www.asciitable.com/), you'll see the
numeric values of some characters. If you were to convert the character `'a'`
into an `int`, for example, it would be 97. ASCII is an older format, but the
characters on that table are generally encoded as the same numbers in more
modern formats.

Note that the encodings for the digits 0 to 9, the lowercase letters a to z, and
the uppercase letters A to Z are sequential. `'a'` is 97, `'b'` is 98, etc. We
can use this fact to determine a letter's place in the alphabet, whether a
`char` is a letter, digit, uppercase, or lowercase, and what letters come before
or after another letter.

## Escape Sequences

Some characters have a special meaning inside `String` and `char` literals, and
some characters cannot be displayed or easily typed into a program. To include
these characters in a `String` or `char` literal, we need to escape them with a
backslash (`\`, which is usually located above the return key on a keyboard).

Characters with special meaning:
- `\` is used to escape other characters, so we need to escape it: `'\\'`
- `'` is used to mark the beginning and end of a `char` literal, so it must be
escaped inside a `char` literal: `'\''`
- `"` is used to mark the beginning and end of a `String` literal, so it must be
escaped inside a `String` literal: `"\""`

Whitespace characters that are hard to print:
- A linebreak is represented as `\n` inside a `char` or `String` literal
- A tab is represented as `\t` inside a `char` or `String` literal

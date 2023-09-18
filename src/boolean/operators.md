# Boolean Operators

There are four boolean logic operators we need to cover: AND, OR, XOR, and NOT.
These operators take one or two boolean operands and result in a new boolean
value.
In Java and many other programming languages, these operators are written as
follows:
- AND: `&&`
- OR (inclusive OR): `||`
- XOR (e**X**clusive OR): `^^`
- NOT: `!`

## AND

If I were to say "it's going to rain and snow tomorrow," then my statement will
only be true if it both rains and snows tomorrow.
If it only rains, only snows, or doesn't rain or snow, then my statement is
false. This is how the boolean AND works.

`a && b` only results in `true` if both `a` and `b` are both `true`. If at least
one operand is `false`, then `a && b` results in `false`.

## OR and XOR

In English, the word "or" can be used inclusively or exclusively: an inclusive
'or' allows both options to be true, and an exclusive 'or' requires exactly one
to be true. For example, consider the following two statements:

1. Tomorrow it's at least going to rain or snow. (*inclusive*)
2. Due to the weather, school will either start late or be cancelled entirely.
(*exclusive*)

The first sentence would be true if it both rained and snowed.
In the second sentence, the options presented are mutually exclusive; only one
can be true.

`a || b` (inclusive or) always results in `true` unless both `a` and `b` are
`false`. If both operands are `false`, then `a || b` results in `false`.
`a ^^ b` (exclusive or) results in `true` if **exactly one** of its
operands is `true` and the other is false. `a ^^ b` results in `false` if both
of its operands are `true` or both are `false`. You can also say `a ^^ b` is
`true` if `a` isn't equal to `b`, or `false` if `a` and `b` are the same.

## NOT

The NOT operator only applies to one operand. `!a` results in the opposite of
whatever `a` is equal to: `true` if `a` is `false`, or `false` if `a` is `true`.
This is how the word "not" is used in English. If I say "I'm not going out
tomorrow," that statement is true if I don't go out and false if I do go out.

## Truth Table

Below is a table showing the result of applying each boolean operator to every
permutation of true/false values.

|    a|    b|a && b|a \|\| b|a ^^ b|   !a|   !b|
|:---:|:---:|:----:|:------:|:----:|:---:|:---:|
| true| true|  true|    true| false|false|false|
| true|false| false|    true|  true|false| true|
|false| true| false|    true|  true| true|false|
|false|false| false|   false| false| true| true|

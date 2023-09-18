# Modulo

The modulo operator is like a fifth arithmetic operation. You're probably used
to addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`).
Modulo is written as `%`, and it will divide its operands but give us the
remainder rather than the quotient. This is the information we normally lose
when performing [integer division](./integers.md#integer-division).

For example, if we calculated 100 / 40 by hand, we would end up with either
2.5, 2 and 1/2, or 2 with a remainder of 20, depending on how we wanted to
write the result. The last version, 2 with remainder 20, shows us the
information we get with integer division (2, the quotient) and modulo (20, the
remainder). `100 / 40` would result in `2`, and `100 % 40` would result in `20`.

Modulo has many uses. A couple that you'll encounter in this class are:
- Checking if one number is divisible by another number, particularly whether
numbers are divisible by 2 (even/odd)
- Breaking a quantity in a small unit (such as cents) into one or more larger
units along with the leftover quantity in the original unit (such as converting
from cents into dollars while remembering the leftover cents: 327 cents is 3
dollars and 27 cents).

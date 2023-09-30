# Else

Optionally, an if statement may include an else immediately after its body. The
else is followed by its own body, which the program will execute if the
if's condition is `false` or skip if the if's condition is `true`. The pattern
[looks like this](../templates.md#if-statement-with-else). Note that, like
`if (condition) {`, `else {` should never include a semicolon.

An if with no else can either execute or skip a block of code. An if with an
else will always execute either the if block or the else block. If you want your
program to execute additional code some of the time, then you should probably
use an if on its own. If you have two different blocks of code and always want
one or the other to execute, then an if followed by an else is appropriate.


Finally, note that an else **never** has a condition. It will only execute when
the if's condition is false, so a condition is not necessary.

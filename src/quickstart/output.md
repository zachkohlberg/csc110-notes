# Output

A program's output is the information it sends to some external location, such
as the terminal, the screen, a speaker, a file, or a web server.
For now, our only method of producing output will be printing text to the
terminal.

## Print Functions

We will primarily use the `println` function, which you saw in the previous
section.
There is a similar function called `print`, which is slightly different.
To illustrate the difference, here are two jshell scripts, `abcPrintln.jsh` and
`abcPrint.jsh`, along with their output:

```java
{{#include abcPrintln.jsh}}
```

```java
{{#include abcPrint.jsh}}
```

```
$ jshell --execution local abcPrintln.jsh
A
B
C
$ jshell --execution local abcPrint.jsh
ABC$
```

As you can see, the `println` function moves to the next line after printing.
This is because it adds a **line break** to the end of whatever text it prints.
The `print` function does not, which even leads to the terminal prompt (`$`)
being on the same line as the second program's output!

Usually you'll want to use `println`, but `print` can be helpful if you want to
create a line of output into multiple print statements.

## Escape Sequences

If you've experimented with printing, then you may have noticed that you cannot
print a double-quote (`"`).
This is because double-quotes are used to mark the beginning and end of a
string of text.
You *can* print `"` and a number of other special characters using escape
sequences.
These are typically a backslash (`\`) followed by the character or a
letter standing in for the special symbol you want to include:
- `\"` is printed as `"`
- `\\` is printed as `\`
- `\t` is printed as a tab
- `\n` is printed as a line break

Try printing messages containing these escape sequences and see what happens!

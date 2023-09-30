# Comments

A comment is text that is ignored when compiling or running a program. Comments
can be used for many purposes, and the way you use comments will evolve as you
learn more about programming.

## Types of Comments

A single-line comment is created with two forward-slashes:

```java
// this text is a comment and will be ignored when the program runs
```

Everything after the slashes is ignored. You can put a comment on the same line
as code, but I find it's easier to read code when comments are on separate
lines:

```java
// a comment on the same line as the code:

int x = 5; // this makes a variable named x with an initial value of 5

// a comment on its own line (usually my preference):

// this makes a variable named y with an initial value of 7
int y = 7;
```

You can create a comment that spans multiple lines (a block comment) using `/*`
to mark the beginning of the block and `*/` to mark the end of the block:

```java
/*
All of the text in this example is inside of a block comment.

Nothing I write here will be treated as code if you were to run this in jshell.

If this were a real program, it would be pointless :(
*/
```

## How to Use Comments

Comments can serve many purposes, and how you use them depends on many things,
such as who you're working with, the project you're working on, and the language
you're coding in. For a beginner programmer, I would recommend using comments
for the following purposes:
- Taking notes inside your code to explain what the code is doing
- Temporarily disabling ("commenting out") code without deleting it (put `//` at
the start of a line of code and it will be ignored when you run the program).
This is helpful if you are trying to fix a problem and want to disable a line of
code that causes an error or see what happens when that line is skipped.
- Documenting important information about your program, such as the author(s),
the program's purpose, citations if appropriate
- Outlining part of a program before you write it
- Leaving "todo" comments, or reminders about tasks you plan to finish later

Some of these will not always be relevant to you. For example, it's usually not
helpful to put comments throughout your program explaining every line of code
once you get the hang of programming.
You and the other experienced programmers will generally assume that the people
working on a project understand code and don't need every line explained.
However, these types of comments can be useful if you're learning a new
language, and they're good to include in code samples that are meant to teach
a new concept to someone.

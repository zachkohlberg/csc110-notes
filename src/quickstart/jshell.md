# Jshell

## Introduction

Jshell is a REPL (**R**ead, **E**xecute, **P**rint, **L**oop). When you run a
REPL program, it does the following:
1. Reads a command
2. Executes the command
3. Prints the result
4. Loops back to step 1 until told to exit

For the first half of the semester, we'll be writing our programs as jshell
scripts.

Note: terminal emulators will show a prompt when waiting for a command. This
prompt often includes your current location and ends with the `$` character.
For clarity, the terminal's command prompt will be marked with `$`, and
jshell's prompt will be marked with `jshell>`.

While jshell or a similar interactive program is running on your terminal,
commands will go to that program instead of the terminal. If no such program is
running, then your commands will be run by the terminal itself. This matters
because jshell commands (like `println` and `/exit`) will only work in jshell,
and terminal commands (like `cd` and `ls`) will not work in jshell.

## Interactive Mode

To open jshell on the terminal, run the `jshell` command. You should see a prompt
similar to the one below:

```
$ jshell
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell>
```

You can now enter jshell commands and snippets of Java code. These will appear
after the `jshell> ` prompt. Once you've typed something, press enter to have
jshell execute it. Most jshell commands (that aren't Java code) are prefixed
with a forward slash (`/`). To exit jshell, type the command `/exit` and press
enter:

```
$ jshell
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell> /exit
|  Goodbye
$ 
```

## Hello World: Interactive Mode

Now we'll write some Java code. Open jshell again and enter
`System.out.println("Hello, world!")`. Jshell should respond by repeating
`Hello, world!` on the next line:

```
$ jshell
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell> System.out.println("Hello, world!")
Hello, world!

jshell>
```

Try running another println instruction with a different message between the
quotes.

## Hello World: Script

Exit jshell and open your [text editor](../software/text_editor.md). Open a new
file and type the following text into the file:

```java
{{#include helloWorld.jsh}}
```

Save this file as `helloWorld.jsh` and return to the terminal.
**All of your jshell scripts should end with the `.jsh` file extension**.
Make sure your terminal is in the directory where you saved the file (`ls`
should show your `helloWorld.jsh` file) and run the command
`jshell --execution local helloWorld.jsh`.
You should see the `Hello, World!` message printed on the terminal:

```
$ jshell --execution local helloWorld.jsh
Hello, world!
$ 
```

## Interactive Mode vs Script

Running `jshell` on its own will launch jshell as an interactive REPL.
If you want to experiment with a small amount of code and get immediate
feedback, you should run jshell in interactive mode.

Running `jshell --execution local` followed by the name of a jshell script (a
`.jsh` file) tells jshell to execute each line of the script in order.
This is useful if you are writing a program and don't want to retype each line
of code every time you test the program.
**Remember to always end your jshell scripts with the `/exit` command**, or
jshell will continue running once it reaches the end of the script.

When jshell runs in interactive mode, it will print additional information even
if you don't include a `println`.
For example, try typing `2 + 2` in jshell:

```
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell> 2 + 2
$1 ==> 4

jshell>
```

When running a script, you will only see error messages and output that you
explicitly print.
For example, write a script with the line from before (`2 + 2`), save it as
`add.jsh`, and run it with `jshell add.jsh`.

The script:

```java
{{#include add.jsh}}
```

The output from running it with jshell:

```
$ jshell --execution local add.jsh
$
```

We didn't include a print command, so no output was produced. This lets us
control exactly what we want the program to show the user as it's running.

Finally, whenever we run a script with jshell, we need to include the
argument `--execution local` with the jshell command. This is necessary to
allow input commands (covered later) to work correctly. We only include
`--execution local` when running a script, not when using interactive mode.

Running a script called `myScriptName.jsh`:

```
$ jshell --execution local myScriptName.jsh
```

Running in interactive mode:
```
$ jshell
```

## Startup Script

To make input and output more convenient, we're going to tell jshell to run a
few scripts on startup before it runs any of our code.
Download the `INPUT.jsh` file from Blackboard, then make sure your terminal is
in the same directory as `INPUT.jsh`.
Run jshell, then run the command `/set start -retain DEFAULT PRINTING INPUT.jsh`
in jshell. Exit jshell, start it again, and run the command `/list -start`.
The result should look similar to this:

```
$ jshell
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell> /set start -retain DEFAULT PRINTING INPUT.jsh

jshell> /exit
|  Goodbye
$ jshell
|  Welcome to JShell -- Version 17.0.7
|  For an introduction type: /help intro

jshell> /list -start

  s1 : import java.io.*;
  s2 : import java.math.*;
  s3 : import java.net.*;
  s4 : import java.nio.file.*;
  s5 : import java.util.*;
  s6 : import java.util.concurrent.*;
  s7 : import java.util.function.*;
  s8 : import java.util.prefs.*;
  s9 : import java.util.regex.*;
 s10 : import java.util.stream.*;
 s11 : void print(boolean b) { System.out.print(b); }
 s12 : void print(char c) { System.out.print(c); }
 s13 : void print(int i) { System.out.print(i); }
 s14 : void print(long l) { System.out.print(l); }
 s15 : void print(float f) { System.out.print(f); }
 s16 : void print(double d) { System.out.print(d); }
 s17 : void print(char s[]) { System.out.print(s); }
 s18 : void print(String s) { System.out.print(s); }
 s19 : void print(Object obj) { System.out.print(obj); }
 s20 : void println() { System.out.println(); }
 s21 : void println(boolean b) { System.out.println(b); }
 s22 : void println(char c) { System.out.println(c); }
 s23 : void println(int i) { System.out.println(i); }
 s24 : void println(long l) { System.out.println(l); }
 s25 : void println(float f) { System.out.println(f); }
 s26 : void println(double d) { System.out.println(d); }
 s27 : void println(char s[]) { System.out.println(s); }
 s28 : void println(String s) { System.out.println(s); }
 s29 : void println(Object obj) { System.out.println(obj); }
 s30 : void printf(java.util.Locale l, String format, Object... args) { System.out.printf(l, format, args); }
 s31 : void printf(String format, Object... args) { System.out.printf(format, args); }
 s32 : Scanner __in = new java.util.Scanner(System.in);
 s33 : String nextLine() { return __in.nextLine(); }
 s34 : String next() { return __in.next(); }
 s35 : int nextInt() { return __in.nextInt(); }
 s36 : int nextIntWithBase(int radix) { return __in.nextInt(radix); }
 s37 : long nextLong() { return __in.nextLong(); }
 s38 : long nextLongWithBase(int radix) { return __in.nextLong(radix); }
 s39 : double nextDouble() { return __in.nextDouble(); }
 s40 : float nextFloat() { return __in.nextFloat(); }
 s41 : boolean nextBoolean() { return __in.nextBoolean(); }

jshell>
```

If you see the same list of 41 lines after running the `/list` command, then
your startup scripts should be set correctly.
The `DEFAULT` script contains the imports on the first 10 lines, and it was
already running every time you started jshell.
Those imports make it easier to access some useful code included with Java,
which is part of the **Java Standard Library**.
The `PRINTING` script is lines 11 to 31, and it lets us run any of the output
functions (such as `println`) without typing `System.out`.
The `INPUT.jsh` script includes the last 10 lines, and it sets up some input
functions to make it easier for us to read user input.
We'll make use of these functions soon.

You don't need to understand any of the code in the startup scripts right now.
We're using them specifically so you *don't* have to think about that stuff until
you learn what it all means.
Try using `println` to print a message, as shown below, to further verify that
the startup scripts were loaded correctly:

```
jshell> println("Hello, world!")
Hello, world!
```

If you run into issues with the startup scripts, you can always reset them with
the command `/set start -retain DEFAULT`, and then repeat the previous
directions to add the `PRINTING` and `INPUT.jsh` scripts.

## Summary

- Use the `jshell` command to run in interactive mode
- You can write jshell scripts in your text editor and save them as `.jsh`
files
- Use the `jshell --execution local` command followed by a script name to run
a jshell script
- Make sure you set the startup scripts as explained above and confirm that
they're working

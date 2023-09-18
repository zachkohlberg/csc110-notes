# Terminal

A terminal is a program that allows you to type commands for your computer to
execute and view the results as text.
You can run other programs from a terminal, and it can serve the same role as
many other programs you're used to using.

## Terminal Programs

On Unix-like operating systems (such as Mac and Linux), you should be
able to find the default terminal program by searching your applications for
"terminal".
This terminal is similar to what you'll see used in the videos.
Many of these terminals run a program called `bash` or `zsh` underneath, and
they should all accept the commands you see in the videos and other examples,
so Mac and Linux users don't need to set up any additional terminal software.

On Windows, there are two built-in terminal programs, neither of which I
recommend using:
- `cmd` is the classic Windows Command Prompt.
Most commands that work with bash/zsh will not work in the command prompt.
- `Powershell` is a more advanced terminal for Windows that supports some of
the commands you'll see used in bash terminals.
However, it will likely not be able to run the test scripts you receive with
your assignments and may not work with all of the commands you see us use.

There are several popular terminal emulators for Windows that emulate bash and
allow you to run the same commands as a bash terminal.
A good example is git bash, which is part of the
[Git for Windows](https://gitforwindows.org/) project.
If you are using Windows, you should install Git for Windows or another terminal
emulator.
This will allow you to run the test scripts for assignments and use the terminal
commands you see demonstrated in class.
It also includes the program `git`, which is used in some later CSC/SER classes.

## Terminal Videos

Mark Lewis, the author of a textbook previously used for this class, has a
[playlist](https://www.youtube.com/watch?v=V-wKBH-gUeo&list=PLLMXbkbDbVt9z5dcm7uRgG3Fhw3u9LKoF)
of videos covering how to use a terminal on YouTube.
Watch these videos for a brief demonstration of the different terminal commands,
and refer to the cheatsheet below if you would like a summary of useful
commands.

## Terminal Cheatsheet

Important terms/concepts:
- A **directory** is a folder on your computer.
- A **path** is the location of a file or directory. It is a series of
directory names separated by forward slashes on Unix-like systems or
backslashes on Windows. Examples:
    - `/home/zach/Documents/Syllabus.pdf` is the location of a file named
    "Syllabus.pdf". It is in a folder named "Documents", which is in a folder
    named "zach", which is in a folder named "home", which is at the root of
    the filesystem (indicated by the leading "/").
    - `C:\Users\Zach\Documents\Syllabus.pdf` is the equivalent path on Windows.
- A **relative path** only tells you how to get to a file or directory from
your current location. For example, if we were in the folder `/home/zach`, then
the relative path to "Syllabus.pdf" in the previous example would be
`Documents/Syllabus.pdf` or `./Documents/Syllabus.pdf`. A `./` at the start of
a path refers to your current location, so a path beginning with `./` is always
relative.
- Many commands will include placeholder text written in all caps. That part
is not meant to be copied literally when you run the command. For example, you
would type `cd Documents` to move to the "Documents" folder rather than
literally typing `cd PATH`.
- Some commands have flags or optional arguments, which are normally written as
one or two hyphens followed by a word or letter.
These allow you to enable certain settings when running a command or include
additional optional information.
Some examples are the `-a` in `ls -a` or the `--version` in `java --version`.

Navigation:
- `pwd`: "**p**rint **w**orking **d**irectory", tells you which folder you're in
- `cd PATH`: "**c**hange **d**irectory", moves you from your current
location to the directory at `PATH`
    - `cd` on its own or `cd ~` will move you to your home directory
- `ls`: "**l**i**s**t", lists everything in the current directory
    - `ls PATH`: lists the contents of the directory at `PATH`
    - `ls -a`: includes hidden items in the output

Viewing Files:
- `cat PATH`: show the contents of the file at `PATH`
- `less PATH`: view the contents of the file at `PATH`, but with more features.
Press `q` to exit `less` and return to the terminal's command prompt.

Manipulating Directories:
- `mkdir PATH`: creates an empty directory at `PATH`
- `rmdir PATH`: deletes the directory at `PATH`, but only if it is empty

Manipulating Files (these are dangerous and can permanently delete files, so
use with care!):
- `rm PATH`: delete the file at `PATH`. It's permanently gone, not moved to the
trash or recycle bin.
- `mv PATH DESTINATION`: move the file or directory at `PATH` to `DESTINATION`.
This can also be used to rename a file or directory.
If you move a file to another file with the same name, you will replace the file
that was already there, permanently deleting the old file.

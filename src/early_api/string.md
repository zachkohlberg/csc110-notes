# String

Java's strings come with a bunch of useful **methods**, which are functions
attached to objects. Unlike the various [primitive types](
../types/primitives.md) we've covered, strings are objects that contain both
information (the characters in the strings) and methods (functions that operate
on those characters). We can call these methods on any string literal or
variable:

```java
String name = "zach";
println(name);
println(name.toUpperCase());
println(name.charAt(3));
println(name);
println("hello".substring(1));
println("HElLo".toLowerCase());
```

A note about all of these methods: Java's strings are **immutable**, which means
they cannot be modified after they are created. Converting a string to all
uppercase letters does not change the original string, it creates a new string
with the same text, but all of the letters are capitalized. This can be observed
when we print `name` for a second time in the previous example. Any method you
call on a string will leave the original intact.

## Indexes

The term **index** refers to the position of something in a sequence. In Java
and most other programming languages, the index 0 corresponds to the first
position within a sequence, the index 1 corresponds to the second position,
and so on. This is called "zero-indexing", and it applies to any index of a
character within a string. For example, the `'H'` in `"Hello, world!"` is at
index 0, and the `','` is at index 5.

## String Methods

As with `Math`, you can read the full [API page for string](
https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/String.html)
if you'd like to see more detail than I've provided in this section. These
methods will also be shown with placeholder variables (`s`, `s1`, `s2`, etc. for
strings, `c`, `c1`, `c2`, etc. for characters, and `x`, `y`, etc. for numbers).
Replace these with the appropriate variables or literals from your own code when
using these methods.

- `s1.equals(s2)` returns `true` if `s1` and `s2` have the exact same sequence
of characters and false if they do not
- `s1.equalsIgnoreCase(s2)` is like `.equals`, but it ignores differences in
capitalization
- `s.length()` returns the number of characters in `s`
- `s.toUpperCase()` and `s.toLowerCase()` convert all of the letters in `s` to
uppercase or lowercase letters
- `s.charAt(x)` returns the character at index `x` in `s`
- `s.indexOf(c)` returns the index where the character `c` first appears in `s`
- `s.lastIndexOf(c)` returns the index where the character `c` last appears in
`s`
- `s1.startsWith(s2)` and `s1.endsWith(s2)` return true if `s1` starts/ends with
`s2` and false if it does not
- `s.substring(x)` returns a string containing every character in `s` from
index `x` until the end of `s`
- `s.substring(x, y)` returns a string containing every character in `s` from
index `x` up to (but not including) index `y`

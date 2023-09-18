# Types

This chapter covers primitive numeric types and Strings. Several new terms are
used in this chapter, so here are some definitions:
- **Primitive Type**: if we store a value of a primitive type in a variable, the
value is stored directly in the variable. Most of the types we're working with
for now are primitive types (except for `String`).
- **Reference Type**: reference types are stored in a different memory location
called the "heap", and variables store the value's location rather than the
entire value (this is because reference types are usually large, and storing a
single copy uses much less memory than giving each variable its own copy). We
don't have to worry about this right now, but I'm mentioning it so you know the
term for types that aren't primitive.
- **Literal**: if we "hard-code" a value, writing the actual number, string, or
char in the code rather than using a variable, this is called a literal value.
For example: numbers (`0`, `3.14`, or `-20`), chars (`'a'`, or `'!'`), and
strings (`"hello"` or `"this is a string"`).

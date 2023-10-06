# Creating Arrays

## Declaring an Array

We can have an array of ints, strings, doubles, or any of the other types we've
seen so far. We can even make arrays of arrays, but that's a topic for later.

An array is stored in a single variable, and unless we're using `var` to infer
the type, we need to state that it's an array and what it's an array of. We can
specify an array of some other type by adding a pair of square brackets (`[]`)
after the other type. For example, `int[]` is an array of integers, and
`String[]` is an array of strings. The following code [declares](
../../variables/creating_variables.md#variable-declaration), but does not
[initialize](../../variables/creating_variables.md#variable-initialization),
several array variables of different types.

```java
int[] arrayOfInts;
String[] arrayOfStrings;
double[] arrayOfDoubles;
```

## Creating a new Array

We'll usually want to initialize an array variable by creating a new array. To
create an array, we write the `new` keyword, the array's type, and the array's
size inside the square brackets. For example, `new int[10]` would create a new
array that holds ten integers. We'll modify the previous code to declare *and*
initialize our array variables:

```java
int[] arrayOfInts = new int[10];
String[] arrayOfStrings = new String[5];
double[] arrayOfDoubles = new double[1000];
```

This has created three arrays: an array of ten integers, an array of five
strings, and an array of one-thousand doubles.

A couple of notes about these arrays before we continue:
- Each array's size is fixed once it has been created. We cannot grow or shrink
these arrays.
- The arrays are not empty. An array always contains exactly the same number of
values. When we create new arrays like this, they are initialized with the
default value for their type: `0` for numeric types, `false` for booleans, and
`null` for strings or other objects/reference types. A value of `null` means
there is no string at that position in the array. We'll learn more about `null`
later, but for now it's enough to understand that it represents the absence of
an object.

If we want to create a small array that starts with a specific set of values
instead of the default value for its type, then we have another option:

```java
int[] countdown = new int[] { 10, 9, 8, 7, 6, 5, 4, 3, 2, 1 };
String[] names = new String[] { "Alice", "Bob", "Charlie" };
```

This could be used for larger arrays, but it's not very practical. If our array
isn't, we'll probably want to use a loop to set the initial values after we
create the array.

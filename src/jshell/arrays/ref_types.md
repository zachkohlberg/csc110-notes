# Reference vs Value Types

Arrays and Strings are both types of objects. We can refer to them as reference
types, which differ from [primitive types (also called value types)](
../../types/primitives.md) in several ways. The primary difference is how the
program stores their data:
- Value-type variables directly store the data for the value they represent. If
`x` and `y` are value types, then the assignment statement `x = y` will copy the
data from `x` into `y`.
- Reference-type variables store a memory address that points to their data,
which is stored in a region of memory called the **heap**. If `x` and `y` are
reference types, then the assignment statement `x = y` will copy the memory
address from `x` into `y`, which means both `x` and `y` will be pointing to the
same object.

## Comparing Reference Types

When you compare two variables using `==` or `!=`, the program checks whether
the data stored in the variables is identical. This works fine for value types,
which directly store a representation of their value. This will not work for
reference types, because the data in the variable is a memory address and not a
representation of the data those variables represent.

If `x` and `y` are reference types, then this means `x == y` will ask whether
`x` and `y` point to the same location in memory, not whether they point to
identical data. If you have two different but identical objects stored in `x`
and `y`, then `x == y` will evaluate to `false`. Try running the code below to
see this in action:

```java
int[] a = new int[] { 1, 2, 3 };
int[] b = new int[] { 1. 2, 3 };
int[] c = a;

if (a == b) {
    println("a equals b");
} else {
    println("a doesn't equal b");
}

if (b == c) {
    println("b equals c");
} else {
    println("b doesn't equal c");
}

if (a == c) {
    println("a equals c");
} else {
    println("a doesn't equal c");
}

String x = new String("Hello");
String y = new String("Hello");
String z = y;

if (x == y) {
    println("x equals y");
} else {
    println("x doesn't equal y");
}

if (y == z) {
    println("y equals z");
} else {
    println("y doesn't equal z");
}

if (x == z) {
    println("x equals z");
} else {
    println("x doesn't equal z");
}
```

Some reference types define an `equals` method to compare their data instead of
their memory addresses. The `String` type does this, so we can use `x.equals(y)`
to ask whether the contents of two strings `x` and `y` are equal. If `x` and `y`
are strings, then `x.equals(y)` behaves the same as `a == b` would behave if `a`
and `b` were value types.

Other reference types, such as arrays, do not define their own version of the
`equals` method. These reference types still have the `equals` method, but it
won't be any more helpful than `==`. If we want to compare two arrays, then we
need to write our own code to check each element of the arrays and determine
whether they're equal:

```java
boolean areEqual(int[] a, int[] b) {
    // If the lengths differ, then we know they're different. It also wouldn't
    // be safe to iterate over both with one loop, so it's important to return
    // before we get to the for loop.
    if (a.length != b.length) {
        return false;
    }

    // If the lengths are the same (and we'll return earlier if they aren't),
    // then we can use a loop to compare the elements at each index of the
    // arrays.
    for (int i = 0; i < a.length; ++i) {
        // If two elements at the same index don't match, then the arrays aren't
        // equal
        if (a[i] != b[i]) {
            return false;
        }
    }

    // If we don't find any pairs of unequal elements, then we know the arrays
    // have the same length and contain the same elements. Sounds like they're
    // equal!
    return true;
}

int[] a = new int[] { 1, 2, 3 };
int[] b = new int[] { 1, 2, 3 };
int[] c = new int[] { 1, 2, 3, 4 };

println("If we use the == comparison operator:");

if (a == b) {
    println("a equals b");
} else {
    println("a doesn't equal b");
}
if (b == c) {
    println("b equals c");
} else {
    println("b doesn't equal c");
}
if (a == c) {
    println("a equals c");
} else {
    println("a doesn't equal c");
}

println("If we use the equals method:");

if (a.equals(b)) {
    println("a equals b");
} else {
    println("a doesn't equal b");
}
if (b.equals(c)) {
    println("b equals c");
} else {
    println("b doesn't equal c");
}
if (a.equals(c)) {
    println("a equals c");
} else {
    println("a doesn't equal c");
}

println("If we use the areEqual function:");

if (areEqual(a, b)) {
    println("a equals b");
} else {
    println("a doesn't equal b");
}
if (areEqual(b, c)) {
    println("b equals c");
} else {
    println("b doesn't equal c");
}
if (areEqual(a, c)) {
    println("a equals c");
} else {
    println("a doesn't equal c");
}
```

## Immutable Data

The `String` type is **immutable**, which means that we can't modify (or mutate)
the data inside of a string after we create the string. However, we can create
new strings based on an existing string, which is what happens when we
concatenate strings or call one of the string methods (such as `toLowerCase`).
The following code demonstrates that the original string `a` won't change when
we concatenate it with other strings and call various methods on it.

```java
String a = "Hello";

// Show the value of a
println("a: " + a);

// Create new strings using a
String b = a + " World";
String c = a.toUpperCase();
String d = a.replace("ello", "i");

// Show the value of a again (hasn't changed)
println("a: " + a);

// Show the value of the variables we created using a
println("b: " + b);
println("c: " + c);
println("d: " + d);
```

If we reassign a variable containing a reference to immutable data, then the
original data still exists. Just because the string `a` points to is immutable,
this doesn't mean the memory address stored in `a` can't be changed to point to
different data.

```java
// Create a new string
String a = "Hello";

// Create a second variable pointing to the same string
String b = a;

// Show the values in each string
println("a: " + a);
println("b: " + b);

// Create a new string and change a to point to the new string
a = a.toUpperCase();

// Show the values in each string again, which demonstrates that the original
// string (stored in b) has not changed
println("a: " + a);
println("b: " + b);
```

## Mutable Data

Unlike the `String` type, an array is **mutable** (which means its data *can*
change). We can reassign any element of an array to a different value, which
changes part of the array. If multiple variables point to the same array, then
they will both reflect this change.

```java
// Need a way to print arrays
void printArray(String label, int[] array) {
    // Include a label for the array
    String s = label + ": ";
    // Add each int to the string
    for (int x: array) {
        s += x + " ";
    }
    println(s);
}

// Create a new array
int[] a = new int[] { 1, 2, 3, 4 };

// Show the value of a
printArray("a", a);

// Create variables that point to the same array as a
int[] b = a;
int[] c = a;
// Create a variable that points to a different array, but contains the same
// elements as a
int[] d = new int[] { a[0], a[1], a[2], a[3] };

// Change a different element of each variable's array
a[0] = 5;
b[1] = 6;
c[2] = 7;
d[3] = 8;

// Show the value of the array that a points to
printArray("a", a);

// b and c contain the same elements because they point to the same array as a
printArray("b", b);
printArray("c", c);

// d contains different elements because it points to a different array from a
printArray("d", d);

// Create a new array using the current elements of a
int[] e = new int[] { a[0], a[1], a[2], a[3] };

// e has the same elements as a
printArray("e", e);

// Change each element of e
e[0] = -1;
e[1] = -2;
e[2] = -3;
e[3] = -4;

// Changing e hasn't affected a, b, c, or d because e is a different array
printArray("a", a);
printArray("b", b);
printArray("c", c);
printArray("d", d);
printArray("e", e);
```

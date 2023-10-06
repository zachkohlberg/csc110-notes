# Accessing and Mutating Arrays

Now that you know how to create an array, what can you do with it? Let's start
by printing the array:

```java
int[] primes = new int[] { 2, 3, 5, 7, 11, 13 };
println(primes);
```

Was the output what you expected? Probably not. Java's default method for
converting objects into strings doesn't produce a very useful string for an
array. We can convert an array to a string with a loop, but first we need to
learn how to access the individual values in an array.

## Indexing

We mentioned indexing in the [String API](../../early_api/string.md) section,
but it's worth going into more detail now that we're dealing with arrays. To
access a single value stored in an array (we call these values the array's
**elements**), we need to specify its index. The index of an element is that
element's distance from the beginning of the array. This means the first element
has an index of 0 because it is at the beginning of the array. The second
element has an index of 1 because it's one space away from the start of the
array.

If we want to refer to a specific element of an array, we put that element's
index in square brackets after the name of the array:

```java
int[] primes = new int[] { 2, 3, 5, 7, 11, 13 };
println(primes[0]); // prints 2
println(primes[1]); // prints 3
println(primes[2]); // prints 5
println(primes[3]); // prints 7
println(primes[4]); // prints 11
println(primes[5]); // prints 13
```

We can reassign one element of the array as long as we specify that element's
index:

```java
int[] primes = new int[] { 2, 3, 5, 7, 11, 13 };
primes[2] = 10;
println(primes[0]); // prints 2
println(primes[1]); // prints 3
println(primes[2]); // prints 10!
```

If you don't specify an index, you'll be attempting to reassign the variable
that holds the array. This will usually result in a syntax error:

```java
int[] primes = new int[] { 2, 3, 5, 7, 11, 13 };
primes = 10; // primes is an array, not an int, so we can't reassign it to 10
```

## Getting Used to Zero-Indexing

Many people find zero-indexing counterintuitive. If you think of the position of
an element, then you need to subtract one from the position to get the element's
index. This isn't intuitive, and it forces you to do extra work each time you
think about the index as a position.

The best analogy I've heard for zero-indexing is a ruler: the first mark on a
ruler represents a distance of zero, not one. This is why I recommend thinking
about indexes as distances rather than positions.

## Array Bounds

You can get the length of an array by typing `.length` after the name:

```java
int[] primes = new int[] { 2, 3, 5, 7, 11, 13 };
println(primes.length); // prints 6
```

The only valid indexes for an array are the integers from zero to its length
minus 1. The length is never a valid index. For example, if we had an array of
length 10 then the tenth and last element would be at index 9. An index of 10
would be the eleventh element, and the array only has ten elements.

If we try to index an array with a negative number, or with a number greater
than or equal to its length, then this will cause an
`ArrayIndexOutOfBoundsException`, which is a type of error that will cause the
program to crash.

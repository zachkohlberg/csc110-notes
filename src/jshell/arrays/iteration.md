# Iterating Over Arrays

So far, arrays haven't made our lives any easier. If we always have to provide a
specific index when we interact with an array, it might as well be a bunch of
separate variables. This:

```java
String[] names = new String[] { "Alice", "Bob", "Charles" };
names[1] = "Robert";
println(names[0]);
println(names[1]);
println(names[2]);
```

is no different from this:

```java
String name1 = "Alice", name2 = "Bob", name3 = "Charles";
name2 = "Robert";
println(name1);
println(name2);
println(name3);
```

In fact, the second version is probably easier to follow. So why would we use an
array?

The short (and probably not very helpful) answer is because we can also index an
array using a variable:

```java
String[] names = new String[] { "Alice", "Bob", "Charles" };
int index = 1;
names[index] = "Robert";
index = 0;
println(names[index]);
index = 1;
println(names[index]);
index = 2;
println(names[index]);
```

Acutally, that's even worse, isn't it? What if we just focus on the printing,
and we increment the index instead of assigning specific numbers?

```java
String[] names = new String[] { "Alice", "Bob", "Charles" };
int index = 0;
println(names[index]);
index = index + 1;
println(names[index]);
index = index + 1;
println(names[index]);
```

That's not much better either. Obviously there's a point to all this, I'm not
just wasting your time. Take another look at the last version. Did you notice
two of the lines were copied and pasted several times with no changes? Isn't
there a more convenient way to repeat two lines of code over and over again?

```java
String[] names = new String[] { "Alice", "Bob", "Charles" };
int index = 0;
while (index < 3) {
    println(names[index]);
    index = index + 1;
}
```

It turns out there is! The fact that we can index with a variable lets us use a
counting loop to print each element of the array. This is even nicer if we use a
for loop:

```java
String[] names = new String[] { "Alice", "Bob", "Charles" };
for (int i = 0; i < 3; ++i) {
    println(names[i]);
}
```

What happens if we add some more names?

```java
// without an array
String name1 = "Alice", name2 = "Bob", name3 = "Charles", name4 = "David",
       name5 = "Eve";
println(name1);
println(name2);
println(name3);
println(name4);
println(name5);

// with an array
String[] names = new String[] { "Alice", "Bob", "Charles", "David", "Eve" };
for (int i = 0; i < names.length; ++i) {
    println(names[i]);
}
```

I changed the condition to `i < names.length` instead of `i < 5` because
`names.length` will always be the length of the array. Now if the array gets
larger again we won't have to change any part of the loop. Hopefully this shows
you why it's nice to have an array. Just in case you're not convinced, consider
what this would look like if we had 1000 names.

```java
// without an array
String name1 = "Alice", name2 = "Bob", /* 997 names omitted */ name1000 = "asdf";
println(name1);
println(name2);
println(name3);
println(name4);
println(name5);
println(name6);
/* 993 print statements omitted */
println(name1000);

// with an array
String[] names = new String[] { "Alice", "Bob", /* 997 names omitted */ "asdf" };
for (int i = 0; i < names.length; ++i) {
    println(names[i]);
}
```

The loop can still print the entire array with three lines of code. This is part
of what makes arrays so powerful: when combined with a loop, you can process
vast amounts of information with several lines of code.

## Enhanced For Loop

Java has another type of for loop called an "enhanced for loop". You might also
see this type of loop referred to as a "foreach" loop or a "for comprehension".
An enhanced for loop is useful when you want to iterate over an array, but you
don't need to modify the array and you don't need to know the index of an
element.

```java
for (String name: names) {
    println(name);
}
```

The `for (String name: names) {` is another example of syntactic sugar. The
enhanced for loop shown above is equivalent to the following regular for loop:

```java
for (int i = 0; i < names.length; ++i) {
    String name = names[i];
    println(name);
}
```

The `for (String name: names) {` is a shorter way of writing the first two
lines, but you no longer have access to the `i` variable inside your loop.

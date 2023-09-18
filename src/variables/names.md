# Variable Names

Variable names, and identifiers in general, have to follow a few rules in Java.
You can find these rules at the end of [this](
https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html) page,
but we'll summarize them here:
- You cannot use a [Java keyword](
https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html as an
identifier.
- An identifier can only contain letters (uppercase or lowercase), numbers,
the underscore character (`_`), or the dollar sign (`$`) character.
- An identifier cannot begin with a number.
- Identifiers are case-sensitive, which means `thisname` and `thisName` are
*different* identifiers even though they look nearly the same.

There are also some optional rules that you *should* follow with identifiers.
These rules are only optional in the sense that your code can technically run if
you break these rules, but your code will be harder to read and much more likely
to contain errors if you don't follow them.
- Java variable names should follow the lower camel case naming convention. This
means all variable names should start with a lowercase letter, contain no
underscores or dollar signs, and each word after the first should start with an
uppercase letter. For example `thisVariableNameIsUsingLowerCamelCase`, although
in practice you don't want your variable names to be that long. This is
important because most other Java code (including the standard library code you
will be using in your own programs) is written this way, and not following this
convention will make the names in your code inconsistent and easy to mix up.
- Don't create two identifiers that are the same except for capitalization. This
is confusing and makes it easy to accidentally use the wrong identifier.
- Whenever possible, give your variables descriptive names. If a variable has
some inherent meaning (such as a variable that stores a person's name), then use
a name that will tell the reader what that meaning is. For example, a variable
that stores someone's age could be called `age`, and a variable that stores a
person's name could be called `name`. This makes it much easier to understand
your code.

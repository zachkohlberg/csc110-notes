# Primitive Type Summary

The table below summarizes Java's [primitive types](
https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html).

|type name|category|size (bits)|size (bytes)|min value|max value|
|:---:|:---:|:---:|:---:|:---:|:---:|
|byte|signed integer|8|1|-256|255|
|short|signed integer|16|2|-32,768|32,767|
|int|signed integer|32|4|-2,147,483,648|2,147,483,647|
|long|signed integer|64|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|
|float|floating-point|32|4|-3.4028235E38|3.4028235E38|
|double|floating-point|64|8|-1.7976931348623157E308|1.7976931348623157E308|
|char|unsigned integer|16|2|0|65,535|
|boolean|boolean|8|1|N/A|N/A|

A few notes about the above table:
- The size is how much of the computer's memory a single value of this type
requires
- The `char` type represents a single text character, but it `char`s are stored
as integers and will readily convert to an `int`
- The main integer types are listed as **signed**, which means they can
represent positive **and** negative numbers (and zero). An unsigned integer type
(such as `char`) can only represent positive numbers (and zero).
- The notation used for the min/max values of floating-point numbers is a form
of scientific notation called "E notation". The E38 means "multiplied by
10^38," and the E308 means "multiplied by 10^308". These are extremely large
numbers, which is why we write them with scientific notation.
- The `String` type is not a primitive type and does not appear on the table

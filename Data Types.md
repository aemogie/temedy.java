**DATA TYPES**
In the java language, there are two kinds of data types:

**1)** Primitive data types\
**2)** Reference data types

**Primitive data types include:**\
`byte`, can store values of `-128` to `127`  (1 byte)\
`short`, can store value of `-32768` to `32767` (2 bytes)\
`int`, can store value of `-2147483648` to `2147483647` (4 bytes)\
`long`, can store value of `-9223372036854775808` to `9223372036854775807` (8 bytes)\
`char`, can store characters (2 bytes)\
`double`, can store decimal numbers (8 bytes)\
`float`, can store decimal numbers (4 bytes)\
`boolean`, can either store **true** or **false** (1 byte)

The reason why would you use data types such as `byte` over an `int` or `long` is saving memory. When you have simple variables and their value doesn't go larger than 127 there's no reason to use `int`

Reference data types include things such as interfaces, classes, arrays, and so on.

**Important notes:** Reference data types are objects, while primitive data types aren't.
Primitive data types can not point to `null` reference while reference data types can.
The value of reference data types defaults to `null`, however. In the case of primitives, their default value is assigned (the minimum value)

Now we will discuss some of the reference types.

`String`, which is a class that is **immutable**, is essentially a type for a sequence of characters with a few useful methods. The string can be of any length that must be within the maximum value of an `int` data type\
`Array`, arrays in java are objects that can be created of any type, regardless if it's a primitive or a reference type. An array is a linear data structure that holds elements. It can have a length that must be within the max value of the data type `int`. If a value below `0` is specified, a `NegativeArraySizeException` is thrown. We will also cover exceptions and all of the other things in the next tutorials. 

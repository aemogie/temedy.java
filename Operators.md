**OPERATORS**\
There are many operators, but we will begin with the simpliest one: the assignment operator.

**ASSIGNMENT OPERATOR**\
To assign our variable foo from the previous section a value, we have two ways of doing that.

The first style is:
```java
int foo = 1;
```
and the other
```java
int foo;
foo = 1;
```

The first is doing a declaration & an assignment at the same time, while the other is split into declaration and assignment (we will discuss this later in the section **7** (OOP))

If we are working with primitives, we are assigning those variables a `value`.
And if we are working with reference types, we are assigning those variables a `reference`.

We will explain the differences between those two, and on how java handles them.

**ARITHMETIC OPERATORS**\
These are five arithmetic operators available.\
`+`,  addition\
`-`,  subtraction\
`/`,  division\
`*`, multiplication\
`%`, modulo (remainder)

Those can be only used while working with primitive types.\
The only exception is a string concatenation, where we want to put two sequence of characters (string literals) together. The java compiler then uses a class in the JDK called StringBuilder and concatenate those strings together.

An example usage of those operators:
```java
int foo = 1;
int bar = 2;

int result = foo + bar;
```

Also we don't have to declare a those variables called `foo`, `bar`.
It can also be written like this
```java
int result = 1 + 2;
```

Although it doesn't make much sense here to do that, it's just to show how to use these operators. The rest can be used just the same as the addition operator.

**Note:** We get an `ArithmeticException` when we try to divide by zero.

**UNARY OPERATORS**\
`+`, gives a value (or a variable) a positive value\
`-`, gives a value (or a variable) a negative value\
`++`, an addition operator that increases a variable value by 1. Can only be performed on variables, and there are two ways of using this operator, we will discuss them.

`--`, a subtraction operator that decreases a variable value by 1. can only be performed on variables, just like the `++` operator.\
`!` inverts the value of a boolean (we will see an example of that)\
The `+`, `-` operators are simply used in value assignment to either give a variable a positive/negative value.\
Behold this code:
```java
int foo = -10;
//foo is now -10
int bar = +10;
//bar is now 10
```

The second set of operators\
`++` and `--` operators can be used like:
```java
int foo = 10;
int result = foo++;
```

Now to explain, `++` **after** a variable reference first gets the original value from `foo` (which is 10) and assigns it to the variable `bar` and then increments by one.

So in conclusion, `foo` will be 11 while `result` will be 10.\
The other way it can be used is before a variable reference.
```java
int foo = 10;
int result = ++foo;
```

To explain the process, first, the variable foo is incremented by one and then assigned to the variable `result`, so both `foo` and `result` will be 11 here.

Now, the last operator, the boolean invert operator is very simple.\
It can only be used on boolean values `true`, `false` and all it's self explanatory.
An example of that is:
```java
boolean foo = true;
boolean bar = !foo;
```

Now, the value of `foo` will remain true, as the operator doesn't change the value of the original variable (it's not an assignment, so it differs from the last two operators), and the variable `bar` will have the value `false`, because we have inverted it. This can obviously be used the other way around aswell (if we start with `false`)

**BOOLEAN OPERATORS**\
`==`, compares a value when used on primitive types and a reference when used on reference types\
`>=`, is greater than or equal\
`<=`, is less than or equal\
`>`, is greater than\
`<`, is less than\
`!=`, an inverted `==` operator (is not equal to)\
`&&`, boolean AND, used to combine many boolean expressions together and check if they **all** return true and returns a boolean value (`true`, `false`) depending on that.\
`||`, boolean OR, used to combine many boolean expressions together and check if **atleast** one of them is true and returns a boolean value (`true`, `false`) depending on that.\
`instanceof`, used for checking if an **object** is an instance of a particular class or it's subtype.\
`? :`, the ternary operator, essentially an inline if statement.

What is a boolean expression?
It's a line of code that either returns `true` or `false`
For example:
```java
boolean foo = 1 < 2;
```

`1 < 2` is the boolean expression here.
The variable `foo` will now hold the value `true`

or:
```java
boolean foo = 1 < 2 || 2 < 1;
```

The variable `foo` will now hold the value `true` again, even though the second expression returns `false`. That is because its an or operator and the first expression has returned `true`.
```java
boolean foo = 1 < 2 && 2 < 1;
```

Would however hold the value `false`, because the second expression returned `false`.

Now, boolean expressions can be used in many places where a boolean is needed. For example an if statement (we will go through those aswell)
```java
int foo = 5;
int bar = 10;

if (bar > foo) {
// run some code
}
```

As for understanding the `instanceof` operator, you may have to go through the object oriented programming section.
Here is an example tho:
```java
Object object = new Boolean(Boolean.TRUE);
boolean foo = object instanceof Boolean;
```

And the last, `?:` (the ternary operator) is an inline if and makes up a boolean expression.
Here is an example:
```java
boolean foo = 10 > 5 ? true : false;
```

Obviously, this could just be simplified to `10 > 5` here because it's a simple assignment, but it could be used to assign different values or possibly references to our variables.
Here is how it looks with a regular if statement:
```java
boolean foo;
if (10 > 5) {
foo = true;
} else {
foo = false;
}
```

**BIT OPERATORS**\
`>>`, unsigned right shift operator, shifts a bit sequence to the right by a specified amount.\
`<<`, unsigned left shift operator, shifts a bit sequence to the left by a specified amount.\
`~`, bit invert operator, goes through a sequence of bits (for example a `byte`) and turns every bit to it's opposite value (`1` to `0` for example)\
`&`, bit AND\
`|`, inclusive bit OR\
`^`, exclusive bit OR

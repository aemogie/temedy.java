# Expressions
Expressions are a part of statements, which are a part of blocks.\
An expression is made up of values/operators and returns a single value.\
Some of the simplest expressions include boolean expressions, number expressions, or, string expressions.

As an example, we can take a boolean expression
```java
1 > 0
```

Which would return the boolean value true.\
A number expression would look like
```java
0
```

while a string expression would look like
```java
"foo"
```


Expressions alone are not useful and cannot be used on their own, but they are the components of statements, which involve functionality.

# Statements
A statement is a unit of execution, and must be ended with the `;` character.

Variable declaration is a **statement**.

A statement may or may not return a value. If it does, it's called an expression statement. Examples of expression statements are method calls that are of a different type than `void`.

Let's take an example of a variable declaration
```java
int foo;
```

This is a **declaration statement**, which does not involve expressions, and is also not useful on it's own.

We can change this by assigning a value to it.
```java
int foo = 0;
```

As you can see, the statement now contains an expression (`0`), takes the value assigns it to the variable `foo`.

However, the statement still remains a declaration statement (it does not return any value).

We can make it an expression statement by splitting into declaration & assignment.
```java
int foo;
foo = 0;
```

The first line of code is a declaration statement, while the other line of code is an expression statement.\
The last type of statements are control flow statements which i'll cover later.

# Blocks
A block is a space which can contain statements, which contain expressions.\
We can define a block by a pair of brackets (`{}`).
```java
{
    int foo;
    foo = 0;
}
```

These four lines of code contain a single block, two statements, and a single expression.
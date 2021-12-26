# Control Flow
Control flow allows us to make decisions, loop, or manipulate with our code in other ways. It is also the last type of statements.

We will begin with if statements. The syntax is the following:
```java
if (expression) {

}
```

First, we begin with the `if` keyword, then put brackets around and a boolean expression inside the brackets. then we add a thing called **if body**, which are just two `{}` brackets that introduce a **block**.

We have used if statements before, they are kinda simple.
```java
if (true) {
    // code ran when true
} else {
    // code ran when false
}
```

With our boolean expressions, we can also apply things such as `||` or `&&` when needed, or possibly invert our boolean expression.

The second control flow statement is a for loop which is a bit harder.
Syntax is the following:
```java
for (declaration; condition; operation) {

}
```

We first declare a variable (such as an `int`), then a condition and finally an operation.

The simpliest form of a for loop is:
```java
for (int counter = 0; counter < 10; counter++) {
    // code here will run 10 times
}
```

We first declare an `int` variable counter and assign it the value `0`, then we specify a condition (a boolean expression which is `counter < 10` here), and then we tell the loop what to do when the condition is true. Here, we [increment](03_Operators.md#unary-operators) the variable `counter` by one.

The `while` loop is also a loop, but it only takes a condition (boolean expression) to run. The loop will run if the condition will be `true`. Once the expression will return `false`, the loop will automatically `break`. `break` is also a keyword, that we will discuss soon alongside with the keyword `continue`. Let's see this example of a while loop that will run infinitely.
```java
while (true) {
    // ..
}
```

The `do-while` loop is essentially almost the same as the while loop and the syntax is the following:
```java
do {
    //code is ran once
} while (false);
```

Now, the only difference here is that the code inside the block of `do` will run **at least** once, even if the expression in `while` always returns `false`

Switch is a way how to chain more `if` statements with the option of breaking. Switch consists of cases and a `default` (optional).
See this example:
```java
int foo = 1;
switch (foo) {
    case 1: {
        // code here is ran
    }
    case 2: {
        // code here is also ran because we have not added a break in the first case
    }
}
```

As you can see, if switch meets the correct case, it will keep going through all the other cases below it until it meets a `break`.
We can also add a default to the switch to run some code if none of the cases is the value specified.

Note that we can only use enumerations, strings and all primitives in a switch, no other `objects`.

I will explain why is an enumeration and a string possible in a switch later.
```java
int foo = 1;
switch (foo) {
    case 1: {
        // code here is ran
        break;
    }
    case 2: {
        // code here is not ran
    }

    default: {
        // code here is always ran
        break;
    }
}
```

**The `break` and `continue` keywords**

As we have seen, the `break` keyword can be used in a loop but also in a switch, however the `continue` keyword can only be used in loops.

The break keyword ends execution of the control flow statement (such as a loop or a switch) and the `continue` keyword skips 1 iteration in the loop (but not ending it entirely)

We will later discuss the keyword `return` and how it's similar to the keyword `continue`, it essentially does the same thing but `continue` only returns from the control flow statement, while return `returns` from an entire function.
```java
int foo = 0;
while (foo < 10) {
    if (foo <= 5) {
        ++foo;
        continue;
    }

    ++foo;
    // do extra work here
}
```

Now, code here will only increment `foo` by one 6 times and by saying `continue`, we skip the current execution (iteration) of the control flow statement, so anything after the first if statement doesn't get executed.
If we used a `break` however, the entire execution of the loop would be terminated.
```java
int foo = 0;
while (foo < 10) {
    if (foo <= 5) {
        ++foo;
        break;
    }

    ++foo;
    // do extra work here
}
```

In addition to if statements, we can write multiple if statements like this:
```java
if (condition) {
    // ..
} else if (condition) {
    // ..
} else if (condition) {
    // ..
} else {
    // ..
}
```

Which would run any of the `if` statements if their condition would be `true`, but note that the difference between writing them as separate statements is that if one of the `if` statements is `true`, the statements after it don't get executed any more, kinda like a switch with a `break` in every case.

If none of those conditions would be `true` however, the `else` statement would run.
# Variables
A variable is a named container that can contain a single value (or a reference) of it's type.

Variables consist of:
1. Type
2. Name
3. Value

The following is an example of the most basic variable:
```java
int foo = 1;
```

- `int` is the type
- `foo` is the name
- `1` is the value.

To declare multiple variables with the same type, we can use:
```java
int foo, foo1, foo2;
```

This style of declaration is also valid for any other data types (reference or primitive)\
We can for example also do:
```java
String foo;
```

and
```java
String foo, foo1, foo2;
```

Remember that the term value is only used when working with primitive types, but when we are working with reference types, we usually store a reference to a particular object. 

There are four types of variables.
1. Instance variable (also known as field)
2. Class variable (also known as static field)
3. Local variable
4. Parameter

Instance variables (fields) are variables that belong to an instance of a particular class. For example, behold a class `Car`.
```java
class Car {
    float speed;
    String make;
}
```

We will discuss the syntax of classes in the next section.\
The class currently has 2 instance fields (`speed`, `make`) which have no value assigned (the `speed` value defaults to `0.0f` and the `make`'s reference defaults to a `null` reference).

Classes in java inherit from a superclass called `Object`. which has an empty **constructor** available.\
That means we can do
```java
Car car = new Car();
```

and we have created out first car. Now to assign values to our fields, we simply do:
```java
Car car = new Car();
car.speed = 1f;
car.make = "Ford";
```

Instance variables just mean that they belong to an **instance of a class** (also known as an object, not to be confused with the class `Object`), they don't represent a global state and are completely instance dependent. We will discuss instances and classes later.

Class variables, are those which are declared with the `static` modifier and belong to the class rather than to an instance of the class (object).\
A class variable is loaded on a load of a class (since it belongs to the class) instead of an instantiation of a class. Since it represents a global state, it's value will be the same across all instances or static contexts.

A class variable **cannot** be garbage collected, unless it's reference or value is set to `null` manually, or unless the class it's contained in is unloaded.

Local variables are those we define in the block (or scope) of a function.\
We have already encountered a block before.

A block is simply a region of code, see this example:
```java
class Car {
    float speed;
    String make;

    void drive() {
        speed = 1f;
    }

    void stop() {
        speed = 0f;
    }
}
```

Within the scope of the `drive` method, we can access all instance variables such as the variable `speed`.\
If we would create a **local variable** inside the method `drive`, it would be only accessible in the scope of the method, not outside the method.
```java
class Car {
    float speed;
    String make;

    void drive() {
        int foo = 1;
        speed = 1f;
    }

    void stop() {
        foo = 2; //undefined variable
        speed = 0f;
    }
}
```

Parameters, are variables that are passed into **functions**.\
Functions include a constructor and a method.\
Let's modify our last example:
```java
class Car {
    float speed;
    String make;

    void drive(float newSpeed) {
        speed = newSpeed;
    }

    void stop() {
        speed = 0f;
    }
}
```

One important thing to remember is that, **primitive types are pass-by-value** and **reference types are pass-by-reference**.\
This means that if we create an instance of our class `Car` and call the `drive` method it's parameter (a `float`)
```java
Car car = new Car();
car.drive(2f);
```

The value will be passed into the method and turned into a local variable in our scope of `drive`.\
If we would predefine a variable called speed and then pass it into the method:
```java
Car car = new Car();
float speed = 2f;

car.drive(speed);
```

And then change the value inside the method `drive`, it's value would only be changed in the scope of the method we called. The original variable `speed` would still have the value `2f` no matter what.\
This is because primitive types are pass by value, so their value gets copied into the method parameter. 

To finish the parameter section, reference types are pass-by-reference as we said. We are still not allowed to change the references of objects when they are passed into functions. The only difference is that there is no copy of an object made, the object that was passed into the function is still the same object. This means that we can still change the fields (mutate) the original object, however we are only not allowed to change the reference (again, only in the scope of the method)
```java
Car toyota = new Car();

Car ford = new Car(toyota);
```


There is a new concept used, which is a **constructor**.
```java
class Car {
    float speed;
    String make;

    Car() { //empty
    }

    Car(Car car) {
        car.speed = 1;
        car.make = "Ford";
    }

    void drive() {
        // ..
    }
}
```

The instance variables (fields) of `toyota` **will change** to the ones we have defined in the `Car` constructor (`1`, `Ford`), but if we attempt to change the reference of the parameter `car` to for example  a `null` reference, nothing will change and we will still be able to operate with our original `toyota` object.

```java
class Car {
    float speed;
    String make;
    
    Car() { //empty
    }
    
    Car(Car car) {
        car.speed = 1;
        car.make = "Ford";
        car = null; // this is fine
    }
    
    void drive() {
    // ..
    }
}
 
```

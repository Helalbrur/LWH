In PHP, functions come in various forms: **variables**, **anonymous functions**, **callables**, **closures**, and **arrow functions**. Let's explore each of these concepts with examples.

### 1. **Variable Functions in PHP**

A **variable function** allows you to call a function dynamically, using the value of a variable as the function name.

#### Example:

```php
function greet() {
    echo "Hello, World!\n";
}

$func = "greet";  // $func holds the function name as a string
$func();  // Outputs: Hello, World!
```

In the above example, the `$func` variable holds the name of the function `greet()`. By calling `$func()`, PHP dynamically invokes the function.

### 2. **Anonymous Functions (Closures)**

An **anonymous function** (also known as a **closure**) is a function that has no name. You can define anonymous functions and assign them to variables. These functions can be passed around as values, which is especially useful in callback contexts.

#### Example of Anonymous Functions:

```php
$greet = function($name) {
    return "Hello, $name!";
};

echo $greet("Alice");  // Outputs: Hello, Alice!
```

### 3. **Callable in PHP**

A **callable** is a type of value that can be used to call a function or method. It can be a string (the name of a function), an array (the class and method), or an anonymous function.

- **String callable:** A named function.
- **Array callable:** A method within a class.
- **Object callable:** An anonymous function or closure.

You can check whether something is callable using the `is_callable()` function.

#### Example of Callable:

```php
function sayHello() {
    echo "Hello!\n";
}

$callable = 'sayHello';  // A string can represent a callable function

if (is_callable($callable)) {
    $callable();  // Calls sayHello(), Outputs: Hello!
}
```

#### Example with Object Method Callable:

```php
class Greeter {
    public function greet($name) {
        return "Hello, $name!";
    }
}

$greeter = new Greeter();
$callableMethod = [$greeter, 'greet'];

echo call_user_func($callableMethod, "Alice");  // Outputs: Hello, Alice!
```

In this case, we use an array to represent a callable method: `[$greeter, 'greet']`, where `$greeter` is an object and `'greet'` is the method name.

### 4. **Closure Functions**

A **closure** is a type of anonymous function that can capture variables from the surrounding scope (i.e., it can "close over" variables). Closures are useful when you need to reference variables from the environment where the closure was created.

To bind a variable to a closure, you can use the `use` keyword.

#### Example of Closures:

```php
$name = "Alice";

$closure = function() use ($name) {
    echo "Hello, $name!";
};

$closure();  // Outputs: Hello, Alice!
```

In the example above, the `$name` variable is captured from the surrounding scope using `use`. Even though `$name` is not defined inside the closure, it is still accessible.

### 5. **Arrow Functions (PHP 7.4+)**

**Arrow functions** are a shorthand for anonymous functions that automatically capture variables from the surrounding scope by reference. They were introduced in PHP 7.4 and simplify the syntax of closures.

#### Syntax of Arrow Functions:

- The arrow function uses `fn` as a keyword.
- It automatically captures variables from the parent scope by reference.

#### Example of Arrow Functions:

```php
$numbers = [1, 2, 3, 4];

$square = fn($num) => $num * $num;

foreach ($numbers as $number) {
    echo $square($number) . " ";  // Outputs: 1 4 9 16
}
```

## 5 High Order function
High Order function are related to functional programming. Basically these kind of functions has at least one of these features.

Takes one or more functions as arguments.
Return a function as its result.

```php
$addNineAndMultiplyByTen = function($callback, $value) {
    return $callback($value) * 10;
};
$addNine = function($value) {
    return $value + 9;
};
$result = $addNineAndMultiplyByTen($addNine, 1); //$addNineAndMultiplyByTen is high order function

echo $result;
```

In the above example, the arrow function `fn($num) => $num * $num` is a short way to define an anonymous function. It automatically captures any required variables (like `$num`) from the outer scope. However, it does **not** require the `use` keyword, and it captures variables by reference automatically.

### Summary Table of Key Concepts

| **Feature**          | **Description**                                                                                                      | **Example**                                                                                       |
|----------------------|----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Variable Function** | Calling a function dynamically using a variable containing the function's name.                                      | `$func = "greet"; $func();`                                                                         |
| **Anonymous Function**| A function without a name, often assigned to variables or passed as arguments.                                        | `$greet = function($name) { return "Hello, $name!"; }; echo $greet("Alice");`                    |
| **Callable**          | A type of value that can be used to call a function or method. It can be a string, array, or object.                 | `call_user_func([$greeter, 'greet'], "Alice");`                                                   |
| **Closure**           | An anonymous function that can capture and use variables from the surrounding scope using the `use` keyword.          | `$name = "Alice"; $closure = function() use ($name) { echo "Hello, $name!"; }; $closure();`       |
| **Arrow Function**    | A shorter syntax for anonymous functions introduced in PHP 7.4 that automatically captures variables by reference.    | `$square = fn($num) => $num * $num;`                                                              |

### Conclusion

- **Variable Functions** allow dynamic function calls.
- **Anonymous Functions** (or **Closures**) are functions without a name, useful for callbacks and encapsulating logic.
- **Callables** are flexible references to functions or methods.
- **Arrow Functions** are a more concise version of closures, automatically capturing variables from the parent scope by reference.

These features are useful when writing flexible and reusable code in PHP, particularly when working with higher-order functions or handling callbacks.
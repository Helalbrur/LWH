### Variable Scopes in PHP

In PHP, the scope of a variable defines where that variable can be accessed and modified. There are four main types of variable scopes:

1. **Global Scope**  
2. **Local Scope**  
3. **Function Scope**  
4. **Static Scope**

#### 1. **Global Scope**

A variable declared outside of any function or class has **global scope**. It can be accessed anywhere outside of functions or classes, but not inside a function unless explicitly referenced using the `global` keyword or by accessing the `$GLOBALS` array.

**Example of Global Scope:**

```php
$globalVar = "I'm a global variable";

function testGlobal() {
    // Accessing global variable using the `global` keyword
    global $globalVar;
    echo $globalVar;  // Output: I'm a global variable
}

testGlobal();
```

Alternatively, you can also access global variables via the `$GLOBALS` array:

```php
$globalVar = "I'm a global variable";

function testGlobal() {
    echo $GLOBALS['globalVar'];  // Output: I'm a global variable
}

testGlobal();
```

#### 2. **Local Scope**

A variable declared inside a function or method has **local scope**, meaning it is only accessible within that function or method.

**Example of Local Scope:**

```php
function testLocal() {
    $localVar = "I'm a local variable";
    echo $localVar;  // Output: I'm a local variable
}

testLocal();

// Trying to access $localVar outside the function will result in an error
// echo $localVar;  // Error: Undefined variable $localVar
```

#### 3. **Function Scope (Parameters)**

Parameters passed to a function have function scope, meaning they are only accessible within that function. They are considered local to the function.

**Example of Function Scope:**

```php
function greet($name) {
    echo "Hello, $name!";  // Output: Hello, Alice!
}

greet("Alice");

// The $name parameter is not accessible outside the function
// echo $name;  // Error: Undefined variable $name
```

#### 4. **Static Variables**

A **static variable** in PHP retains its value between function calls. It does not lose its value when the function execution is completed, unlike normal local variables. A static variable is declared using the `static` keyword.

**Example of Static Variables:**

```php
function counter() {
    static $count = 0;
    $count++;
    echo $count . "\n";  // Output: 1, 2, 3, ...
}

counter();  // Output: 1
counter();  // Output: 2
counter();  // Output: 3
```

In this example, the static variable `$count` retains its value between function calls, so the count continues incrementing each time `counter()` is called.

Without the `static` keyword, the variable would be reset to `0` every time the function is called.

```php
function counter() {
    $count = 0;
    $count++;
    echo $count . "\n";  // Output: 1, 1, 1...
}

counter();  // Output: 1
counter();  // Output: 1
counter();  // Output: 1
```

#### Static Variables and Memory Efficiency

Static variables are stored in memory throughout the script's execution, unlike normal local variables, which are discarded after the function call ends.

### Using Static Variables in Classes

You can also use static variables inside classes. In this case, the static variable belongs to the class rather than an instance of the class. It can be accessed using the `::` syntax.

**Example with Static Variables in Classes:**

```php
class Counter {
    static $count = 0;
    
    public static function increment() {
        self::$count++;
    }
    
    public static function getCount() {
        return self::$count;
    }
}

Counter::increment();
Counter::increment();

echo Counter::getCount();  // Output: 2
```

In this example:
- `self::$count` refers to the static variable `$count` inside the class `Counter`.
- We use `Counter::increment()` to modify the static variable, and `Counter::getCount()` to access its value.

### Summary of Scopes in PHP

| **Scope Type**       | **Description** | **Access**  |
|----------------------|-----------------|-------------|
| **Global Scope**      | Variables outside functions | Accessible anywhere outside functions |
| **Local Scope**       | Variables inside functions  | Accessible only within the function |
| **Function Scope**    | Function parameters | Accessible only within the function |
| **Static Variables**  | Variables with `static` keyword | Retain values across function calls, accessible only inside the function or class |

Static variables are useful when you need to preserve the state between function calls or maintain state at the class level across instances, without making it part of the instance itself.
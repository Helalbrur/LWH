# Lesson 1.2 - Data Types & Casting

# PHP Data Types

Variables can store data of different types, and different data types can perform various operations. PHP supports the following data types:

## Data Types Overview

- **String**
  - A sequence of characters.
  - **Example:** 
    ```php
    $name = "John Doe";
    ```

- **Integer**
  - A whole number, positive or negative.
  - **Example:**
    ```php
    $age = 30;
    ```

- **Float**
  - Floating point numbers (also called double).
  - **Example:**
    ```php
    $price = 19.99;
    ```

- **Boolean**
  - Represents two possible values: `true` or `false`.
  - **Example:**
    ```php
    $isStudent = true;
    ```

- **Array**
  - A collection of values, which can be of different types.
  - **Example:**
    ```php
    $colors = ["red", "green", "blue"];
    ```

- **Object**
  - An instance of a class, encapsulating data and functions.
  - **Example:**
    ```php
    class Car {
        public $brand;
        public function honk() {
            return "Beep!";
        }
    }
    
    $myCar = new Car();
    $myCar->brand = "Toyota";
    ```

- **NULL**
  - Represents a variable with no value.
  - **Example:**
    ```php
    $nothing = null;
    ```

- **Resource**
  - A special variable holding a reference to an external resource (like a database connection).
  - **Example:**
    ```php
    $connection = mysqli_connect("localhost", "username", "password");
    ```

Feel free to explore these data types as you build your PHP applications!

## PHP Variable Handling Functions

The PHP variable handling functions are part of the PHP core. No installation is required to use these functions.

| Function                    | Description                                              |
|-----------------------------|----------------------------------------------------------|
| `boolval()`                 | Returns the boolean value of a variable                  |
| `debug_zval_dump()`         | Dumps a string representation of an internal zend value to output |
| `doubleval()`               | Alias of `floatval()`                                    |
| `empty()`                   | Checks whether a variable is empty                       |
| `floatval()`                | Returns the float value of a variable                    |
| `get_defined_vars()`        | Returns all defined variables, as an array               |
| `get_resource_type()`       | Returns the type of a resource                           |
| `gettype()`                 | Returns the type of a variable                           |
| `intval()`                  | Returns the integer value of a variable                  |
| `is_array()`                | Checks whether a variable is an array                    |
| `is_bool()`                 | Checks whether a variable is a boolean                   |
| `is_callable()`             | Checks whether the contents of a variable can be called as a function |
| `is_countable()`            | Checks whether the contents of a variable is a countable value |
| `is_double()`               | Alias of `is_float()`                                    |
| `is_float()`                | Checks whether a variable is of type float               |
| `is_int()`                  | Checks whether a variable is of type integer             |
| `is_integer()`              | Alias of `is_int()`                                      |
| `is_iterable()`             | Checks whether the contents of a variable is an iterable value |
| `is_long()`                 | Alias of `is_int()`                                      |
| `is_null()`                 | Checks whether a variable is NULL                         |
| `is_numeric()`              | Checks whether a variable is a number or a numeric string |
| `is_object()`               | Checks whether a variable is an object                   |
| `is_real()`                 | Alias of `is_float()`                                    |
| `is_resource()`             | Checks whether a variable is a resource                  |
| `is_scalar()`               | Checks whether a variable is a scalar                    |
| `is_string()`               | Checks whether a variable is of type string              |
| `isset()`                   | Checks whether a variable is set (declared and not NULL) |
| `print_r()`                 | Prints the information about a variable in a human-readable way |
| `serialize()`               | Converts a storable representation of a value            |
| `settype()`                 | Converts a variable to a specific type                   |
| `strval()`                  | Returns the string value of a variable                   |
| `unserialize()`             | Converts serialized data back into actual data           |
| `unset()`                   | Unsets a variable                                        |
| `var_dump()`                | Dumps information about one or more variables            |
| `var_export()`              | Returns structured information (valid PHP code) about a variable |

# PHP Function: Iterating Through Arrays

## Function Definition

```php
function iterateArray($array) {
    foreach ($array as $key => $value) {
        if (is_array($value)) {
            // If the value is an array, call the function recursively
            iterateArray($value);
        } else {
            // Otherwise, it's a scalar value, so process it
            echo "Key: $key, Value: $value\n";
        }
    }
}
```

## Example Usage

```php
$multiDimensionalArray = [
    'a' => [
        'b' => [
            'c' => 1,
            'd' => 2
        ],
        'e' => 3
    ],
    'f' => 4
];

iterateArray($multiDimensionalArray);
```

## Change Data Type

Casting in PHP is done with the following statements:

- **(string)** - Converts to data type String
- **(int)** - Converts to data type Integer
- **(float)** - Converts to data type Float
- **(bool)** - Converts to data type Boolean
- **(array)** - Converts to data type Array
- **(object)** - Converts to data type Object
- **(unset)** - Converts to data type NULL

Use these casting statements to explicitly change the data type of a variable in your PHP code!
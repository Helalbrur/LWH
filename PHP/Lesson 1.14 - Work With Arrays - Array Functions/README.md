In PHP, arrays are a fundamental data structure, and there are a lot of built-in functions to help manipulate and work with arrays. We'll cover the most commonly used array functions, categorized into various groups, such as array creation, modification, search, sorting, and iteration.

### 1. **Array Creation Functions**

You can create arrays in PHP using several functions and techniques.

#### **`array()`**

The `array()` function is the traditional way to create arrays. 

```php
// Indexed array
$fruits = array("Apple", "Banana", "Cherry");

// Associative array
$person = array("name" => "John", "age" => 25);

// Multidimensional array
$matrix = array(
    array(1, 2, 3),
    array(4, 5, 6),
    array(7, 8, 9)
);
```

#### **`range()`**

The `range()` function creates an array of elements between two given values.

```php
$numbers = range(1, 5);  // [1, 2, 3, 4, 5]
$letters = range('a', 'e');  // ['a', 'b', 'c', 'd', 'e']
```

### 2. **Array Modification Functions**

These functions help modify or manipulate arrays.

#### **`array_push()`**

Adds one or more elements to the end of an array.

```php
$fruits = array("Apple", "Banana");
array_push($fruits, "Cherry", "Date");
print_r($fruits);  // Output: ["Apple", "Banana", "Cherry", "Date"]
```

#### **`array_pop()`**

Removes the last element from an array.

```php
$fruits = array("Apple", "Banana", "Cherry");
$removed = array_pop($fruits);
echo $removed;  // Outputs: Cherry
print_r($fruits);  // Output: ["Apple", "Banana"]
```

#### **`array_shift()`**

Removes the first element from an array.

```php
$fruits = array("Apple", "Banana", "Cherry");
$removed = array_shift($fruits);
echo $removed;  // Outputs: Apple
print_r($fruits);  // Output: ["Banana", "Cherry"]
```

#### **`array_unshift()`**

Adds one or more elements to the beginning of an array.

```php
$fruits = array("Banana", "Cherry");
array_unshift($fruits, "Apple");
print_r($fruits);  // Output: ["Apple", "Banana", "Cherry"]
```

#### **`array_splice()`**

Removes a portion of an array and optionally replaces it with something else.

```php
$fruits = array("Apple", "Banana", "Cherry", "Date");
array_splice($fruits, 1, 2, array("Grape", "Orange"));
print_r($fruits);  // Output: ["Apple", "Grape", "Orange", "Date"]
```

### 3. **Array Search Functions**

PHP provides several functions for searching or checking conditions within arrays.

#### **`in_array()`**

Checks if a value exists in an array.

```php
$fruits = array("Apple", "Banana", "Cherry");
if (in_array("Banana", $fruits)) {
    echo "Banana is in the array!";
}  // Output: Banana is in the array!
```

#### **`array_search()`**

Returns the key/index of a value in an array, or `false` if the value is not found.

```php
$fruits = array("Apple", "Banana", "Cherry");
$key = array_search("Banana", $fruits);
echo $key;  // Output: 1 (index of "Banana")
```

#### **`array_key_exists()`**

Checks if a key exists in an associative array.

```php
$person = array("name" => "John", "age" => 25);
if (array_key_exists("age", $person)) {
    echo "Age is set.";
}  // Output: Age is set.
```

### 4. **Array Sorting Functions**

PHP provides multiple ways to sort arrays, whether by value or key.

#### **`sort()`**

Sorts an indexed array in ascending order (numeric or alphabetical).

```php
$numbers = array(3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5);
sort($numbers);
print_r($numbers);  // Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

#### **`rsort()`**

Sorts an indexed array in descending order.

```php
$numbers = array(3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5);
rsort($numbers);
print_r($numbers);  // Output: [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1]
```

#### **`asort()`**

Sorts an associative array by value, maintaining key-value associations.

```php
$person = array("John" => 25, "Alice" => 22, "Bob" => 30);
asort($person);
print_r($person);  // Output: ["Alice" => 22, "John" => 25, "Bob" => 30]
```

#### **`ksort()`**

Sorts an associative array by key.

```php
$person = array("John" => 25, "Alice" => 22, "Bob" => 30);
ksort($person);
print_r($person);  // Output: ["Alice" => 22, "Bob" => 30, "John" => 25]
```

#### **`array_multisort()`**

Sorts multiple arrays or a multidimensional array.

```php
$names = array("John", "Alice", "Bob");
$ages = array(25, 22, 30);

array_multisort($ages, SORT_ASC, $names);
print_r($names);  // Output: ["Alice", "John", "Bob"]
print_r($ages);   // Output: [22, 25, 30]
```

### 5. **Array Iteration Functions**

These functions allow you to iterate over arrays in various ways.

#### **`foreach()`**

The `foreach()` loop is the most common way to iterate over arrays in PHP.

```php
$fruits = array("Apple", "Banana", "Cherry");
foreach ($fruits as $fruit) {
    echo $fruit . "\n";  // Outputs: Apple, Banana, Cherry
}
```

You can also get both the key and the value using `foreach()`.

```php
$person = array("name" => "John", "age" => 25);
foreach ($person as $key => $value) {
    echo "$key: $value\n";  // Output: name: John, age: 25
}
```

#### **`array_map()`**

Applies a callback function to the elements of an array.

```php
$numbers = array(1, 2, 3, 4);
$squared = array_map(function($num) {
    return $num * $num;
}, $numbers);
print_r($squared);  // Output: [1, 4, 9, 16]
```

#### **`array_filter()`**

Filters elements of an array using a callback function.

```php
$numbers = array(1, 2, 3, 4, 5);
$evenNumbers = array_filter($numbers, function($num) {
    return $num % 2 === 0;
});
print_r($evenNumbers);  // Output: [2, 4]
```

#### **`array_reduce()`**

Iterates through an array and reduces it to a single value using a callback function.

```php
$numbers = array(1, 2, 3, 4);
$sum = array_reduce($numbers, function($carry, $item) {
    return $carry + $item;
});
echo $sum;  // Output: 10
```

### Summary of Key Array Functions

| **Function**             | **Description**                                               | **Example**                                              |
|--------------------------|---------------------------------------------------------------|----------------------------------------------------------|
| `array_push()`            | Adds one or more elements to the end of an array.             | `array_push($array, $value);`                             |
| `array_pop()`             | Removes the last element of an array.                         | `array_pop($array);`                                      |
| `array_shift()`           | Removes the first element of an array.                        | `array_shift($array);`                                    |
| `array_unshift()`         | Adds one or more elements to the beginning of an array.       | `array_unshift($array, $value);`                          |
| `array_splice()`          | Removes a portion of an array and optionally replaces it.     | `array_splice($array, 1, 2, ["new"]);`                    |
| `in_array()`              | Checks if a value exists in an array.                         | `in_array($value, $array);`                               |
| `array_search()`          | Returns the key of a value in an array.                       |

 `array_search($value, $array);`                           |
| `array_key_exists()`      | Checks if a key exists in an associative array.               | `array_key_exists($key, $array);`                         |
| `sort()`                  | Sorts an array in ascending order.                            | `sort($array);`                                           |
| `rsort()`                 | Sorts an array in descending order.                           | `rsort($array);`                                          |
| `array_map()`             | Applies a callback to each element of an array.               | `array_map($callback, $array);`                           |
| `array_filter()`          | Filters elements of an array using a callback.               | `array_filter($array, $callback);`                        |
| `array_reduce()`          | Reduces an array to a single value using a callback.          | `array_reduce($array, $callback);`                        |

PHP offers a rich set of functions for working with arrays, and understanding how to use them effectively will significantly enhance your ability to manipulate data structures in PHP.
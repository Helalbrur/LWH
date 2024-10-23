# Arrays in PHP

PHP supports several types of arrays, allowing you to store multiple values in a single variable. Below are the main types of arrays in PHP, along with examples for each.

## 1. Indexed Arrays

Indexed arrays are arrays with a numeric index. The index starts at 0.

### Example:

```php
$fruits = array("Apple", "Banana", "Cherry");
echo $fruits[0]; // Outputs: Apple
2. Associative Arrays
Associative arrays use named keys that you assign to them. This allows you to access the values using keys instead of numeric indexes.

Example:
php
Copy code
$person = array(
    "name" => "John",
    "age" => 30,
    "city" => "New York"
);
echo $person["name"]; // Outputs: John
3. Multidimensional Arrays
Multidimensional arrays are arrays that contain other arrays. They can have multiple levels of depth.

Example:
php
Copy code
$contacts = array(
    "John" => array("phone" => "123-456-7890", "email" => "john@example.com"),
    "Jane" => array("phone" => "098-765-4321", "email" => "jane@example.com")
);
echo $contacts["John"]["email"]; // Outputs: john@example.com
4. Array Functions
PHP provides a variety of built-in functions for working with arrays. Here are a few common ones:

count(): Counts all elements in an array.

php
Copy code
$numbers = array(1, 2, 3, 4);
echo count($numbers); // Outputs: 4
sort(): Sorts an array in ascending order.

php
Copy code
$fruits = array("Banana", "Apple", "Cherry");
sort($fruits);
print_r($fruits); // Outputs: Array ( [0] => Apple [1] => Banana [2] => Cherry )
array_merge(): Merges one or more arrays.

php
Copy code
$array1 = array("a" => "Apple", "b" => "Banana");
$array2 = array("c" => "Cherry", "d" => "Date");
$merged = array_merge($array1, $array2);
print_r($merged); // Outputs: Array ( [a] => Apple [b] => Banana [c] => Cherry [d] => Date )
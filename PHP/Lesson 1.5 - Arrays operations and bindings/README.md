# Types of Arrays in PHP

PHP offers several types of arrays to store multiple values in a single variable. Below are the main types of arrays, along with examples for each.

## 1. Indexed Arrays

Indexed arrays use numeric indexes, starting from 0. They can be created using the `array()` function or the shorthand `[]` syntax.

### Example:

```php
// Using array() function
$fruits = array("Apple", "Banana", "Cherry");

// Using shorthand syntax
$vegetables = ["Carrot", "Peas", "Corn"];

echo $fruits[0]; // Outputs: Apple
```
## 2. Associative Arrays
Associative arrays use named keys that you assign to them. This allows you to access values using keys instead of numeric indexes.

Example:
```php
Copy code
$person = array(
    "name" => "John",
    "age" => 30,
    "city" => "New York"
);

echo $person["name"]; // Outputs: John
```

## 3. Multidimensional Arrays
Multidimensional arrays are arrays that contain other arrays. They can have multiple levels of depth, allowing for more complex data structures.

Example:
```php
Copy code
$contacts = array(
    "John" => array(
        "phone" => "123-456-7890",
        "email" => "john@example.com"
    ),
    "Jane" => array(
        "phone" => "098-765-4321",
        "email" => "jane@example.com"
    )
);

echo $contacts["John"]["email"]; // Outputs: john@example.com
```
## 4. Array of Arrays
This is a specific type of multidimensional array where each element is an array itself, often used for tabular data.

Example:
```php
Copy code
$students = array(
    array("name" => "Alice", "age" => 20),
    array("name" => "Bob", "age" => 22),
    array("name" => "Charlie", "age" => 21)
);

echo $students[1]["name"]; // Outputs: Bob
```
# PHP Array Operations

This document provides a summary of common array operations in PHP, including examples for each operation.

```php
Function	Description
array()	Creates an array
array_change_key_case()	Changes all keys in an array to lowercase or uppercase
array_chunk()	Splits an array into chunks of arrays
array_column()	Returns the values from a single column in the input array
array_combine()	Creates an array by using the elements from one "keys" array and one "values" array
array_count_values()	Counts all the values of an array
array_diff()	Compare arrays, and returns the differences (compare values only)
array_diff_assoc()	Compare arrays, and returns the differences (compare keys and values)
array_diff_key()	Compare arrays, and returns the differences (compare keys only)
array_diff_uassoc()	Compare arrays, and returns the differences (compare keys and values, using a user-defined key comparison function)
array_diff_ukey()	Compare arrays, and returns the differences (compare keys only, using a user-defined key comparison function)
array_fill()	Fills an array with values
array_fill_keys()	Fills an array with values, specifying keys
array_filter()	Filters the values of an array using a callback function
array_flip()	Flips/Exchanges all keys with their associated values in an array
array_intersect()	Compare arrays, and returns the matches (compare values only)
array_intersect_assoc()	Compare arrays and returns the matches (compare keys and values)
array_intersect_key()	Compare arrays, and returns the matches (compare keys only)
array_intersect_uassoc()	Compare arrays, and returns the matches (compare keys and values, using a user-defined key comparison function)
array_intersect_ukey()	Compare arrays, and returns the matches (compare keys only, using a user-defined key comparison function)
array_key_exists()	Checks if the specified key exists in the array
array_keys()	Returns all the keys of an array
array_map()	Sends each value of an array to a user-made function, which returns new values
array_merge()	Merges one or more arrays into one array
array_merge_recursive()	Merges one or more arrays into one array recursively
array_multisort()	Sorts multiple or multi-dimensional arrays
array_pad()	Inserts a specified number of items, with a specified value, to an array
array_pop()	Deletes the last element of an array
array_product()	Calculates the product of the values in an array
array_push()	Inserts one or more elements to the end of an array
array_rand()	Returns one or more random keys from an array
array_reduce()	Returns an array as a string, using a user-defined function
array_replace()	Replaces the values of the first array with the values from following arrays
array_replace_recursive()	Replaces the values of the first array with the values from following arrays recursively
array_reverse()	Returns an array in the reverse order
array_search()	Searches an array for a given value and returns the key
array_shift()	Removes the first element from an array, and returns the value of the removed element
array_slice()	Returns selected parts of an array
array_splice()	Removes and replaces specified elements of an array
array_sum()	Returns the sum of the values in an array
array_udiff()	Compare arrays, and returns the differences (compare values only, using a user-defined key comparison function)
array_udiff_assoc()	Compare arrays, and returns the differences (compare keys and values, using a built-in function to compare the keys and a user-defined function to compare the values)
array_udiff_uassoc()	Compare arrays, and returns the differences (compare keys and values, using two user-defined key comparison functions)
array_uintersect()	Compare arrays, and returns the matches (compare values only, using a user-defined key comparison function)
array_uintersect_assoc()	Compare arrays, and returns the matches (compare keys and values, using a built-in function to compare the keys and a user-defined function to compare the values)
array_uintersect_uassoc()	Compare arrays, and returns the matches (compare keys and values, using two user-defined key comparison functions)
array_unique()	Removes duplicate values from an array
array_unshift()	Adds one or more elements to the beginning of an array
array_values()	Returns all the values of an array
array_walk()	Applies a user function to every member of an array
array_walk_recursive()	Applies a user function recursively to every member of an array
arsort()	Sorts an associative array in descending order, according to the value
asort()	Sorts an associative array in ascending order, according to the value
compact()	Create array containing variables and their values
count()	Returns the number of elements in an array
current()	Returns the current element in an array
each()	Deprecated from PHP 7.2. Returns the current key and value pair from an array
end()	Sets the internal pointer of an array to its last element
extract()	Imports variables into the current symbol table from an array
in_array()	Checks if a specified value exists in an array
key()	Fetches a key from an array
krsort()	Sorts an associative array in descending order, according to the key
ksort()	Sorts an associative array in ascending order, according to the key
list()	Assigns variables as if they were an array
natcasesort()	Sorts an array using a case insensitive "natural order" algorithm
natsort()	Sorts an array using a "natural order" algorithm
next()	Advance the internal array pointer of an array
pos()	Alias of current()
prev()	Rewinds the internal array pointer
range()	Creates an array containing a range of elements
reset()	Sets the internal pointer of an array to its first element
rsort()	Sorts an indexed array in descending order
shuffle()	Shuffles an array
sizeof()	Alias of count()
sort()	Sorts an indexed array in ascending order
uasort()	Sorts an array by values using a user-defined comparison function and maintains the index association
uksort()	Sorts an array by keys using a user-defined comparison function
usort()	Sorts an array by values using a user-defined comparison function
```

## 1. Creating Arrays
You can create an array using the `array()` function or the shorthand `[]`.

```php
// Using array() function
$fruits = array("Apple", "Banana", "Cherry");

// Using shorthand
$vegetables = ["Carrot", "Peas", "Corn"];
```

## 2. Accessing Array Elements
Access elements using their index.

```php
echo $fruits[0]; // Outputs: Apple
```

## 3. Adding Elements
Add elements to an array using [] or array_push().
```php
$fruits[] = "Date"; // Adds "Date"
array_push($vegetables, "Broccoli"); // Adds "Broccoli"
```

## 4. Removing Elements
Remove elements using unset() or array_pop().

```php
unset($fruits[1]); // Removes "Banana"
$lastVeg = array_pop($vegetables); // Removes and returns "Corn"
```

## 5. Looping Through Arrays
Use foreach to loop through an array.

```php
foreach ($fruits as $fruit) {
    echo $fruit . "\n"; // Outputs each fruit
}
```

## 6. Counting Elements
Use count() to get the number of elements in an array.
```php
echo count($fruits); // Outputs: 3 (after removing "Banana")
```

## 7. Sorting Arrays
Sort arrays using sort(), asort(), ksort(), etc.
```php
PHP - Sort Functions For Arrays
In this chapter, we will go through the following PHP array sort functions:

sort() - sort arrays in ascending order
rsort() - sort arrays in descending order
asort() - sort associative arrays in ascending order, according to the value
ksort() - sort associative arrays in ascending order, according to the key
arsort() - sort associative arrays in descending order, according to the value
krsort() - sort associative arrays in descending order, according to the key


$people = [
    "Alice" => 25,
    "Bob" => 30,
    "Charlie" => 20,
];

// Comparison function
function compareAges($a, $b) {
    return $a <=> $b; // Using spaceship operator
}

// Sort the array
uasort($people, 'compareAges');

// Print the sorted array
print_r($people);

$trans_data[1]['qnty'] 		= 50;
$trans_data[1]['name'] 	    = 'pen';

$trans_data[2]['qnty'] 		= 100;
$trans_data[2]['name'] 	    = 'book';

$trans_data[3]['qnty'] 		= 200;
$trans_data[3]['name'] 	    = 'mobile';
echo "<pre>";
print_r($trans_data);
echo "</pre>";
function lwh($a,$b)
{
   return $b['qnty'] <=> $a['qnty'];
}
uasort($trans_data,'lwh');
echo "<pre>";
print_r($trans_data);
echo "</pre>";

```


## 8. Merging Arrays
Merge two or more arrays using array_merge().

```php 
$combined = array_merge($fruits, $vegetables);
```
## 9. Splitting Arrays
Split an array using array_slice().
```php 
array_slice(array, start, length, preserve)

```

## 10. Searching Arrays
Check if a value exists in an array using in_array().

```php
Copy code
if (in_array("Cherry", $fruits)) {
    echo "Cherry is in the array!";
}
```

## 11. Filtering Arrays
Filter elements based on a callback function using array_filter().

```php
Copy code
$numbers = [1, 2, 3, 4, 5];
$evenNumbers = array_filter($numbers, function($num) {
    return $num % 2 == 0;
}); // Outputs: [2, 4]
```

## 12. Transforming Arrays
Apply a function to each element using array_map().

```php
Copy code
$squared = array_map(function($num) {
    return $num * $num;
}, $numbers); // Outputs: [1, 4, 9, 16, 25]

```
## 13. Reducing Arrays
Reduce an array to a single value using array_reduce().

```php
Copy code
$sum = array_reduce($numbers, function($carry, $num) {
    return $carry + $num;
}, 0); // Outputs: 15

```
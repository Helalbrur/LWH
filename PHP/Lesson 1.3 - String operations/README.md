1. Concatenation (.)

Combines two or more strings.

php

$firstName = "John";
$lastName = "Doe";
$fullName = $firstName . " " . $lastName;
echo $fullName; // Output: John Doe

2. String Length (strlen)

Returns the length of a string.

php

$string = "Hello, World!";
echo strlen($string); // Output: 13

3. String to Lowercase (strtolower)

Converts a string to lowercase.

php

$string = "HELLO";
echo strtolower($string); // Output: hello

4. String to Uppercase (strtoupper)

Converts a string to uppercase.

php

$string = "hello";
echo strtoupper($string); // Output: HELLO

5. Substring (substr)

substr(string,start,length) 
Extracts a part of a string.

php

$string = "Hello, World!";
echo substr($string, 7, 5); // Output: World

6. Replace Substring (str_replace)

Replaces all occurrences of a substring with another substring.

php

$string = "Hello, World!";
echo str_replace("World", "PHP", $string); // Output: Hello, PHP!

7. Find Position of Substring (strpos)

Finds the position of the first occurrence of a substring.

php

$string = "Hello, World!";
echo strpos($string, "World"); // Output: 7

8. Trim Whitespace (trim)

Removes whitespace (or other characters) from the beginning and end of a string.

php

$string = "  Hello, World!  ";
echo trim($string); // Output: Hello, World!

9. Explode a String into an Array (explode)

Splits a string by a delimiter and returns an array.

php

$string = "apple,banana,orange";
$array = explode(",", $string);
print_r($array);
// Output: Array ( [0] => apple [1] => banana [2] => orange )

10. Implode an Array into a String (implode)

Joins array elements into a string with a delimiter.

php

$array = ["apple", "banana", "orange"];
echo implode(", ", $array); // Output: apple, banana, orange

11. String Repeat (str_repeat)

Repeats a string a specified number of times.

php

$string = "Hello";
echo str_repeat($string, 3); // Output: HelloHelloHello

12. String Comparison (strcmp)

Compares two strings. Returns 0 if the strings are equal.

php

$string1 = "apple";
$string2 = "apple";
echo strcmp($string1, $string2); // Output: 0 (because they are equal)

13. String Contains (str_contains) (PHP 8.0+)

Checks if a string contains a specific substring.

php

$string = "Hello, World!";
if (str_contains($string, "World")) {
    echo "Found!";
} // Output: Found!

14. String Reverse (strrev)

Reverses a string.

php

$string = "Hello";
echo strrev($string); // Output: olleH
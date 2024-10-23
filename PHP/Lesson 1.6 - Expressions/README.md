# Lesson 1.6 - Expressions in PHP
In PHP, an expression is a combination of variables, constants, operators, and functions that evaluates to a value. Expressions can be as simple as a single value or variable, or they can be more complex, involving multiple operations.

## Types of Expressions:
### Arithmetic Expressions: Perform mathematical operations.

Example:
```php
Copy code
$a = 5;
$b = 10;


```
## String Expressions: Combine strings.
Example:
```php
Copy code
$firstName = "John";
$lastName = "Doe";
$fullName = $firstName . " " . $lastName; // $fullName evaluates to "John Doe"
```
## Logical Expressions: Evaluate to true or false.
Example:
```php
Copy code
$isAdult = true;
$isStudent = false;
$canVote = $isAdult && !$isStudent; // $canVote evaluates to true

```

## Comparison Expressions: Compare values.

Example:
```php
Copy code
$x = 10;
$y = 20;
$isEqual = ($x == $y); // $isEqual evaluates to false
Function Expressions: Call functions that return values.

Example:
php
Copy code
function square($num) {
    return $num * $num;
}
$result = square(4); // $result evaluates to 16


```
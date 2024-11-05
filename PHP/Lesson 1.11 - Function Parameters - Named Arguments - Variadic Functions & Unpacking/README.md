# Function Parameters - Named Arguments - Variadic Functions & Unpacking

## 1. Named Arguments (PHP 8.0+)
Named arguments allow you to pass arguments to a function by explicitly specifying the parameter names, rather than just passing them in the order defined by the function signature. This feature can improve code readability, especially when you have many optional parameters.
```php
Copy code
function createProfile($name, $age, $email = null, $isActive = true) {
    echo "Name: $name\n";
    echo "Age: $age\n";
    echo "Email: $email\n";
    echo "Active: " . ($isActive ? "Yes" : "No") . "\n";
}

// Using named arguments
createProfile(age: 30, isActive: false,name: 'John Doe');
 
```

## 2. Variadic Functions (PHP 5.6+)
A variadic function allows you to pass an arbitrary number of arguments to the function. The parameter in the function declaration that accepts these arguments is prefixed with .... Inside the function, the variadic parameter is treated as an array.

```php
Copy code
function sumNumbers(...$numbers) {
    $sum =0;
    foreach ($numbers as $number) {
        $sum+= $number;
    }
    return $sum;
}

// Passing a variable number of arguments
echo sumNumbers(1, 2, 3, 4);  // Outputs: 10
echo sumNumbers(5, 10);       // Outputs: 15

 
```

## 3. Unpacking in PHP (PHP 7.4+)
Unpacking allows you to pass an array or an object (that implements Traversable) as individual arguments to a function. This is done using the ... syntax when calling the function.

```php
Copy code
function greet($greeting, $name) {
    echo "$greeting, $name!\n";
}

$args = ['Hello', 'Alice'];
greet(...$args);  // Outputs: Hello, Alice!


function printNumbers(...$numbers) {
    foreach ($numbers as $number) {
        echo $number . " ";
    }
    echo "\n";
}

$numbersArray = [1, 2, 3, 4, 5];
printNumbers(...$numbersArray);  // Outputs: 1 2 3 4 5

```

## Combining Variadic Functions, Named Arguments, and Unpacking
You can combine all these features in a single function for more flexibility. Here's an example that combines variadic arguments, named arguments, and unpacking:

```php
Copy code
function displayDetails($title, string $name, ...$traits) {
    echo "$title: $name\n";
    echo "Traits: " . implode(", ", $traits) . "\n";
}

$personDetails = ['John', 'Brave', 'Smart', 'Loyal'];

// Using named argument for the title and unpacking the array for traits
displayDetails(title: 'Person', name: $personDetails[0], ...array_slice($personDetails, 1));
```
# Functions & Type Hinting in PHP

## Type hinting in PHP
Type hinting is a concept that provides hints to function for the expected data type of arguments.
```php
Copy code
function add(array $numbers){ 
      $sum=0; 
      foreach($numbers as $item){ 
          $sum=$sum+$item; 
      } 
      echo $sum; 
  } 
  
  add(array(10,10)); 
```
Advantages of type hinting:

    Type hinting helps users debug the code easily or the code provides errors very specifically.
    It is a great concept for static kind of programming/data.

Disadvantages of type hinting:

    Functions only take one type of data.
    The dynamicity of data or argument is not there.


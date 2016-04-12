# PHP

## Variables
#### Naming Variables
| Name & Example | Type   |
|----------------|--------|
| `$name = "Jim";` | string |
| `$number = 23;`  | number |
| `$Float = 55.67;` | float  |
| `$_included = true;` | boolean  |
| `$stuff_array = ["string", 44, false];` | array  |
| `$nothing2 = null;` | null  |

**Naming:** Variables can only contain numbers, letters, and underscores, although they must begin with a letter or underscore. They are case sensitive.

**Types:** Variables can store the data types string, number, float, boolean, array, and null.
<br /><br />
#### Modifying Variables
Set the value of the variable to its current value plus 5
```php
$number += 5
```

Increment the variable value by 1
```php
$number++;
```

Decrement the variable value by 1
```php
$number--;
```
<br /><br />
#### Casting Variables
The process of casting is forcing a variable to be another datatype.
```php
$number_string = "3";

// Cast to integer
$number_int = (int) $number_string; // int(3)

// Cast to float
$number_float = (float) $number_string // float(3)

// Cast to string
$number_string = (string) $number_int; // string(1) "3"

// Cast to array
$number_string_array = (array) $number_string; // array(1) { [0] => string(1) "3" }
```

<br>
#### Useful internal constants
| Constant Name | Purpose   | Demo |
|----------------|--------|-------|
| [`PHP_EOL`](http://phppot.com/php/php-line-breaks/) | Outputs end of line character that is compatible with any system | `echo "End of Line" . PHP_EOL; // Displays: "End of Line" followed by a new-line character` |

<br><br>
## Arrays
#### Creating Arrays
##### Declaring an array (two ways)
```php
$car_makes = array("Ford", "VW", "Saab");
$car_models = ["Focus", "Jetta", "Miata"];
```

##### Indexed array
```php
$car_models = ["Focus", "Jetta", "Miata"];

$car_models[1] // returns "Jetta"
```

##### Associate array
```php
$car_models = [
  "model" => "Volkswagen", 
  "make" => "Passat", 
  "year" => 2013
];

$car_models["make"] // returns "Passat"
```

##### Multidimensional array
```php
$car_parts = [
  "wheels" => ["hubcap", "rim", "tire", "lugnut"];
];

$car_parts["wheels"][3] // returns "lugnut"
```

<br><br>
## Conditional Logic
#### If statement - http://www.phptherightway.com/pages/The-Basics.html#if-statements
```php
if ($num_pizzas === 1) {
  echo "Give me more!";
} elseif ($num_pizzas === 3) {
  echo "I'm stuffed";
} else {
  echo "What does it matter? I'm unhealthy anyways.";
}

// If statements can also be written without curly braces if the statement within the condition is only one line
if ($num_pizzas === 1)
  echo "Give me more!";
elseif ($num_pizzas === 3)
  echo "I'm stuffed";
else
  echo "What does it matter? I'm unhealthy anyways.";
```
<br>
#### Switch statement - http://www.phptherightway.com/pages/The-Basics.html#switch-statements
Switch statements can only check for equality, so if a more advanced condition needs to be evaluated, then an if statement is preferred.
```php
switch ($num_pizzas) {
  case 1:
    echo "Give me more!";
    break;
  case 3:
    echo "I'm stuffed";
    break;
  default:
    echo "What does it matter? I'm unhealthy anyways.";
}
```

<br>
#### Ternary Operator - http://www.phptherightway.com/pages/The-Basics.html#ternary-operators
Ternary operators can be used to reduce code but can get confusing if too complex. Use sparingly.
```php
echo ($num_pizzas === 1 ? "Give me more!") 
: ($num_pizzas === 3 ? "I'm stuffed")
: "What does it matter? I'm unhealthy anyways.";
}
```
A better implementation is for short if/then statements that are easy to read.
```php
echo ($num_pizzas === 0) ? "Rage growing!" : "Mmm, love me some pie's";
```

## Functions
A function is a collection of statements that execute together.
```php
function welcome($name, $location) {
  // Return a value (in this case a string) from the function
  return "Welcome to {$location}, {$name}!";
}

echo welcome("David", "Downtown"); // Displays: Welcome to Downtown, David!

// If there are multiple values you want to pass into a function and they don't need to be accessed in any specific order, you can use the func_get_args() function which will return an array of all the values that have been passed as parameters to the function. You could, ofcourse, also just pass them as an array in the first place, but this is another way.
function add_numbers() {
  $numbers = func_get_args();

  $total = 0;
  foreach ($numbers as $number) {
    $total += $number;
  }
  
  return $total;
}

echo add_numbers(1, 5, 10, 20); // Displays: 36

```

#### [Anonymous Functions (a.k.a. Lambda functions)](http://culttt.com/2013/03/25/what-are-php-lambdas-and-closures/)
Anyonymous functions provide a way to use a function (often as a parameter for another function) that will only be used once and serves no other purpose as a function to be called elsewhere.
```php
// A function that runs a callback function
function speech ($message){
  echo "Let me clear my throat...Ok, I'm ready" . PHP_EOL;
  
  // Run callback
  echo $message();
}

// Call function using pre-defined function
function jfk() {
  return "Ich bin ein Berliner!";
};
speech("jfk");
// Returns
// -> Let me clear my throat...Ok, I'm ready
// -> Ich bin ein Berliner!
 
// Call function using anonymous function
speech(function(){
  return "Ich bin ein Berliner!";
});
// Returns
// -> Let me clear my throat...Ok, I'm ready
// -> Ich bin ein Berliner!
```

<br>
#### Useful internal functions
| Function Name | Action   | Demo |
|----------------|--------|-------|
| [`gettype()`](http://www.w3resource.com/php/function-reference/gettype.php) | Returns the data type of the provided argument | `echo gettype(102) // Returns: "integer"` |


## Loops
That are several control statements that can be used within loops:
<br>**break** - break out of the loop entirely
<br>**continue** - break out of the loop iteration and continue with the next iteration

#### While loop
A loop that will continue to run while a condition evaluates to true
```php
$mph = 45;

while ($mph < 65) {
  echo "Get off the highway slow-poke! \n";
  $mph++;
}
```

A while loop is often used to loop through the results set returned from a database
```php
// Provide example here
```

<br>
#### Do While loop
A do while loop will will _always_ execute the code block at least once, before it checks the condition to determine if it should execute any longer.
```php
$hunger_level = 100;
$chips = 5;

do {
  echo "Still hungry! Need chips now! \n";
  $hunger_level += $chips;
} while ($hunger_level > 30);
```

<br>
#### For loop
A for loop loops through a block of code a specified number of times. You specify the initial counter variable, the condition, and the incrementer all within the arguments.
<br><br>The first section, the counter, is executed **before** the loop is executed.
<br>The second statement, the condition, is evaluated **every time** the loop is executed.
<br>The third statement is executed **after** the loop is executed.
```php
for ($i = 0; $i <= 24; $i++) {
  echo "Hours finished for this day: {$i} \n";
}
```

<br>
#### Foreach loop
A foreach loop is used to loop through the items in an array. The number of iterations of the loop are, therefore, determined by the number of items in the array.
```php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

foreach ($numbers as $number) {
  // If the number in the loop is odd, then break the iteration and continue with the next iteration
  if ($number % 2 !== 0) {
    continue;
  }
  
  // If the number is equal to 8, break out of the loop completely
  if ($number === 8) {
    break;
  }
  
  echo "The number {$number} made the cut! Phew!" . PHP_EOL;
}

// Foreach loops can also access key => value pairs
$employee_ages = [
  "John" => 14,
  "Nelson" => 25,
  "Eric" => 51,
];

// It is common to use $key and $value as the variables representing the key and value for the current iteration, but $name and $age is better this case as it provides context within the loop iteration
foreach ($employee_ages as $name => $age) {
  echo "{$name} is {$age} years old" . PHP_EOL;
}
```

## [Type Hinting (a.k.a. type declarations)](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration)
A way to specify the data type accepted for the parameter of a function or method. If the correct data type is not provided when the function gets called, PHP will display an error.
```php
// Provide example here (From functions chapter and later on)
// Show examples of type hinting for array, Closure, 
// Say hello to an array of people.
function sayHello(array $names) {
  foreach ($names as $name) {
    echo "Hello, {$name}!\n";
  }
}

sayHello(['Katie', 'Corissa', 'Lucy']); // Runs the function as expected
sayHello('Jeffrey'); // Displays error: Uncaught TypeError: Argument 1 passed to sayHello() must be of the type array, string given
```

## Partials
There are several ways to include the code from another file within the current file, thereby eliminating the need to repeat code on several pages for repetitive functionality or markup.

#### Include
Include a file's contents on the current page. If it can't be found, it will continue to load the rest of the page without emitting an error.
```php
  include 'includes/vendor/classes.php';
```

#### Require
Include a file's contents on the current page. If it can't be found, it will throw a fatal error.
```php
  require 'includes/vendor/classes.php';
  
  // Use require_once if there's a possiblity it may be required multiple times
  require_once 'includes/vendor/classes.php';
```

<br>
## Classes
A class is a collection of variables (called properties) and functions (called methods) that have a common organizational purpose. They are contained within an *object*, which can be accessed by creating an *instance* of (or instantiating) the class.
```php
// Define the Book class.
class Book
{
  // Declare properties.
  public $title;
  public $author;
  public $publisher;
  public $yearOfPublication;
  public $format = "paperback";
  
  // Declare a method.
  function go_to_page(int $page_num)
  {
    return "Viewing page {$page_num}";
  }
  
  // Access values of the current instance from inside a class method by using the $this property
  function summary()
  {
    echo 'Title: '      . $this->title        . PHP_EOL;
    echo 'Author: '     . $this->author       . PHP_EOL;
    echo 'Publisher: '  . $this->publisher    . PHP_EOL;
  }
}

// Create a new book instance.
$book = new Book;

// Set properties for this object.
$book->title                = 'Game of Thrones';
$book->author               = 'George R R Martin';
$book->publisher            = 'Voyager Books';
$book->yearOfPublication    = 1996;

// Echo out the property
echo $book->title . PHP_EOL;
// Displays
// -> Game of Thrones

// Execute the go_to_page() method.
echo $book->go_to_page(44) . PHP_EOL;
// Displays
// -> Viewing page 44

// Execute the summary() method.
$book->summary();
// Displays
// -> Title: Game of Thrones
// -> Author: George R R Martin
// -> Publisher: Voyager Books
```

<br><br>
## Glossary
| Term        | Definition           |
| ------------- |-------------|
| String Interpolation      | Embedding variable value in a string. It is best practice to wrap the variable in curly braces. <br>Example: `echo "My name is {$name};"` |
| Concatenation      | Joining two strings end to end. <br>Example: `"Jim" + "Bob" // "JimBob"`      |
| Casting | The process of transforming a variable from one data type to another      |

<br><br>
## Links
#### Test Environments
http://sandbox.onlinephpfunctions.com/

#### Reference
PHP Pandas: http://daylerees.com/php-pandas/<br>
PHP: The Right Way: http://www.phptherightway.com/

#### Syntax Documentation
OnlinePHPFunctions: http://onlinephpfunctions.com/<br>
W3Resource: http://www.w3resource.com/php/function-reference/function-reference.php

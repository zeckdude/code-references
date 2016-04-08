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
// Provide example here using parameters, return, func_get_args()
```


## Loops
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
// Provide example here using return, break, and continue
```

## Type Hinting
A way to specify the data type accepted for the parameter of a function or method. If the correct data type is not provided when the function gets called, PHP will display an error.
```php
// Provide example here (From functions chapter and later on)
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

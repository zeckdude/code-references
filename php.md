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
## Glossary
| Term        | Definition           |
| ------------- |:-------------:|
| String Interpolation      | Embedding variable value in a string. It is best practice to wrap the variable in curly braces. <br>Example: `echo "My name is {$name};"` |
| Concatenation      | Joining two strings end to end. <br>Example: `"Jim" + "Bob" // "JimBob"`      |
| Casting | the process of transforming a variable from one data type to another      |
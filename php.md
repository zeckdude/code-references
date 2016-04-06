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
<br><br>
## Arrays
#### Creating Arrays
Declaring an array (two ways)
```php
$car_makes = array("Ford", "VW", "Saab");
$car_models = ["Focus", "Jetta", "Miata"];
```

Indexed array
```php
$car_models = ["Focus", "Jetta", "Miata"];
$car_models[1] // returns "Jetta"
```

Associate array
```php
$car_models = [
  "model" => "Volkswagen", 
  "make" => "Passat", 
  "year" => 2013
];

$car_models["make"] // returns "Passat"
```

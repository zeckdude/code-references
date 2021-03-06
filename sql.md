### MySQL

**Test MySQL:** http://sqlfiddle.com/<br>
**Learn and find documentation:** http://sqlbolt.com/<br>

<br>

#### Table of Contents
1. [Return all rows where the specified column value is between two numbers](#return-all-rows-where-the-specified-column-value-is-between-two-numbers)
2. [Return all rows where the specified column value is not between two numbers](#return-all-rows-where-the-specified-column-value-is-not-between-two-numbers)
3. [Return all rows where the specified column value is equal to one of several possible values](#return-all-rows-where-the-specified-column-value-is-equal-to-one-of-several-possible-values)
4. [Return all rows where the specified column value is not equal to one of several possible values](#return-all-rows-where-the-specified-column-value-is-not-equal-to-one-of-several-possible-values)
5. [Return all rows where the specified column value is equal to a specific value (case-sensitive)](#return-all-rows-where-the-specified-column-value-is-equal-to-a-specific-value-case-sensitive)
6. [Return all rows where the specified column value is not equal to a specific value (case-sensitive)](#return-all-rows-where-the-specified-column-value-is-not-equal-to-a-specific-value-case-sensitive)
7. [Return all rows where the specified column value is equal to a specific value (case-insensitive)](#return-all-rows-where-the-specified-column-value-is-equal-to-a-specific-value-case-insensitive)
8. [Return all rows where the specified column value is not equal to a specific value (case-insensitive)](#return-all-rows-where-the-specified-column-value-is-not-equal-to-a-specific-value-case-insensitive)
9. [Return all rows where the specified column value begins with a specific value (case-insensitive)](#return-all-rows-where-the-specified-column-value-begins-with-a-specific-value-case-insensitive)
10. [Return all rows where the specified column value ends with a specific value (case-insensitive)](#return-all-rows-where-the-specified-column-value-ends-with-a-specific-value-case-insensitive)
11. [Return all rows where the specified column value matches a specified pattern (case-sensitive)](#return-all-rows-where-the-specified-column-value-matches-a-specified-pattern-case-sensitive)
12. [Return all rows where the specified column value contains a specific value (case-insensitive)](#return-all-rows-where-the-specified-column-value-contains-a-specific-value-case-insensitive)

<br>

#### Return all rows where the specified column value is between two numbers
> Using BETWEEN condition - http://www.techonthenet.com/mysql/between.php
```sql
SELECT *
FROM tbl_name
WHERE col_name BETWEEN 3 AND 6;
```

> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name >= 3 AND col_name <= 6;
```

<br>

#### Return all rows where the specified column value is not between two numbers
> Using NOT BETWEEN condition - http://www.techonthenet.com/mysql/between.php
```sql
SELECT *
FROM tbl_name
WHERE col_name NOT BETWEEN 3 AND 6;
```

> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name < 3 AND col_name > 6;
```

<br>

#### Return all rows where the specified column value is equal to one of several possible values
> Using IN condition - http://www.techonthenet.com/mysql/in.php
```sql
SELECT *
FROM tbl_name
WHERE col_name IN (2, 4, 6);
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name IN ("active", "waiting_approval", "in_progress");
```

> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name = 2
OR col_name = 4
OR col_name = 6; 
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name = "active"
OR col_name = "waiting_approval"
OR col_name = "in_progress"; 
```

<br>

#### Return all rows where the specified column value is not equal to one of several possible values
> Using NOT IN condition - http://www.techonthenet.com/mysql/in.php
```sql
SELECT *
FROM tbl_name
WHERE col_name NOT IN (1, 3, 5);
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name NOT IN ("active", "waiting_approval", "in_progress");
```

> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name != 1
AND col_name != 3
AND col_name != 5 
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name != "active"
AND col_name != "waiting_approval"
AND col_name != "in_progress" 
```

<br>

#### Return all rows where the specified column value is equal to a specific value (case-sensitive)
> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name = 5;
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name = "active";
```

<br>

#### Return all rows where the specified column value is not equal to a specific value (case-sensitive)
> Using Comparison Operators - http://www.techonthenet.com/mysql/comparison_operators.php
```sql
SELECT *
FROM tbl_name
WHERE col_name != 5;
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name <> 5;
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name != "active";
```

> ```sql
SELECT *
FROM tbl_name
WHERE col_name <> "active";
```

<br>

#### Return all rows where the specified column value is equal to a specific value (case-insensitive)
> Using LIKE condition - http://sqlbolt.com/lesson/select_queries_with_constraints_pt_2
```sql
# Examples of accepted values for col_name: Active, active, AcTiVe, etc.
SELECT *
FROM tbl_name
WHERE col_name LIKE "active";
```

<br>

#### Return all rows where the specified column value is not equal to a specific value (case-insensitive)
> Using LIKE condition - http://sqlbolt.com/lesson/select_queries_with_constraints_pt_2
```sql
# Examples of accepted values for col_name: "approved", "Waiting_Approval", "DiSabLeD", etc.
# Not accepted values for col_name: "Active", "active"
SELECT *
FROM tbl_name
WHERE col_name NOT LIKE "Active";
```

<br>

#### Return all rows where the specified column value begins with a specific value (case-insensitive)
> Using LIKE condition - http://www.mysqltutorial.org/mysql-like/<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-like/#1
```sql
# Examples of accepted values for col_name: "active", "Action", "Act One", etc.
SELECT *
FROM tbl_name
WHERE col_name LIKE "act%";
```

> Using REGEXP condition - http://www.mysqltutorial.org/mysql-regular-expression-regexp.aspx<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-regular-expression/#2
```sql
# Examples of accepted values for col_name: "active", "Action", "Act One", etc.
SELECT *
FROM tbl_name
WHERE col_name REGEXP "^act";
```

<br>

#### Return all rows where the specified column value ends with a specific value (case-insensitive)
> Using LIKE condition - http://www.mysqltutorial.org/mysql-like/<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-like/#2
```sql
# Examples of accepted values for col_name: "Right On", "won", "action", etc.
SELECT *
FROM tbl_name
WHERE col_name LIKE "%on";
```

> Using REGEXP condition - http://www.mysqltutorial.org/mysql-regular-expression-regexp.aspx<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-regular-expression/#4
```sql
# Examples of accepted values for col_name: "Right On", "won", "action", etc.
SELECT *
FROM tbl_name
WHERE col_name REGEXP "on$";
```

<br>

#### Return all rows where the specified column value matches a specified pattern (case-sensitive)
> Using REGEXP condition - http://www.mysqltutorial.org/mysql-regular-expression-regexp.aspx<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-regular-expression/#3<br>
> Notes: The BINARY keyword forces the case-sensitive match. This example is looking for any values that begin with "act", but any regular expression pattern is valid.
```sql
# Examples of accepted values for col_name: "active", "action", "act One", etc.
SELECT *
FROM tbl_name
WHERE col_name REGEXP BINARY "^act";
```

<br>

#### Return all rows where the specified column value contains a specific value (case-insensitive)
> Using LIKE condition - http://www.mysqltutorial.org/mysql-like/<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-like/#3
```sql
# Examples of accepted values for col_name: "Patterson", "Jones", "Only", etc.
SELECT *
FROM tbl_name
WHERE col_name LIKE "%on%";
```

> Using REGEXP condition - http://www.mysqltutorial.org/mysql-regular-expression-regexp.aspx<br>
> Demo: http://www.mysqltutorial.org/tryit/query/mysql-regular-expression/#5
```sql
# Examples of accepted values for col_name: "Patterson", "Jones", "Only", etc.
SELECT *
FROM tbl_name
WHERE col_name REGEXP "on";
```

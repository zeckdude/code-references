### MySQL

**Test MySQL:** http://sqlfiddle.com/<br>
**Learn and find documentation:** http://sqlbolt.com/<br>

<br>

*Return all rows where the specified column value is between two numbers*

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

*Return all rows where the specified column value is not between two numbers*
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

*Return all rows where the specified column value is equal to one of several possible values*
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

*Return all rows where the specified column value is not equal to one of several possible values*
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

*Return all rows where the specified column value is equal to a specific value (case-sensitive)*
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

*Return all rows where the specified column value is not equal to a specific value (case-sensitive)*
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

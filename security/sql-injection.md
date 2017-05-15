## SQL Injection

SQL Injection is a strategy that hackers use to take control of the database through form fields, links, URL parameters, or any other means that query the database.

Hackers will write a closing quote followed by their own SQL command into either a form field or at the end of a URL which has a URL parameter, for example. Then they have full control over the database.

![SQL Injection URL](img/security/sql-injection-url-1.png)
![SQL Injection URL](img/security/sql-injection-url-2.png)
![SQL Injection URL](img/security/sql-injection-url-3.png)

<br>

![SQL Injection Summary](img/security/sql-injection-summary.png)

Ways to defend against a SQL Injection:
  * Disable error messages on production environment
  * Use prepared statements / parameterized queries at all times when dealing with user-entered input
  * Don't dynamically build any SQL strings

## Forcible Browsing

Forcible Browsing is a strategy where hackers will guess certain pages on your site which they shouldn't have access to. Without proper user permissions, simply knowing (or guessing correctly) the URL will allow a hacker access to the restricted pages and/or content.

![Forcible Browsing vulnerability](https://github.com/zeckdude/code-references/blob/master/img/security/forcible-browsing-1.png)
<br>*Example of pages a given user should have access to and should not have access to*

Conditions that need to be met in order for this exploit to work:
  * A hacker must guess certain pages to visit on your site
  * Restricted pages are not employing user permissions to determine if a user should have access to a given page
  
Ways to defend against this exploit:
  * Use page level authorization to determine if a user has access to that page
    * For example, a basic logged in user could have a session variable that identifies them as a basic user. Page level authorization could check for the presence of such a session variable and if it exists, allow them to see the page.
    * Page level authorization is good as a first step, but if more detailed actions can be taken that need to check for further conditions past just the user type, then page level authorization on its own is not adequate enough.
  * Use programmed authorization (logic in code) to check if a given user meets the necessary criteria to perform a specified action. This would usually involve a query to the database to verify roles and permissions or other information.
    

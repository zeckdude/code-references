## Parameter Manipulation

Parameter manipulation is a strategy to change the values of URL parameters to see if it will show other data that the hacker is not authorized to see. This strategy can also be applied to POST variables sent in a form via traffic interception tools.

![Parameter Manipulation Vulnerability](https://github.com/zeckdude/code-references/blob/master/img/security/parameter-manipulation-vulnerability.png)

Ways to defend against parameter manipulation:
  * Server-side validation
    * Verify for things such as:
      * Value Type (ex: Number)
      * Other business logic, such as checking if a number is positive number or if a string matches a specified number of options
      ![Parameter Manipulation Defense 1](https://github.com/zeckdude/code-references/blob/master/img/security/parameter-manipulation-defense-1.png)
      * Authenticating that the logged-in user is authorized to see a record with a specified id
  * If possible, use session variables instead of URL parameters
  
![Parameter Manipulation Defense 1](https://github.com/zeckdude/code-references/blob/master/img/security/parameter-manipulation-defense-2.png)
![Parameter Manipulation Defense 2](https://github.com/zeckdude/code-references/blob/master/img/security/parameter-manipulation-defense-3.png)
  
  




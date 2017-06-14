## Unchecked Redirects

Unchecked redirects is a strategy where hackers will find a URL on your site that has a redirect URL parameter which is used to redirect the user to another page/site without properly validating it first. The hacker can create a fake email to send to people using a link to the legitimate URL on your site, but include the redirect parameter that is actually redirecting the user to a site of their choosing.

Conditions that need to be met in order for this exploit to work:
  * A URL needs to be using a redirect URL GET parameter on your site 
  * The parameter is not being validated before redirecting the user to another location
  
Ways to defend against this exploit:
  * Don't use a redirect URL GET parameter within a URL if possible. Use logic in the code instead to send the user to a specified location.
  * If using a redirect URL GET parameter is absolutely necessary, follow these steps:
    * Make sure the current user has the proper permission to be redirected
    * Compare the redirect URL GET parameter string value against a white list of approved sites and only redirect if it matches.
    * ![Unchecked Redirects white list](https://github.com/zeckdude/code-references/blob/master/img/security/unchecked-redirects-1.png)
    

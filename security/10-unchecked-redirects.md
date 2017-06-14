## Unchecked Redirects

Unchecked redirects is a strategy where hackers will find a URL on your site that has a redirect URL parameter which is used to redirect the user to another page/site without properly validating it first. The hacker can create a fake email to send to people using a link to the legitimate URL on your site, but include the redirect parameter that is actually redirecting the user to a site of their choosing.

Conditions that need to be met in order for this exploit to work:
  * A URL needs to be using a redirect URL GET parameter on your site 
  * The parameter is not being validated before redirecting the user to another location
  
Ways to defend against this exploit:
  * 
    

## Cross-site request forgery

Cross-site request forgery is a strategy where hackers send a link to users that looks like it is coming from a site they frequently visit (such as a bank or shopping site). When a user is logged into the real site it creates a valid session. Then if the user clicks on the link to the fake site in the email created by the hackers, the fake site performs malicious actions (such as transfer money if it is dealing with a bank login or buy items on a shopping site).

![Cross-site request forgery vulnerability](https://github.com/zeckdude/code-references/blob/master/img/security/xss-request-forgery-1.png)
<br>*Example of email with a link to the malicious site which contains the cross-site request forgery actions*

![Cross-site request forgery vulnerability](https://github.com/zeckdude/code-references/blob/master/img/security/xss-request-forgery-2.png)
<br>*Example of image tags that are automatically loaded when the malicious site loads. They will run actions on other sites in hopes that the user is currently authenticated on the site they are targeting.*

Conditions that need to be met in order for this exploit to work:
  * User needs to be authenticated on a site
  * Hacker must be able to take an action all through a URL (using GET variables), such as `http://bank.com/transfer.asp?from=32938&to=39394&amt=2500`
  
Ways to defend against cross-site request forgery:
  * Shorten session timeouts so that if a user goes away from a page for a specified amount of time, the authenticated session is destroyed.
  * Prompt the user to re-authenticate again. This will lessen usability somewhat, but in cases where the action being performed is particularly sensitive it is a good way to defend.
  * Generate a unique token when a form is being processed. When the form is sent back to the server, the token needs to be verified. Since the token is random and only generated at the time the form is submitted, a hacker would not be able to know what the token is.


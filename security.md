## Security

### Links
| Name          | Link                                                            |
|---------------|-----------------------------------------------------------------|
| Security Compass - XSS Attacks | http://www.securitycompass.com/training/free/course-demos/modules/XSS/player.html |

### XSS Attacks

XSS attacks are strategies that hackers use to insert their own javascript code onto the users machine via two ways:

* Reflected XSS
  * When a user enters html, with javascript, into a form field that will eventually re-display the entered information on the page 
    * Example case: A search field where the next page re-displays the search term entered
    * Example search value entered: `This is my search string <script>alert('Hello');</script>`
    * Commonly used when added to a link that is sent for others to click on. The link will be to your site so people will usually trust it. Once people click on it, it will take them to your site and will use the entered information to re-display on the page while executing the malicious code.
      * Requires the search terms to use a GET variable to access the information to re-display
      * Hackers will usually encode the html so it is not obvious as being malicious.
        * ![Encoded malicious code](/images/malicious_encoded.png)

Using either of these strategies, if the site developers aren't properly re-encoding user-entered values before re-displaying them on the screen, then any malicious code that is entered will be run when the information is displayed. In the case of a reflected XSS attack it would only occur on the same user's browser, but in the case of a stored XSS attack, this it would occur whenever the stored information is displayed on any other user's browser.

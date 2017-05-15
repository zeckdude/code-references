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

## Session Hijacking

Session hijacking is a strategy to obtain a user's session ID in order to fool the browser into allowing a hacker access to the site as the logged-in user.

![Session Hijacking Vulnerability 1](https://github.com/zeckdude/code-references/blob/master/img/security/session-hijacking-vulnerability-1.png)
![Session Hijacking Vulnerability 2](https://github.com/zeckdude/code-references/blob/master/img/security/session-hijacking-vulnerability-2.png)

Session ID's can be obtained by a hacker by using a network sniffer on the same wifi network as the user. The sniffer will give the hacker the hostname, full URL being viewed, and any session cookies. By using a proxy tool and injecting the stolen session id into his own browser, he can fool the site into gaining access as the logged-in user.

There are some ways to defend against session hijacking:
  * Use SSL encryption (HTTPS) on entire site
  * Disable HTTP on entire site
  * Kill the session after 15-20 minutes of inactivity if the site is sensitive
    * This will affect the user friendliness of the site, so if the site is not very sensitive, then adjust the timeout time to a longer period, but still make sure it is implemented
    
![Session Hijacking Defense](https://github.com/zeckdude/code-references/blob/master/img/security/session-hijacking-defense.png)

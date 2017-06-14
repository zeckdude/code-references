## Clear-text Communication

Intercepting the transmission of unencrypted (clear-text communication) sensitive data is a strategy where hackers will easedrop on a user's session using a public wifi connection and if the website data is sent via clear-text then certain data can be stolen.

Conditions that need to be met in order for this exploit to work:
  * Site is not using SSL encryption to serve pages
  
Ways to defend against this exploit:
  * Always encrypt site traffic if the site uses any sensitive data (disable HTTP completely)
  * Do not use mixed HTTP/HTTPS
  * Encrypt traffic using SSL
    * Use minimum 128-bit ciphers & disable weaker ciphers
    * Use SSLv3 / TLS & disable older v1, v2 protocols
    
    

## Insecure Configuration

Identifying insecure configuration is a strategy where hackers will find outdated software on the server and run exploits against them in order to gain access to the server. 

Conditions that need to be met in order for this exploit to work:
  * Lack of a standard hardening process for deployed infrastructure and software
  * No central account management mechanism in place on each server
  * No standardized and central process for patch management of servers, libraries or software
  
Ways to defend against insecure configuration:
  * Repeatable Hardening Processes
    * Have a means to reproduce the same hardened configuration on each operating system or server type (e.g. database)
    * Document exact steps to repeat hardening when adding new systems
    * Create a hardened build image or automated configuration script that can be run when adding new systems
      * Reduces human error
      * Ensures hardening is the same across the board
      * Speeds up the process
  * Patch Management
    * Use a central server to keep inventory of all software versions, accounts, passwords, permissions, etc in order to identify servers or software that need to be updated
  * Regular Updates & Audits
    * Periodic audits will help to keep systems in check
    * Update standardized builds frequently each year
    * Re-evaluate installed software, it may no longer be needed

## Insecure Storage

Identifying insecure storage is a strategy where hackers will find sensitive data (user information, passwords, credit card numbers) stored in a database in plain text. 

Conditions that need to be met in order for this exploit to work:
  * Storing of sensitive data in the database in plaintext or using a rudimentary encryption method
  
Ways to defend against this exploit:
  * Determine if any given data is absolutely necessary to be stored in the database
  * NEVER store any sensitive data in the database in plaintext
  * Use [threat modeling](https://www.youtube.com/watch?v=GqmQg-cszw4) to determine which data in the database needs to be encrypted
  * Use cryptographically strong algorithms to encrypt stored sensitive data
    * Use algorithms of over 168 bits, such as `SHA-256`
    * Avoid algorithms that have been broken and are less secure, such as `MD5`, `SHA-0`, or `SHA-1`
  * Use long keys
  * Use hashing with salts to encrypt data even further
  * Use safe key management
    * [Key management](https://info.townsendsecurity.com/definitive-guide-to-encryption-key-management-fundamentals) is keeping the encryption key separate from where the encrypted data is stored, via a service such as:
      * [AWS Key Management Service](https://aws.amazon.com/kms/)
      * [Townsend Centralized Encryption Key Management](https://www.townsendsecurity.com/products/centralized-encryption-key-management)
    * The encryption keys themselves are encrypted on the external service
    * User access to the keys are strictly controlled
    

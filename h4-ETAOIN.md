## Summary of Schneier 2015: Applied Cryptography

[Chapter 1 Foundations](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006)



### 1.1	Terminology
Sender and Receiver: sender transmits a secure message to receiver without it being able to be read by someone else.
Messages and Encryption
-	Message (M)/Plaintext (P): Original message
-	Encryption (E): Disguising the message
o	Function: E(M) = C 
-	Ciphertext (C): Encrypted message
-	Decryption (D): Converting ciphertext back to plaintext
o	Function: D(C) = M

Key aspects: Authentication, Integrity, and Nonrepudiation
-	Authentication: verify the origin of a message
-	Integrity: Ensure message hasn’t been altered
-	Nonrepudiation: Senders cannot falsely deny sending message 

Algorithms and Keys
-	Cryptographic Algorithm (Cipher): mathematical function for encryption and decryption
-	Restricted Algorithm: Security relies on keeping the algorithm secret
o	not up to today’s standards
o	not ideal for larger/changing groups, as if one user leaves then the algorithm must change
o	no quality control or standardization
-	Modern algorithms user a key (K)
o	K = number, keyspace is the range of possible key values
- Earlier functions become:
  - EK(M) = C
  - DK(C) = M 

![Näyttökuva 2023-09-16 202741](https://github.com/marissakirjonen/informationSecurity/assets/142782994/b411cc62-6571-412f-8286-1f82519ffd06)


Symmetric Algorithms
-	Same key for decryption and encryption
-	Security depends on the secrecy of the shared key
-	Two types: 
o	Stream algorithms/ciphers: operate on single bit/byte of plaintext at a time
o	Block algorithms/ciphers: operate on groups of bits (blocks)

Public-Key Algorithms
-	Different keys for decryption (private key) and encryption (public key)

Cryptanalysis
-	Recovering the plaintext without access to the key 
-	Cryptanalytic attacks: 
o	**Ciphertext-only:** access to encrypted message
o	**Known-plaintext:** access to plaintext and corresponding ciphertext
o	**Chosen-plaintext:** able to choose the specific large block of plaintext to be encrypted
o	**Adaptive-chosen-plaintext:** able to choose specific small block of plaintext + choose another block based on previous encryption
o	**Chosen-ciphertext:** able to choose different cipher-texts to decrypt and has access to decrypted plaintetext
o	**Chosen-key:** has knowledge of the relationship between keys
o	**Rubber-hose cryptanalysis:** forceful attainment of key through threats/violence 
o	**Purchase-key:** bribery for key

Security of Algorithms
-	Security depends on cost, time, and amount of data encrypted 
o	Should cost more to break than the value of the data + time needed to break should exceed duration that the data needs to be secured 


### 1.2	Steganography 

**Steganography** is hiding messages within other messages
-	recent methods include; hiding messages in graphic images by replacing the least significant bit of each byte of the image with bits of the message 


### 1.3	Substitution Ciphers and Transposition Ciphers 

**Substitution Ciphers** replace characters in plaintext with other ciphertexts
-	Types: 
o	**Simple substitution cipher (monoalphabetic cipher):** each plaintext character is substituted for a specific ciphertext character
o	**Homophonic substitution cipher:** single plaintext characters maps to multiple ciphertext characters
o	**Polygram substitution cipher:** groups of characters are encrypted together
o	**Polyalphabetic substitution cipher:** made of multiple monoalphabetic ciphers
**Transposition cipher** is where the plaintext remains the same but the order is rearranged 

### 1.4	Simple XOR

**XOR:** eclusive-or
-	basic symmetric encryption to combine plaintext with a key
-	not secure and easily broken

### 1.5	One-time Pads

-	theoretically perfect encryption scheme using sets of random key letters that encrypt only one plaintext character making sure all messages have unique non-repeating keys
-	secure as long as key remains secret and never reused
-	practical limitations: key distribution and synchronization

### 1.6	Computer Algorithms
-	**DES (Data Encryption Standard):** most popular symmetric algorithm 
-	**RSA:** most common public-key algorithm 
-	**DSA (Digital Signature Algorithm):** public-key algorithm used in DIginal Signature Standard




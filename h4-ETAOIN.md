## Summary of Schneier 2015: Applied Cryptography

[Chapter 1 Foundations](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006)



### 1.1	Terminology
Sender and Receiver: sender transmits a secure message to receiver without it being able to be read by someone else.
Messages and Encryption
-	Message (M)/Plaintext (P): Original message 
-	Encryption (E): Disguising the message
  -	Function: E(M) = C 
-	Ciphertext (C): Encrypted message
-	Decryption (D): Converting ciphertext back to plaintext
  - Function: D(C) = M

Key aspects: Authentication, Integrity, and Nonrepudiation
-	Authentication: verify the origin of a message
-	Integrity: Ensure message hasn’t been altered
-	Nonrepudiation: Senders cannot falsely deny sending message 

Algorithms and Keys
-	Cryptographic Algorithm (Cipher): mathematical function for encryption and decryption
-	Restricted Algorithm: Security relies on keeping the algorithm secre
  -	not up to today’s standards
  -	not ideal for larger/changing groups, as if one user leaves then the algorithm must change
  -	no quality control or standardization
-	Modern algorithms user a key (K)
-	K = number, keyspace is the range of possible key values
- Earlier functions become:
  - EK(M) = C
  - DK(C) = M 

![Näyttökuva 2023-09-16 202741](https://github.com/marissakirjonen/informationSecurity/assets/142782994/b411cc62-6571-412f-8286-1f82519ffd06)


Symmetric Algorithms
-	Same key for decryption and encryption
-	Security depends on the secrecy of the shared key
-	Two types:
  -	Stream algorithms/ciphers: operate on single bit/byte of plaintext at a time
  -	Block algorithms/ciphers: operate on groups of bits (blocks)

Public-Key Algorithms
-	Different keys for decryption (private key) and encryption (public key)

Cryptanalysis
-	Recovering the plaintext without access to the key 
-	Cryptanalytic attacks: 
  - **Ciphertext-only:** access to encrypted message
  - **Known-plaintext:** access to plaintext and corresponding ciphertext
  - **Chosen-plaintext:** able to choose the specific large block of plaintext to be encrypted
  - **Adaptive-chosen-plaintext:** able to choose specific small block of plaintext + choose another block based on previous encryption
  - **Chosen-ciphertext:** able to choose different cipher-texts to decrypt and has access to decrypted plaintetext
  - **Chosen-key:** has knowledge of the relationship between keys
  - **Rubber-hose cryptanalysis:** forceful attainment of key through threats/violence
  - **Purchase-key:** bribery for key

Security of Algorithms
-	Security depends on cost, time, and amount of data encrypted
  -	Should cost more to break than the value of the data + time needed to break should exceed duration that the data needs to be secured 


### 1.2	Steganography 

**Steganography** is hiding messages within other messages
  -	recent methods include; hiding messages in graphic images by replacing the least significant bit of each byte of the image with bits of the message 


### 1.3	Substitution Ciphers and Transposition Ciphers 

**Substitution Ciphers** replace characters in plaintext with other ciphertexts
-	Types: 
  - **Simple substitution cipher (monoalphabetic cipher):** each plaintext character is substituted for a specific ciphertext character
  - **Homophonic substitution cipher:** single plaintext characters maps to multiple ciphertext characters
  - **Polygram substitution cipher:** groups of characters are encrypted together
  - **Polyalphabetic substitution cipher:** made of multiple monoalphabetic ciphers
  - **Transposition cipher** is where the plaintext remains the same but the order is rearranged 

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
  
##
### Frequency distribution of letters for Finnish

This is the [website](https://www.sttmedia.com/characterfrequency-finnish) I used to find the following information:

![Näyttökuva 2023-09-16 215856](https://github.com/marissakirjonen/informationSecurity/assets/142782994/51802a81-cb4b-4b1e-a0b3-0b3ce277724a)


##
### Password Manager: [KeePassXC](https://keepassxc.org/)


Password Manager: [KeePassXC](https://keepassxc.org/)
1.	**What threats does it protect against?**
- Brute-force attacks: difficult for an attacker to guess your password
- Phishing: passwords are associated with specific URLs, therefore it’s less likely for a user to write the password to a malicious site
- Data breaches: because you’re using unique passwords, if one gets compromised, other ones will not

2.	**What information is encrypted, what's not?**
- Encrypted: entire database content
- Not encrypted: database header

4.	**What's the license? How would you describe license's effects or categorize it?**
- License: [GNU General Public License Version 3]( https://www.gnu.org/licenses/gpl-3.0.en.html) (GPLv3)
- Open-source license: anyone can view, modify, or distribute

6.	**Where is the data stored? If in "the cloud", which country / juristiction / which companies? If on local disk, where?**
- Stored locally on user’s machine, not in “the cloud”, however user can choose to sync

7.	**How is the data protected?**
- Encryption: combining AES256-CBC and HMAC-SHA256 
- Master password

Found an interesting review for [KeyPassXC]( https://keepassxc.org/assets/pdf/KeePassXC-Review-V1-Molotnikov.pdf)

##

### Crack This Ciphertext

HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG

![Näyttökuva 2023-09-16 223421](https://github.com/marissakirjonen/informationSecurity/assets/142782994/6a66b7b0-708c-4962-92f0-d56b0e9b0d61)


##

### Demonstrate a Password Manager: KeePassXC

This is a random user screenshot from [Medium]( https://gagarine.medium.com/open-source-password-manager-a-viable-alternative-to-lastpass-and-dashlane-435ad92ff716) to show you what KeePassXC looks like, since I blocked most of my own manager.

![Näyttökuva 2023-09-16 225115](https://github.com/marissakirjonen/informationSecurity/assets/142782994/826d2ffc-5414-4385-b7f3-994367decbf4)

From the view you see on the screenshot, you could press Ctrl + N to create a new password for an account (or press the addition button on the top bar).
After this, the view is the following screenshot. You can add the username, website, and manually write a password for this. 

![Näyttökuva 2023-09-30 110759](https://github.com/marissakirjonen/informationSecurity/assets/142782994/01401be5-6dd7-4da1-8067-5f949cf41238)

Optionally, you are able to use the password generator tool, which can be found right next to where you would type in the password (the square button). This is what I personally prefer always:

![Näyttökuva 2023-09-30 110847](https://github.com/marissakirjonen/informationSecurity/assets/142782994/b2066f4d-5ad0-4721-9985-323b2087858e)

I'll demonstrate the use for my Adlibris account!

![keepass](https://github.com/marissakirjonen/informationSecurity/assets/142782994/f1d23e82-904b-4fa4-9a55-8da42df26495)

I clicked the Adlibris account and copied the password to the clipboard and inserted it to the password section on the Adlibris webpage. It's very simple to use! You can optionally add a chrome extension, where it would automatically link the password to the account, however I personally don't have this installed. 

Essentially, the user would have all their usernames and passwords linked into this platform that is downloaded onto the user’s machine (not in cloud, unless manually added). This is all secured under a master password as well, which you set up when you have downloaded KeePassXC. With this, you can automatically pull usernames and passwords directly into the website you are trying to login to. There is also a browser extension available!


##

### Encrypt and Decrypt a Message

I used Gpg4win (Windows) from GNU Privacy Guard. This uses Kleopatra. Despite changing the settings, I couldn't get the language to change from Finnish to English, so I'll translate some of the needed words. 

The first step was to create a key pair by pressing uusi avainpari (new key pair):

![Näyttökuva 2023-09-16 232911](https://github.com/marissakirjonen/informationSecurity/assets/142782994/09bdc9e1-87a4-43d8-80d6-ec4dfd97d54b)

Then I created a plaintext file on Notepad:

![Näyttökuva 2023-09-17 001920](https://github.com/marissakirjonen/informationSecurity/assets/142782994/fcd9ab7f-502a-4cd5-b7da-4c8374f194f0)

After this, I clicked on allekirjoita tai salaa tiedostoja (sign/encrypt files) to encrypt the plaintext I just created:

![here](https://github.com/marissakirjonen/informationSecurity/assets/142782994/6b5aecab-4fb7-4ff9-9e38-5c1e02b2e2e2)

Then it was encrypted! "message.txt --> message.txt.gpg: signing and encryption worked":

![Näyttökuva 2023-09-17 000839](https://github.com/marissakirjonen/informationSecurity/assets/142782994/6f214932-5d18-4613-ab00-7073e9184e78)

To decrypt I just opened the file from my folder with Kleopatra and there we go! It changed the .gpg back to .txt

![this](https://github.com/marissakirjonen/informationSecurity/assets/142782994/d10d87b0-b78e-48a7-9f51-3eb594c07faa)








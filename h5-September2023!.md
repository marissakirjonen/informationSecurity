## h4 September2023!

### Summary of [Schneiner 2015: Applied Cryptography: 2.3 & 2.4](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003)

#### 2.3	One-Way Functions

One-way functions are fundamental to public-key cryptography. They are easy to compute one-way but are significantly harder to reverse. For instance, computing f(x) when given x is simple, but more challenging if only given f(x). Another practical example would be breaking a plate, which is easy to break, but hard to reassemble. 
The article mentions that from a mathematical perspective, there is no proof that one-way functions exist or can be constructed. They have proceeded to explain them in the article despite this as some functions seemingly operate as one-way. 
Trapdoor one-way function: similarly, to the explained version of one-way functions, however in this instance, trapdoor one-way functions are easily computed both ways by possessing the “secret” (e.g., instructions).


#### 2.4 One-Way Hash Functions
One-way hash functions have been used substantially in cryptographic protocols. The function processes a variable-length input string (a pre-image) and converts it to a fixed-length output string (a hash value) which is typically smaller. The goal of these functions is to be a “fingerprint” for the pre-images by providing an indication whether two pre-images are potentially identical.  
Additionally, good hash functions are collision-free, meaning it is hard to generate two identical hash values for different pre-images.
An application of a one-way hash function is verifying authenticity of files of a financial transaction without the need to transfer the entire file, enhancing security. 
Message authentication code (MAC): a one-way hash function with the inclusion of a secret key, which is used to verify the hash value. 

##



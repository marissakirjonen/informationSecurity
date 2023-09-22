### Summary of Schneiner 2015: Applied Cryptography

#### [2.3 One-Way Functions](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003)
 
One-way functions are fundamental to public-key cryptography. They are easy to compute one-way but are significantly harder to reverse. For instance, computing f(x) when given x is simple, but more challenging if only given f(x). Another practical example would be breaking a plate, which is easy to break, but hard to reassemble. 

The article mentions that from a mathematical perspective, there is no proof that one-way functions exist or can be constructed. They have proceeded to explain them in the article despite this as some functions seemingly operate as one-way. 

**Trapdoor one-way function**: similarly, to the explained version of one-way functions, however in this instance, trapdoor one-way functions are easily computed both ways by possessing the “secret” (e.g., instructions).


#### [2.4 One-Way Hash Functions](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003)

One-way hash functions have been used substantially in cryptographic protocols. The function processes a variable-length input string (a pre-image) and converts it to a fixed-length output string (a hash value) which is typically smaller. The goal of these functions is to be a “fingerprint” for the pre-images by providing an indication whether two pre-images are potentially identical.  

Additionally, good hash functions are collision-free, meaning it is hard to generate two identical hash values for different pre-images.

An application of a one-way hash function is verifying authenticity of files of a financial transaction without the need to transfer the entire file, enhancing security.

**Message authentication code (MAC)**: a one-way hash function with the inclusion of a secret key, which is used to verify the hash value. 

##

### Summary of Disobey Niklas Särökaari 2018: [Phishing Through Email](https://www.youtube.com/watch?v=m9YFJGSHYtY) 


Phishing is a tactic where adversaries send emails appearing to be from legitimate sources containing malicious attachments or links to gain sensitive information, e.g., login credentials. Users tend to click these malicious links due to them expecting a similar link (e.g., they ordered a package, and they were expecting an email from Posti), simply out of curiosity, or the user thinking they knew the sender. 

There are several protection mechanisms set in place for countering these phishing threats. 
-	**Sender Policy Framework (SPF)**, which is an email validation system to ensure that the sender’s IP address is the expected one. 
-	**DomainKeys Identified Mail (DKIM)**, which has the inclusion of a digital signature into the email headers that is applied by the sending mail server that can be verified by the recipient.
-	**Domain Message Authentication, Reporting & Conformance (DMARC)**, a policy, which builds on top of SPF and DKIM, to receive reports to detect possibilities of abuse. 
Although these are protection methods against phishing, adversaries can utilize SPF and DKIM within their attacks, making their domains appear more reputable. 

Other security measures in place include: 
-	**Filtering** of malware/spam
-	**URL Whitelisting** restricting access of domains if not on list of approved domains
-	**Greylisting** anti-spam that rejects unfamiliar email senders allowing for approval 

Common attack methods include:
-	**Site Cloning**, where duplicates of websites are developed mainly for stealing credentials of the user. It was pointed out that when site cloning, Full Qualified Domain Names (FQDN) and HTTPS should be used.
-	**IDN Homography Attack**, where Punycode is used to register domains with foreign chars that are similar to common ASCII chars. 

The most effective methods of phishing include package delivery messages, mail from ServiceDesk/IT department, mimicking platforms like LinkedIn, Gmail or Dropbox, or simply adversaries finding something relevant to the company whether that be IPOs, marketing campaigns or even Christmas party plans to exploit. 

To protect yourself from phishing, it’s important to implement SPF, DKIM and DMARC, as well as keeping domains safe by securing similar-looking domains ensuring adversaries cannot use these to their advantage. Additionally, educating users to recognize common attempts, securing infrastructure, and utilizing tools like x0rz phishing catcher, which detects malicious phishing domains similar to own domain. 

























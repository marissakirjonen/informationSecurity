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


##

### Installing Hashcat

To install Hashcat, I opened VirtualBox terminal and followed the guidelines on [TeroKarvinen.com](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)

I used the following commands. I already had Hashcat downloaded, so the terminal message explains this in the screenshots. 

    $ sudo apt-get update
    $ sudo apt-get -y install hashid hashcat wget


![Näyttökuva 2023-09-21 110508](https://github.com/marissakirjonen/informationSecurity/assets/142782994/ca5612ab-1f81-46fe-9b53-02e392596e6f)

![Näyttökuva 2023-09-21 110516](https://github.com/marissakirjonen/informationSecurity/assets/142782994/d8d8442a-02ea-4acc-b659-1e84f5587bed)

## 
Next I created a new directory using these commands: 

    $ mkdir hashed
    $ cd hashed

![Näyttökuva 2023-09-21 110540](https://github.com/marissakirjonen/informationSecurity/assets/142782994/af32c581-c387-43d0-86f0-a59134f21dec)

(I had created the same file previously)

##
Next I used rockyou dictionary as recommended, using these commands: 

    $ wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
    $ tar xf rockyou.txt.tar.gz
    $ rm rockyou.txt.tar.gz

![Näyttökuva 2023-09-21 110702](https://github.com/marissakirjonen/informationSecurity/assets/142782994/d440ed49-545f-4bc1-afa5-70100c0ef68a)

Next I used this command:

    $ head rockyou.txt

![Näyttökuva 2023-09-21 110825](https://github.com/marissakirjonen/informationSecurity/assets/142782994/1efbb944-9c89-409f-87db-12b8a0721b9f)

Lastly you can see that it contains over 14 million words:
    
    $ wc -l rockyou.txt 

![Näyttökuva 2023-09-21 110940](https://github.com/marissakirjonen/informationSecurity/assets/142782994/8de447b4-7f6e-403b-b2df-aa97ff2666f1)


##

### Crack this hash 8eb8e307a6d649bc7fb51443a06a216f

Following the same guidelines as before, I solved the hash '8eb8e307a6d649bc7fb51443a06a216f'.

I used the following command to identify the hash type:

    $ hashid -m 8eb8e307a6d649bc7fb51443a06a216f

![Näyttökuva 2023-09-21 111209](https://github.com/marissakirjonen/informationSecurity/assets/142782994/457ad665-2165-4afe-98c0-f89345ad11be)

From the results we can try to crack the hash using md5.

Let's crack the hash using the following command: 

    $ hashcat -m 0 '8eb8e307a6d649bc7fb51443a06a216f' rockyou.txt -o solved

![Näyttökuva 2023-09-21 111528](https://github.com/marissakirjonen/informationSecurity/assets/142782994/41e8c2a8-9797-47e4-bf94-314ca882cfb4)

Here's a screenshot from the guidelines used, which explains what the command means:

![Näyttökuva 2023-09-22 123826](https://github.com/marissakirjonen/informationSecurity/assets/142782994/72fba622-490d-425d-a3b4-555e40cb7618)

![Näyttökuva 2023-09-21 111609](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a5dc899b-f50e-44e8-8ca8-81858856bd0d)

From this, we can see that the status of the hash is cracked! Additionally, we can see that the type if MD5, which is what we chose, and the target is the hash. We can see the speed as well, which was 12161 H/s (0.03ms).

To see what the result is from the file, I used the following command: 

    $ cat solved


![Näyttökuva 2023-09-21 111539](https://github.com/marissakirjonen/informationSecurity/assets/142782994/f033163b-5309-4c83-b837-d4cea6ce357e)

The result is february! 











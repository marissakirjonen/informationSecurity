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



I created a new directory using these commands (I had created the same file previously):

    $ mkdir hashed
    $ cd hashed

![Näyttökuva 2023-09-21 110540](https://github.com/marissakirjonen/informationSecurity/assets/142782994/af32c581-c387-43d0-86f0-a59134f21dec)


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


Next we can test it with a simple hash that I got from the guidelines above. 

We need to identify the hash type to crack using the following command: 

    $ hashid -m 6b1628b016dff46e6fa35684be6acc96

Then we crack and show the hash with the following commands:

    $ hashcat -m 0 '6b1628b016dff46e6fa35684be6acc96' rockyou.txt -o solved
    $ cat solved 

The cat colved command wasn't showing the result, so I used the next command to display the result: 

    $ hashcat -m 0 6b1628b016dff46e6fa35684be6acc96 rockyou.txt --show

![Näyttökuva 2023-09-22 230146](https://github.com/marissakirjonen/informationSecurity/assets/142782994/9c012409-bb30-4b91-8613-baaf9276d9c3)

##

### Crack this hash 8eb8e307a6d649bc7fb51443a06a216f

Following the same guidelines as before, I solved the hash '8eb8e307a6d649bc7fb51443a06a216f'.

I used the following command to identify the hash type:

    $ hashid -m 8eb8e307a6d649bc7fb51443a06a216f

![Näyttökuva 2023-09-21 111209](https://github.com/marissakirjonen/informationSecurity/assets/142782994/457ad665-2165-4afe-98c0-f89345ad11be)

From the results we can try to crack the hash using md5.

Let's crack the hash using the following command: 

    $ hashcat -m 0 '8eb8e307a6d649bc7fb51443a06a216f' rockyou.txt -o solved

Here's a screenshot from the guidelines used, which explains what the command means:

![Näyttökuva 2023-09-22 123826](https://github.com/marissakirjonen/informationSecurity/assets/142782994/72fba622-490d-425d-a3b4-555e40cb7618)

Result of the command:

![Näyttökuva 2023-09-21 111528](https://github.com/marissakirjonen/informationSecurity/assets/142782994/41e8c2a8-9797-47e4-bf94-314ca882cfb4)

![Näyttökuva 2023-09-21 111609](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a5dc899b-f50e-44e8-8ca8-81858856bd0d)

From this, we can see that the status of the hash is cracked! Additionally, we can see that the type if MD5, which is what we chose, and the target is the hash. We can see the speed as well, which was 12161 H/s (0.03ms).



To see what the result is from the file, I used the following command: 

    $ cat solved


![Näyttökuva 2023-09-21 111539](https://github.com/marissakirjonen/informationSecurity/assets/142782994/f033163b-5309-4c83-b837-d4cea6ce357e)

The result is february! 


##

### Gone Phising: Create a Phising Email

My idea for a phishing email relates to LinkedIn. The email would alert the user of an unknown device accessing their account, and that their password should be changed in order to prevent malicious attacks. 

The first step would be to create an email which closely resembles genuine LinkedIn emails. The tactic used is psychological: worrying the user of unauthorized access to their account. The email exudes a sense of reputability by the inclusion of commonly used elements of LinkedIn emails. Additionally, it creates a sense of urgency for the user, as they wouldn't want to fall victim to unauthorized access to their account!

For the technical part, the email would contain a link (button) redirecting them to a page resembling the LinkedIn’s login page. On this page, the user would need to enter their login credentials to “change their password”. 

I figured out what type of structure is typically used in LinkedIn emails.

Here are a few examples: 


![Näyttökuva 2023-09-22 224411](https://github.com/marissakirjonen/informationSecurity/assets/142782994/18ac36a8-8f37-49c0-a01c-9ef114a6a850)


Based on these, I made the following recreation of a LinkedIn email with my modifications. 


![Näyttökuva 2023-09-22 224606](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a306145f-4858-4944-9d9b-ab1e3bef6bbb)


##

### Voluntary: Compile John the Ripper, Jumbo version

John the Ripper can crack passwords for encrypted files with dictionary attacks. I used the guidelines on [TeroKarvinen.com](https://terokarvinen.com/2023/crack-file-password-with-john/) for these next tasks. 

To start we need to install prerequisites required for John. For some reason the longer command below wasn't working properly. It sent out a message that it was unable to locate package zlib-gst, so I removed that part of the command and tried again and it worked properly as seen on the screenshot.

    $ sudo apt-get update
    $ sudo apt-get -y install micro bash-completion git build-essential libssl-dev zlib1g zlib1g-dev zlib-gst libbz2-1.0 libbz2-dev atool zip wget

![Näyttökuva 2023-09-23 092328](https://github.com/marissakirjonen/informationSecurity/assets/142782994/ff5b7d48-8681-478c-af96-92eb0d4abe4f)

Here's the command I used:

    $ sudo apt-get -y install micro bash-completion git build-essential libssl-dev zlib1g zlib1g-dev libbz2-1.0 libbz2-dev atool zip wget


Now we can start to download and compile John! I started off with the command using git clone which copies the whole project, and to save download time --depth=1 copies just the latest versions of the files. 

    $ git clone --depth=1 https://github.com/openwall/john.git

![Näyttökuva 2023-09-23 093002](https://github.com/marissakirjonen/informationSecurity/assets/142782994/0aca58e4-dd2e-4f51-ae63-90deba848176)

I got a message that the directory couldn't be created as there was no space on my device, so I used the following commands to clean up some space. Ignore the typo in the screenshot, I fixed that afterwards :)

    $ sudo apt-get clean
    $ sudo apt-get autoremove

![Näyttökuva 2023-09-23 093002](https://github.com/marissakirjonen/informationSecurity/assets/142782994/9b641b86-310f-492b-9f9c-e701431d8d63)



After cleaning up some space, the command worked: 

![Näyttökuva 2023-09-23 093014](https://github.com/marissakirjonen/informationSecurity/assets/142782994/2889ddd1-8de0-45f3-ad4a-dcf340c0f8b7)



Next, I used the following commands, where cd = change directory (move to the location you want) & ./configure checks that your system has the requirements for installing a software and creates a Makefile for 'make' command. This needs to be run again if other dependencies are installed in the future. 

    $ cd john/src/	
    $ ./configure


![Näyttökuva 2023-09-23 093152](https://github.com/marissakirjonen/informationSecurity/assets/142782994/44f2bd4c-5bd9-4bd5-a217-e7809e71f5c7)

After running these, the next step was to do the compliation. The command was printed at the end of the previous output, which I copied:

    $ make -s clean && make -sj4

![Näyttökuva 2023-09-23 093302](https://github.com/marissakirjonen/informationSecurity/assets/142782994/5f974e7f-fb74-490f-9a6d-c9d75715f28b)


Once the compliation of John was completed we can use the following commands to find the new executables and scripts in run/ and run John!

    $ cd ../run/
    $ ls -1
    $ cd

![Näyttökuva 2023-09-23 093532](https://github.com/marissakirjonen/informationSecurity/assets/142782994/4f06801e-6c0c-4ed8-a96c-bc05cdb3a54d)


Let's run John now.

    $ $HOME/john/run/john 

![Näyttökuva 2023-09-23 093652](https://github.com/marissakirjonen/informationSecurity/assets/142782994/6be333a4-1a22-4129-a515-2db6a0ff761c)


Now John is downloaded, complied and running!



##

### Voluntary: Crack a Zip File Password


Now with John running, we can test the setup. I downloaded the sample ZIP file from the same [guidelines](https://terokarvinen.com/2023/crack-file-password-with-john/) I used in the previous exercise. 


As seen from the screenshot, it's possible to try and open the file with the command below, however it obviously requires the password that we don't have.. yet. So, let's try and crack the ZIP password. 

    $ unzip tero.zip

![Näyttökuva 2023-09-23 093932](https://github.com/marissakirjonen/informationSecurity/assets/142782994/18758688-0213-41f8-ab7a-cb2e62337704)


First, we need to extract the hash into a new file called tero.zip.hash with the command: 

    $ $HOME/john/run/zip2john tero.zip >tero.zip.hash

Optionallty, we can also look at the extracted hash with the next command: 

    $ cat tero.zip.hash

![Näyttökuva 2023-09-23 094221](https://github.com/marissakirjonen/informationSecurity/assets/142782994/0ad2b7fe-060d-492f-b813-6f95c3ae2407)


Now, we can allow John to do a dictionary attack against the hash with the command: 

    $ $HOME/john/run/john tero.zip.hash 


![Näyttökuva 2023-09-23 094301](https://github.com/marissakirjonen/informationSecurity/assets/142782994/5cad1e1e-c57b-4ef6-9626-237179b02cb9)


Here we can actually find the password, which is butterfly. Now we can use the same command used at the beginning to try and open the file:

    $ unzip tero.zip  


We can use the cat command to look at the extracted hash:

    $ cat secretFiles/SECRET.md 


![Näyttökuva 2023-09-23 094424](https://github.com/marissakirjonen/informationSecurity/assets/142782994/45f19179-48b7-42e9-a0f2-f5cbab134e08)



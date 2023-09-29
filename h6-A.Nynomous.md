## Summaries 

### Quintin 2014: [7 Things You Should Know About Tor]( https://www.eff.org/deeplinks/2014/07/7-things-you-should-know-about-tor)


1.	Tor still works
-	Attacks on Tor have been done due to exploitation of a user who has misconfigured Tor. 

2.	Tor is not only used by criminals 
-	Many activists use Tor for avoiding censorship, and journalists use Tor for research and secure communication with sources 

3.	Tor does not have a military backdoor
-	Despite the initial development being funded by the military, it has no backdoor in the software.
-	Open-source

4.	No one is the US has been prosecuted for running a tor relay
-	Running a Tor relay/“routers”/”nodes”  is not illegal under US law

5.	Tor is easy to use
-	You can download the pre-configured Tor Brower Bundle for [here](https://www.torproject.org/download/) and then start browsing!
-	Another possibility is to run Tor with [Tails]( https://tails.net/), a live operating system, running on a DVD or thumb drive, that routes your internet connection through Tor. 

6.	Tor is not as slow as you think
-	slower than the regular internet, however with more relays, the faster it becomes. 

7.	Tor is not foolproof
-	keep your software up to date and use the Tor Browser Bundle or Tails to make sure you’re using Tor correctly
-	If you want to stay anonymous within Tor, don’t login to services like Google… 😊


##
### Shavers & Blair 2016: [Hiding Behind the Keyboard: The Tor Browser]( https://www.oreilly.com/library/view/hiding-behind-the/9780128033524/XHTML/B9780128033401000021/B9780128033401000021.xhtml#s0010)

Subchapters: 
-	“Introduction”
-	"History and Intended Use of The Onion Router"
-	"How The Onion Router Works"
-	"Tracking Criminals Using TOR".


The Onion Router, Tor, is an Internet browser modified from the Firefox browser. The user’s IP address is hidden when within Tor, making it nearly impossible to identify the user. Tor allows access to otherwise government blocked websites, and secure and private communications between parties. Because of the anonymity aspect, Tor can be used for crime. Initially developed by the US government, nowadays Tor allows for improvements by anyone most typically technically skilled activists wanting to improve the site and is not controlled by anyone, especially not the US government. 

In onion routing, the connection moves through multiple servers. The messages and responses received are encrypted with different keys. Each server has its own unique key for encryption. 

How it works: Let’s say this message will go through three nodes. The first server, node 1, has the address of node 2 and key 1. Node 1 decrypts message using key 1, because it doesn’t have all the keys, node 1 cannot read the encrypted file, so it sends it to node 2. Node 2 has key 2 and the addresses of node 1 (input node) and node 3 (exit node). Node 2 decrypts the message using key 2, it’s still encrypted, so it sends it to node 3, the exit node. Node 3 decrypts the message using key 3, which is the “last layer of the onion”, and the message is passed on to the destination server. The response goes through the same process but adding layers of encryption instead. Essentially throughout the process of going through each node, one layer of encryption is removed (or added), therefore one layer of the onion is peeled (or added back). The core of the onion, the message, is not revealed until the end, which is why nodes cannot see the actual message. 

Mistakes made by users on Tor are the reasons why they are discovered. Settings of the browser should not be changed, as this can result in an accidental leak. A few examples include, allowing location sharing, installing plugins, and allowing scripts and java to run on the browser. 










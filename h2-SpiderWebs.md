# Homework 2 Spider Webs

### A) Read and summarize OWASP: OWASP 10 2021

### Summary of A05:201-Security Misconfiguration

#### Vulnerabilities can arise when:
- Non-appropriate security hardening or misconfigured cloud permissions.
- Unnecessary features, e.g., accounts, unnecessary ports.
- Unchanged default accounts and passwords.
- Detailed error messages to users, e.g., stack traces.
- Updated systems with weak or disabled security.
- poor error handling revealing overly informative error messages, e.g., stack traces
- Out-of-date software. 

#### Prevention methods: 
- Repeat and automate secure setup for development, quality assurance (QA: ensuring product/service/software meets required quality standards), and production.
- Simple platform without unnecessary features.
- Review and update regularly.
- Segmented architecture: separate parts of the application to be better secured.
- Automated verification to check the effectiveness of security.

#### Reference: 
- OWASP. 2021. A05:201-Security Miconfiguration. URL: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/. Accessed: 31 August 2023. 
##
### Summary of A06:2021 – Vulnerable and Outdated Components 

#### Vulnerabilities can arise when: 
- Poor knowledge of versions of all components you use: not running the newest version makes you vulnerable to attacks
- Scanning for vulnerabilities is not regularly done. 
- Devs don't test the compatibility of updated, upgraded, or patched libraries. 

#### Prevention methods: patch management
- Remove unused features.
- Use official sources over secure links and signed packages (reduces the risk of malicious components attached).
- Inventory (record and track) versions used.
- Monitor sources for vulnerabilities, e.g., Common Vulnerability and Exposures (CVE) and National Vulnerability Database (NVD) 
- Utilize email alerts for security vulnerabilities in components in use.

#### Reference: 
- OWASP. 2021. A06:20121 – Vulnerable and Outdated Components. URL https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/.  Accessed: 31 August 2023.
##
### Summary of A03:2021 – Injection

#### Vulnerabilities can arise when: 
- User-supplied data isn't properly examined or filtered, which risks it having malicious data. 
- Dynamic queries are executed without appropriate safeguards: e.g., online shopping platform, where users can search products by name. Attackers can type in commands to change what happens when a user types something in the search box: instead of searching for shoes, an attacker can change it to delete everything with the correct commands. 
- User data is unsafely used within search parameters, risking exposure of sensitive records.

Common types of attacks include e.g., SQL (Structured Query Language), NoSQL (Not Only SQL), and OS Command

#### Detection methods: 
- Manual review of the application's source code.
- Automated testing of all potential input points (e.g., parameters, headers, cookies, URLs).
- Integrating security testing tools into the development pipeline, such as SAST (Static Application Security Testing), DAST (Dynamic Application Security Testing), and IAST (Interactive Application Security Testing).

#### Prevention methods: 
- Use a safe API, or leverage ORM tools that handle data in a safer manner.
- Escape (\) characters input by the user that may have specific meanings in the query language; can be otherwise exploited, e.g., SQL injection.
- Use of ‘LIMIT’ SQL control: prevents attackers from accessing large amounts of data as it restricts the number of records seen. 

#### Reference: 
OWASP. 2021. A03:2021 – Injection. URL: https://owasp.org/Top10/A03_2021-Injection/. Accessed 31 August 2023. 


## 
### A) Install WebGoat

I started off by installing Java. I opened the terminal by pressing ctrl + alt + T then used the following commands: 
- $ sudo apt-get update
- $ sudo apt-get -y install openjdk-17-jre ufw wget bash-completion
  

![Näyttökuva 2023-09-01 102114](https://github.com/marissakirjonen/informationSecurity/assets/142782994/d7c486a5-79f4-4ed5-9031-4f4f6a011413)

##
Next I enabled a firewall using the command: 
- $ sudo ufw enable

![Näyttökuva 2023-09-01 103115](https://github.com/marissakirjonen/informationSecurity/assets/142782994/cb4df020-22a5-423f-acda-3f34edc8f246)

##
The next step was to install and run WebGoat. I did this by using the following commands in the terminal: 
- $ wget https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/webgoat-server-8.0.0.M26.jar
- $ java -jar webgoat-server-8.0.0.M26.jar

![Näyttökuva 2023-09-01 103704](https://github.com/marissakirjonen/informationSecurity/assets/142782994/f2f82f3a-1db0-41cc-ac69-e05fb6fc0bf3)

##
Lastly, I registered as a new user of WebGoat. I also disconnected from the internet as required. 


##
### B) Solve Webgoat 8: General: Developer tools

After I logged into the WebFoat account I chose the Developer Tools tab from General and started the exercises. I began by learning how to check the HTML and CSS of the site and being able to change it. I switched the text color: 

![Näyttökuva 2023-09-01 115601](https://github.com/marissakirjonen/informationSecurity/assets/142782994/239e404f-2650-4a4d-87b7-847a33b837d9)
##
The next task was about the console. I typed console.log("Hello WebGoat!"); which showed 'Hello WebGoat!' in the console, and did a simple math exercise as shown: 

![Näyttökuva 2023-09-01 115814](https://github.com/marissakirjonen/informationSecurity/assets/142782994/022150fe-0640-4305-b7b4-29e6156cc181)
##
Next, I used the command webgoat.customjs.phoneHome() to generate a phone number, which I then had to copy to the input box on the page to see if it was correct. 

![Näyttökuva 2023-09-01 120004](https://github.com/marissakirjonen/informationSecurity/assets/142782994/bce5a48b-6266-4043-a0a2-7bd7d2fc99c4)
##
Then I learned more about the sources tab where you can find different files, e.g. js. 

![Näyttökuva 2023-09-01 120604](https://github.com/marissakirjonen/informationSecurity/assets/142782994/fe9aa8ef-571e-4eac-b1ce-7127eedf4d58)
##
For the next exercise, I had to copy a number that appears in the network section after pressing 'Go!'. Press 'Go!' > wait for it to generate the correct request > click it and go to request > copy the number after networkNum.

![Näyttökuva 2023-09-01 122046](https://github.com/marissakirjonen/informationSecurity/assets/142782994/bdcb3091-ad74-4700-a5f5-212c0ef45c55)





##
### C) Not outdated. 


My next task was to update all operating systems and all applications in my Linux. 

First, I checked all the possible updates needed using the command $ sudo apt-get update in the terminal. 
Then I updated using the command $ sudo apt-get dist-upgrade 

![Näyttökuva 2023-09-01 135520](https://github.com/marissakirjonen/informationSecurity/assets/142782994/541678da-62cc-4f0c-ab4d-2cc18794a85f)

##
### D) Sequel. Solve SQLZoo 
### 0 SELECT basics

![Näyttökuva 2023-09-02 204925](https://github.com/marissakirjonen/informationSecurity/assets/142782994/cead1a25-d57e-4101-a5d1-b88996a279af)
##
![Näyttökuva 2023-09-02 205017](https://github.com/marissakirjonen/informationSecurity/assets/142782994/39cc7be0-3363-4083-8ebe-70d516540f8f)
##
![Näyttökuva 2023-09-02 205059](https://github.com/marissakirjonen/informationSecurity/assets/142782994/cbe4a103-79bc-4651-b695-ca11bdf0c4c7)
##

### 2 SELECT from World, from the first two subtasks


![Näyttökuva 2023-09-02 205320](https://github.com/marissakirjonen/informationSecurity/assets/142782994/185a2a97-242d-47e2-8460-921fd265f1e3)
##
![Näyttökuva 2023-09-02 205500](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a2b291e9-43aa-4aa9-a17b-3d733f04383a)
##

### E) Johnny Tables. Solve Portswigger Labs

##### This lab contains a vulnerability for SQL injection.
##### Original: SELECT * FROM products WHERE category = 'Gifts' AND released = 1 
##### This means it is selecting products from the category gifts AND only released products only. 

##### The original webpage shows 3 released gifts:

![Näyttökuva 2023-09-02 211928](https://github.com/marissakirjonen/informationSecurity/assets/142782994/04056f8f-0913-44d6-8333-d3adf3a62b5b)

##### Modify the category parameter, giving it the value '+OR+1=1-- (insert this behind the URL)
##### Now the webpage shows ALL the products, even unreleased ones: 

![Näyttökuva 2023-09-02 212525](https://github.com/marissakirjonen/informationSecurity/assets/142782994/c1f9adf5-d36c-4601-aded-6f1e32f53b94)

##
### Voluntary bonus: WebGoat: SQL Injection

![Näyttökuva 2023-09-02 223720](https://github.com/marissakirjonen/informationSecurity/assets/142782994/50d272b0-d7ea-4483-8966-d6b731d04a78)

##
![Näyttökuva 2023-09-02 224035](https://github.com/marissakirjonen/informationSecurity/assets/142782994/54d63aef-6617-463b-a9a1-a539c9673f61)

##
![Näyttökuva 2023-09-02 224137](https://github.com/marissakirjonen/informationSecurity/assets/142782994/670b1efa-f637-46e1-8faa-df5ceaa8e538)

##
![Näyttökuva 2023-09-02 224243](https://github.com/marissakirjonen/informationSecurity/assets/142782994/c24f9d20-6d9e-4e8e-a97c-f6bc9705ea56)
##

##### For this exercise, I typed in the input box: ' OR '1' = '1
##### The input shown in the screenshot is what it updated to:
![Näyttökuva 2023-09-02 225022](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a1436c3e-0cc6-4fc8-bc27-9360464ab7f8)

##
##### For this exercise, I inputted login_count: 0 and user_id: 1 or 1=1
![Näyttökuva 2023-09-02 231401](https://github.com/marissakirjonen/informationSecurity/assets/142782994/102a5ea1-03e0-46fd-bb8a-151f39b88886)

##
##### I inputted employee name: a and authentication TAN: 'or'1'='1
![Näyttökuva 2023-09-02 225619](https://github.com/marissakirjonen/informationSecurity/assets/142782994/8d0c922e-1835-4389-b3d6-618ed7e034fd)

##
##### I inputted employee name: smith and authentication TAN: 3SL99A';UPDATE employees SET salary=10000000 WHERE last_name='Smith
![Näyttökuva 2023-09-02 225938](https://github.com/marissakirjonen/informationSecurity/assets/142782994/08d8ae18-d021-44de-9df7-41c6f7118c64)

##
##### I inputted into the action contains field: 1';DROP TABLE access_log;--ss
![Näyttökuva 2023-09-02 230109](https://github.com/marissakirjonen/informationSecurity/assets/142782994/636601c6-7cc6-4061-a7b7-49edd9830cae)










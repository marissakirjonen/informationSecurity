# Homework 2 Spider Webs

A) Read and summarize OWASP: OWASP 10 2021
##
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






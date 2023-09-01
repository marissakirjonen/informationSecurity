# Homework 2 Spider Webs

### Read and summarize OWASP: OWASP 10 2021
 
### Summary of A05:201-Security Misconfiguration

#### •	Vulnerabilities can arise when:
#### o	Non-appropriate security hardening or misconfigured cloud permissions.
#### o	Unnecessary features, e.g., accounts, unnecessary ports, services. 
#### o	Unchanged default accounts and passwords.
#### o	Detailed error messages to users, e.g., stack traces.
#### o	Updated systems with weak or disabled security.
#### o	Non-securely set security options in applications, databases, etc. 
#### o	Website sends no/weak security headers to protect.
#### o	Out-of-date software.

#### •	Prevention methods: 
#### o	Repeatable hardening process: repeat and automate secure setup for development, quality assurance (QA: ensuring product/service/software meets required quality standards), and production.
#### o	Simple platform without unnecessary features.
#### o	Review and update regularly.
#### o	Segmented architecture: separate parts of the application to be better secured.
#### o	Automated verification to check the effectiveness of security referring to the configurations and settings of all environments. 

#### Reference: 
#### OWASP. 2021. A05:201-Security Miconfiguration. URL: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/. Accessed: 31 August 2023. 

### Summary of A06:2021 – Vulnerable and Outdated Components 

#### •	Vulnerabilities can arise when: 
#### o	Poor knowledge of versions of all components you use (client- and server-side).
#### o	Vulnerable/out-of-date software.
#### o	Scanning for vulnerabilities is not regularly done. 
#### o	Upgrading the platform is not done. 
#### o	Devs don't test the compatibility of updated, upgraded, or patched libraries.
#### o	Components’ configurations are not secured. 

#### •	Prevention methods: 	
#### o	Remove unused dependencies, unnecessary features, components, files, and documentation. 
#### o	Use official sources over secure links and signed packages (reduces risk of malicious components attached).
#### o	Monitor unmaintained/unpatched libraries and components for older versions.
#### 	If patching is not possible, deploy virtual patch (rules to apply to prevent vulnerabilities from being exploited).
#### o	Use e.g., OWASP Dependency Check to inventory (record and track) versions of client- and server-side components (e.g., libraries) and their dependencies.
#### o	Monitor sources e.g., Common Vulnerability and Exposures (CVE) and National Vulnerability Database (NVD) for vulnerabilities.
#### o	Automate process with software composition analysis tools. 
#### o	Utilize email alerts for security vulnerabilities in components in use.

#### Reference: 
#### OWASP. 2021. A06:20121 – Vulnerable and Outdated Components. URL https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/.  Accessed: 31 August 2023.

### Summary of A03:2021 – Injection

#### Vulnerabilities can arise when: 
#### •	User-supplied data isn't properly validated, filtered, or sanitized by the application. 
#### •	Dynamic queries are executed without appropriate safeguards. 
#### •	User data is unsafely used within search parameters, risking exposure of sensitive records.
#### •	Malicious data is incorporated directly into SQL or commands.

#### Common types of attacks include e.g., SQL (Structured Query Language), NoSQL (Not Only SQL), and OS Command

#### Detection methods: 
#### •	Manual review of the application's source code.
#### •	Automated testing of all potential input points (e.g., parameters, headers, cookies, URLs).
#### •	Integrating security testing tools into the development pipeline, such as SAST (Static Application Security Testing), DAST (Dynamic Application Security Testing), and IAST (Interactive Application Security Testing).

#### Prevention methods: 
#### •	Use a safe API, or leverage ORM tools that handle data in a safer manner.
#### •	escape (\) characters input by the user that may have specific meanings in the query language; can be otherwise exploited, e.g., SQL injection. 
#### •	Use of ‘LIMIT’ SQL control: prevents attackers from accessing large amounts of data as it restricts the number of records seen. 

#### Reference: 
#### OWASP. 2021. A03:2021 – Injection. URL: https://owasp.org/Top10/A03_2021-Injection/. Accessed 31 August 2023. 






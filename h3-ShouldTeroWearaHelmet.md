## Threat Modeling Summaries

Braiterman et al 2020: [Threat modeling manifesto](https://www.threatmodelingmanifesto.org/)

### Threat Modeling
-	Threat modeling: A method to identify system vulnerabilities throughout its lifecycle (design and development to testing and post-deployment). The Threat Modeling Manifesto provides guidance for anyone aiming to improve system security.


Do:
- Systematic Approach: Use a structured method.
- Informed Creativity: Use both structured methods and creativity.
- Varied Viewpoints: Involve a mix of experts.
- Useful Toolkit: Utilize tools to streamline tasks.
- Theory into Practice: Apply proven methods. 


Avoid:
- Hero Threat Modeler: Don't depend on just one expert.
- Admiration for the Problem: Seek practical solutions rather than just problem analysis.
- Tendency to Overfocus: Keep a broad perspective.
- Perfect Representation: Use multiple models; one doesn’t show everything.

## 

Shostack 2022: [Welcome to the Worlds Shortest Threat Modeling Course](https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf)

Anticipate problems when it’s inexpensive to deal with them, so at the beginning of the design phase! 

Framework questions: 

1. **What are we working on?**
   - Remember that collaboration is important!
   - Sketching is important when collaborating to share thoughts with others.
   - Be sure to record your work for business reasons/regulators.
   - The data flow diagrams should be clear and simple to understand.

2.  **What can go wrong?**
     - STRIDE Mnemonic: spoofing, tampering, repudiation, information disclosure, denial of service, elevation of privileges
     - Each of these are possible threats.
    
3. **What are we going to do about it?**
   - Implement security measures based on prioritized threats.
     
4. **Did we do a good enough job?**
   - Review and seek feedback!

##

Shostack 2014: [Chapter 1 - Dive In and Threat Model!](https://www.oreilly.com/library/view/threat-modeling-designing/9781118810057/9781118810057c01.xhtml#c1)

### Understanding Threat Modeling:
- A tool to spot security issues.
- See the broad view, not just code specifics.
- Identifies problems before they arise.
- Foresees possible security threats.

##

OWASP CheatSheets Series Team 2021: [Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)

### What Does Threat Modeling Involve?
- Mapping out data flow in a system to find weak points.
- Listing all possible threats to the system.
- Recommending security measures to tackle those threats.


### Terminology
1. Threat Agent - Who's Behind the Threat?
   - Potential culprits: individuals or organizations.
2. Impact - What's at Stake?
   - The potential fallout from a threat: monetary losses (direct) or harm to brand image (indirect). 
3. Likelihood - What are the Odds?
   - How probable is it for the threat to happen.
4. Controls - How to defend?
   - Actions and tools to address threats.
5. Preventions
   - Solutions that prevent a threat.
6. Mitigations
   - Strategies to lessen the severity or chances of a threat.
7. Data Flow Diagram
   - A visual tool showing how data moves and interacts within a system, pointing out potential weak spots.
8. Trust Boundary
   - Locations in a system where data's reliability might shift or be compromised, like when reading a file or getting user input.


### Design Documentation
- [4 + 1 architectural view model](https://en.wikipedia.org/wiki/4%2B1_architectural_view_model)

![Näyttökuva 2023-09-08 231107](https://github.com/marissakirjonen/informationSecurity/assets/142782994/3b54b5a9-7fb1-47dd-9e04-23763c68a447)


- Logical View: For designers (functional requirements).
-	Implementation View: For programmers (software components).
-	Process View: For integrators (non-functional needs).
-	Deployment View: For managers (software to hardware mapping).
-	Use-Case View: For all stakeholders.

## 

Evaluate Assets: Use the CIA model: confidentiality, integrity, and availability. 
- Data in rest (non-transmitted data) is considered to be less vulnerable and threat agents attack more likely than data in transit. 

Define System Aspects: Including data flows, trust boundaries/levels, roles, and entry points.

Identify Threats: List all potential threats and threat agents using attack vectors and trees. 

Threat Mapping: Link threat agents to system entry points.

Attack Framework: 
- Draw attack vectors/trees.
- Abuse Cases: Relate them to use cases.
- Refine Attack Vectors: Adjust based on findings.

Threat Matrix: Document threat traceability.
- Risk Assessment: Define threat impact/probability.
- Rank risk value.
- Identify risk owners. 





## 

## Security Hygiene

Make sure to follow basic security hygiene. 

1. Use unique and different passwords for everything; a unique password would use special characters, numbers, and a mix of capitalized and lowercase letters. Avoid common words/phrases. This can be achieved best by using a password manager, for example [KeePassXC](https://keepassxc.org/).
2. Software updates; updating whenever it is available keeps your device from being compromised easily. They patch vulnerabilities within the updates.
3. Anti-virus software
4. Be mindful of ports on the device, not to allow e.g. unknown USB sticks to access points.
5. Backup your devices.


## 

## Make-belief boogie-man - a threat model for a company

### StudyHelp

Company overview: A platform for students who need tutoring/study partners. It matches students with study partners and tutors to aid them with their studies. It contains academic resources, flashcards, notes, and practice exams for different subjects. This contains in-app purchases. 

**1. What are we working on?**
Assets:
Primary assets
- User profiles: includes personal data (names, addresses, financial details), and links with academic subjects.
- Payments
- Backups
- Academic resources: summaries, practice exams, flashcards, etc.
- Collaboration tools: video/audio tools, collaborative documents


Diagram of systems: 

![Näyttökuva 2023-09-09 214847](https://github.com/marissakirjonen/informationSecurity/assets/142782994/37fbedf2-b1d4-4a2f-ae0c-b6b1dffeebcc)

The platform StudyHelp connects to each of the following nodes (no arrows to keep the diagram readable). The user management system includes user data, payment data, and preferences; so this then would connect to collaboration tools to connect to other users, scheduling systems to schedule sessions with tutors, and payment system for required payment of subscriptions. The academic resources connects to user system to be able to link preferences, and the collaboration system to be able to study resources with other users. The scheduling system would connect to the collaboration system for sessions. The notification system connects to the scheduling system to alert of upcoming sessions. The backup system connects to each of these!


** 2. What can go wrong?**














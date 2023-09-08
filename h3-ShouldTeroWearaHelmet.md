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

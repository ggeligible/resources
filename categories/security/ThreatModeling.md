Threat Modeling: Threat modeling is software design analysis that looks for security weakness by juxtaposing software design view against a set of threat agents.


You begin threat modeling by focusing on four key questions:
* What are you building?
* What can go wrong?
* What should you do about those things that can go wrong? 
* Did you do a decent job of analysis?

# Process:
* Decompose and model the software
* Identify what is in scope, partially in scope and out of scope
* Identify assets, controls and attackers
* Juxtapose attack possibilities and software model
* Interpret the threat model
* Rank the risk of the attack
* Propose mitigations

## Decompose and model the software
* Understand systems and create development diagrams
* List down componenets which are in scope
* How control flows
* How components and flows relate to the host boundaries
* Applicatio layer communication protocols

Create following models for the system:
* Logical models
* Layer models
* Deployment models

System Models:
* Components come from logical and layer models
* Maching boundary come from deployment model
* Protocol come from deployment model
* Network zones come from deployment model

## Identify assets, controls and attackers
* Assets: The data and functions that the system must protect
* Security Controls: The mechanisms currently designed and implemented to protect the assests
* Threat agents: The actors that want to harm the system

### Typical asset examples
* PHI/PII
* Logs
* Session information
* Any type of credentials, tokens
* Keys
* Audit and reporting information
* Credit card information
* Privelege codes

### Typical control examples


### Typical Threat agent examples


* 

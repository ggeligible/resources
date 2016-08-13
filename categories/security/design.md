### Requirements
* Security Policy/Goal
* Required mechanism to enforce security policy

#### Security Policy
* Confedentiality - Sensitive information is not leaked to unauthorized paries
 * Privacy
 * Anonymity
* Availability - System should respond to the requests
* Integrity - Sensitive information should not be tampered by unauthorized users

#### Require mechanisms
* Aunthentication - identify the identity
 * User __knows__ eg. password
 * User __is__ eg. Biometric
 * User __has__ eg smartphone
 * Multi Factor Authentication
* Authorization - when a principal may perform an action
 * user based access control policies
 * role based access control policies
 * originator based access control policies
* Auditability / Accountability - Retain enough information to be able to determine the circumstances of a breach or misbehavior
 * Log files and protected from tampering


#### Defining Security requirements
Forces enforcing and driving security requirements:
 * Regulation / Standard Compliance like HIPAA, PCI, SOX etc
 * Organization values like privacy, integrity, etc
 * Threat modeling and Architecture Risk Analysis
 * Attacks have already ocurred
 
#### Designing Abuse Cases
Abuse case illustrate security requirements which describes what a __system should not do__. How to design abuse cases:
* Using attack patterns abd likely scenarios, build cases where adversary can violate a security requirement
* Assume adversary's power based on thread model and what could go wrong.
* What might occur if security measure didn't exist or removed.

### Design Phase
* Processes, interactions, programming langages and framework
* Decomposition into modules and components
* Implemtning data types, functions, data structure

#### Process
* Design system based on the requirements
* Perform risk based analysis of the design
* Determine improvements and risks as part of the analysis and improve the original design until we are satisfied

#### Desgin Principal 
__Categories:__
* Prevention - Eliminate software defect entirely
* Mitigation - Reduce the harm from exploitation of unknow defects
* Detection & Recovery - Identify and understanding an attack and undo the damage if possible

__Principals:__
* Favor simplicity
 * Use fail safe defaults
 * Do not expect expert users
* Trust with reluctance
 * Employ a small computing base
 * Grant least privilege required
* Defend in depth
* Monitoring and trace

##### Favor simplicity

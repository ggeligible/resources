__Security is not an optional feature, its a mandatory requirement__

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
* Make sure to test for what should not happen.

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
* [Favor simplicity|https://github.com/1989gaurav/resources/blob/master/categories/security/design.md#favor-simplicity]
 * Use fail safe defaults
 * Do not expect expert users
* Trust with reluctance
 * Employ a small computing base
 * Grant least privilege required
* Defend in depth
* Monitoring and trace

##### Favor simplicity
* Category: Prevention
* Understanding system is very important which requires simplicity
* Includes external interfaces, internal design and interactions
* Use fail safe/secure defaults
 * Prefer whitelist over blacklist
 * No default passwords
 * Strong cryptography key length as default like 4096
* Don't expect expert users
 * Simple user interface
 * Natural and obvious choice should be the most secure choice
 * Don't force users to make frequent secuirty choices, might end up chosing insecure option by selecting Yes
 * Help users to explore consequences of choice in case of security choices
* Passwords
 * Easy to remember for owner and hard to guess for adverseries 
 * Password reuse of strong password
 * Password Managers - Encrypted by single strong passwords

##### Trust with reluctances
* Category: Prevention & Mitigation
* Security of system depends on security of each part
* Imporve security by reducing the amount of trust placed in each part
 * Better design
 * Function safely
 * Avoid unnecessary assumtions - Like third party libraries are correct
 * Small trusted computing base
* Trusting with least privilege / Need to know
* Trust is transitive - If you trust something, you trust what it trusts
* Input validation
* Promote Privacy - Restrict flow of sensitive information as much as possible
* Compartmentalization - Isolate system components in compartments like sandbox

##### Defend in depth
* Security by diversity - Do not rely on single defense or single kind of defense
 * Firewall
 * Encrypt at rest
 * Use type safe language to write web server
* Community resources
 * Use community resources like hardened code, cryptography libraries
 * Vet design publically
 * Stay up on recent threats and research 

##### Monitoring and Tracebility
* If a attack happens, how will you know it
* Once we know, how to stop the attacker
* Logs for operational information
 * Failed logging attempts
 * Transactions processed
 * Events handled
* Log aggregation


### Top Design Flaws
* Don't assume trust rather explicitly give it or award it
* Don't use an authentication mechanism which can be bypassed or tempered
* Don't authorize without considering sufficient context
* Don't confuse data, control and process instructions from untrusted sources
* Fail to validate the data explicitly and comprehensively
* Fail to use cryptography correctly
* Fail to identify and handle sensitive data correctly
* Don't ignore the user
* Don't integrate external components without considering their attack surface
* Don't constrain future changes to objects and actors

---
aliases:
  - Information Security Best Practices
tags:
  - Notes
  - Cybersecurity
Date: 2023-12-11
Completion: true
obsidianUIMode: preview
---
# Panama Papers
## What went wrong?
The company does not encrypt their email and uses a 3 year old content management system called Drupal, with well known vulnerabilities. The content management system is not protected against SQLi attacks. The network architecture is inherently insecure as the email and web servers are not separated from the user database in anyway. Some parts of the website is also running an older version of WordPress and an outdated version of Slider Revolution, a plugin with well documented securities issues. The client login portal has 4 government grade remote access trojan horse, RATs. 
# Solarwinds Supply chain attack
## What went wrong?
Exposed server, unpatched software and weak password, leading to password spraying/brute force attack
## What did they do?
Once the attackers got in, they modify the build process and inject malicious code in to the Solarwinds's Orion software platform. Once the build has been released, thousands of individuals including big industries are infected with SUNBURST trojan horse. These attackers would obtain their credentials and important information.
# Other attacks 
Pandora papers
JPN information leak
# Laws
## Malaysia
### Copyright Amendment Law
1. To make unauthorised transmission of copyrighted material over the Internet as infringement of copyright
2. Any attempt to bypass/circumvent the measures used to restrict access to copyright materials is also an infringement of copyright
### Computer Crime Law
1. Unauthorised use of computer
2. Unauthorised modification in a computer
3. Use of computer to commit crimes or unlawful activities
### Digital Signature Law
1. Provides a framework for the licensing and regulation of Certification Authorities (CA) and provide legal recognition to digital signature
## USA
**Computer Fraud and Abuse Act**
### Identity theft
*Identity theft is not a joke Jim!*
### Digital Millennium Copyright Act

# Organisations
## Malaysia
### MCMC
Regulating, supervising, and monitoring communication and multimedia activities
### MBOT
Just a group of technologists who wants to get international name
# Security Risk Management
Analyse and understand the current system that is being deployed and the threats that the organisation is currently facing or will be facing. 
**Components of Risk Management** -> PPOSH
1. **P**eople
2. **P**rocedures
3. **D**ata
4. **S**oftware
6. **H**ardware
**Evaluating asset value**
1. Is it worth saving?
2. What damage would it cost if exposed?
3. Is it important to the organisation
4. How much would it take to protect/save it?
**Prioritising threats**
1. How much would it take to defend against it?
2. What damage would it make
3. Which is the most dangerous
4. How much does it take to recover from that attack
## Risk assessment & Cost Benefit Analysis
### Risk assessment
**Formula:** $$x = value_{asset} \;\times \; likelihood$$
$$Risk \; = \; x\;- control_{current} \; + \;x \;\times \; uncertainty\;\times x $$
### Cost Benefit analysis
**Formula:**$$ALE_{Annual\;Loss\;Expectancy}\;=\;SLE_{Single\;Loss\; Expectancy}\;\times\;ARO_{Annual\;Rate\;Occurance}$$
$$SLE = EF_{Exposure\;Factor}\;\times\;value_{asset}$$
## Risk control Strategies
### Terminate
1. Advise the organisation on the uncontrollable risks and vulnerabilities associated with certain services.
2. Think of other services that can satisfy the customer
### Transfer
1. Process of transferring risk to another asset, process or organisation
2. Company A can reach out to other firms or organisations specialising in security management and administrative expertise
3. Company A can then transfer the risk associated with management of complex system to the organisation that specialises in them
### Acceptance
1. Company A does not defend against the exploitation of the vulnerabilities 
2. Usually done if the asset is not important
### Mitigation
1. Attempts to attenuate or reduce the impact of the attack
2. 3 common plans are used
	1. Disaster recovery plan
	2. Incident response plan
		1. Decide what to do during an attack
	3. Business continuity plan
		1. Continuation of business if an attack happens
### Defense
1. Most common and popular risk control strategy
2. Employ procedures to defend against the attack or to protect the vulnerabilities from being exploited. 
# Policies
A collection of rules and instructions that is agreed upon by a group of people, authorities, etc., and meant to guide employees on specific situations
## Functions of policy
1. Defines how security should be in an organisation
2. Defines the security mechanisms put into place to protect sensitive information
3. Guides employees on what they should do when things go awry
4. Guides employees on how they should behave when using computer system
5. Guides employees on how they should carry out security related duties
## Types of policy
### Information policy
Defines what information are sensitive and how the organisation should protect them. It also defines the kind of information that is accessible to specific groups of people. 
**Example**
- Students can access lesser information than lecturers. 
## Backup policy
Defines how the organisation should back up their files
1. Most common way is to do a full backup once a week with incremental back up every other day
2. Incremental back up means only files that have been changed are backed up
3. This is faster and takes up lesser space
## E-mail policy
Some email leaving an organisation may contain sensitive information.
The policy defines under which condition is this acceptable
## Security Policy

### File control
- Specify the requirements of file access control
	1. It should be on all files in a system
	2. Work alongside authentication mechanism to prevent unauthorised users from accessing the file 
	3. It should specify which groups of users can read, write or execute programs
### User Control
- Defines how system or network administrator should configure a system
- They should also specify how authentication of users is done
	- User-id
	- Passwords
		- Specify the minimum and maximum length of password
		- Specify the content of the password
### Network
- Specify the rules of network connectivity
### Data Security
- Determines the appropriate encryption algorithm to protect sensitive data
- Specifies the procedures for key management
### Antivirus
- Specifies the details of the security program of the system
- The antivirus program should be installed in the file server and email server. 
- The antivirus should check specific types of files or when files are opened or when scheduled
# Incidence Response Procedure
1. Before declaring an incident, an investigation is carried out to confirm if the incident has actually happened.
2. Specify an escalation procedure as more information of the incident is garnered, usually mobilising a response team
3. Control the information that is shared to the public
4. The response plan usually aligns with the objective of the IRP
# Chapter 5 - Disaster Recovery
[[Chapter 5 - Disaster Recovery]]
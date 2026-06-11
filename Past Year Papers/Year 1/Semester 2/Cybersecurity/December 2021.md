---
aliases:
  - December 2021
tags:
  - PYQ
  - Cybersecurity
Creation Date: 2023-11-29T14:25:00
Completion: true
obsidianUIMode: preview
---
# Question 1
## Question a
Which is to implement salt to both password and the associated user-id. Salt is a sequence of random number that is concatenated to the password. The salt is concatenated before the password is put into a hash function. The addition of salt increases the complexity of the password. 

This way, the system does not only check the hash of the entered password with the hash of the password in the system but the hash of the entered password and the salt associated with the user id with the stored hash of password and salt. 
## Question B
--
## Question C
--
## Question D - use ASCII code for simplicity 
$$C = M^e \; mod N$$
$$C = 676150^{17} mod 11$$
$$C=7$$
## Question E
The values of p and q can be 7 and 17. In this case, the value of Z would be 96. The formula to find d would be $ed\;mod\;Z = 1$ The multiplication of 5 nearest to 96 will be 95 and 100. In the first case, the value mod of Z does not result in a 1, instead it results in a 95. In the second case, $100 \; mod \; 96$ will yield 4 instead of one. In both of these cases, the value of d is wrong. Thus, the value of d cannot be found with conventional method. 
# Question 2
## Question a
1. DDoS attacks
	1. Distributed Denial of Service attacks aim to block users from accessing services in a network.
	2. These attacks work by flooding the network with excessive packets until they could no longer respond
2. Malware
	1. Malware comprises viruses, worms, and Trojan Horse.
	2. These malwares aim to steal the victim's essential information and use them for the attacker's gain
	3. These malware may also serve as a tool to damage the victim's system
3. Surveillance
	1. The attacker may use nmap ping scan to determine the number of hosts in the network.
	2. They are also able to determine how many ports or even backdoors that they can exploit
## Question b 
--
## Question C
--
# Question 3
## Question A
### Question I
1. Implement stronger firewall. The firewall should prevent unauthorised users from entering and accessing the system. 
2. Implement multi-factor authentication. Users attempting to access the hospitals' database has to enter a sequence of random numbers generated randomly each time.
### Question II
cat rockyou.txt get Taylor
grep Taylor rockyou.txt
### Question III
--
### Question iv
by using sftp. 
## Question B
### Question I
#### File Control
- Specify the requirements of file access control
- The file access control should be available on all files in a computer
- Should work alongside authentication mechanism to prevent unauthorised users from accessing
#### User Control
- Determines how the system or network administrator should configure the system
- Determines how authentication of users should be done. 
	- User-id
	- Password
		- Determine the minimum and maximum length of password
		- Determine the content of the password
#### Network
- Specify the rule of network connectivity
#### Data Security
- Specify the appropriate data encryption algorithm
- Details the procedure of key management
#### Antivirus
- Details the system's security program
- The anti virus should be installed in the file server and the web server
- The anti virus should be required to examine specific types of files, or when they are opened or according to schedule
### Question II
Impose stricter rules on campus. Anyone who refuses or fail to comply to the security policy set by the organisation would be punished severely. This would incentivise everyone to comply to the policy. 

# Question 4
## Question a
### Question I
Adware. The victim is bombarded with pop-up adverts that show desirable products or services that is designed to lure the victim. Adware is secretly installed onto the victim's computer when the victim installed an infected program. Adware may also be able to track the victim's activity. 
### Question II
1. Exercise caution when installing any program, files, or applications.
	1. Jennie should be careful around applications that offer desirable use but it is free
	2. Jennie should use websites such as VirusTotal or use antivirus programs to scan the program to determine if it is actually safe.
3. Install adblockers
	1. Adblockers can block any pop-ups and advertisements that appears when Jennie is browsing the web. 
	2. This can prevent Jennie from accidentally clicking on a ad that leads her to a malicious website that automatically downloads a malicious program.
### Question III
Page in the middle attack. In this attack, Jennie is redirected to a website that is meant to look authentic and trick the victim into believing that they are in the legitimate website. Then, Jennie unknowingly inputs her financial and sensitive information into the website which is then recorded by the attacker. The attacker then uses her information to disguise as her to access her bank account or other personal information. One method to detect such attack is to refer to the top search bar of the website n determine whether it has https or not. 
## Question b
### Question I
I would investigate the company device given to her. I will try recover any deleted files from the device using hex editor such as Winhex or HxD. This way, I can bypass her attempts at covering her tracks. I would also check any records or log of UTAR database to determine the times she had accessed sensitive information. Finally, I would also check her emails that she has sent and received. The content of the emails will be analysed to find any sensitive information or  to find signs of inappropriate behaviour
### Question II
Using Static method. The metadata of the file can be analysed. The author, permissions, date of create and the software used to create the file. The attacker can modify these information to conceal their activity. The structure of the file should be analysed. Look for any suspicious objects or scripts. Finally, look for any embedded objects. Embedded objects may be viruses or indicate presence of malware. 
## Week 2: Security Planning & Testing Methodology ##

This week I will be designing a security baseline and performance testing methodology. From this task I will be learning how to think like a systems administrator and design a secure system. To do this efficiently, it is important to firstly understand the threats and how to prevent them. 

**Threat Models:**

**Threat (1):** Brute-force SSH attacks--> this is when attackers attempt to gain unauthorised access by repeatedly guessing the SSH passwords. 
The solution below also prevents the threat of having weak or default authentication credentials, mentioned in our week 7 lectures. 

**Solutions(Mitigation Strategies):** Disable password-based authenication. By doing this it removes the attackers ability to guess the password, which prevents brute-force SSH attackers from gaining access to the server. Instead of having a password-based authenication, the server can have a SSH key-based authentication. This means the server uses two files, one private key file kept on the workstation connecting to the sever and one public key file stored on the server. The server uses it's public key to authenically check if the private key being used can have access to the server. If the keys don't match, there is no access to the server. 

**Threat (2):** System compromise due to misconfigurations or missing security controls --> Attackers can exploit any weaknesses of the operating system if there are unnecessary services or missing security controls that remain undetected. 

**Solutions(Mitigating Strategies):** By performing regular security audits using automated tools such as Lynis. Lynis performs a full security audit of a linux system, checking for: SSH configuration, firewall status, user privilges, file permissions and the system hardening level. By using a tool like Lynis, it greatly prevents missing security controls and any misconfigurations. 






**Performance Testing Plan:**

-From the workstation, I will remotely monitor the servers system using the SSH. This shows that the server is headless and further strengthens my knowlegde of working directly with a server without any graphical interface. 

-Performance monitoring will be done via Linus command-line tools & the metric to be observed will be: CPU usage, disk utiliation, memory usage and network activity.




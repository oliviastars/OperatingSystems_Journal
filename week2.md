## Week 2: Security Planning & Testing Methodology ##

This week I will be designing a security baseline and performance testing methodology. From this task I will be learning how to think like a systems administrator and design a secure system. To do this efficiently, it is important to firstly understand the threats and how to prevent them. 

**Threat Models:**

**Threat (1):** Brute-force SSH attacks--> this is when attackers attempt to gain unauthorised access by repeatedly guessing the SSH passwords. 
The solution below also prevents the threat of having weak or default authentication credentials, mentioned in our week 7 lectures. 

**Solutions(Mitigation Strategies):** Disable password-based authenication. By doing this it removes the attackers ability to guess the password, which prevents brute-force SSH attackers from gaining access to the server. Instead of having a password-based authenication, the server can have a SSH key-based authentication. This means the server uses two files, one private key file kept on the workstation connecting to the sever and one public key file stored on the server. The server uses it's public key to authenically check if the private key being used can have access to the server. If the keys don't match, there is no access to the server. 

**Threat (2):** System compromise due to misconfigurations or missing security controls --> Attackers can exploit any weaknesses of the operating system if there are unnecessary services or missing security controls that remain undetected. 

**Solutions(Mitigating Strategies):** By performing regular security audits using automated tools such as Lynis. Lynis performs a full security audit of a linux system, checking for: SSH configuration, firewall status, user privilges, file permissions and the system hardening level. By using a tool like Lynis, it greatly prevents missing security controls and any misconfigurations. 

**Threat (3):** Excessive user privileges and improper access control. --> If users are granted more permissions than necessary or if the administrative access is poorly controlled, this means that a compromised account cna lead to full system control. Direct root access (logging into the system as root itself, allowinng user to have full system power) and shared privileged accounts can increase the chances of accidental misconfigurations and malicious action.

**Solutions(Mitigating Strategies):** Disable direct root login (to prevent user from having full power over the system), and instead use a non-root user account for administration. Further security strengthening can be done by applying the principle of least privilage, which grants only the minimum necessary permissions to users and processes. Lastly, by granting sudo access only where required and logging the administrative actions, it allows us to closely monitor security actions, while making threats inside the system easier to detect. 




**Performance and Security Testing Methodology:**

Performance testing will be carried out remotely from the workstation using SSH. This approach reflects real world administration practicers, where systems are managed without and graphical interfaces.

-Performance monitoring will be done via Linus command-line tools. The key metrics that will be observed are: CPU usage, memory usage, disk utilisation and network activity. 

-Security testing will also be done alongside performance testing, to ensure controls do no negatively impact the systems behaviour. Automated security auditting tools such as Lynis will be used to identify: misconfigurations, missing controls and hardening opportunities. 


-Baseline measurements will be taken initally, with further monitoring to be performed under different workloads in later weeks...likewise with repeating the audit process after implementing security controls to verfiy that issues identified have been addressed. 




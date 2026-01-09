# Week 4: Initial System Configuration & Security Implementation

This week I will be deploying my server and implementing foundational security controls.
The current server was operating on default installation settings and has not undergone security hardening.
Below will demonstrate the process of SSH hardening:

### (1) Configure SSH with key-based authenication

#### Step 1: Creating the keypair in the workstation

--> ssh-keygen: this creates two keys and stores them in ~/.ssh/ 
Chosen key type: ed22519 was reccomended by OpenSSH as it is modern and secure.

--> Passphrase = a password that protects the private key file itself (incase someone steals laptop or VM disk)

As seen from the image below, two keys were successfully created in the workstation, the private key was also given a passphrase to ensure further security on the private key:

<img width="710" height="221" alt="image" src="https://github.com/user-attachments/assets/615e6c3b-4ef9-42f6-a70b-c98caf1164ba" />


#### Step 2: Copy the public key file into the servers files:

<img width="703" height="235" alt="image" src="https://github.com/user-attachments/assets/3108bc08-7d41-4531-a899-579280a1c469" />


#### Step 3: Login to server and check correct files are saved:

Instantly asked for the passphrase key when attempting to log into server:
<img width="481" height="338" alt="image" src="https://github.com/user-attachments/assets/9dd9f766-5976-4167-951e-4c29f31e1536" />

Succesfully accessed the server though without having to input the login password.
Logged in once again to ensure there was no password queries and there was not, the files were also correctly copied to the server 'user' :

<img width="1386" height="442" alt="image" src="https://github.com/user-attachments/assets/98ef7c63-f4bd-4da4-b540-eb08d4666e11" />

### (2) Configuring a firewall that permits SSH from only one workstation:

Firewall--> a rule-based traffic filter that decides whether a network packet is allowed in or not.

UFW --> command line that allows you to add rules 

Below the server has now only permitted SSH from the workstation, using the workstations server:
<img width="903" height="269" alt="image" src="https://github.com/user-attachments/assets/3b6f325a-80e5-43f7-9bb3-28bb1ea7c8f1" />

Further evidence that firewall is successfully working:
<img width="854" height="256" alt="image" src="https://github.com/user-attachments/assets/dba7735e-736b-4fa8-b2e5-f86baa7eab28" />

### (3) Managing Users:

#### Creating a non-root administrative user:

Using 'sudo adduser' to create new user

'sudo usermod -aG sudo ...' to allow user to have sudo privilges 

'groups' to prove new user 'adminuser' is allowed sudo privilges 

<img width="895" height="731" alt="image" src="https://github.com/user-attachments/assets/643cc0bf-b185-4e16-9705-43fe19403a64" />

Evidence that adminuser has sudo privilges:
<img width="900" height="1045" alt="image" src="https://github.com/user-attachments/assets/cabe83fc-8ef5-4c73-be4a-e2e586d39cba" />

### (4) SSH Access Evidence:

Disabling root login:
1) copy key file path to adminuser files:
<img width="795" height="360" alt="image" src="https://github.com/user-attachments/assets/f1eac852-0a32-45a8-b607-583d528ed23c" />

2) Log into adminuser on server (Ubuntu) via SSH with no password login:
<img width="681" height="750" alt="image" src="https://github.com/user-attachments/assets/c764604e-f4d5-4963-8f98-e2b52666ffb8" />

### (5) Configuration Files Evidence:

Below are the highlighted changes of the configurtation file of the server. 
Key three changes were: 
denying root login(changing yes to no), denying password authentication(changing yes to no) and permitting public key authentication(changing no to yes): 

<img width="1452" height="1357" alt="image" src="https://github.com/user-attachments/assets/8cd68f4a-6ee8-47e2-8556-33b7641047c2" />







 






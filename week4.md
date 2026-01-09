# Week 4: Initial Systme Configuration & Security Implementation

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

Below the server has now only permitted SSH from the workstation:
<img width="903" height="269" alt="image" src="https://github.com/user-attachments/assets/3b6f325a-80e5-43f7-9bb3-28bb1ea7c8f1" />

 






# Week 7 - Security Audit and System Evaluation

On the final week, a full security audit will be generated, remedications will be made and the audit will be done again to provide evidence of improvments. A final evaluation of the system will be done too.

### Step 1) Installing Lynis:

<img width="866" height="697" alt="image" src="https://github.com/user-attachments/assets/d8704a36-2f65-4c1d-a555-d5ff58ba159a" />

### Running Lynis:

As seen below, Lynis was successfully installed and ran:

<img width="929" height="1826" alt="image" src="https://github.com/user-attachments/assets/7e816dae-9bee-458a-ac06-88ab0aa6e002" />

## Step 2) Initial Lynis Security Scan Details (before remediations):

<img width="887" height="1065" alt="image" src="https://github.com/user-attachments/assets/a35798a4-a947-4999-8aac-c29d7e8e3754" />

From above the initial Lynis audit produced a hardening index of 58, which indicates a moderate baeline security result of defualt Ubunutu installation.

There were **257 test performced**, **2 Warnings** and **49 Suggestions**
Below are the two Warnings and some of the suggestions:

<img width="1969" height="1313" alt="image" src="https://github.com/user-attachments/assets/c27f297a-7d9b-4623-81a1-9af4fd0e9c6f" />

<img width="2138" height="1399" alt="image" src="https://github.com/user-attachments/assets/eac8f512-9b48-4e6b-b0c3-ce6db212132b" />

### Step 3) Executing recommended improvements:

- Rebooting system, as recommended by first warning:

<img width="885" height="491" alt="image" src="https://github.com/user-attachments/assets/51ccb0fb-a866-41c3-9771-ffc7f43b196a" />

- Updating and upgrading system, to improve vulnerable packages:

<img width="940" height="671" alt="image" src="https://github.com/user-attachments/assets/7488df6c-85b6-418a-9e19-da01a84b8594" />

Further evidence of upgrade results:

<img width="936" height="668" alt="image" src="https://github.com/user-attachments/assets/486157cf-59fd-4623-b6ee-6dc0315f695d" />

## Step 4) Re-running Lynis security audit:

<img width="942" height="1062" alt="image" src="https://github.com/user-attachments/assets/45dd9599-2a34-405c-8730-c6b3cc43ac94" />

# Before and After audit evaluation:

Hardening index improved from 58 to 64, showing successful remediation and improved security proccesses! 

Below also illustrates how both warnings from the initial test are resolved now:

<img width="956" height="804" alt="image" src="https://github.com/user-attachments/assets/618d1700-94c4-4b08-8c61-adfdc9ddbe2a" />

## Network Security Assessment (with nmap)

nmap--> Network Mapper, that scans security and shows what parts of the system are reachable.


#### Installing nmap:

<img width="943" height="826" alt="image" src="https://github.com/user-attachments/assets/9eb96e48-2f7f-4b83-b88c-9506e5f33e16" />

#### Running nmap:

--> -sS is a stealth TCP scan (standard security scan)
--> -sV detects service versions

<img width="915" height="533" alt="image" src="https://github.com/user-attachments/assets/ca08ae62-34f4-4615-b525-cbbd534cbfe9" />

### Results from nmap:

-These reulsts depicts how 999 out of 1000 scanned TCP ports were closed, which means there is less area for attackers to come in from.

-Port 22 is open and SSH is running successfully

-Packges are all up to date snd no unexpected services were detected showing the firewall configuration is successful too.

## Access Control Verification:

-Using AppArmor to confirm mandatory access contol (MAC) is enforced:

Below shows that multiple profiles were loaded and operating in enforce mode. This ensures that even if a service is attacked, its access to system resources are restricted.

<img width="923" height="322" alt="image" src="https://github.com/user-attachments/assets/5993377a-c40a-4d6f-8f9e-ad77ff17eb1c" />

## Service Audit justifying running services:

Below shows there are active services running, with main services hightlighted that are enforcing  stronger security systems:

<img width="754" height="1593" alt="image" src="https://github.com/user-attachments/assets/0d86dacc-7038-42f5-bfbf-a1c690489e9a" />




































# Advanced Security Monitoring Infrastructure

This week I will be implementing advanced security controls and develop monitoring capabilities.

### Implementing access control with AppArmor:

AppArmor is a MAC (mandatory access control) system built into Ubunti which controls what files, directories and system resources an application is allowed/ not allowed to access
By connecting to the server from the workstation('Operating Systems') via the SSH,
we can check if AppArmor is enabled with the command line 'sudo aa-status':

<img width="755" height="874" alt="image" src="https://github.com/user-attachments/assets/bdb9ff0d-08fa-4ca4-8cd1-041ad9561584" />

Now that the module has successfully loaed, from here we can review AppArmor entries into the systemd journal, which tracks AppArmor decisions:

To access the journal and AppArmor activities, the command line 'journalctl | grep apparmor' is used:
<img width="926" height="1072" alt="image" src="https://github.com/user-attachments/assets/5b2d6bc0-415f-4981-94fb-ded2e6eeaef9" />


^ Tracking and reporting these entries allows for greater security monitoring. These entries can also be filtered, so that specific events are easy to track/monitor.

## Configuring automatic security updates:

To enable automatic security updates the 'unattended-upgrades' package must be installed and its' configuration will need to be re-run by using the 'dpkg-reconfigure' command to allow automatic installation of security updates.

Below will be evidence of this process:

### Installing unattended-upgrades:

<img width="915" height="376" alt="image" src="https://github.com/user-attachments/assets/f4a02d1d-8a14-4ae9-b89f-745c678815d4" />


### Applying reconfiguring step for automatic updates:

<img width="910" height="641" alt="image" src="https://github.com/user-attachments/assets/d137e1c5-52e0-4eb3-9046-b5a3e31828b9" />

## Configuring fail2ban:

fail2ban monitors repeatedly failed authentication attempts and then blocks the attackers IP address via firewall rules.

### Installing fail2ban:

<img width="921" height="655" alt="image" src="https://github.com/user-attachments/assets/4e14e314-b55f-409e-a3c9-cbaa268ccc05" />



### Evidence of successful installment & that fail2ban is working:

<img width="914" height="382" alt="image" src="https://github.com/user-attachments/assets/70eb7e4d-5146-4c76-b402-e69eff10ab73" />

#### Below is further evidence that fail2ban is activley monitoring SSH logins and is ready to block any potential brute-force attackers:

<img width="739" height="342" alt="image" src="https://github.com/user-attachments/assets/19244fa5-b235-49f5-b0ff-30592934912b" />

## Security baseline verification script

Here I will create a verification script to ensure the minimum security settings are in place, from week 4 and 5. This script will be able to automatically check the system and the specific security configurations written in the script.

### Creating script:

Command 'nano securityscript.sh' was used to create the file on the server. '.sh' was used as the file will need to be executed and contains shell commands:

<img width="895" height="1143" alt="image" src="https://github.com/user-attachments/assets/ff766fc7-2c0d-41a5-a530-00502c7da731" />


### Making script ready to execute:

<img width="899" height="288" alt="image" src="https://github.com/user-attachments/assets/4f3d08de-5f40-4db8-9099-3d3cbf9ed6c8" />


### Executing Script:

<img width="899" height="849" alt="image" src="https://github.com/user-attachments/assets/18fd035c-501f-4124-801c-8c1ce9bd6619" />

## Creating remote monitory script:

<img width="1276" height="1598" alt="image" src="https://github.com/user-attachments/assets/3a95f0c7-58b7-49bd-9944-919afac8a68a" />



### Results of Server Monitoring:

<img width="900" height="1133" alt="image" src="https://github.com/user-attachments/assets/0ced49a5-bde6-4fa4-867b-9c5f730144ce" />































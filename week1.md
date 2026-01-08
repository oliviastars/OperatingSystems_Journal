#Week 1: System Planning and Distribution Selection

**Overview** : 

This week I learnt the fundamentals of Linux servers and virtual machines. I was able to successfully download Ubuntu Server, create my two virtual machines: one as a workstation and another as a headless server. From here I was able to successfully connect the workstation to the server by using the SSH protocol. 

**Distribution Selection Justification:**

I chose to use Ubuntu servers because it is known to work well with beginners, it was recommended in the coursework brief and compared to distro's such as Debian, it is a newer package.

**Workstation Configuration Decision:**

By using Ubuntu Desktop virtual machines, I am able to use Linux tools and experiment on the virtual machine while keeping my personal laptop safe.

**System Architecture Diagram:**

   <img width="1061" height="271" alt="image" src="https://github.com/user-attachments/assets/2f05df5f-0889-4211-8632-ce6ff3e74108" />


**Network Configuration:**

The virtual machine 'Operating Systems' was given two network adapters (1&2), the second network adapter is a 'host-only', which allows it to connect to the headless server I created.

<img width="1890" height="1060" alt="image" src="https://github.com/user-attachments/assets/23a0792b-9b38-4f38-9d83-9c81233bd5f1" />


<img width="1890" height="1012" alt="image" src="https://github.com/user-attachments/assets/773fd44e-6a5f-487c-85c6-585cf5f622fb" />


Now that both the virtual machine and the headless server have the correct network adapters, the next step is to get the ip address of the server using the 'ip addr' command:


<img width="1277" height="1525" alt="image" src="https://github.com/user-attachments/assets/69654c77-23ac-4239-aef3-28b3eeed3a82" />

At the bottom of the image we're able to see that the servers IP address is: 192.168.56.103
From here, I then connected the virtual machine 'Operating Systems' to the headless server by using the SSH protocol and managed to succesfully logged in with the servers password:

<img width="712" height="457" alt="image" src="https://github.com/user-attachments/assets/54159051-d292-450d-9528-c7310bfbb00c" />

From the screenshot above it shows a secure SSH session from the work station to server. This also shows that the server is reachable over a private virtual network and below i will demonstrate how remote commands (taken from assignment brief) are able to be executed in the server via the SSH session:


<img width="884" height="735" alt="image" src="https://github.com/user-attachments/assets/5a9e2416-49b8-4227-a630-d7905eb80cb1" />

<img width="876" height="732" alt="image" src="https://github.com/user-attachments/assets/a13304a3-1994-43ed-80c3-16fcd51beeac" />

As seen above, this week I successfully managed to connect a workstation to a server and I began to further expand my knowlegde of specific command lines.




***Learning Notes:***


SSH --> an encrypted protocol for accessing and mainaging remote systems (such as a server over the internet)

Command line to connect to server: ssh (WorkStationName)@192.168.56.xxx 
^This command line connects the servers 'home address' to the workstation. 

uname - a --> shows the kernel name and the version

free -h --> shows the ram usage and memory management

df -h --> shows the disk usage and filesystem layout 

lsb_release --> shows the linux distribution (Ubuntu)





   


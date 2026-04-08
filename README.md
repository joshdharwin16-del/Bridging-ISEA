# BRG-27-labs  
## Introduction to Server Environments and Architectures  

**Student Name:** Josh Dharwin Letchmanan  
**Kaplan Student ID:** CT0386869  
**Murdoch Student ID:** 35850966  

---

# 📘 Session 1 – Setting Up Linux  

## Basic Linux Navigation  

In this session, I set up an Ubuntu virtual machine using VirtualBox and began working with the Linux command-line interface.

### Commands Used
```bash
pwd
ls
cd ~
mkdir -p isea-lab1
cd ~/isea-lab1
touch notes.txt
ls
ls -l
man ls
Explanation
pwd shows the current directory
ls lists files and folders
cd ~ returns to the home directory
mkdir -p creates a directory
touch creates a file
ls -l shows file permissions
man ls displays command manual

Figure 1: Basic navigation using pwd and ls
<img src="https://github.com/user-attachments/assets/b90f36f2-242f-48fd-b88f-d52285cd7151" width="700"/>

Figure 2: Creating directory and notes.txt file
<img src="https://github.com/user-attachments/assets/4af3bae7-f1f6-40a6-8a4d-3e8031873459" width="700"/>

Figure 3: File permissions using ls -l
<img src="https://github.com/user-attachments/assets/97f9769a-3116-4ea1-bed0-b854736a1e40" width="700"/>

Exploring Linux File Structure
Commands Used
cd /etc
pwd
cd /var
pwd
cd /home
pwd
Explanation
/etc → system configuration
/var → logs and variable data
/home → user directories

Figure 4: Navigating system directories
<img src="https://github.com/user-attachments/assets/896737aa-2f18-40f8-b20b-a8000cf03c3e" width="700"/>

File Permissions
Commands Used
touch test.sh
chmod 755 test.sh
ls -l
Explanation
755 = owner (rwx), group (r-x), others (r-x)

Figure 5: Changing file permissions using chmod
<img src="https://github.com/user-attachments/assets/0075c150-c1e5-476d-8062-2be750fac61f" width="700"/>

Searching in Linux
Commands Used
echo "hello world" > notes.txt
find ~/isea-lab1 -name "test.sh"
grep -r "hello" ~/isea-lab1

Figure 6: Searching file using find and grep
<img src="https://github.com/user-attachments/assets/feb0a0f7-ab7c-431f-a226-b0c5124d7f2b" width="700"/>

Reflection

In this session, I learned how to navigate the Linux file system and use basic commands to manage files and directories. I also explored system directories such as /etc, /var, and /home.

One issue I encountered was using the wrong directory name (isea_lab1 instead of isea-lab1) when running the find command. This resulted in an error, which I fixed by correcting the directory name. This taught me the importance of accuracy when working in Linux.

Overall, this session helped me become more confident using the command line.

☁️ Session 2 – Cloud Services and TCO
SSH and Server Setup
Commands Used
chmod 400 asure9_key.pem
ssh -i asure9_key.pem azureuser@<IP>

Figure 7: SSH connection to remote server
<img src="https://github.com/user-attachments/assets/04bfc19e-2510-4f99-aae4-625a17b49619" width="700"/>

System Update
sudo apt update
sudo apt upgrade -y

Figure 8: System update and upgrade
<img src="https://github.com/user-attachments/assets/74089f74-53f4-4354-90ef-198f46ec2fbc" width="700"/>
<img src="https://github.com/user-attachments/assets/2f2edc5b-6249-4134-b9f2-fc357ddf8af1" width="700"/>

Bash Script
Commands Used
nano script.sh
chmod +x script.sh
./script.sh
Script
#!/bin/bash
echo "Hello from VM"
date
pwd

Figure 9: Script execution output
<img src="https://github.com/user-attachments/assets/f6330ca8-43da-4d34-a548-63f009223e17" width="700"/>
<img src="https://github.com/user-attachments/assets/f161755c-2c34-47ee-8837-37d55c6dc73c" width="700"/>

TCO Analysis

Figure 10: Cloud cost analysis table
<img src="https://github.com/user-attachments/assets/22b41573-1a7e-4dba-91cb-e165092cf535" width="600"/>

Figure 11: On-premise cost analysis table
<img src="https://github.com/user-attachments/assets/e961a327-8611-4661-b2f4-f77b3df8538d" width="600"/>

Figure 12: Cost comparison and break-even analysis
<img src="https://github.com/user-attachments/assets/710eb10e-941e-48d8-b792-ed499eb31ee7" width="600"/>
<img src="https://github.com/user-attachments/assets/aafc178e-b3f4-4aa8-804c-b1556bc33959" width="600"/>

Reflection

In this session, I learned how to connect to a cloud server using SSH and perform system updates. I also created and executed a Bash script, which helped me understand automation.

From the TCO analysis, I learned that cloud infrastructure is more cost-effective over time compared to on-premise solutions. Cloud services reduce upfront costs and provide flexibility, while on-premise solutions require higher capital investment and maintenance.

🌐 Session 3 – Networking, Web Server, Automation
DNS Testing
nslookup google.com

Figure 13: DNS lookup using nslookup
<img src="https://github.com/user-attachments/assets/5ba77a48-37f1-4843-8bfd-6f1cd4861f6e" width="700"/>

Web Server Setup
sudo apt install nginx -y
sudo systemctl start nginx
curl http://localhost

Figure 14: Nginx installation
<img src="https://github.com/user-attachments/assets/4b3681b3-1fc6-46aa-9ab0-0ff3e2e376ba" width="700"/>

Figure 15: Web server test using curl
<img src="https://github.com/user-attachments/assets/854acdda-b279-4e70-b614-a856c759bc4c" width="700"/>

Apache Conflict (Troubleshooting)
sudo lsof -i :80
sudo systemctl stop apache2
sudo systemctl disable apache2

Figure 16: Apache using port 80 (issue)
<img src="https://github.com/user-attachments/assets/991f70da-aeac-4de6-a733-b882ad0d7a2a" width="700"/>
<img src="https://github.com/user-attachments/assets/030570c8-235c-4ed1-81a4-30d7403e9ea5" width="700"/>

Automation Script
nano update.sh
chmod +x update.sh
sudo ./update.sh
cat /var/log/task.log

Figure 17: Script log output
<img src="https://github.com/user-attachments/assets/5baf5894-d111-43a1-ba3c-9933ec9da6a0" width="700"/>

Cron Job
Issue
crontab: command not found
Fix
sudo apt install cron
crontab -e
crontab -l

Figure 18: Cron not found error
<img src="https://github.com/user-attachments/assets/4262cd61-9ce7-42bf-b153-7d7e0a337fb7" width="700"/>

Figure 19: Cron job configured
<img src="https://github.com/user-attachments/assets/53e05a70-591b-4d06-85ae-fa22de569363" width="700"/>
<img src="https://github.com/user-attachments/assets/58838347-5218-44cc-9ecb-0cf7ffe6f556" width="700"/>

Reflection

In this session, I worked with networking and server configuration. I used nslookup to test DNS resolution and confirmed that domain names resolve correctly.

While setting up Nginx, I encountered a port conflict with Apache. I resolved this by stopping Apache, which allowed Nginx to run successfully.

I also created an automation script and scheduled it using cron. Initially, cron was not installed, but I fixed this by installing the package. This experience improved my troubleshooting and automation skills.

🗄️ Session 4 – MySQL Server
sudo apt install mysql-server -y
sudo systemctl status mysql

Figure 20: MySQL service running
<img src="https://github.com/user-attachments/assets/19271fa0-aea3-4a72-b843-ede8bc9c9c07" width="700"/>
<img src="https://github.com/user-attachments/assets/b131553c-0f65-470b-9b30-b20543461620" width="700"/>

SQL Commands
CREATE DATABASE testdb;
USE testdb;

CREATE TABLE Students (
    id INT AUTO_INCREMENT,
    name VARCHAR(50),
    PRIMARY KEY(id)
);

INSERT INTO Students (name) VALUES ('Josh');
SELECT * FROM Students;
Reflection

In this session, I installed and configured MySQL. I created a database, table, and inserted data successfully.

I encountered an error due to incorrect table naming, which I resolved by correcting the case sensitivity. This helped me understand how SQL syntax and naming conventions work.

🎯 Final Overall Reflection

Throughout this module, I gained hands-on experience in Linux system administration, cloud computing, networking, and server management.

I learned how to:

Use Linux commands and manage files
Configure and troubleshoot services
Deploy a web server
Automate tasks using scripts and cron
Install and manage MySQL
Analyse cloud vs on-premise costs

I also encountered several issues such as incorrect commands, missing packages, port conflicts, and SQL errors. By resolving these issues, I improved my problem-solving skills and confidence.

Overall, this module provided practical experience relevant to real-world IT environments and strengthened my understanding of server systems.

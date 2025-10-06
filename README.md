# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system
## OUTPUT:
<img width="762" height="342" alt="exp 5 1st" src="https://github.com/user-attachments/assets/0e0baef8-6ef4-49b8-b591-a0574689d0d0" />

invoke msfconsole:
<img width="922" height="760" alt="exp 5 2nd" src="https://github.com/user-attachments/assets/d25ef13a-bfea-4951-a71c-02a6bec57349" />

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

<img width="1027" height="738" alt="exp 5 3rd" src="https://github.com/user-attachments/assets/856ae77d-ab90-4844-a83c-63df62356fb9" />
## PORT SCANNING:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

<img width="1031" height="67" alt="exp 5 4th" src="https://github.com/user-attachments/assets/5f296ef1-ce4e-4efa-b460-d499b040b5f9" />

## OUTPUT:
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

<img width="647" height="302" alt="exp 5 5th" src="https://github.com/user-attachments/assets/d52f7013-ae62-4baa-9b83-116379091c71" />

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

<img width="1032" height="790" alt="exp 5 6th" src="https://github.com/user-attachments/assets/42bb9b76-b387-4537-a181-9c79214cb211" />

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address> Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

<img width="1032" height="576" alt="exp 5 7th" src="https://github.com/user-attachments/assets/060d4406-c337-4b6d-9d32-23a2bf40a4bc" />

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

<img width="1032" height="140" alt="exp 5 8th" src="https://github.com/user-attachments/assets/972b8b63-5c87-4786-9029-2642117e721f" />

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

<img width="1033" height="495" alt="exp 5 9th" src="https://github.com/user-attachments/assets/21fcbba8-50d5-46b8-9cfd-60fb9cb8dad9" />

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

<img width="1027" height="217" alt="exp 5 10th" src="https://github.com/user-attachments/assets/a04b0fce-add5-4a01-ab71-1478eba9e3c0" />

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

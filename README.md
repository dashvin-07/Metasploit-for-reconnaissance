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
![image](https://github.com/user-attachments/assets/a5aaa4bd-dd73-4bb3-9bb7-8878432497bb)
POSTGRESQL
msfdb :

![435354326-8586ca9f-3770-4bd1-a7fa-d0b543046e2c](https://github.com/user-attachments/assets/5b5d242d-4426-43fe-b652-40893fa2ebf3)


## OUTPUT:
![image](https://github.com/user-attachments/assets/a0810903-5d52-4406-ae8c-a03bba905591)

## OUTPUT:
![image](https://github.com/user-attachments/assets/0b13a54c-3149-4192-bfe4-263442d809b8)
## OUTPUT:
![image](https://github.com/user-attachments/assets/ba351dca-6045-42a4-b0f7-d6b598250f5a)

## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/user-attachments/assets/c6a46e4c-98fe-4be8-9b9d-e3bf2b549717)

## Step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![image](https://github.com/user-attachments/assets/5832a222-8477-46c3-a65c-2ac3b54fc6d7)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![image](https://github.com/user-attachments/assets/37433b95-302b-4313-8b2f-5230b855ef1b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
## OUTPUT:
![image](https://github.com/user-attachments/assets/6f372ef8-787f-4adc-a5e6-39f573c7f842)

The info command provides information regarding a module or platform,
## OUTPUT:
![image](https://github.com/user-attachments/assets/41a6b961-0e06-4a61-973f-a7152c17f45a)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:
![image](https://github.com/user-attachments/assets/582a1bc5-1452-4f31-b828-e8aa6da0b372)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
## OUTPUT:
![image](https://github.com/user-attachments/assets/606ed94d-b2d8-4c10-a72e-4016d7666a6d)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
## OUTPUT:
![image](https://github.com/user-attachments/assets/d6ea943a-fcbe-4496-834e-2937361cb913)

Use the set rhosts command to set the parameter and run the module, as follows:
## OUTPUT:
![image](https://github.com/user-attachments/assets/2d929cec-c949-4b37-9b67-dc546abeb1ca)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT:
![image](https://github.com/user-attachments/assets/dde18013-cc3d-41d2-8f4d-d36ad0e107c0)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
## OUTPUT:
![image](https://github.com/user-attachments/assets/c8935e82-5471-4af5-b3c8-2f10118009ee)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

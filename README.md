![image](https://github.com/user-attachments/assets/d570bc8b-3e09-45e7-8c6a-f1b21f12359f)# Metasploit-for-reconnaissance
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

![image](https://github.com/user-attachments/assets/4af30c44-e2a1-47ad-a8b3-0f00572227a4)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

- systemctl start postgresql
- msfdb init
Invoke msfconsole

## OUTPUT:
![image](https://github.com/user-attachments/assets/c76b8203-ec88-4d4a-82a7-3d6821034ea7)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/user-attachments/assets/05d203e7-48e1-4b14-8395-8fd0773b4cab)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/user-attachments/assets/9297d461-d795-4d6f-b51a-91c0e9fd2480)


use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24


## OUTPUT:
![image](https://github.com/user-attachments/assets/b731f43e-0649-4565-8370-832719b9734b)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /user/share /metasploit-framework/modules/auxiliary kali > ls -l



## OUTPUT:

![image](https://github.com/user-attachments/assets/8a33f203-a018-4b42-9f40-946f69443cde)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit



## OUTPUT:

![image](https://github.com/user-attachments/assets/24b55740-4e4f-4319-91a3-ef04245e40a7)

The info command provides information regarding a module or platform, Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

- systemctl start postgresql
- msfdb init

### MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![image](https://github.com/user-attachments/assets/00ea6c33-0bf0-4995-b0cf-cb687937cfc0)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql image

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/user-attachments/assets/f79d4f03-cfee-49ea-87b9-fd2261dac909)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/user-attachments/assets/783031cc-fd37-4423-b68f-edc25a393e32)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/user-attachments/assets/5136bb9b-ed28-49d2-bcc3-78f34376e2fd)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

set BLANK_PASSWORDS true

![image](https://github.com/user-attachments/assets/532a762d-253c-4c9d-b818-7a6a382a1117)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

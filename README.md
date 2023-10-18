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

![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/4e4616c4-adc0-434f-94d4-97816e857e3e)

Invoke msfconsole:

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/5c84368c-1641-4af4-ba22-35885063c068)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/13ad74cf-54fe-4ab9-937c-3c6aee640c40)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/c77e91a0-9271-40c5-ba4b-cbaf67a458ed)
eht 5 4
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/d5d33c67-11bb-40ea-81d2-bb3898eedc0f)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/3641763c-5181-4d06-9bd5-80d9b632d2bb)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:

![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/b21a4053-e2b7-4f60-8895-ebeb206a4f96)
The info command provides information regarding a module or platform,

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/ff7b97b0-2537-4d21-950c-9201833b9263)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/c8768d30-9ce2-4e8b-9afe-805a4d3743f3)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/860a47b8-8a16-4b2a-9a75-8c37c844ff9f)


use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/3b322d7c-a650-4cd6-ab2d-222dfd91279b)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/bc1fc1ea-50fe-444f-8be9-75b9e3dba187)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:
![image](https://github.com/Shobika187/Metasploit-for-reconnaissance/assets/94508142/03660bd5-d04d-496e-9519-7f402fb23483)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

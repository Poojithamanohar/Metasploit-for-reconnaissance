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

## OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/c69684e6-1d11-4895-8bb4-9a93d1873a7f)

Invoke msfconsole:


## OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/ac8e3880-ccbe-40f7-b7f0-b0a159f5333f)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/4b207e38-6631-47f8-afb8-f7051d1109e7)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/0b4dff53-c7f1-44d3-a6ee-8ca5c72c55cf)

Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/f4fc23f3-0cb8-4e39-ae3e-51670c0d9755)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/954348e3-5e90-4e7b-9917-2f99a30523a8)

![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/1e1c3e56-b09a-40b2-b1e5-fe6dc1c32fe1)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/808aba62-dfcc-441b-bdfe-c589ede3fb2c)

The info command provides information regarding a module or platform
OUTPUT:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/2ee16f38-853f-4c63-9ff0-16747ce4fd98)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/701fa1e7-f5d2-472c-a83b-b9d07dd18226)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/566dc27b-c0ea-4878-a3e3-e1654bc8506b)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/35a9f792-6dc3-40cf-b9be-3c7873126b1e)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/d6a134e0-b656-47e6-837f-ffe399afad5c)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/d3c1edfc-360f-4320-82c7-93a413b641fa)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/Poojithamanohar/Metasploit-for-reconnaissance/assets/119423592/3bfbf68b-2ece-4d14-851b-92ecce8e10af)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

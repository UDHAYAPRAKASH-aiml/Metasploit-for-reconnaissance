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
![Screenshot 2025-04-21 105202](https://github.com/user-attachments/assets/86ba51a0-e584-424d-9464-f62ead367e28)
This command displays the network configuration of the Kali Linux machine.
Network interface name (eth0, wlan0, etc.)
IPv4 address
MAC address
Broadcast address
The IP address identified here is the attacker machine’s address, which is required for scanning and communication with target systems.

## Invoke msfconsole

## OUTPUT:
![Screenshot 2025-04-21 105320](https://github.com/user-attachments/assets/63e7e164-a669-48de-81a3-52c016e9cedf)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
This command launches the Metasploit Framework console.
Metasploit banner
Framework version
Database connection status
![Screenshot 2025-04-21 105356](https://github.com/user-attachments/assets/079b649b-b9c2-434c-ae97-baba1ffe83fc)
The help command displays all available commands in the Metasploit Framework. It helps users understand how to use msfconsole by listing commands related to modules, scanning, database operations, sessions, and exploits.
### PORT SCANNING
## msf > nmap -sT 192.168.1.100/24 -p1-1000
![Screenshot 2025-04-21 105637](https://github.com/user-attachments/assets/b7f3d688-974f-481d-9186-a331b1628cbe)
This command performs a TCP Connect Scan on all hosts in the subnet and scans ports 1 to 1000.
Parameters
-sT → TCP connect scan
192.168.1.100/24 → scans all hosts in the subnet
-p1-1000 → scans ports from 1 to 1000
## msf > db_nmap 192.168.1.100/24
![image](https://github.com/user-attachments/assets/a1d3fa3c-3e52-439b-9442-33705ae44e73)
db_nmap performs an Nmap scan and stores the results directly into the Metasploit database.
Output Shows
Detected hosts
Open ports
Operating system details
Services running on targets

This allows Metasploit modules to reuse scan data later.
### kali ls -l

![Screenshot 2025-04-21 105950](https://github.com/user-attachments/assets/6c2f1baa-2e1f-4857-b983-95488fafea28)
This command lists files and directories in long format.
Output Includes
File permissions
Owner name
Group name
File size
Date and time
File name
This helps understand Linux file structures and permissions.
### search

![Screenshot 2025-04-21 110118](https://github.com/user-attachments/assets/3bf64e21-323d-410d-adcb-d037146df215)
The search command looks for modules related to a keyword.
Output Shows
Module names
Module types
Disclosure dates
Ranks
Descriptions
### info
![Screenshot 2025-04-21 110222](https://github.com/user-attachments/assets/2e121d08-57c9-4894-971f-bf6800f4cdc7)
Explanation
The info command provides detailed information about a module.
Output Includes
Module description
Author
References
Required options
Targets supported

This helps understand how the module works before using it.
### MYSQL ENUMERATION
## db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/user-attachments/assets/9d2428aa-bba5-4783-b322-a658552b5b4e)
This command scans MySQL service running on port 3306.
Parameters
-sV → Service version detection
-sC → Runs default NSE scripts
-p 3306 → Scans MySQL port
## search 
![image](https://github.com/user-attachments/assets/d5e12707-9f73-4422-9a24-7175dc37dc15)
The search command looks for modules related to a keyword.

Output Shows
Module names
Module types
Disclosure dates
Ranks
Descriptions
## use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/user-attachments/assets/0b58f28c-89b4-40ee-8a82-f5fb61fe73f9)
This command loads the MySQL version scanning module in Metasploit.
The module is used to identify the MySQL service version running on the target system.
After executing the command, the Metasploit prompt changes to:
## Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/user-attachments/assets/9f910374-df42-4001-a552-fccaa4510d7b)
This command scans MySQL service running on port 3306.
Parameters
-sV → Service version detection
-sC → Runs default NSE scripts
-p 3306 → Scans MySQL port
## After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/user-attachments/assets/17c637ee-f95f-4000-93d5-d0c61831a5b6)
This searches Metasploit for MySQL-related modules.
Output Shows
Modules for:
Version detection
Login scanning
Enumeration
Brute force attacks

This helps select appropriate modules for reconnaissance.
## /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt

![image](https://github.com/user-attachments/assets/790829a8-ea62-418e-a0e0-a044551c9d0a)
Explanation
set RHOSTS specifies the target machine IP address.
run executes the module.
Output Shows
Successful connection
MySQL server version
Service details
This confirms that the MySQL service is reachable.
![image](https://github.com/user-attachments/assets/35500dc6-51f0-4ad4-bbd1-401517856bcb)

This executes the MySQL login brute force attack.

Output Shows
Username/password attempts
Successful logins if credentials are weak
Authentication results

This helps identify weak passwords in the target database server.





## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

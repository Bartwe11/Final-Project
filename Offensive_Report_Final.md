# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services


Nmap scan results for each machine reveal the below services and OS details:

$ nmap -sV 192.168.1.110
  
![Nmap](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/NMap_Target1.jpg)

This scan identifies the services below as potential points of entry:
- Target 1
  - Open SSH on Port 22
  - HTTP on open port 80

The following vulnerabilities were identified on each target:
- Target 1
  - Sensitive Data Exposure
  - Open SSH
  - Wordpress
  - Weak Password
  - MYSql Access

### Exploitation

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`: Flag1: b9bbcb33ellb80be759c4e844862482d
    - **Exploit Used**
      - Sensitive Data Exposure
      - Searched through the source code on the website to find the Flag
![Flag1](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/Flag1.jpg)
  - `flag2.txt`: Flag2: fc3fd58dcdad9ab23faca6e9a36e581c
    - **Eploit Used**
      - Open SSH port 22
      - ssh michael@192.168.1.110
    - **Exploit Used**
      - Wordpress
      - wpscan --url http://192.168.1.110/wordpress --enumerate u
    - **Exploit Used**
      - Weak Password
      - easy to guess password
![WP_and_SSH](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/Michael_WPscan_Shell.jpg)
![Flag2](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/Flag2.jpg)
  - `flag3.txt`: Flag3:afc01ab56b50591e7dccf93122770cd2
    - **Exploit Used**
      - MYSql Access
      - select * from wp_posts;
![MYSql](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/MySql.jpg)
![Flag3](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/Flag3.jpg)
  - `flag4.txt`: Flag4:715dea6c055b9fe3337544932f2941ce
    - **Exploit Used**
      - MYSql Access
      - select * from wp_users;
![Flag4](https://github.com/Bartwe11/Final-Project/blob/c55c445693bbf8ee4e34b8c723d5f5364328d1fc/Images/flag4.jpg)

# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services


Nmap scan results for each machine reveal the below services and OS details:

$ nmap -sV 192.168.1.110
  
(https://github.com/Bartwe11/Final-Project/blob/a80c7f89f082d11b81b880b74655b7db743719a3/Images/Flag1.jpg)

This scan identifies the services below as potential points of entry:
- Target 1
  - Open SSH on Port 22
  - HTTP on open port 80

_TODO: Fill out the list below. Include severity, and CVE numbers, if possible._

The following vulnerabilities were identified on each target:
- Target 1
  - Sensitive Data Exposure
  - Open SSH
  - Wordpress
  - Weak Password
  - MYSql Access

_TODO: Include vulnerability scan results to prove the identified vulnerabilities._

### Exploitation
_TODO: Fill out the details below. Include screenshots where possible._

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`: Flag1: b9bbcb33ellb80be759c4e844862482d
    - **Exploit Used**
      - Sensitive Data Exposure
      - Searched through the source code on the website to find the Flag
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
  - `flag3.txt`: Flag3:afc01ab56b50591e7dccf93122770cd2
    - **Exploit Used**
      - MYSql Access
      - select * from wp_posts;
  - `flag4.txt`: Flag4:715dea6c055b9fe3337544932f2941ce
    - **Exploit Used**
      - MYSql Access
      - select * from wp_users;

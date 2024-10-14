# Vulnerability Assessment and Penetration Testing (VAPT) Project

## Overview

This project involves conducting a Vulnerability Assessment and Penetration Testing (VAPT) on the Metasploitable 2 machine using Kali Linux. The goal was to identify potential security vulnerabilities and suggest recommendations for improving security.

## Tools Used

**Kali Linux**: A Debian-based Linux distribution for penetration testing.
**Nmap**: A network scanning tool to discover hosts and services.

## Project Setup

**Target System**: Metasploitable 2
**Testing Platform**: Kali Linux in Oracle VirtualBox

## Key Findings

The Nmap scan revealed several open ports with associated services that may have vulnerabilities. Here is a summary of the open ports discovered:

| Port    | State  | Service         | Version/Details                                | Vulnerability or Note                            |
|---------|--------|-----------------|------------------------------------------------|--------------------------------------------------|
| 21/tcp  | open   | ftp             | vsftpd 2.3.4                                   | Known backdoor vulnerability (CVE-2011-2523)     |
| 22/tcp  | open   | ssh             | OpenSSH 4.7p1 Debian 8ubuntu1                   | No specific vulnerabilities identified           |
| 23/tcp  | open   | telnet          | Linux telnetd                                  | Insecure service, transmits data in plaintext    |
| 25/tcp  | open   | smtp            | Postfix smtpd                                  | SSL POODLE and Weak DH Key Exchange vulnerabilities |
| 80/tcp  | open   | http            | Apache httpd 2.2.8                             | Potential Slowloris DoS and SQL Injection        |
| 139/tcp | open   | netbios-ssn     | Samba smbd 3.X - 4.X                           | Potential for SMB vulnerabilities                |
| 445/tcp | open   | netbios-ssn     | Samba smbd 3.X - 4.X                           | Potential for SMB vulnerabilities                |
| 3306/tcp| open   | mysql           | MySQL 5.0.51a-3ubuntu5                         | Default MySQL configuration may be weak         |
| 8180/tcp| open   | http            | Apache Tomcat/Coyote JSP engine 1.1            | Potential misconfigurations or vulnerabilities  |

For a detailed analysis of each port and the identified vulnerabilities, refer to the uploaded document.


## Commands Used

Here are the key commands executed during the assessment:

1. **Ping the target to check connectivity:**
   ```
   ping 192.168.56.5 ( Metasploitable 2 In VM)
   ```
2. **Perform a SYN scan with service version detection:**
   ```   
   sudo nmap -sS -sV -O 192.168.56.5
   ```
3. **Running a Vulnerability Scan with Nmap:**
   ```
   sudo nmap --script vuln 192.168.56.5
   ```

## Recommendations
Recommendations for improving security based on the findings are included in the full report.


## Documentation
For a comprehensive overview of the assessment, including detailed findings and recommendations, please refer to the uploaded document file.

## Example Image
![image](https://github.com/user-attachments/assets/999cb045-2b51-4021-9b5d-af0d85e4737a)

   
   

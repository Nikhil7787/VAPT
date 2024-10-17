# Vulnerability Assessment and Penetration Testing (VAPT) Project

## Overview

In this project, I conducted a Vulnerability Assessment and Penetration Testing (VAPT) on the Metasploitable 2 machine using Kali Linux. The main goal was to identify potential security vulnerabilities and suggest improvements for enhancing the overall security of the system.

## Tools Used

- **Kali Linux**: I utilized this Debian-based Linux distribution designed specifically for penetration testing.
- **Nmap**: This powerful network scanning tool helped me discover hosts and services on the Metasploitable 2 machine.
- **Wireshark**: I used this network protocol analyzer to capture and analyze network traffic during the assessment.

## Project Setup

- **Target System**: Metasploitable 2
- **Testing Platform**: Kali Linux running in Oracle VirtualBox

## Key Findings

During my Nmap scan, I uncovered several open ports and their associated services that could pose vulnerabilities. Here’s a summary of what I found:

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

### Wireshark Analysis

I used Wireshark to capture and analyze the network traffic between my Kali Linux and Metasploitable 2 machines. Here’s how I went about it:

#### Steps to Use Wireshark

1. **Started Wireshark**: I opened Wireshark on my Kali Linux machine.
2. **Selected the Network Interface**: I chose the `eth0` interface to capture traffic effectively.
3. **Started Capturing Traffic**: I clicked on the interface to begin capturing traffic, ensuring that I saw "Live capture in progress" at the bottom of the window.
4. **Performed Actions to Generate Traffic**: While capturing, I ran the Nmap scan and executed other relevant commands on the Metasploitable 2 machine to generate network traffic.
5. **Stopped Capturing**: After completing the scans, I stopped the capture in Wireshark.
6. **Analyzed Captured Packets**: I utilized Wireshark’s filtering tools to examine the packets, focusing on protocols, potential attacks, and unusual traffic.
7. **Saved the Capture File**: Finally, I saved the captured traffic as a `.pcap` file for further analysis and reporting.


## Commands Used for Nmap

Here are the key commands executed during the assessment for Nmap:

1. **Ping the target to check connectivity:**
   ```
   ping 192.168.56.5 (Metasploitable 2 In VM)
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

Nmap
![image](https://github.com/user-attachments/assets/999cb045-2b51-4021-9b5d-af0d85e4737a)

Wireshark
![image](https://github.com/user-attachments/assets/fac7948d-7dd6-493f-a8a5-280927e4cca3)


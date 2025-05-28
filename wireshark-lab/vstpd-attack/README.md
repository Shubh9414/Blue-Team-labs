# VSFTPD 2.3.4 Attack Analysis (Wireshark)

This project involves analyzing malicious FTP behavior caused by a known vulnerability in **vsftpd version 2.3.4** using **Wireshark**. The goal is to detect the reverse shell activity triggered after a specially crafted FTP login.

## Objective

Analyze the traffic generated during the exploitation of the backdoored `vsftpd` service and identify:
- The suspicious login pattern
- The reverse shell connection
- The attacker’s interaction with the shell

## Lab Setup

| Component     | Details                          |
|---------------|----------------------------------|
| Attacker VM   | Kali Linux (Metasploit used)     |
| Victim VM     | Metasploitable 2                 |
| Tool Used     | Wireshark                        |
| Network Type  | Host-Only/Bridged                |

## Attack Summary

- The attacker connects to the victim's FTP server.
- A crafted username containing `:)` is used to trigger the backdoor.
- A reverse shell is opened on TCP port **6200**.
- The attacker gains remote access to the victim system.

## Screenshots

| Step | Description                     | Screenshot                                    |
|------|---------------------------------|-----------------------------------------------|
| 1    | Port Scan                          | ![nmap-vsftpd-scan](https://github.com/user-attachments/assets/d32ac994-0a16-4729-97a0-c5c0bfab4d28)          |
| 2    | Exploiting vsftpd using metasploit | ![msf-vsftpd-exploit-shell](https://github.com/user-attachments/assets/fa82b0c8-8e59-4cfb-8a49-5dd4ddbf6f43)            |
| 3    | Attacker interaction via stream |                    (screenshots/)             |

## Key Wireshark Filters Used

ftp
tcp.port == 6200
ip.addr == <192.168.56.101>
tcp.stream eq <6>

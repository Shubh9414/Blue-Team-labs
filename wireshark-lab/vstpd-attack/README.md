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
| 1    | FTP login with backdoor trigger | ![FTP Login](screenshots/ftp-login.png)       |
| 2    | Reverse shell on port 6200      | ![Shell Port](screenshots/tcp-6200-shell.png) |
| 3    | Attacker interaction via stream | ![TCP Stream](screenshots/stream-output.png)  |

## Key Wireshark Filters Used

```wireshark
ftp
tcp.port == 6200
ip.addr == <192.168.56.101>
tcp.stream eq <stream_number>

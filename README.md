# Blue Team Labs

Welcome to the **Blue Team Labs** repository! This project is a collection of hands-on exercises and investigations designed to sharpen my skills in **Defensive Cybersecurity (Blue Teaming)** using industry-standard tools like **Splunk**, **Wireshark**, **Nmap**, and **TCPDump**.

Each folder in this repository represents a lab or real-world inspired investigation using logs, packets, or command-line tools to detect and understand malicious activity.

## Repository Structure

```bash

blue-team-labs/
├── Nmap-Basics               : Nmap basic command execution.
├── Splunk-Lab                
│ ├── Apache-Log-Lab          : Detected suspicious user-agent strings and common attack patterns.
│ ├── DNS-log-Analysis        : Monitored DNS queries for tunneling and data exfiltration patterns.
│ ├── SSH-BruteForce          : Detected brute-force attempts using Splunk SPL and IP extraction via `rex`.
│ ├── Windows-Event-4625      : Parsed Windows failed login events (Event ID 4625).
│ └── README.md
├── wireshark-lab
│ ├── HTTP-Analysis           : Analyzed HTTP traffic in PCAP files.
│ ├── tcp-dump-ftp-analysis   : Captured and filtered FTP traffic using Tcpdump.
│ ├── vsftpd-attack-lab       : Investigated a known backdoor in vsftpd 2.3.4 using PCAP.
│ └── README.md
└── README.md 
```
## Completed Labs

| Tool        | Lab Name            | Description                                     |
|-------------|---------------------|-------------------------------------------------|
| Splunk      | Apache Logs         | Detects suspicious web access patterns          |
| Splunk      | SSH Brute Force     | Identifies multiple failed login attempts       |
| Splunk      | DNS Logs            | Analyzes suspicious domain queries              |
| Splunk      | Windows Event Logs  | Analyze windows logs for failed logins          |

## Tools Used

- **Splunk**: For centralized log analysis and dashboards.
- **Wireshark**: To inspect packet captures and spot anomalies.
- **Nmap**: For scanning, reconnaissance, and enumeration.
- **TCPDump**: For lightweight command-line packet analysis.

## Status

This repository is actively maintained as part of my personal blue team learning.  
I’ll continue to update it as I complete more practical labs and investigations.

## Connect

Feel free to check out the labs and suggest improvements.  
Want to collaborate, offer feedback, or see how I did something? Reach out!

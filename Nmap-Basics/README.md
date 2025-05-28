# Nmap Basics

This section covers the basic usage of **Nmap**, a powerful network scanning tool used in cybersecurity for discovering hosts, services, and vulnerabilities on a network.

## What is Nmap?

**Nmap** is an open-source tool that allows users to:
- Discover live hosts on a network
- Identify open ports and running services
- Perform OS detection and version detection
- Enumerate services and perform scriptable vulnerability scanning

## Use Cases in Blue Team

- Monitor internal network for unauthorized hosts
- Detect exposed services (e.g., open SSH or HTTP)
- Track changes in network configuration
- Audit systems before patching

## Common Nmap Commands

| Command                         | Description                                      |
|---------------------------------|--------------------------------------------------|
| `nmap <target>`                 | Basic scan (host discovery and port scan)        |
| `nmap -sV <target>`             | Service and version detection                    |
| `nmap -O <target>`              | OS detection (needs 1 open and 1 closed port)    |
| `nmap -A <target>`              | Aggressive scan                                  |
| `nmap -p 80,443 <target>`       | Scan specific ports                              |
| `nmap -T4 <target>`             | Speed up scan (timing template)                  |
| `nmap -sS <target>`             | Stealth SYN scan                                 |
| `nmap -sn <subnet>`             | Ping sweep (host discovery)                      |
| `nmap -oN output.txt <target>`  | Save output to a file                            |
| `nmap -oX output.xml <target>`  | Save file in XML format                          |

## Sample Output

> See the `screenshots/` folder for actual output examples of the scans.

## Notes

- OS detection may fail if the target has all ports closed or filtered.
- Use `sudo` for deeper scans requiring raw packet privileges.
- Scans may be detected as intrusive by security appliances so us it responsibly.


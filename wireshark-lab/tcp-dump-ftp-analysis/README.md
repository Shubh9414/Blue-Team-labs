# Tcpdump FTP Traffic Analysis

## Objective:

To capture and analyze FTP traffic between two machines using tcpdump and inspect it in Wireshark, showcasing how credentials and commands are transmitted in plaintext.

## Tools Used:

 - tcpdump – for capturing network packets

 - Wireshark – for in-depth traffic analysis

 - Kali Linux – as the attacker/analyst system

 - Metasploitable 2 – as the vulnerable FTP server

## Lab Setup & Execution

1. Identify Target IP On Metasploitable (ip a) and On Kali ping (ip of metaasploit)

2. Start Packet Capture on Kali: sudo tcpdump -i eth0 host <Target-IP> -w ftp_traffic.pcap

 - -i eth0 = interface to listen on

 - host <Target-IP> = filter only target host

 - -w ftp_traffic.pcap = write output to file

3. Initiate FTP Session from Kali: ftp <metasploitable ip in my case 192.168.*.*>

 - Use credentials:

   - Username: anonymous

   - Password: anything

Run a few basic FTP commands like: ls, pwd, bye

4. Stop tcpdump Capture

Use Ctrl+C on Kali to stop tcpdump. The .pcap file will be saved in your working directory.

5. Analyze in Wireshark: wireshark ftp_traffic.pcap

 - Use filters like:

   - ftp

   - tcp.port == 21

   - tcp.stream eq 0

 - What to look for:

   - FTP USER and PASS commands

   - File listings

   - Login credentials in plain text

## Screenshots

 - tcpdump capture in terminal

 - FTP session on terminal

 - Wireshark showing:

   - login credentials

   - FTP control commands

   - TCP stream view

## Learning Outcomes

 - Practice using tcpdump with host-based filtering and file output

 - Understand how insecure protocols expose credentials

 - Learn to inspect .pcap files in Wireshark for forensic and security analysis

## Folder Contents

 - ftp_traffic.pcap – captured file

 - Screenshots

 - This README.md

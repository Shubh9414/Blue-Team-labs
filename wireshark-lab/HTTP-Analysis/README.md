# HTTP Traffic Analysis using Wireshark

## Description

This lab demonstrates how to analyze HTTP traffic using Wireshark. The captured `.pcapng` file contains HTTP communication between a client and a server. The goal is to extract meaningful information such as HTTP requests, responses, payloads, and identify any potentially suspicious activity.

## Tools Used

- Wireshark
- Kali(attacker)
- metasploitable2(victim)

## Objectives

- Apply display filters to isolate HTTP traffic.
- Analyze HTTP request and response headers.
- Inspect HTTP payload content.
- Identify anomalies or suspicious behavior.

## Files Included

| File Name                    | Description                                      |
|------------------------------|--------------------------------------------------|
| `HTTP-packet-analysis.pcapng`| PCAP file with captured HTTP traffic             |
| `HTTP-Get-Request.png`       | Screenshot of filtered HTTP GET request          |
| `HTTP-packet-details.png`    | Screenshot showing detailed packet structure     |
| `HTTP-payload.png`           | HTTP payload (possibly containing credentials)   |
| `HTTP-filter.png`            | Applied Wireshark display filter (`http`)        |

## Steps Performed

1. **Loaded the PCAPNG file** in Wireshark.
2. Applied display filter: http
3. Identified HTTP GET requests and followed TCP streams.
4. Inspected headers and body content to find potential data leakage.
5. Took screenshots of relevant packets and payloads.

## Observations

- Found plaintext HTTP traffic including a possible login attempt.
- Noted that sensitive data was not encrypted.
- Demonstrated risks of using unsecured protocols like HTTP.

## Learning Outcome

This lab reinforces how attackers can intercept sensitive information in plaintext if HTTPS is not enforced, and how defenders can use Wireshark to detect such risks quickly during forensic analysis.

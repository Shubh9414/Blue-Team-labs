# Apache Log Analysis
This repository contains hands-on Splunk log analysis projects focusing on log ingestion, visualization, and threat detection — especially relevant for Blue Team cybersecurity learning.

## Project 1: 
Apache Logs

## Objective: 
Analyzed Apache HTTP server logs using Splunk, extract meaningful insights like top IP addresses, most requested resources, and HTTP status distribution, and visualize the data using a custom dashboard.

## Tools Used: 
Splunk Enterprise (local installation), Apache access logs (`apache_logs.log`)

## Steps Performed

### 1. Log Upload:
- Uploaded `apache_logs.log` into Splunk via GUI

### 2. SPL Queries Executed:

- Top 10 IP Addresses: index=test_logs | stats count by clientip | sort -count | head 10

- Most Requested URLs: index=test_logs | stats count by uri_path | sort -count | head 10

- HTTP Status Code Distribution: index=test_logs | stats count by status | sort -count

### 3. Dashboard Creation:

- Created a dashboard named Apache Log Insights with Top 10 IPs, Top requested URLs, HTTP status code distribution chart

### 4. Key Learnings:
- Ingesting custom log files in Splunk

- Writing and interpreting basic SPL queries

- Creating dashboards for log visualization

- Understanding web traffic through log forensics

This repository contains hands-on Splunk log analysis projects focusing on log ingestion, visualization, and threat detection — especially relevant for Blue Team cybersecurity learning.

Project 1: Apache Logs

Objective: Analyzed Apache HTTP server logs using Splunk, extract meaningful insights like top IP addresses, most requested resources, and HTTP status distribution, and visualize the data using a custom dashboard.

Tools Used: Splunk Enterprise (local installation), Apache access logs (`apache_logs.log`)

Steps Performed

1. Log Upload:
- Uploaded `apache_logs.log` into Splunk via GUI

2. SPL Queries Executed:

🔹 Top 10 IP Addresses

index=test_logs 
| stats count by clientip 
| sort -count 
| head 10

🔹 Most Requested URLs

index=test_logs 
| stats count by uri_path 
| sort -count 
| head 10

🔹 HTTP Status Code Distribution

index=test_logs | stats count by status | sort -count

3. Dashboard Creation: Created a dashboard named Apache Log Insights with:

Top 10 IPs, Top requested URLs, HTTP status code distribution chart

4. Screenshots: 
![Log-Upload](https://github.com/user-attachments/assets/9f5b9446-7df2-4d21-b4ae-f4f269bb608c)
![Top-IP](https://github.com/user-attachments/assets/719cbf47-5521-4684-aa4d-07d117ab7e2a)
![Top-URl](https://github.com/user-attachments/assets/490a0389-7f1d-46b3-a2d6-95d87ead7e90)
![Status-codes](https://github.com/user-attachments/assets/da6c9b2f-d17b-4e44-8810-1c3c934aa7b5)
![Full-Dashboard](https://github.com/user-attachments/assets/e64fdae3-6ec2-4893-bc82-6575b9b1c063)


5. Key Learnings:
Ingesting custom log files in Splunk

Writing and interpreting basic SPL queries

Creating dashboards for log visualization

Understanding web traffic through log forensics

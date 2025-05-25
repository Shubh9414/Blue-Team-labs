# DNS Log Analysis 

## Objective
To analyze DNS logs in Splunk and identify potential suspicious/malicious behavior using SPL (Search Processing Language).

## Dataset
Sample DNS logs were ingested into Splunk from a `.log` file.

## Key Queries & Results

- Query 1: Count of All DNS Queries [index=main_sourcetype=dns | stats count by query]

- Query 2: Looking for NXDOMAIN and REFUSED eroors [index=main sourcetype=dns response_code=NXDOMAIN OR response_code=REFUSED | stats count by src, query, response_code]

- Query 3: Suspicious TLDs [index=main sourcetype=dns | where like(query, "%.com") OR like(query, "%.net") OR like(query, "%.xyz") | stats count by src, query]

## Summary
- Used rex to extract fields dynamically.

- Detected NXDOMAIN patterns.

- Found top TLDs and identified suspicious ones.

- Practiced real-world detection logic useful in Blue Team work.

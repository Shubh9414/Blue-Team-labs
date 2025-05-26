# Windows Event 4625 - Failed Login Attempt Analysis

## Objective
Analyze Windows Security EventCode `4625` (failed logon) to detect potential brute-force login attempts using Splunk.

## What The Query Does

- Extracts:
  - `username` from: `log entry for <username>`
  - `src_ip` from: `from <src_ip>`
- Counts how many times each `username` attempted to log in from each `src_ip`
- Filters only those with more than 2 failed login attempts (possible brute-force)
- Sorts the result by the highest count

## Sample Query

- index="main" sourcetype="WinEventLog:Security" EventCode=4625 | rex field=_raw "log entry for (?<username>.*?) from (?<src_ip>\d+\.\d+\.\d+\.\d+)" | stats count by src_ip, username | where count > 2 | sort - count

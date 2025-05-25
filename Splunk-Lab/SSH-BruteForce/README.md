SSH Brute Force Detection Lab (Splunk)

Log File Used
+ File name:`auth.log`
+ Source: Standard Linux authentication logs, commonly found in `/var/log/auth.log`

Objective: The goal of this lab is to detect brute force SSH login attempts using Splunk by analyzing Linux authentication logs. Brute force attacks are typically indicated by repeated "Failed password" messages from the same IP or against the same username.

Steps Performed:

-Step 1: Uploading the Log
 + Logged into Splunk at `localhost:8000`
 + Chose "Upload" option under "Add Data"
 + Uploaded `auth.log`
 + Selected source type `linux_secure`
 + Indexed under `SSH_log`

-Step 2: SPL queries
  + Detecting Failed Login Attempts [index=main sourcetype="linux_secure" "Failed password" | rex "Failed password for (invalid user )?(?<username>\w+)" | stats count by username, host | where count > 5
  + Trying to detect Attacker's IP [index=main sourcetype="linux_secure" "Failed password" | rex "from (?<ip>\d{1,3}(?:\.\d{1,3}){3})" | stats count by ip | where count > 5 | sort -count

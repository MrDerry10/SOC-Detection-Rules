# SOC Detection Rules & Use Cases

This repository contains a collection of custom detection rules and use cases designed for a SOC environment. These use cases are focused on detecting various security incidents such as brute-force attacks, privilege escalation, unusual network traffic, and more. Each use case includes detection logic, relevant queries for SIEMs (Splunk), and examples of how to implement them.

## List of Use Cases

# Brute-Force Login Detection

### Use Case Overview
This rule detects brute-force login attempts by monitoring multiple failed login attempts (Event ID 4625) followed by a successful login (Event ID 4624) from the same source within a 5-minute window.

### Query
The following Splunk query captures the failed and successful login events:

```splunk
(source="WinEventLog:Security" EventCode=4625) 
| stats count by src_ip, user 
| where count > 5 
| append [search (source="WinEventLog:Security" EventCode=4624) | stats count by src_ip, user] 
| where src_ip = src_ip AND user = user
```


3. **Privilege Escalation Detection**  
   Detect unauthorized privilege escalations by monitoring changes to user group memberships.  
   [View Details](PrivilegeEscalationDetection/use_case_description.md)

4. **Unusual Network Traffic - Data Exfiltration**  
   Identify potential data exfiltration by analyzing outbound traffic patterns to suspicious external IPs.  
   [View Details](UnusualNetworkTraffic/use_case_description.md)

# SOC Detection Rules & Use Cases

This repository contains a collection of custom detection rules and use cases designed for a SOC environment. These use cases are focused on detecting various security incidents such as brute-force attacks, privilege escalation, unusual network traffic, and more. Each use case includes detection logic, relevant queries for SIEMs (Splunk), and examples of how to implement them.

## List of Use Cases

1. **Brute-Force Login Detection**  
   Detect multiple failed login attempts followed by a successful login, indicating a potential brute-force attack.  
   [View Details](BruteForceLoginDetection)

2. **Privilege Escalation Detection**  
   Detect unauthorized privilege escalations by monitoring changes to user group memberships.  
   [View Details](Privilege-Escalation-Detection)

3. **Unusual Network Traffic - Data Exfiltration**  
   Identify potential data exfiltration by analyzing outbound traffic patterns to suspicious external IPs.  
   [View Details](Unusual-Network-Traffic)

  

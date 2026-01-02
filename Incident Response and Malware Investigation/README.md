📖 Overview

CYB102 Project 6 was completed as part of CodePath’s Intermediate Cybersecurity course. This project focused on investigating a simulated malware incident using Splunk and managing the case through Catalyst. The goal was to identify indicators of compromise, analyze a malicious artifact, document findings, and reflect on lessons learned using industry standard incident response frameworks.
Through this project, I gained hands on experience working through a real world styled security incident, correlating log data, validating malware using external analysis tools, and documenting an investigation from detection through response.

⚙️ Tools and Environment

Splunk
Catalyst Case Management
VirusTotal
Simulated enterprise log data

🧩 Project Summary

In this project, I investigated a malware related security alert generated from simulated Splunk logs. By analyzing login activity and system behavior, I identified a suspicious file named malware.exe that triggered the incident. The artifact was documented in Catalyst and analyzed using VirusTotal, where it was flagged as malicious by over 40 antivirus engines and linked to prior phishing campaigns.
The investigation emphasized the importance of early detection, proper alerting, and structured incident response. I concluded the project by reflecting on what went well, areas for improvement, and security controls that could prevent similar incidents in the future.

💡 Key Takeaways

Improved understanding of how SIEM tools support incident response
Learned how to document and manage cases using Catalyst
Gained experience validating malware with external intelligence tools
Strengthened my ability to think critically during incident investigations
Developed clearer technical documentation and reporting skills

📂 Repository Contents

README.md – Project overview and professional reflection
screenshots/ – Splunk, VirusTotal, and Catalyst screenshots

Item 1: Splunk Malware Case

Item 2: Artifact + External Analysis Notes

Artifact Type: Filename
Value: malware.exe
Source: Splunk logs
External Analysis Tool Used: VirusTotal

Findings
VirusTotal flagged this file as malicious with over 40 AV engines. It attempted outbound connections and had behavior consistent with known ransomware. Several reports linked this file to prior phishing campaigns.

Item 3: Brief Write-Up and Lessons Learned

What was done well
I was able to use Splunk to trace unusual login activity and identify the file that triggered the alert. Once the artifact was found, I documented it in Catalyst and tied it to a known MITRE TTP.

What could have been done better
Our simulated logs didn’t include much alerting, so a better alerting system in place would’ve helped us respond faster. Also, we could’ve had more endpoint detail.

What changes can be made to prevent similar incidents in the future
Organizations should enable multi-factor authentication, better network segmentation, and implement automated alerting through SIEM tools like Splunk. Also, user awareness training could reduce phishing success rates.


 Item #3

Stretch Challenges

 Bonus Task #1

 Bonus Task #2

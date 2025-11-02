# Splunk Commands and Environment  

### Environment Setup  
- Tool: Splunk Enterprise  
- Operating System: Ubuntu Virtual Machine  
- Interface: Splunk Search & Reporting App  
- Purpose: Used to analyze structured and unstructured log data for the CodePath SIEMsational Capture the Flag project.  

---

## Project Overview  
This project was part of CodePath’s Intermediate Cybersecurity course and focused on using Splunk Enterprise to perform data analysis and incident investigation through a Capture the Flag (CTF) challenge. I explored structured datasets, built search queries, and identified malicious activity in simulated logs.  
The experience helped strengthen my understanding of SIEM systems, event correlation, and the process of tracing attacker activity using log data.  

---

## Skills Demonstrated  
- SIEM configuration and log analysis in Splunk Enterprise  
- Writing and testing Splunk Search Processing Language (SPL) queries  
- Event correlation and timestamp-based analysis  
- Identifying suspicious IP addresses, user accounts, and file hashes  
- Investigating real-world attack behavior through simulated data  
- Creating visualizations and data summaries from structured logs  

---

# Splunk Commands and CTF Challenge Walkthrough  

Project: CodePath – SIEMsational Capture the Flag  

---

## Environment  
- Tool: Splunk Enterprise (local instance via Ubuntu VM)  
- Interface: Splunk Search & Reporting App  
- Datasets Used:  
  - netflix_titles.csv  
  - failedlogins64.csv  
  - webserver02.csv  
  - uploadedhashes.csv  

---

## Project Goal  
This project focused on searching, analyzing, and investigating simulated log data using Splunk.  
The challenges were divided into two parts:  
- Part 1: Exploring Netflix data  
- Part 2: Investigating a simulated security breach at PathCode Inc.  

---

## Part 1: Netflix Dataset Analysis  

### Challenge 1  
Question: How many TV shows on Netflix are in the Docuseries genre?  
Solution: 790  

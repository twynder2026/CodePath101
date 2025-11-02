# CodePath: SIEMsational Capture The Flag

### 📖 Overview
The SIEMsational Capture The Flag (CTF) project was completed as part of CodePath’s Intermediate Cybersecurity course. It focused on using Splunk Enterprise, a Security Information and Event Management (SIEM) tool, to analyze, search, and investigate simulated log data.  
The challenge was divided into two sections: analyzing a Netflix dataset and investigating a security breach at a fictional company, PathCode Inc.

Through this project, I gained hands-on experience in identifying malicious activity, correlating log events, and understanding how SIEM tools support real-world cybersecurity investigations.

---

### ⚙️ Tools and Environment
- Splunk Enterprise (local instance via Ubuntu Virtual Machine)
- Splunk Search & Reporting App
- Datasets:
  - netflix_titles.csv
  - failedlogins64.csv
  - webserver02.csv
  - uploadedhashes.csv

---

### 🧠 Skills Demonstrated
- SIEM setup and configuration using Splunk Enterprise  
- Writing and executing Splunk Search Processing Language (SPL) queries  
- Data filtering, event correlation, and timestamp analysis  
- Identifying malicious activity through MD5 hash tracking and log review  
- Investigating simulated breaches and analyzing attacker behavior  
- Visualizing and reporting security data  

---

### 🧩 Project Summary
The project consisted of 15 Capture the Flag challenges across two parts:

**Part 1: Netflix Dataset Analysis**  
Focused on querying and filtering structured data using SPL.  
Tasks included identifying docuseries, filtering by movie ratings, analyzing release years, and sorting results by country or duration.

**Part 2: PathCode Inc. Investigation**  
Simulated a real-world security incident.  
I analyzed system logs to uncover the malicious actor who uploaded a file named `EvilScript.exe` with a known MD5 hash.  
Through event correlation, I traced the attacker’s IP address (192.168.1.10), user activity, and browser user agent (`Firefox/89.0`) to confirm the source of compromise.

---

### 💡 Key Takeaways
- Learned how to use Splunk to search and analyze large datasets efficiently.  
- Gained a deeper understanding of how SIEM tools detect suspicious network behavior.  
- Improved my ability to think critically when investigating cybersecurity incidents.  
- Strengthened technical writing by documenting each challenge with detailed commands and screenshots.

---

### 📂 Repository Contents
- `splunk_commands.md` – Full list of Splunk queries and results with screenshots.  
- `screenshots/` – Visual output from Splunk searches and dashboard views.  
- `README.md` – Project summary and professional overview.

---

### 🔗 Linked Work
For detailed commands, results, and visual outputs, see the full project walkthrough:  
[splunk_commands.md](./splunk_commands.md)

Connect with me on LinkedIn: [linkedin.com/in/teliyahwynder](https://linkedin.com/in/teliyahwynder)

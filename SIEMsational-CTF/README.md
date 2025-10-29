CodePath: SIEMsational Capture The Flag

📖 Overview

The SIEMsational CTF project focused on using Splunk, a Security Information and Event Management (SIEM) tool, to search, analyze, and investigate simulated log data.
The Capture-the-Flag (CTF) challenge included two parts:

Netflix Dataset Analysis – running searches and filters to explore structured data.

PathCode Inc. Incident Investigation – identifying a malicious actor based on system logs and file uploads.

This project demonstrated how a SIEM helps detect suspicious behavior, correlate events across multiple data sources, and pinpoint threats in a network.

⚙️ Tools and Environment

Splunk Enterprise (local instance via Ubuntu VM)

Datasets:

netflix_titles.csv

pathcode index logs (failedlogins64.csv, webserver02.csv, uploadedhashes.csv)

Browser Interface: Splunk Search & Reporting App

🧠 Key Learning Objectives

Understand SIEM concepts and Splunk architecture (Index, Source, Sourcetype, Host, Time).

Run Splunk search queries using fields and filters.

Identify patterns and anomalies through event correlation.

Investigate attacker behavior using log data.

Create meaningful visualizations and tables from structured data.

🧩 CTF Challenge Summary
Part 1: Netflix Dataset Analysis
Challenge	Description	Search Used	Result
#1	TV shows in the Docuseries genre	source="netflix_titles.csv" type="TV Show" listed_in="*Docuseries*"	count shown
#2	Movies rated TV-PG	`source="netflix_titles.csv" rating="TV-PG" type="Movie"	stats count`
#3	Movies released in 2020	`source="netflix_titles.csv" release_year=2020 type="Movie"	stats count`
#4	Longest duration by season	`source="netflix_titles.csv" type="TV Show"	stats max(duration) by rating`
#6	Country of origin as Turkey	`country="Turkey"	stats count`
#8	Two TV-Y7 shows released 2019, added Nov 22 2019	rating="TV-Y7" release_year=2019 date_added="November 22, 2019"	Trolls: The Beat Goes On! & The Dragon Prince
Part 2: PathCode Inc. Investigation
Challenge	Description	Search Used	Result
#11	IP that uploaded malware (MD5: 3AADBF7E527FC1A050E1C97FEA1CBA4D)	index=pathcode "3AADBF7E527FC1A050E1C97FEA1CBA4D"	192.168.1.10
#12	Usernames tried by attacker	`index=pathcode IP="192.168.1.10"	table Username Event`
#13	User Agent String during upload	`index=pathcode IP="192.168.1.10" Event="File Upload"	table "User Agent"`
#14	Other users who uploaded files	`index=pathcode Event="File Uploaded"	table IP Filename Timestamp`
#15	Files uploaded and which was malicious	`index=pathcode Event="File Uploaded"	table IP Filename "File Hash"`
🧩 Investigation Summary

During the incident at PathCode Inc., multiple employees uploaded files to the server. One upload stood out:

Filename: EvilScript.exe

IP: 192.168.1.10

User: ABurke

Browser: Firefox/89.0

File Hash: 3AADBF7E527FC1A050E1C97FEA1CBA4D

This matched the known malicious MD5 hash. All other uploads (e.g., Homepage.html, ProjectFiles.zip, Style.css) were normal user activity.

💡 Reflection

Through this lab, I learned how SIEM platforms like Splunk can centralize log data and enable quick detection of malicious activity. The most important log field is the timestamp, as it allows event correlation and reconstruction of attack timelines.

This hands-on experience strengthened my ability to analyze logs, detect anomalies, and think like a threat investigator.

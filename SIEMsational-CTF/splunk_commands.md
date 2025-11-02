# Splunk Commands and Environment  

### Environment Setup  
- **Tool:** Splunk Enterprise  
- **Operating System:** Ubuntu Virtual Machine  
- **Interface:** Splunk Search & Reporting App  
- **Purpose:** Used to analyze structured and unstructured log data for the CodePath SIEMsational Capture the Flag project.  

---

### Example Commands  
Below are some of the Splunk searches I ran during the project to explore datasets, investigate log activity, and identify the malicious actor.  

```spl
index=pathcode "3AADBF7E527FC1A050E1C97FEA1CBA4D" | table src_ip
index=pathcode Event="File Uploaded" | table IP Filename "File Hash"
index=pathcode IP="192.168.1.10" Event="File Upload" | table Username "User Agent"
index=pathcode action="upload" | table user src_ip _time
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" country="*United States*" | stats count by release_year | sort -count
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" rating="TV-Y7" release_year=2019 date_added="November 22, 2019" | table title

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
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" country="*United States*" | stats count by release_year | sort -count
<img width="1136" height="600" alt="image" src="https://github.com/user-attachments/assets/bc2113a4-9362-4632-98da-e55e39648a0c" />


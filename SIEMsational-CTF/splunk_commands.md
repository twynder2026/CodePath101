# Splunk Commands and Environment  

### Environment Setup  
- Tool: Splunk Enterprise  
- Operating System: Ubuntu Virtual Machine  
- Interface: Splunk Search & Reporting App  
- Purpose: Used to analyze structured and unstructured log data for the CodePath SIEMsational Capture the Flag project.  


# Splunk Commands and CTF Challenge Walkthrough  

Project: CodePath – SIEMsational Capture the Flag  


## Environment  
- Tool: Splunk Enterprise (local instance via Ubuntu VM)  
- Interface: Splunk Search & Reporting App  
- Datasets Used:  
  - netflix_titles.csv  
  - failedlogins64.csv  
  - webserver02.csv  
  - uploadedhashes.csv  


## The Project Goal 
This project focused on searching, analyzing, and investigating simulated log data using Splunk.  
The challenges were divided into two parts:  
- Part 1: Exploring Netflix data  
- Part 2: Investigating a simulated security breach at PathCode Inc.  


## Part 1: Netflix Dataset Analysis  

Challenge 1  
Question: How many TV shows on Netflix are in the Docuseries genre?  
Solution: 790  
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="TV Show" listed_in="*Docuseries*" | stats count
#### This command filtered TV shows that contained the word “Docuseries” in the genre field and counted the total number.
<img width="1139" height="568" alt="image" src="https://github.com/user-attachments/assets/35809b32-13dd-4731-830d-4ea806e728b9" />


Challenge 2: How many movies on Netflix have a rating of TV-PG?
Solution: 1080
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" rating="TV-PG" | stats count
#### This search looked only at movies rated TV-PG and displayed the count.
<img width="1137" height="562" alt="image" src="https://github.com/user-attachments/assets/2a79ff70-0c57-43c3-8cb4-871cb3ddeba4" />


Challenge 3: How many movies on Netflix were released in the year 2020?
Solution: 1034
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" release_year=2020 | stats count
#### Filtered the dataset by release year 2020 and movie type.
<img width="1139" height="559" alt="image" src="https://github.com/user-attachments/assets/f5c9a4ce-c3de-4d0c-b841-9040b50cfd70" />


Challenge 4: What is the longest duration by season on Netflix, and what is its TV rating?
Solution: TV-MA and TV-PG
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="TV Show" | stats max(duration) as Longest_Season by rating
#### Calculated the longest duration for all TV shows and grouped by rating.
<img width="1139" height="553" alt="image" src="https://github.com/user-attachments/assets/3e9929b3-aae4-4d0c-8e46-bf4fba942306" />

Challenge 5: How many movies on Netflix are listed as Action and rated PG-13?
Solution: 296
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" rating="PG-13" listed_in="*Action*" | stats count
#### Filtered by rating and genre, returning all PG-13 action movies.
<img width="1139" height="563" alt="image" src="https://github.com/user-attachments/assets/92ad518c-d7e3-40ab-9e6c-faa3a1e886b3" />

Challenge 6: How many movies and TV shows on Netflix have their country of origin as Turkey?
Solution: 226
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" country="*Turkey*" | stats count
#### Searched all entries that listed Turkey as the country of origin.
<img width="1138" height="455" alt="image" src="https://github.com/user-attachments/assets/b09dd7af-7cdd-4618-8f37-4a97a19e3e74" />

Challenge 7: Which release year had the most movies rated G (not TV-G)?
Solution: 2009
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" rating="G" | stats count by release_year | sort -count
#### Grouped and sorted G-rated movies by release year to find the most common.
<img width="1138" height="614" alt="image" src="https://github.com/user-attachments/assets/ca03b46c-8a16-44ac-819a-950a5a5349e9" />

Challenge 8: What two TV-Y7 shows were released in 2019 and added on November 22, 2019?
Solution: Trolls: The Beat Goes On! and The Dragon Prince
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" rating="TV-Y7" release_year=2019 date_added="November 22, 2019" type="TV Show" | table title
#### Filtered the dataset using rating, release year, and date added.
<img width="1139" height="274" alt="image" src="https://github.com/user-attachments/assets/739d8548-1b60-4039-aec8-5c8bcf4ec531" />

Challenge 9: Which year had the most movies from the United States?
Solution: 2017
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="Movie" country="*United States*" | stats count by release_year | sort -count
#### Displayed total movies per year from the United States, sorted in descending order.
<img width="1140" height="502" alt="image" src="https://github.com/user-attachments/assets/85ea59f1-e719-418f-aea3-c64db2c7acb0" />

Challenge 10: What is the oldest TV show by release year on Netflix?
Solution: 1925
source="/home/codepath/Files/Splunk-5-6-7/netflix_titles.csv" type="TV Show" | stats min(release_year) as Oldest_Year by title | sort Oldest_Year
#### Found the minimum release year and the corresponding TV show titles.
<img width="1138" height="514" alt="image" src="https://github.com/user-attachments/assets/b0674abc-3265-43a4-aeb8-811d5a287203" />

## Part 2 – PathCode Inc. Malware Investigation

Challenge 11: What was the IP address that uploaded the malware (MD5: 3AADBF7E527FC1A050E1C97FEA1CBA4D)?
Solution: 192.168.1.10
index=pathcode "3AADBF7E527FC1A050E1C97FEA1CBA4D" | table src_ip
#### Matched the MD5 hash of the malicious file to identify the attacker’s IP.
<img width="1135" height="494" alt="image" src="https://github.com/user-attachments/assets/ab6de4cc-d861-4f25-ae19-6224df03f6aa" />

Challenge 12: What usernames did that IP address try to log in as, and which one uploaded the file?
Solution: Pi, ABurke, and Admin
index=pathcode IP="192.168.1.10" | table User Event
#### Listed all usernames and events associated with the attacker's IP.
<img width="656" height="665" alt="image" src="https://github.com/user-attachments/assets/4c5a20b2-3e23-4278-b1c3-01cd1ec2c257" />

Challenge 13: What was the User Agent String of the attacker when they successfully uploaded a file?
Solution: Firefox/89.0
index=pathcode src_ip="192.168.1.10" action="upload" | table user_agent
#### Captured the browser user agent associated with the upload event.
<img width="1139" height="239" alt="image" src="https://github.com/user-attachments/assets/2da5db51-c49b-438d-811c-a99bff66fd8a" />


Challenge 14: Did any other users also upload a file around that time? If so, who and what was their IP address?
Solution: Yes – 192.168.1.8, 192.168.1.4, and 192.168.1.11
index=pathcode Event="File Uploaded" | table IP Filename Timestamp
#### Displayed all uploads and timestamps to identify other users active at the same time.
<img width="769" height="662" alt="image" src="https://github.com/user-attachments/assets/69f926de-7571-4fc2-90c0-ff18322c33ad" />


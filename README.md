Custom Honeypot SIEM 
=======
## 🚀 Overview
This project builds a cloud-based security operations using:

- Azure Sentinel (SIEM)
- Honeypot VM with RDP exposed
- GeoIP map visualization using KQL

# 💻 Technologies used
* Azure Virtual Machines (Windows 11)
* Microsoft Sentinel
* Kusto Query Language (KQL)
* Azure Virtual Network (VNet)
* Network Security Group (NSG)
* Azure Monitor Agent (AMA)
* Log Analytics Workspace



## 🧠 Skills Demonstrated
- Threat intelligence ingestion
- Cloud SOC automation
- Azure Sentinel analytics rules
- Incident creation & investigation
- Kusto Query Language (KQL)


## 🚀 Objective  
Developed a cloud based SIEM that traps user who try to gain unauthorized access to my deployed virtual machine leveraged by Remote Desktop Protocol 3389 (this left the virtual machine exposed in the internet without firewall configurations). The aim of the project was to simulate a cloud detection system by the collection of user logs from Log Analytics, watchlists, and custom workbooks. Documentation is provide to understand the thought process throught the project. Below is the amount of atttacks since the 18th of October
<img width="1439" height="812" alt="attackattempts" src="https://github.com/user-attachments/assets/d6c7bfb1-0a5d-4c20-8299-d4223b6f90b9" />


## Project Setup
* Depolyed a virual machine using RDP 3389
* Configured NSG to allow inbound RDP 
* Allowed the VM to run for 24 hours to attract attacks
* <img width="1440" height="772" alt="step1" src="https://github.com/user-attachments/assets/4ee2e57b-0310-4dab-a702-48d9c9cad3b0" />

## Sentinel Setup
* Deployed a Log Analytics Workspace
* Write a query to detected failed signins and brute force attacks
* Connected the VM using the Azure Monitor Agent
* Enable Windows Security Event Collections which intergrate to Sentinel log analysis
* <img width="1439" height="812" alt="nsjfnrshjfbrshjfbsrhf" src="https://github.com/user-attachments/assets/1bc8159a-2857-4e4d-8fe5-249e61dce40c" />



## Threat Monitoring 
* Based on Event ID 4625 (failed RDP authentication)
* Collected houndreds of brute force attempts within hours of VM deployment
* Created a watchlist named geoipmap for IP
* Located attackers location by IP, city, country, latitude, and longitude
* <img width="1440" height="811" alt="Untitled" src="https://github.com/user-attachments/assets/a28faaaa-1c7c-4b34-8fe9-946fcb763c30" />
* The query,"where EventID == 4625" means it logs the failed attempted into the VM's sentinel which was up to 1000 within the 24 hour timesframe

## Visualization
* With the geoIP indentification -> The graph was used the model the attack locations based off their IP address, city, country, latitude, and longitude
* Frequency heatmap included
<img width="1232" height="773" alt="attackmapazure" src="https://github.com/user-attachments/assets/14efb6e9-a3d7-4031-a251-8471acea974b" />

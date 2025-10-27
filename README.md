Custom Honeypot SIEM 
=======
## 🚀 Overview
This project builds a cloud-based security operations using:

- Azure Sentinel (SIEM)
- Honeypot VM with RDP exposed
- GeoIP map visualization using KQL

# 💻 Technologies used
* Azure Virtual Machines (Windows 11)
* Azure Virtual Network (VNet)
* Log Analytics Workspace
* Kusto Query Language (KQL)


## 🧠 Skills Demonstrated
- Threat intelligence ingestion
- Cloud SOC automation
- Azure Sentinel analytics rules
- Incident creation & investigation
- Kusto Query Language (KQL)


## 🚀 Objective  
Architect a cloud based SIEM that traps user who try to gain unauthorized access to my deployed virtual machine leveraged by Remote Desktop Protocol 3389 (this left the virtual machine exposed in the internet without firewall configurations). The aim of the project was to simulate a cloud detection system by the collection of user logs from Log Analytics, watchlists, and custom workbooks. Documentation is provide to understand the thought process throught the project. 

## Project Setup
* Depolyed a virual machine using RDP 3389
* Configured NSG to allow inbound RDP 
* Allowed the VM to run for 24 to attract attacks
(Insert Screenshot: VM + NSG Rules)

## Sentinel Setup
* Deployed a Log Analytics Workspace
* Write a query to detected failed signins and brute force attacks
* Enable Windows Security Event Collections which intergrate to Sentinel log analysis
*  (Insert Screenshot: LAW + AMA configuration)

## Threat Monitoring 
* Based on Event ID 4625 (failed RDP authentication)
* Collected houndreds of brute force attempts within hours of VM deployment
* Created a watchlist named geoipmap for IP
* Located attackers location by IP, city, country, latitude, and longitude
(Insert Screenshot: SecurityEvent logs)

## Visualization
* With the geoIP indentification -> The graph was used the model the attack locations
* Frequency heat included

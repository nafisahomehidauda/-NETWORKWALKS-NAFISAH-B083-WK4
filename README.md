# PENETRATION TESTING & VULNERABILITY ASSESSMENT 

Footprinting / Network Scanning / Gain Access / Password cracking 

| Pentester | Nafisat Omehi Dauda|
|-----------|--------------------|
| Batch     | B083               |
| Intern    | Networkwalks       |
| Instructor| Waqas Qarim CCIE   |
| Client    | Mediroza Hospital  |
| Date      | 29th September,2026|

## Project detail

|Project Type | Pentesting & Vulnerability Assessment                                                                                                             |
| ------------| -------------------------
|Client Name  | Mediroza General Hospital                                                                                                                         |
|Target       | Https:/Medirozahospital.com                                                                                                                       |
|Scope        | Full black box penetration test. Identify & exploit vulnerabilities to demonstrate real impact and document all findings in a professional report |
|             |                                                                                                                                                   | 
|Rules        |Testing limited to the target domain only. No social engineering. No denial of service. No testing outside agreed scope                            |
|Authorization|The client has provided written authorisation to conduct security testing on their web infrastructure                                              |


## Liability Disclaimer 

I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

## Introduction 

This report covers footprinting the medirozahospital domain using nmap Kali Linux tools, scanning and Gain access with Maltego, Zenmap and Hydra in Kali Linux tools. One module covers the footprinting phase, the other covers the scanning phase and lastly gaining access, so together they show how an attacker moves from gathering public information to mapping live hosts on a network and gain accessing in live network. It is the Week 4 part of my ongoing internship program at Networkwalks.

All commands were run in Kali Linux (footprinting) and on a Windows PC with Zenmap installed (scanning).I have also used Maltego for emails extraction from the domain. Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.

## Phases covered 

### Phase 1: Reconnaissance & Footprinting

### Phase 2: Scanning & Network Discovery 

### Phase 3: Gaining Access 

### Phase 4: Password Cracking 


## Tools Used

The table below lists each tool used in this report and its purpose. 

|Tool                   | Purpose                                                       |
|-------------          | ------------------                                            |
|Kali Linux & Windows OS| used for reconnaissance activities                            |
|WHOIS                  | Find domain registration details (owner, dates, name servers) |  
|whatweb                |Fingerprint web technologies (server, CMS, plugins, IP)        |
|nslookup               |Resolve the domain name to its IP address using DNS. curl      | 
|wafw00f                |Detect whether a Web Application Firewall protects the site    |
|dnsrecon               |Enumerate all DNS records (NS, MX, SPF, TXT, SRV)              |
|Zenmap (Nmap GUI)      |Scan the local subnet to find live hosts, IPs and MAC addresses| 
|Maltego                | Emails extraxtion from the domain or website                  |
|Hydra                  | used to gaining access Staff and Patient Login pages          |

## Activities Performed

1. Footprinting & Reconnaissance I performed reconnaissance against # https:/medirozahospital.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. Each tool was used to collect a different type of information about the target.

### WHOIS:
to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.

### WhatWeb: 
to identify technologies used by the website. The results identified the domain is hosted using a light speed server, along with other information exposed by the website.

### nslookup:
I resolved the domain name to its IP address. The provided result identified 199.188.201.16

### wafw00f: 
to determine whether a Web Application Firewall was protecting the website. The result  showed that the site sits behind Lite speed (Litespeed Technology)

I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

Network Scanning with Zenmap For the second activity, I used Zenmap to perform network discovery on medirozahospital.com. In scanning, I used Zenmap and selected intense scan and identified one live host:

199.188.201.16
### Harvester 
Found 3 subdomains 
2 Ips
1 email
2 hosts - FTP, Mediroza hospital.com and mail.medirozahospital.com

## Summary 
This domain has publicly discoverable infrastructure including mail/FTP related host names.

## Risk Analysis / Impact

Based on the information collected during the footprinting and network scanning activities, I identified the following potential risks.

Footprinting and Scanning

I have derived possible emails and results are show in the screenshot attached. [Low Risk🚦] and I have used WHOIS Find domain registration details (owner, dates, name servers)

I have also used Zenmap, using intensive scan, to scan open ports and have found two, FTP port and SIP. [Medium Risk 🚦]

Gain Accessing

I have used Hydra on Staff Login and Patient Login pages. The results are show in the screenshot attached. In staff login I found 16 passwowds [High Risk🚦] while patient login page I found none but child numbers. The screenshots are also attached.



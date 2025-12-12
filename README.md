# CEH-Nmap-Scapy-lab
🛡️ CEH Lab: Network Reconnaissance with Nmap & Scapy
📌 Overview
This repository documents my hands-on lab for the Certified Ethical Hacker (CEH) course, focusing on network reconnaissance using Nmap and Scapy on a Kali Linux system.
The objective was to identify services and potential vulnerabilities on a suspicious host within a DMZ network.

🎯 Assignment Goals

Perform active reconnaissance using Nmap and Scapy.
Document all steps with explanations and screenshots.
Publish findings and reflections on learning outcomes.


🛠️ Tools & Environment

Operating System: Kali Linux
Tools:

Nmap – Network mapping and service enumeration
Scapy – Packet crafting and analysis


Target: Suspicious host at 10.6.6.23 in the 10.6.6.0 DMZ network


🔍 Key Steps
1. Environment Setup

Verified network interface configuration.
Confirmed Nmap installation and version.

2. Host Discovery
nmap -sn 10.6.6.0/24

Identified 7 active hosts in the DMZ.

3. Basic Scan
nmap 10.6.6.23

Open ports: 21, 22, 53, 80, 139, 445.

4. OS & Service Detection
sudo nmap -O -sV -p 21,22,53,80,139,445 10.6.6.23

OS: Linux kernel 4.15–5.8

Services:
FTP: vsftpd 3.0.3
SMB: Ports 139 & 445

5. Aggressive Scan
nmap -A 10.6.6.23S

Combined OS detection, version detection, script scanning, and traceroute.

6. SMB Enumeration
nmap --script smb-enum-users.nse,smb-enum-shares.nse -p 139,445 10.6.6.23

Enumerated users: arbiter, masterchief
Discovered hidden administrative shares ending with $.


✅ Learning Outcomes

Mastered Nmap scanning techniques and options.
Understood OS fingerprinting and service version detection.
Learned SMB enumeration using NSE scripts.


🔗 Resources

Nmap Documentation
Scapy Documentation


💡 Reflection:
This lab reinforced the importance of structured reconnaissance in ethical hacking and how these tools uncover critical insights during penetration testing.

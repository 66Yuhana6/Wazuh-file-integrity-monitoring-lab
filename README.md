#File Integrity Monitoring (FIM) Using Wazuh SIEM
Project Overview
This project demonstrates how Wazuh File Integrity Monitoring (FIM) can detect unauthorized changes to critical files and directories on Linux systems.

The lab simulates real-world scenarios where attackers modify sensitive files, and Wazuh generates alerts to help security analysts identify suspicious activities.

Objectives
Understand File Integrity Monitoring (FIM)
Configure Wazuh FIM on Linux
Monitor sensitive directories
Simulate unauthorized file modifications
Generate and analyze security alerts
Document incident findings
Lab Environment
Component	Details
SIEM	Wazuh 4.x
Manager OS	Ubuntu Server
Agent OS	Ubuntu Server
Virtualization	VirtualBox
Monitoring Feature	File Integrity Monitoring (FIM)
Architecture Diagram
Architecture_Diagram

Prerequisites
Wazuh Manager installed
Ubuntu Agent installed
Agent connected to manager
Root privileges
Configure File Integrity Monitoring
 nano /var/ossec/etc/ossec.conf
ossec.conf_file

Now, scroll a little and look for with the comment File Integrity Monitoring. You should see the tag is set to NO, meaning it’s enabled.
Restart Wazuh Agent
sudo systemctl restart wazuh-agent
Verify Configuration
 systemctl status wazuh-agent
Attack Simulation
Create a File
 touch newfile.txt
Create a File

Detection Results
Wazuh successfully generated alerts for:

File creation
Detection Results

Incident Analysis
MITRE ATTACK Technique: T1565 – Stored Data Manipulation

MITRE ATTACK Technique

Potential Risks:

Unauthorized configuration changes
Malware persistence
Insider threats
Key Learnings
Learned how File Integrity Monitoring works.
Configured Wazuh Syscheck module.
Simulated file tampering scenarios.
Investigated alerts from the Wazuh Dashboard.
Understood the importance of monitoring critical files.

---
tags:
  - delete
MOC: "[[CNCA Operations Fundamentals]]"
---
-- --

# PowerShell

* [[Windows PowerShell]]
* Windows XP SP2
* Scripts and interactive terminal
- Object oriented
	- Create commands with modules
	- Granular permissions
- PowerShell Integrated Scripting Environment (ISE)
	- .ps1
- Language
	- Verb-Noun format
	- Get-Command
		- List available commands
	- Get-Help Get-Process -showWindow
		- Help for command
	- select .property
	- Pipe `|`
		- Run multiple 
	- Export/Import 
		- Export-Csv
		- Export Clixml
		- Out-Gridview
- Remote Management
	- Serverside
		- netsh firewall set service RemoteAdmin
		- netsh advfirewall set currentprofile settings remotemanagement enable
	- Enter-PSSession
		- Similar to SSH
	- New-PSSession
		- Persistent session
		- Can store multiple sessions in one variable
	- Invoke-Command
		- execute block of code with session as arguments
	- Get-Credentials
		- Save credentials in variable
- Arguments
	- $args
# Event Logs

- Chronological list of recorded events 
- .evtx extensions
- Main logs are Security, System, and Application
- View in GUI, PowerShell, or log collections
- Event Codes
	- 4624 successful login
	- 4625 failed login
	- 4609 Windows shutdown
	- 4732 Member added to local security group
	- 1102 Security audit log
# Registry

* [[Windows Registry]]
* Hierarchical database storing low-level settings for [[Windows MOC]]
* Structure 
	* Registry values are instructions
	* Registry keys are folders for data
	* Registry hives categorize data in registry
* Registry Hives
	* HKEY_CLASSES_ROOT contains registered applications
	* HKEY_CURRENT_USER stores settings specific to current user
	* HKEY_LOCAL_MACHINE stores settings for local computers
	* HKEY_USERS corresponding HKCU keys for each user
	* HKEY_CURRENT_CONFIG stores current hardware profile information
	* HKEY_LOCAL_MACHINE/SAM contains user/admin accounts with hashed passwords
	* HKEY_LOCAL_MACHINE/SECURITY Stores security policies for current user
* Viewing the registry
	* regedit
	* Get-PSDrive
		* cd HKCU
		* Get-ChildItem
		* New-Item -path . -name MQT
		* Set-ItemProperty -path .\MQT -name CMR -type String -value "Hey!"
* Export registry
	* Invoke-Command -computername \[IP] -credential \[username] -scriptblock {get-ItemProperty HKLM:\\Software\\Microsoft\\Windows\\CurrentVersion\\Run\\\*} | export-csv IP-HKLM-Run.csv
# Persistence

- Object and process characteristics continue to exist after machine is powered off
- Saved in non-volatile storage 
- Scheduled Tasks
	- Launches programs at pre-defined times
	- Get-ScheduledTask
	- (Get-ScheduledTask -TaskName "<\TASKNAME>").Action
- Services
	- Background Windows program
	- Get-Service
	- Get-WmiObject -Class win32_service | select name, displayname, state, pathname
- Users
	- Get-LocalUser

# Sysinternals

- Tools to manage, troubleshoot, and monitor [[Windows MOC]] systems
	- Autoruns
	- Procmon
	- Sysmon
	- Strings
	- Process explorer (procexp)
	- Psexec
# Log Collections/Flow

- Collecting information from individual hosts for aggregating for analysis
# Kibana

- View data from Zeek, Suricata, and host event logs in Elastic Stack with real time analysis
- Main views
	- Discover
	- Visualizations
	- Dashboards
	- Security
- Kibana Query Language (KQL)
	- Simple syntax
	- Field suggestion
	- Boolean queries
	- Range queries 
	- Wildcards
# Security Onion

- Free & open source Linux distribution for intrusion detection, security monitoring, and log management
	- CyberChef
	- NetworkMiner
	- Elastic Stack
	- OS Query
	- Suricata
	- Zeek
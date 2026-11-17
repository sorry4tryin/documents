---
class:
aliases:
tags:
  - note/quick
created: 2026-10-28 18:37
modified: 2026-11-17 09:32
---

- ch 8. 
	- codes: the use of a caret identifies it
	- How can you identify inherited permissions?
	- How do Share and NTFS permissions differ?
	- On which elements can NTFS permissions be set?
	- How can you view the users who have permissions for a particular drive?
- ch 9
	- ch. 9.1
		- isolation: limit the attack
		- containment: first step; disconnect machine from network—terminate connections
		- segmentation: separate network to prevent threat pivoting; occurs to VLANs, software-defined networks, switches, subnetting or physically
			- screened subnet: virtual area to separate internal network from the rest
		- security orchestration, automation, and response (SOAR): use different security endpoints for compiled security data
			- does: collect alert data and geo-data; create cases; supports multiple playbooks along with step automation
		- incident plans: playbook and runbook for better efficiency—automation; 
			- playbook: series of protocols to automate a security incident response
			- runbook: guide on how to respond to threat
	- ch. 9.2
		- SIEM:  security information and event management; combines security information management (SIM) and security even management (SEM)——tool used to monitor and display info for daily incident response tasks
			- sensors: most critical for monitoring and securing network endpoints, services, and other vulnerable locations
			- SIEM dashboards: use ot effectively monitor and respond to events on the network in real-time
			- correlation: analyze attacker behavior against aggregated data from log files, system applications, and network appliances
			- alert: informs IT that a pre-established parameter is not within the acceptable range
			- trend: pattern sent to the SIEM
			- sensitivity: when sensors are released; configure data sent to SIEM
			- vulnerability scan output: scan vulnerabilities along with providing solutions
			- PRI code is calculated from the facility and severity level
			- IPfix: tool that addresses a protocol for internal protocol flows; helps collect data from  routers servers, and other networks
			- file metadata: metadata linked with files; creation date, access history, and security permissions
			- even metadata: source and time of event; host or network address, a process name, and categorization/priority fields
	- ch. 9.3
		- digital forensics:
			- reporting: evidence cannot be change; if  so there  must be a reason behind it
			- data image acquisition:
				- video recording—ensures proof derives from the crime scene
			- legal hold—significant information must be preserved; it cannot be tampered with
			- chain of custody: items must be identified correctly; item must be in a secure location
				- provenance must be displayed; evidence moved should not be tampered with
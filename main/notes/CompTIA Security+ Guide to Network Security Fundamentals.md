---
created: 2026-10-23 08:41
modified: 2026-10-28 09:44
---
toc
wireless denial attacks - [[CompTIA Security+ Guide to Network Security Fundamentals (Mark Ciampa) (z-library.sk, 1lib.sk, z-lib.sk).pdf#page=359&selection=78,0,78,3|p. 339]]

mod. 10
- describe the different types of wireless network attacks
	- cellular: through telecommunication it allows use to a fixed wireless service for internet connectivity.
	- bluetooth: wireless technology using short-range radio frequency (RF) transmissions for short distance communication; 
		- attacks: bluejacking, which involves unsolicited messages being sent to bluetooth-enabled devices (like images, sounds, or text messages); bluesnarfing, which involves the access of unauthorized information through wireless devices to bluetooth-enabled devices.
	- near field communication (NFC): a way of communication between devices in close proximity; leads to major vulnerabilities like eavesdropping, data theft, man-in-the-middle attack, and device theft
	- radio frequency identification (RFID): ability to transmit information between employee identification badges, inventory tags, book labels, and other paper-based tags that can be detected by a proximity reader; attacks include: unauthorized tag access,  fake tags, eavesdropping, and RFID cloning
	- wlan: a replacement for a wired local area network; the process: there is a wireless client network interface card (wireless adapter) which sends and receives signals through airwaves—similar to a wired adapter; there is an access point (AP) at the center of the wlan device that sends and receives wireless signals—there are fat APs (or autonomous APs; specifically used for authentication, encryption, and other functions for wireless client devices), thin APs (they do not manage or configure functions), controller APs (managed through a specific wireless lan controller 'WLC'), and a captive portal AP (a user signs their agreement to a policy in order to receive information or to present valid login credentials).
	- wlan enterprise: there are well-defined boundaries (or "hard edges") in order to protect data—types of hard edges: network and a second (which makes up the structure for the enterprise)
		- more ap attacks: rogue AP (invalid ap that allows the attacker to bypass network security configs), and evil twin (ap configured by an attacker in order to mimic an authorized one or capture transmissions)
- list the vulnerabilities of WLAN security
- explain the solutions for securing a wireless network

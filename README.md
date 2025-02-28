# Cybersecurity HomeLab

## Overview
This project documents my journey in setting up a cybersecurity home lab using VMware Workstation 15 Player. The lab consists of multiple virtual machines, a firewall, a vulnerability scanner, and a SIEM system. It serves as a hands-on environment to practice security concepts, penetration testing, and system administration.

## Components

### 1. Installing Windows 10 Image
- Download Windows 10 Enterprise VM from Microsoft.
- Install and configure the VM for domain integration.
[Download Windows 10 VM](https://developer.microsoft.com/en-us/windows/downloads/virtual-machines/)

### 2. Installing Ubuntu Linux 18.04.4 LTS
- Base version installation from the Ubuntu website.
- Configure networking and security settings.
[Download Ubuntu Desktop](https://ubuntu.com/download/desktop)

### 3. Setting up VMware Workstation 15 Player
- VMware Workstation 15 Player is free for home use.
- Used to create, configure, and manage virtual machines.
[Download VMware Workstation Player](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html)

### 4. Configuring and Working with Active Directory
- Setting up an Active Directory (AD) environment for centralized device management.
- Followed Adam Heath’s tutorial for guidance.
[Active Directory Setup Tutorial](https://www.youtube.com/watch?v=xftEuVQ7kY0)

### 5. Connecting Desktops to Active Directory
#### Linux Desktop
- Ubuntu Linux 18.04.4 TLS is connected to AD.
[Download Ubuntu Desktop](https://ubuntu.com/download/desktop)

#### Windows 10 Pro (Enterprise)
- Windows 10 Enterprise VM connected as an employee workstation.
[Download Windows 10 VM](https://developer.microsoft.com/en-us/windows/downloads/virtual-machines/)

### 6. Securing Home Network with pfSense Firewall
- Installing and configuring the open-source pfSense firewall for network segmentation.
- Download and setup guide available below:
[Download pfSense](https://www.pfsense.org/download/)
[pfSense VMware Setup Guide](https://www.vgemba.net/vmware/pfSense-VMware-Workstation/)

### 7. Configuring a Vulnerability Scanner (Nessus)
- Nessus Essentials used for vulnerability scanning (free for up to 16 IPs).
- Simulated vulnerability scans for network security assessment.
[Download Nessus Essentials](https://www.tenable.com/products/nessus/nessus-essentials)

### 8. Configuring a SIEM System with Splunk
- Splunk SIEM used for event logging and correlation.
- Set up log collection from Windows and Linux machines.
[Download Splunk](https://www.splunk.com/en_us/download/splunk-enterprise.html)

## Future Enhancements
- Implementing an IDS/IPS system.
- Setting up a honeypot for threat analysis.
- Automating security alerts and responses.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

---
This repository serves as a reference for others looking to set up their own home lab for cybersecurity learning and testing.

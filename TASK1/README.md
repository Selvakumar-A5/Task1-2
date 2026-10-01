# Task 1: Scan Your Local Network for Open Ports

##  Overview

This project was completed as part of a Cyber Security Internship task. The objective was to perform basic network reconnaissance by scanning the local network for open ports and understanding the network services exposed by devices.

##  Objective

The main objectives of this task were:

* Discover devices available on the local network.
* Identify open ports on network devices.
* Understand the purpose of open ports and network services.
* Identify potential security risks associated with exposed ports.
* Gain practical experience with Nmap and network reconnaissance.

##  Tools Used

* **Nmap** – Used for network discovery and port scanning.
* **Wireshark** – Used optionally for packet analysis.
* **GitHub** – Used to store and submit the project files.

##  Methodology

### 1. Identify the Local Network

The local network IP range was identified before performing the scan.

### 2. Perform TCP SYN Scan

Nmap was used to perform a TCP SYN scan on the local network using:

```bash
nmap -sS <local-network-range>
```

The `-sS` option performs a TCP SYN scan to identify accessible TCP ports on discovered hosts.

### 3. Analyze Scan Results

The Nmap scan results were reviewed to identify:

* Devices discovered on the network
* Open TCP ports
* Services associated with the open ports
* Potentially unnecessary network exposure

### 4. Security Analysis

The discovered open ports were analyzed to understand the services running on the network and the potential security risks associated with unnecessary exposed services.

##  Security Considerations

Open ports are not necessarily vulnerabilities. However, unnecessary or improperly secured services can increase the attack surface of a system.

Some security considerations include:

* Closing unnecessary ports.
* Disabling services that are not required.
* Restricting access using firewall rules.
* Keeping network services updated.
* Avoiding unnecessary exposure of administrative services.
* Regularly reviewing network services and exposed ports.

##  Key Concepts Learned

### Open Port

An open port indicates that a network service is listening for connections on that port.

### TCP SYN Scan

A TCP SYN scan is a technique used by Nmap to determine whether TCP ports are open by sending SYN packets and analyzing the responses.

### Port Scanning

Port scanning is a network reconnaissance technique used to discover accessible ports and services on network devices.

### Network Reconnaissance

Network reconnaissance involves gathering information about devices, IP addresses, ports, and services within a network.

### Firewall

A firewall helps control network traffic and can restrict access to ports and services that should not be accessible.

##  Repository Contents

The repository contains the files and evidence related to the completed network scanning task, including scan results and screenshots where applicable.

Only the files relevant to the completed task are included in the repository.

##  Ethical and Safety Note

The network scanning activity was performed for educational and cybersecurity learning purposes on an authorized/local network.

Network scanning should only be performed on systems and networks where you have permission to conduct security testing.

##  Outcome

This task provided practical experience with basic network reconnaissance and helped develop an understanding of network exposure, open ports, TCP SYN scanning, and network security fundamentals.

The task also provided hands-on experience using Nmap to discover network devices and analyze their accessible services.

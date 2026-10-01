# Task 1: Local Network Port Scanning – Findings Report

## 1. Objective

The objective of this task was to perform network reconnaissance using Nmap to identify active hosts, detect open TCP ports, identify associated services, and understand potential security risks related to exposed network services.

## 2. Tools Used

* Nmap 7.99
* Linux Terminal
* Virtual Network Environment

## 3. Network Configuration

| Parameter         | Value         |
| ----------------- | ------------- |
| Network Interface | eth0          |
| IP Address        | 10.0.2.15     |
| Subnet Mask       | 255.255.255.0 |
| Network Range     | 10.0.2.0/24   |

## 4. Methodology

### Step 1: Host Discovery

Command executed:

```bash
sudo nmap -sn 10.0.2.0/24
```

This command was used to discover active hosts in the local virtual network without performing a port scan.

**Result:** 3 active hosts were discovered out of 256 IP addresses.

### Step 2: TCP SYN Scan

Command executed:

```bash
sudo nmap -sS 10.0.2.0/24 -oN scan_results.txt
```

The TCP SYN scan was performed to identify open TCP ports on discovered hosts. The scan results were saved in a text file for documentation.

## 5. Scan Results

| IP Address | Port | Protocol | Service      | State                    |
| ---------- | ---- | -------- | ------------ | ------------------------ |
| 10.0.2.2   | 135  | TCP      | MSRPC        | Open                     |
| 10.0.2.2   | 445  | TCP      | Microsoft-DS | Open                     |
| 10.0.2.2   | 3306 | TCP      | MySQL        | Open                     |
| 10.0.2.3   | 53   | TCP      | DNS          | Open                     |
| 10.0.2.15  | -    | TCP      | -            | No open ports identified |

**Additional observation:** The 1,000 scanned TCP ports on 10.0.2.15 were reported as filtered.

## 6. Potential Security Risks

### Port 135 – MSRPC

* Used for Microsoft Remote Procedure Call services.
* Unnecessary exposure may increase the attack surface.
* Access should be restricted to trusted networks.

### Port 445 – SMB

* Commonly used for Windows file and printer sharing.
* Misconfigured file shares or outdated SMB implementations may introduce security risks.
* Access should be restricted to authorized devices.

### Port 3306 – MySQL

* Commonly used for MySQL database communication.
* Unauthorized access attempts may occur if the service is exposed.
* Database access should be restricted using authentication and network access controls.

### Port 53 – DNS

* Used for Domain Name System services.
* Misconfigured DNS services may expose information or be abused.
* DNS access should be limited to intended clients.

**Note:** These are potential risks associated with the identified services. The scan did not confirm any vulnerability or successful unauthorized access.

## 7. Key Observations

1. Three active hosts were discovered in the scanned virtual network.
2. Four open TCP ports were identified across two hosts.
3. The detected services included MSRPC, Microsoft-DS, MySQL, and DNS.
4. The local Linux VM had no ports identified as open among the 1,000 scanned TCP ports.
5. The scan reported filtered ports, indicating that responses were blocked or unavailable.
6. The environment appears to be a virtual NAT network rather than the physical Wi-Fi network.

## 8. Recommendations

* Disable unnecessary network services.
* Restrict access to database and file-sharing services.
* Configure firewall rules to allow only required connections.
* Use strong authentication for database services.
* Keep operating systems and network services updated.
* Perform regular authorized network security assessments.

## 9. Conclusion

This task provided practical experience with network reconnaissance using Nmap. Host discovery and TCP SYN scanning were performed to identify active devices and open ports in a virtual network.

The results helped demonstrate how exposed services can be identified and why network access controls, firewall configurations, and service security are important.

## 10. Learning Outcomes

* Understanding IP addresses and CIDR notation.
* Performing network host discovery.
* Understanding TCP SYN scanning.
* Identifying open and filtered ports.
* Recognizing common network services.
* Understanding potential security risks associated with exposed ports.
* Documenting network scan results for security assessment.

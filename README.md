# Task 3 – Vulnerability Scan using Nessus Essentials

## Objective
The objective of this task is to perform a basic vulnerability scan on my personal machine using Tenable Nessus Essentials and document the identified vulnerabilities, scan results, and remediation suggestions.

## Tools Used
- **Nessus Essentials**
- **Local Scanner**
- Report Generated: 17 Nov 2025

## Target Information
- **Target IP:** 192.168.1.27
- **Hostname:** AMAL
- **Operating System:** Windows 11
- **Scan Type:** Basic Network Scan
- **Authentication:** Not provided (Auth = Fail)

## Scan Summary
- **Start Time:** 4:48 PM  
- **End Time:** 4:56 PM  
- **Total Scan Duration:** 8 minutes  
- **Total Vulnerabilities Found:** 82  
- **Severity Breakdown:**  
  - Critical: 0  
  - High: 0  
  - Medium: 1  
  - Low: 0  
  - Info: 81  

## Key Findings
Most findings are informational, with one medium-severity issue:  
- **SSL Certificate Cannot Be Trusted (Medium)**  
This occurs because Nessus uses a self-signed certificate on port 8834.

Other informational findings include:  
- Open ports enumeration  
- SMB service detection  
- RPC services enumeration  
- TLS/SSL version support  
- DNS hostname detection  
- OS fingerprinting  

## Files Included
- **scan_report.pdf** – Full Nessus report  
- **vulnerabilities.md** – Detailed explanation of selected vulnerabilities  
- **system_info.txt** – Scanner and OS details  
- **/screenshots** – Scan results, findings, and Nessus interface

## How to Reproduce the Scan
1. Install Nessus Essentials.  
2. Create a new “Basic Network Scan”.  
3. Set target to your own system’s IP (e.g., `192.168.X.X`).  
4. Launch the scan.  
5. Export the report as PDF.

## Conclusion
This vulnerability scan provides a basic overview of exposed services, SSL configuration, and network information. Although no critical or high-severity vulnerabilities were identified, the informational items highlight network services that may require further hardening.

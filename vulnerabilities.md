#### **# Vulnerabilities Summary – Nessus Scan (192.168.1.xx)**



Below are the key vulnerabilities identified in the Nessus scan, including their risk ratings and remediation suggestions.



---



\## 1. SSL Certificate Cannot Be Trusted  

\*\*Severity:\*\* Medium  

\*\*Plugin ID:\*\* 51192  

\*\*CVSS Score:\*\* 6.5  

\*\*Description:\*\*  

Nessus detected that the SSL certificate running on port 8834 is self-signed and not issued by a trusted certificate authority. This is expected because Nessus itself uses a self-signed certificate.



\*\*Why This Happens:\*\*  

\- The certificate is generated locally by Nessus  

\- Browsers and scanners cannot verify the trust chain  



\*\*Risk:\*\*  

Medium risk for public-facing servers. Safe for localhost.



\*\*Remediation:\*\*  

\- For real servers: Install a certificate from a trusted CA  

\- For Nessus (local): No action needed  



---



\## 2. Additional DNS Hostnames  

\*\*Severity:\*\* Info  

\*\*Plugin ID:\*\* 46180  

\*\*Description:\*\*  

Nessus detected alternate hostnames (e.g., `amal`) that map to this machine.



\*\*Remediation:\*\*  

No action needed unless hostname exposure is a concern.



---



\## 3. SMB and NetBIOS Information Disclosure  

\*\*Severity:\*\* Info  

\*\*Plugin ID:\*\* 10150, 11011  

\*\*Description:\*\*  

Windows exposes SMB and NetBIOS details, allowing enumeration of OS, hostname, and SMB versions.



\*\*Remediation:\*\*  

\- Disable SMBv1 (if enabled)  

\- Restrict SMB/NetBIOS ports to trusted networks  



---



\## 4. Open Ports Exposed on the System  

\*\*Severity:\*\* Info  

\*\*Plugin ID:\*\* 14272  

\*\*Description:\*\*  

Many ports were found open, including:  

135, 139, 445 (Windows services),  

500/4500 (IKE/IPSec),  

8834 (Nessus),  

1900 (UPnP),  

multiple ephemeral RPC ports.



\*\*Remediation:\*\*  

\- Enable Windows Firewall  

\- Allow only required ports  

\- Disable unnecessary services  



---



\## 5. OS Fingerprinting and Service Enumeration  

\*\*Severity:\*\* Info  

\*\*Plugin ID:\*\* 11936, 97993  

\*\*Description:\*\*  

Nessus was able to detect OS version and software using fingerprint techniques.



\*\*Remediation:\*\*  

This is normal but can be hardened by:  

\- Restricting inbound connections  

\- Enabling firewall rules to limit probing



---



\# Conclusion  

Only one medium-severity vulnerability was found. Others are informational and reflect normal Windows networking behaviour.




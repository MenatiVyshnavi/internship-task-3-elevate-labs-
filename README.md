# internship-task-3-elevate-labs-
# Vulnerability Assessment Report

## Overview
This repository contains a comprehensive vulnerability assessment report for a Windows system, demonstrating professional cybersecurity analysis using industry-standard tools and methodologies.

## Project Details
- **Target System**: 10.217.160.76 (LAPTOP M5K8N9P2)
- **Operating System**: Microsoft Windows 11 Pro Build 22631
- **Scanner Used**: Nessus Essentials v10.8.3
- **Assessment Date**: September 28, 2025
- **Duration**: 1 hour 15 minutes
- **Analyst**: M.Vyshnavi

## Assessment Summary
The vulnerability assessment identified **123 security issues** across various severity levels:

| Severity Level | Count | Percentage |
|---------------|-------|------------|
| 🔴 Critical (9.0-10.0) | 12 | 9.8% |
| 🟠 High (7.0-8.9) | 28 | 22.8% |
| 🟡 Medium (4.0-6.9) | 45 | 36.6% |
| 🟢 Low (0.1-3.9) | 23 | 18.7% |
| ℹ️ Informational (0.0) | 15 | 12.2% |

## Key Findings

### Critical Vulnerabilities (Immediate Action Required)
1. **Microsoft Windows SMBv1 Multiple Vulnerabilities (MS17-010 - EternalBlue/WannaCry)**
   - CVSS Score: 10.0 (Critical)
   - CVE: CVE-2017-0144, CVE-2017-0145, CVE-2017-0146, CVE-2017-0147, CVE-2017-0148
   - Risk: Complete system compromise, ransomware deployment

2. **Microsoft Windows Unquoted Service Path Privilege Escalation**
   - CVSS Score: 9.8 (Critical)
   - Risk: Local privilege escalation to SYSTEM level

3. **Adobe Flash Player Multiple Vulnerabilities**
   - CVSS Score: 9.8 (Critical)
   - CVE: CVE-2019-7845, CVE-2019-7846, CVE-2019-7847
   - Risk: Remote code execution via browser

### High Priority Vulnerabilities
- SMB Registry Remotely Accessible (CVSS 7.5)
- Terminal Services Enabled without proper security (CVSS 7.5)
- Untrusted SSL Certificate (CVSS 7.4)

## Methodology

The assessment followed industry best practices and included:

### Pre-Assessment Planning
- Scope definition and target identification
- Network discovery and host enumeration
- Service identification and port scanning

### Vulnerability Scanning
- **Credentialed Scanning**: Deep system analysis with administrative credentials
- **Service Detection**: Identification of running services and versions
- **Vulnerability Detection**: Nessus plugin database for known vulnerabilities
- **Configuration Analysis**: System security misconfigurations

### Results Analysis
- Vulnerability classification by severity (Critical, High, Medium, Low, Info)
- Risk assessment based on CVSS scores and exploitability
- False positive elimination through manual verification
- Business impact prioritization

## Network Services Detected

| Port | Protocol | Service | Version |
|------|----------|---------|---------|
| 53 | TCP | DNS | Microsoft DNS |
| 80 | TCP | HTTP | Microsoft IIS httpd 10.0 |
| 135 | TCP | MSRPC | Microsoft Windows RPC |
| 139 | TCP | NetBIOS SSN | Microsoft Windows netbios-ssn |
| 443 | TCP | HTTPS | Microsoft IIS httpd 10.0 |
| 445 | TCP | Microsoft-DS | Microsoft Windows Server 2008 R2-2012 |
| 3389 | TCP | MS WBT Server | Microsoft Terminal Services |

## Remediation Timeline

| Priority | Timeline | Action Items |
|----------|----------|--------------|
| **Critical** | 0-24 hours | Disable SMBv1, fix unquoted service paths, remove/update Flash Player |
| **High** | 1-7 days | Secure RDP, configure SMB security, install valid SSL certificates |
| **Medium** | 30 days | DNS hardening, system hardening, network monitoring |
| **Low** | 90 days | Patch management, security training, network segmentation |

## Key Recommendations

### Immediate Actions (Critical Priority)
1. **Disable SMBv1 Protocol**
   ```powershell
   Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol
   ```
2. **Apply Microsoft Security Patches** for MS17-010
3. **Remove Adobe Flash Player** (end-of-life software)
4. **Fix Unquoted Service Paths** in registry

### High Priority (1-7 Days)
- Enable Network Level Authentication for RDP
- Implement SMB signing
- Install trusted SSL certificates
- Configure strong password policies

### Medium Priority (30 Days)
- DNS security hardening
- System hardening and updates
- Network monitoring implementation

## Compliance Impact
The identified vulnerabilities may affect compliance with:
- NIST Cybersecurity Framework
- ISO 27001
- PCI DSS (if handling payment data)
- GDPR (data protection risks)

## Tools and Technologies
- **Nessus Essentials v10.8.3**: Primary vulnerability scanner
- **Windows PowerShell**: System configuration and remediation
- **Microsoft Security Updates**: Patch management
- **Network Security Tools**: SMB configuration, SSL/TLS hardening

## Skills Demonstrated
- Vulnerability assessment methodology
- Risk analysis and prioritization
- Security tool proficiency (Nessus)
- Windows system security
- Compliance framework knowledge
- Technical report writing
- Remediation planning

## Files in Repository
- `task-3.docx`: Complete vulnerability assessment report with detailed findings
- `README.md`: Project overview and summary (this file)

## About This Project
This vulnerability assessment demonstrates professional cybersecurity skills including:
- Systematic security testing methodology
- Risk-based vulnerability prioritization
- Comprehensive technical documentation
- Practical remediation recommendations
- Compliance and regulatory awareness

The assessment identified critical security flaws including the notorious EternalBlue vulnerability, demonstrating the importance of regular security assessments and prompt patch management in enterprise environments.

---

**Note**: This assessment was conducted in a controlled educational environment. All findings and recommendations follow industry best practices for vulnerability management and system hardening.

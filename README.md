# 🛡️ Google Cybersecurity Professional Certificate — Portfolio

**Cristian Fajardo** | Cybersecurity Analyst in Training  
[![Google Cybersecurity Certificate](https://img.shields.io/badge/Google-Cybersecurity%20Professional%20Certificate-4285F4?style=flat-square&logo=google)](https://grow.google/certificates/cybersecurity/)
![Status](https://img.shields.io/badge/Status-Completed-success?style=flat-square)
![Last Updated](https://img.shields.io/badge/Updated-2025-informational?style=flat-square)

---

## 📋 About This Portfolio

This repository showcases hands-on projects completed as part of the **Google Cybersecurity Professional Certificate**. Each project demonstrates practical skills applied to real-world security scenarios — from analyzing incidents and managing Linux permissions to writing SQL queries for threat detection and automating file updates with Python.

> These projects reflect my ability to think like a security professional: identifying threats, applying frameworks, documenting findings, and implementing remediations.

---

## 🗂️ Projects

---

### 1. 🔍 Apply Filters to SQL Queries

**File:** [`Apply_filters_to_SQL_queries.pdf`](./Apply_filters_to_SQL_queries_docx.pdf)

**Description:**  
As a security professional investigating suspicious login activity and employee data, I applied SQL filters to isolate relevant records from a relational database. This included identifying failed logins after business hours, login attempts on specific dates, and access from outside specific regions.

**Key Concepts:**
- `AND`, `OR`, `NOT` logical operators
- `LIKE` with wildcard `%` for pattern matching
- Filtering by time, date, and country fields

**Queries Demonstrated:**

| Scenario | SQL Technique Used |
|---|---|
| After-hours failed logins | `WHERE login_time > '18:00' AND success = 0` |
| Logins on specific dates | `WHERE login_date = 'X' OR login_date = 'Y'` |
| Logins outside Mexico | `WHERE country NOT LIKE 'MEX%'` |
| Marketing employees in East offices | `WHERE department LIKE '%Marketing%' AND office LIKE 'East%'` |
| Finance or Sales employees | `WHERE department LIKE '%Finance%' OR department LIKE '%Sales%'` |
| Non-IT employees | `WHERE department NOT LIKE '%Information Technology%'` |

**Skills:** SQL, Database Querying, Security Investigation, Log Analysis

---

### 2. 🐍 Algorithm for File Updates in Python

**File:** [`Algorithm_for_file_updates_in_Python.pdf`](./Algorithm_for_file_updates_in_Python_docx.pdf)

**Description:**  
I developed a Python algorithm to automate the maintenance of an IP address allow list for a healthcare company. The script reads the current allow list, removes unauthorized IP addresses found in a separate remove list, and writes the updated list back to the file — ensuring only authorized users retain network access to restricted patient information.

**Algorithm Overview:**

```python
def update_file(import_file, remove_list):
    with open(import_file, "r") as file:
        ip_addresses = file.read()

    ip_addresses = ip_addresses.split()

    for element in ip_addresses:
        if element in remove_list:
            ip_addresses.remove(element)

    ip_addresses = " ".join(ip_addresses)

    with open(import_file, "w") as file:
        file.write(ip_addresses)
```

**Key Concepts:**
- File I/O with `open()` and the `with` statement
- String manipulation: `.read()`, `.split()`, `.join()`
- List iteration and conditional removal with `.remove()`
- Access control automation

**Skills:** Python, File Handling, Automation, Access Control Management

---

### 3. 🐧 File Permissions in Linux

**File:** [`File_permissions_in_Linux.pdf`](./File_permissions_in_Linux_docx.pdf)

**Description:**  
Working as a security professional on a research team, I audited and corrected file and directory permissions in a Linux environment to align with organizational security policy. I identified overly permissive access, removed unauthorized write access, corrected hidden file permissions, and restricted directory access.

**Permission Changes Made:**

| Target | Issue Found | Fix Applied | Result |
|---|---|---|---|
| `project_k.txt` | Others had write access | `chmod o-w` | `-rw-rw-r--` |
| `.project_x.txt` (hidden) | Owner could write; group had no read | `chmod u-w,g-w,g+r` | `-r--r-----` |
| `drafts/` directory | Group had execute (entry) access | `chmod g-x` | `drwx------` |

**Key Commands Used:**
```bash
ls -la /home/researcher2/projects     # Audit permissions
chmod o-w project_k.txt               # Remove others' write
chmod u-w,g-w,g+r .project_x.txt     # Fix hidden file
chmod g-x drafts/                     # Restrict directory
```

**Skills:** Linux CLI, File System Security, `chmod`, Least Privilege Principle

---

### 4. 📓 Incident Handler's Journal

**File:** [`Incident_handlers_journal.pdf`](./Incident_handler_s_journal__docx.pdf)

**Description:**  
A structured journal documenting four cybersecurity incidents analyzed throughout the course. Each entry follows the **5 W's** framework (Who, What, When, Where, Why) and maps to the **NIST Incident Response Lifecycle**.

**Incidents Documented:**

| Entry | Date | Incident Type | Tools Used | NIST Phase |
|---|---|---|---|---|
| 1 | Oct 9, 2025 | Ransomware via phishing email | Email security tools, Antivirus, Network monitoring | Detection & Analysis / Containment & Recovery |
| 2 | Oct 13, 2025 | Malicious `.xls` spreadsheet payload | VirusTotal, IDS alerts, SHA256 Hashing | Detection & Analysis |
| 3 | Oct 17, 2025 | Phishing with malicious `.exe` attachment | VirusTotal, Email header analysis | Detection & Analysis |
| 4 | Oct 18, 2025 | Forced browsing / web app data exfiltration | Web server logs, Vulnerability scanner | Containment & Post-Incident Activity |

**Key Takeaways:**
- Phishing remains the primary attack vector across multiple incident types
- VirusTotal and hash analysis are critical for rapid malware confirmation
- Proper incident documentation enables faster containment and post-incident learning

**Skills:** Incident Response, NIST Framework, IoC Analysis, Documentation, VirusTotal, IDS

---

### 5. 📊 Incident Report Analysis (NIST CSF)

**File:** [`Completed_Incident_report_analysis.pdf`](./Completed_Example_of_an_Incident_report_analysis_docx.pdf)

**Description:**  
A comprehensive incident report analyzing a credential theft and data breach caused by a phishing attack targeting an intern. The report applies the **NIST Cybersecurity Framework (CSF)** across all five functions to document both the incident and the remediation steps taken.

**Incident Summary:**  
An intern's credentials were stolen via a phishing link. The attacker used those credentials to access the customer database, deleting and manipulating records. The breach was detected when the intern reported being locked out while access logs showed her account was still active.

**NIST CSF Response:**

| Function | Action Taken |
|---|---|
| **Identify** | Audited systems, access policies, and devices to find security gaps |
| **Protect** | Implemented MFA, limited login attempts to 3, employee training, firewall config, IPS |
| **Detect** | Deployed firewall logging and IDS to monitor incoming traffic |
| **Respond** | Disabled compromised account, trained staff, notified management and law enforcement |
| **Recover** | Restored deleted data from last night's full database backup |

**Skills:** NIST CSF, Incident Reporting, Credential Security, MFA, IDS/IPS, Database Recovery

---

### 6. ✅ Controls and Compliance Checklist (Botium Toys)

**File:** [`Controls_and_compliance_checklist.pdf`](./Controls_and_compliance_checklist_--_reviewed_--.pdf)

**Description:**  
A security audit of a fictional company, **Botium Toys**, evaluating existing controls and compliance posture against three major frameworks: **PCI DSS**, **GDPR**, and **SOC Type 1/2**. The checklist identifies gaps and provides prioritized recommendations for the IT Manager.

**Frameworks Assessed:**
- 💳 **PCI DSS** — Payment Card Industry Data Security Standard
- 🇪🇺 **GDPR** — General Data Protection Regulation
- 🏢 **SOC 1 / SOC 2** — System and Organization Controls

**Controls Evaluated:**
Least Privilege · Disaster Recovery · Password Policies · Separation of Duties · Firewall · IDS · Backups · Antivirus · Encryption · Password Management · Physical Security (Locks, CCTV) · Fire Detection

**Top Recommendations Issued:**
1. Implement least privilege and separation of duties
2. Adopt encryption for PCI DSS and GDPR compliance
3. Create a disaster recovery and backup plan
4. Deploy a centralized password management system
5. Implement IDS/IPS for active threat detection
6. Formalize legacy system monitoring schedule

**Skills:** Security Auditing, Risk Assessment, PCI DSS, GDPR, SOC, Compliance Frameworks

---

### 7. 🗄️ Vulnerability Assessment — Database Server

**File:** [`Security_analysis_and_proposal.pdf`](./Security_analysis_and_proposal_docx.pdf)

**Description:**  
A formal vulnerability assessment of a publicly accessible database server critical to business operations. Threats were identified, scored by likelihood and severity, and a remediation strategy was proposed based on the risk scores.

**Risk Assessment Matrix:**

| Threat Source | Threat Event | Likelihood (1-3) | Severity (1-3) | Risk Score |
|---|---|---|---|---|
| External Hacker | Data exfiltration | 3 | 3 | **9** 🔴 |
| Competitor | Denial of Service (DoS) | 2 | 3 | **6** 🟡 |
| Malicious Insider | Alter/Delete critical data | 2 | 3 | **6** 🟡 |

**Remediation Strategy:**
- Restrict public database access immediately
- Enforce least privilege via role-based access controls (RBAC)
- Implement MFA and strong password policies
- Encrypt data in transit using TLS 1.3
- Apply IP allow-listing to restrict connections to trusted networks
- Deploy continuous monitoring, logging, and auditing
- Add IDS and firewall layers (Defense-in-Depth)

**Skills:** Vulnerability Assessment, Risk Scoring, RBAC, TLS, Defense-in-Depth, Threat Modeling

---

## 🧰 Tools & Technologies

| Category | Tools / Technologies |
|---|---|
| **Languages** | Python, SQL (MariaDB), Bash |
| **Operating Systems** | Linux (Ubuntu), Windows |
| **Security Tools** | VirusTotal, Suricata, IDS/IPS, Firewalls |
| **Frameworks** | NIST CSF, NIST IR Lifecycle, PCI DSS, GDPR, SOC 1/2 |
| **Concepts** | Incident Response, Threat Modeling, Risk Assessment, Least Privilege, Defense-in-Depth, Access Control, Encryption |

---

## 🎓 Certificate

**Google Cybersecurity Professional Certificate**  
Offered by Google via Coursera — an 8-course program covering foundations of cybersecurity, network security, Linux & SQL, threat analysis, incident response, Python automation, and more.

🔗 [View Certificate Program](https://www.credly.com/badges/850b7bde-8637-4e4f-b9e0-bcb8f5366ba0/linked_in_profile)

---

## 📬 Contact

**Cristian Fajardo**  
Open to entry-level cybersecurity analyst and SOC analyst roles.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](www.linkedin.com/in/cristian-fajardo-7132352a6)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat-square&logo=gmail)](mailto:cristianfajardo1909@gmail.com)

---

*This portfolio was built as part of the Google Cybersecurity Professional Certificate program. All scenarios and company names (e.g., Botium Toys) are fictional and used for educational purposes.*

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

**File:** [`Apply filters to SQL queries.docx.pdf`](./Apply%20filters%20to%20SQL%20queries.docx.pdf)

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

**File:** [`Algorithm for file updates in Python.docx.pdf`](./Algorithm%20for%20file%20updates%20in%20Python.docx.pdf)

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

**Files:** [`File permissions in Linux.docx.pdf`](./Use%20Linux%20commands%20to%20manage%20file%20permissions/File%20permissions%20in%20Linux.docx.pdf) · [`Current file permissions.docx.pdf`](./Use%20Linux%20commands%20to%20manage%20file%20permissions/Current%20file%20permissions.docx.pdf)

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

**File:** [`Incident handler_s journal_.docx.pdf`](./Document%20an%20incident%20with%20an%20incident%20handler_s%20journal/respond%20to%20a%20phishing%20incident/Incident%20handler_s%20journal_.docx.pdf)

**Description:**  
A structured journal documenting four cybersecurity incidents analyzed throughout the course. Each entry follows the **5 W's** framework (Who, What, When, Where, Why) and maps to the **NIST Incident Response Lifecycle**.

**Incidents Documented:**

| Entry | Date | Incident Type | Tools Used | NIST Phase |
|---|---|---|---|---|
| 1 | Oct 9, 2025 | Ransomware via phishing email | Email security tools, Antivirus, Network monitoring | Detection & Analysis / Containment & Recovery |
| 2 | Oct 13, 2025 | Malicious `.xls` spreadsheet payload | VirusTotal, IDS alerts, SHA256 Hashing | Detection & Analysis |
| 3 | Oct 17, 2025 | Phishing with malicious `.exe` attachment | VirusTotal, Email header analysis | Detection & Analysis |
| 4 | Oct 18, 2025 | Forced browsing / web app data exfiltration | Web server logs, Vulnerability scanner | Containment & Post-Incident Activity |

**Related files:**
- [`Alert ticket.docx.pdf`](./Document%20an%20incident%20with%20an%20incident%20handler_s%20journal/respond%20to%20a%20phishing%20incident/Alert%20ticket.docx.pdf)
- [`Phishing incident response playbook.docx.pdf`](./Document%20an%20incident%20with%20an%20incident%20handler_s%20journal/respond%20to%20a%20phishing%20incident/Phishing%20incident%20response%20playbook.docx.pdf)
- [`Data breach final report.docx.pdf`](./Document%20an%20incident%20with%20an%20incident%20handler_s%20journal/data%20breach/Data%20breach%20final%20report.docx.pdf)

**Key Takeaways:**
- Phishing remains the primary attack vector across multiple incident types
- VirusTotal and hash analysis are critical for rapid malware confirmation
- Proper incident documentation enables faster containment and post-incident learning

**Skills:** Incident Response, NIST Framework, IoC Analysis, Documentation, VirusTotal, IDS

---

### 5. 📊 Incident Report Analysis (NIST CSF)

**Files:** [`Completed Example of an Incident report analysis.docx.pdf`](./DDoS%20attack%20analysis/Completed%20Example%20of%20an%20Incident%20report%20analysis.docx.pdf) · [`Incident report analysis.docx.pdf`](./DDoS%20attack%20analysis/Incident%20report%20analysis.docx.pdf) · [`Applying the NIST CSF_.docx.pdf`](./DDoS%20attack%20analysis/Applying%20the%20NIST%20CSF_.docx.pdf)

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

**Files:** [`Controls and compliance checklist -- reviewed --.pdf`](./Conduct%20a%20security%20audit/Controls%20and%20compliance%20checklist%20--%20reviewed%20--.pdf) · [`Control categories.docx.pdf`](./Conduct%20a%20security%20audit/Control%20categories.docx.pdf)

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

**Files:** [`Security analysis and proposal.docx.pdf`](./Analyze%20a%20vulnerable%20system%20for%20a%20small%20business/Security%20analysis%20and%20proposal.docx.pdf) · [`NIST SP 800-30 Rev. 1.docx.pdf`](./Analyze%20a%20vulnerable%20system%20for%20a%20small%20business/NIST%20SP%20800-30%20Rev.%201.docx.pdf)

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

🔗 [View Certificate](https://www.credly.com/badges/850b7bde-8637-4e4f-b9e0-bcb8f5366ba0/linked_in_profile)

---

## 📬 Contact

**Cristian Fajardo**  
Open to entry-level cybersecurity analyst and SOC analyst roles.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/cristian-fajardo-7132352a6)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat-square&logo=gmail)](mailto:cristianfajardo1909@gmail.com)

---

*This portfolio was built as part of the Google Cybersecurity Professional Certificate program. All scenarios and company names (e.g., Botium Toys) are fictional and used for educational purposes.*

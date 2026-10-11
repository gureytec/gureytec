
# SOC Analyst Portfolio

Hi, I'm learning cybersecurity with the goal of becoming a SOC Analyst L1.

I'm currently working through the TryHackMe SOC Level 1 path and practicing in hands-on labs. This repository is where I keep track of what I'm learning, the tools I'm using, and the investigations I complete along the way.

## About Me

- **Current focus:** SOC Analyst L1
- **Training:** TryHackMe SOC Level 1
- **Environment:** Kali Linux and Windows lab environments
- **Interests:** Security monitoring, log analysis, incident response, and threat detection

I'm still learning, so this portfolio will grow as I complete more labs and gain practical experience.

## What I'm Learning

| Area | Topics |
|---|---|
| Linux | Commands, authentication logs, SSH activity |
| Windows | Event Logs, Sysmon, PowerShell |
| SOC Fundamentals | Alert triage, investigation, incident reporting |
| Threat Intelligence | IOCs, file hashes, malicious IPs and domains |
| Malware Analysis | File analysis, process behavior, sandbox reports |
| Network Analysis | Wireshark, DNS, TCP/IP |
| Security Frameworks | MITRE ATT&CK |
| SIEM | Log correlation, detection rules, security monitoring |

## Practical Labs & Investigations

### 1. SSH Brute-Force Investigation

Practicing how to investigate failed SSH login attempts using Linux authentication logs.

What I'm working on:
- Finding failed authentication attempts
- Identifying source IP addresses and targeted usernames
- Counting login failures using Linux commands
- Checking for successful logins
- Documenting findings and possible next steps

**Tools:** Kali Linux, Bash, Linux authentication logs

**Related technique:** [MITRE ATT&CK T1110 — Brute Force](https://attack.mitre.org/techniques/T1110/)

[View investigation report](investigations/ssh-brute-force/incident-report.md)

### 2. Windows Event Log Analysis

Learning how to examine Windows logs and Sysmon events to understand process activity, authentication events, and potentially suspicious behavior.

### 3. Malware Analysis

Learning the basics of examining suspicious files, checking hashes, reviewing sandbox results, and identifying indicators of compromise.

### 4. Security Alert Triage

Practicing how to review alerts, collect evidence, correlate events, assess suspicious activity, and document when an incident needs further investigation.

*I'll add detailed reports as I complete and verify each investigation.*

## Tools & Technologies

- **Operating systems:** Linux, Windows
- **Command line:** Bash, basic Linux utilities
- **Log analysis:** Linux authentication logs, Windows Event Logs, Sysmon
- **Security tools:** Wireshark, VirusTotal
- **Framework:** MITRE ATT&CK
- **SIEM:** Learning security monitoring and event correlation

My experience with these tools varies, and I'll update this section as I gain more hands-on practice.

## Learning Roadmap

- [ ] Complete the TryHackMe SOC Level 1 path
- [x] Start practicing Linux authentication-log analysis
- [ ] Document completed investigations
- [ ] Practice Windows event and Sysmon analysis
- [ ] Build basic detection rules
- [ ] Practice SIEM investigations
- [ ] Upload my TryHackMe completion certificate

## Certifications

**TryHackMe SOC Level 1**

Currently studying. I'll add my certificate here after completing the learning path.

## Repository Structure

```text
gureytec/
├── README.md
├── investigations/
│   └── ssh-brute-force/
│       └── incident-report.md
├── detection-rules/
├── incident-reports/
└── evidence/
```

## Disclaimer

All exercises are for educational and defensive cybersecurity purposes. Findings will be based on lab evidence, and training exercises will not be presented as professional work experience.

---

I'm documenting my progress as I work toward my first SOC Analyst role.

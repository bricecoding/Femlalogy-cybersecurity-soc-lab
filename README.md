# Femlalogy-cybersecurity-soc-lab
Hands-on SOC lab for Femlalogy: simulating real-world cyberattacks and defenses using Wireshark, pfSense (Snort), and Wazuh. Includes report, lab setup, configs, findings, and recommendations for building layered, proactive cybersecurity defenses.

This repository documents the process, findings, and recommendations from the Femlalogy Security Operations Center (SOC) project. The project demonstrates how to detect, analyze, and respond to cyber threats using open-source tools: **Wireshark**, **pfSense (with Snort)**, and **Wazuh**.

## Project Overview

- **Goal:** Strengthen Femlalogy’s cybersecurity posture through hands-on simulation of real-world attacks and layered defense.
- **Tools Used:** Wireshark, pfSense, Snort, Wazuh
- **Lab Environment:** Kali Linux (attacker), Ubuntu (victim & Wazuh agent)

## Table of Contents

- Project Introduction
- Lab Setup
- Phase 1: Wireshark
- Phase 2: pfSense & Snort
- Phase 3: Wazuh
- Findings
- Recommendations
- Conclusion
- References

## Project Introduction

Cybersecurity is critical for organizational success. This project simulates attacks and defenses in a controlled lab to test readiness and demonstrate best practices.

## Lab Setup

- **Attacker:** Kali Linux
- **Victim:** Ubuntu (with Wazuh agent)
- **Firewall/IDS:** pfSense with Snort
- **SIEM:** Wazuh

## Phase 1: Wireshark – Network Traffic Capture & Analysis

- Captured and analyzed normal and malicious traffic (Nmap scans, ping floods).
- Used filters to identify suspicious activity.
- See detailed steps and screenshots in `/docs/images/wireshark/`

## Phase 2: pfSense & Snort – Firewall & Policy Enforcement

- Configured firewall rules to block ransomware IPs (Lockbit, Medusa, Phobos).
- Rejected risky protocols (ICMP, SSH).
- Implemented GeoIP filtering to restrict high-risk regions.
- Enabled Snort for intrusion detection and alerting.

## Phase 3: Wazuh – Security Event Monitoring & Response

- Forwarded logs from pfSense and endpoints to Wazuh.
- Detected and correlated multiple attack types (brute-force, ping flood, Nmap scan).
- Used Wazuh dashboard for real-time investigation.

## Findings

- Open SSH port exposed to brute-force risk.
- ICMP traffic initially allowed, enabling DoS attacks until blocked.
- Snort and Wazuh provided actionable alerts and event correlation.
- GeoIP and IP blocklists significantly reduced attack surface.

## Recommendations

1. Enforce least privilege access (restrict SSH, use key-based auth).
2. Maintain updated blocklists and threat feeds.
3. Enable Snort blocking mode.
4. Expand GeoIP filtering.
5. Centralize logging to Wazuh.
6. Conduct regular security simulations.
7. Train staff on threat awareness.

## Conclusion

Layered, proactive defense using open-source tools is effective for detecting and responding to cyber threats. With continuous improvement, Femlalogy can maintain a strong cybersecurity posture.

## References

•	Wireshark Documentation (https://www.wireshark.org/docs/)
•	pfSense and IDS/IPS Configuration (https://docs.netgate.com/pfsense/en/latest/)
https://docs.netgate.com/pfsense/en/latest/packages/snort/index.html
Snort IDS: (https://www.snort.org/)
•	Wazuh Official Guide 
https://documentation.wazuh.com/current/installation-guide/wazuh-agent/index.ht ml
(https://documentation.wazuh.com/)
•	MITRE ATT&CK Framework (https://attack.mitre.org/)
•	Nmap Network Scanner (https://nmap.org/)
•	hping3 Packet Generator (http://www.hping.org/)
•	Logs and dashboards from the lab environment 
•	Raw logs, alert data, and full packet captures 

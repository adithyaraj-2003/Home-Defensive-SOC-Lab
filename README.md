# 🛡️ Defensive Home SOC Lab: Wazuh SIEM & Kali Attack Simulation

## 📌 Project Overview
Designed and deployed a localized Security Information and Event Management (SIEM) home lab environment using Oracle VirtualBox. The objective was to simulate real-world cyber attacks from an offensive machine (Kali Linux) and configure a centralized defensive monitoring platform (Wazuh SIEM) to detect, log, and alert on malicious activity in real time.

---

## 🛠️ Architecture & Technology Stack
* **SIEM & Endpoint Monitoring:** Wazuh (Wazuh Server on Ubuntu Server, Wazuh Agent on endpoints)
* **Offensive Security / Attack Simulation:** Kali Linux (Utilized for generating telemetry and attack vectors)
* **Virtualization & Networking:** Oracle VirtualBox (Configured with isolated internal/host-only networking)
* **Core Log Sources Monitored:** Windows Security Event logs, Linux authentication logs (`auth.log`), and File Integrity Monitoring (FIM).

---

## 🔬 Simulated Attack Scenarios & Detection Engineering
During this lab, various adversary tactics were executed from Kali Linux to validate defensive detection capabilities:

1. **Brute-Force Attack Simulation:**
   * **Action:** Executed SSH brute-force attempts against target endpoints from Kali Linux.
   * **Detection:** Wazuh triggered high-severity alerts (`Rule 5710 - SSH brute-force attempt`) based on repeated authentication failures within a short time window.

2. **File Integrity Monitoring (FIM):**
   * **Action:** Modified critical system binaries and configuration files on the monitored endpoint.
   * **Detection:** Wazuh FIM engine instantly flagged unauthorized file modifications, capturing file hashes, timestamps, and user context.

3. **Process & Command-Line Auditing:**
   * **Action:** Ran suspicious enumeration commands and reconnaissance scripts from Kali.
   * **Detection:** Correlated process execution logs via Wazuh agents to track adversary behavior and map to MITRE ATT&CK.

---

## 📂 Repository Contents
* `configs_and_rules/ossec_agent_custom.conf`: Custom Wazuh agent configuration defining FIM target directories and local log collection paths.
* `configs_and_rules/local_rules.xml`: Custom Wazuh detection rules written to flag brute-force attempts and unauthorized user account creation.

---

## 🚀 Key Skills Demonstrated
* **SIEM Deployment & Configuration:** Setting up Wazuh managers and configuring custom agent parameters.
* **Detection Engineering:** Writing custom XML detection rules mapped to the MITRE ATT&CK framework.
* **Log Analysis & Threat Detection:** Analyzing raw security telemetry and interpreting Wazuh alert levels and rule IDs.
* **Adversary Simulation:** Using Kali Linux to generate realistic security events in a controlled environment.

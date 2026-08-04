# mini-soc-detection-platform-
A hands-on SOC Detection Response Platform built using Wazuh, Elastic Stack, Sigma Rules, and MITRE ATT&CK.

# Overview
The **Mini SOC Detection & Response Platform** is a hands-on Security Operations Center (SOC) lab built to simulate real-world security monitoring, threat detection, and incident response. The project combines open-source security tools to collect endpoint telemetry, detect malicious activities using Sigma rules, visualize alerts through the Elastic Stack, and map detections to the MITRE ATT&CK framework.

The platform consists of a central Ubuntu Server hosting the Wazuh platform and Elastic Stack, monitored Windows and Linux endpoints running Wazuh agents, and a Kali Linux machine used to simulate cyber attacks. Attack scenarios are executed in a controlled lab environment to validate detections and improve security monitoring capabilities.

This project demonstrates practical SOC analyst skills including SIEM deployment, detection engineering, log analysis, threat hunting, MITRE ATT&CK mapping, dashboard creation, and incident response validation. It is designed as a portfolio project to showcase end-to-end SOC operations using industry-standard tools.

# Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c9d2e4f9-b175-48ed-b3ca-2762d3a8e82e" />

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Ubuntu Server | Hosts the SOC platform |
| Docker & Docker Compose | Deploy and manage Wazuh services |
| Wazuh | SIEM/XDR platform for log collection, detection, and response |
| Wazuh Indexer | Stores and indexes security events |
| Wazuh Dashboard | Visualizes alerts and dashboards |
| Windows 10 | Monitored endpoint |
| Ubuntu Desktop | Monitored Linux endpoint |
| Sysmon | Enhanced Windows event logging |
| Auditd | Linux audit logging |
| Sigma | Detection rules for threat detection |
| MITRE ATT&CK | Maps detections to adversary techniques |
| Kali Linux | Attack simulation environment |
| Git & GitHub | Version control and project documentation |   

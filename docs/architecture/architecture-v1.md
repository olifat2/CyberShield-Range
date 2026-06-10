# CyberShield Range Architecture v1.0

## Document Information

| Field        | Value             |
| ------------ | ----------------- |
| Project      | CyberShield Range |
| Version      | 1.0               |
| Status       | Draft             |
| Author       | Olivier Fatombi   |
| Last Updated | June 2026         |

---

# 1. Purpose

This document defines the initial technical architecture of CyberShield Range.

The architecture provides the foundation for the development of an intelligent cyber range capable of:

* Simulating cyberattacks;
* Monitoring security events;
* Detecting threats;
* Assisting incident response;
* Supporting cybersecurity education and experimentation.

The architecture is designed to support both academic research and practical implementation.

---

# 2. High-Level Architecture

CyberShield Range consists of six main layers:

```text
Users
│
├── Learner
├── SOC Administrator
│
▼

SOC Dashboard

▼

Detection & Correlation Layer

▼

Log Collection Layer

▼

CyberHealth Application

▼

Cyber Lab Infrastructure

▼

Attack Simulation Engine
```

---

# 3. System Components

## 3.1 CyberHealth Application

CyberHealth serves as the primary target environment.

Purpose:

* Generate realistic user activity.
* Produce application logs.
* Provide attack surfaces.
* Support security experimentation.

Technology:

* Laravel
* PHP
* MySQL

Main Modules:

* Authentication
* Patient Management
* Medical Records
* Appointments
* User Management
* Audit Logs

---

## 3.2 Attack Simulation Engine

Responsible for executing attack scenarios.

Objectives:

* Reproduce realistic attack behaviors.
* Generate security events.
* Produce network and application traces.

Initial Attack Scenarios:

* SQL Injection
* Brute Force
* Session Hijacking
* Port Scanning
* Data Exfiltration

Future Scenarios:

* Privilege Escalation
* Lateral Movement
* Insider Threat Simulation

---

## 3.3 Log Collection Layer

Centralizes events generated across the platform.

Collected Sources:

* Laravel Logs
* Linux Logs
* MySQL Logs
* IDS Logs
* Simulation Logs

Purpose:

* Event aggregation.
* Centralized analysis.
* Long-term storage.

---

## 3.4 Detection Engine

Responsible for identifying malicious activity.

Detection Approaches:

### Signature-Based Detection

Known attack patterns.

Examples:

* SQL Injection signatures
* Port Scan signatures
* Brute Force signatures

### Rule-Based Detection

Event correlation.

Examples:

* Multiple failed logins
* Suspicious database access
* Reconnaissance followed by exploitation

### Behavioral Detection

Detection of abnormal activities.

---

## 3.5 AI Engine

Provides intelligent assistance for threat analysis.

Objectives:

* Anomaly detection.
* Threat scoring.
* Incident classification.
* Security recommendations.

Expected Inputs:

* Network events
* Application logs
* Detection alerts

Expected Outputs:

* Risk Score
* Attack Probability
* Recommended Actions

---

## 3.6 SOC Dashboard

Central supervision interface.

Features:

* Alert visualization
* Incident management
* Timeline analysis
* Threat scoring
* Event exploration

Users:

* SOC Administrator
* Learners

---

## 3.7 Response Engine

Provides semi-automated incident response.

Possible Actions:

* IP Blocking
* Session Termination
* Account Locking
* Alert Escalation
* Remediation Suggestions

Administrative validation remains required for critical actions.

---

# 4. Data Flow

The platform follows the following event processing workflow:

```text
Attack Simulation
        │
        ▼
CyberHealth
        │
        ▼
Logs Generation
        │
        ▼
Log Collection Layer
        │
        ▼
Detection Engine
        │
        ▼
AI Engine
        │
        ▼
SOC Dashboard
        │
        ▼
Response Engine
```

---

# 5. Technology Stack

## Application Development

* PHP
* Laravel
* REST API

## Database

* MySQL

## Infrastructure

* Ubuntu Linux
* Docker
* Docker Compose

## Network Security

* Suricata
* Wireshark
* Nmap

## Security Monitoring

* Wazuh

## Artificial Intelligence

* Python
* Pandas
* Scikit-Learn
* Jupyter Notebook

## Version Control

* Git
* GitHub

---

# 6. Security Layers

CyberShield Range adopts a defense-in-depth approach.

## Layer 1 — Application Security

CyberHealth:

* Authentication
* Authorization
* Session Management
* Input Validation

---

## Layer 2 — Network Security

Monitoring:

* Network Traffic Analysis
* IDS Detection
* Traffic Inspection

Tools:

* Suricata
* Wireshark

---

## Layer 3 — Host Security

Monitoring:

* System Logs
* Process Activity
* Authentication Events

Tool:

* Wazuh

---

## Layer 4 — Detection and Correlation

Combines:

* Signatures
* Rules
* Behavioral Analysis

Purpose:

* Reduce false positives.
* Improve attack visibility.

---

## Layer 5 — AI-Assisted Security

Provides:

* Threat Scoring
* Incident Classification
* Response Recommendations

---

# 7. Initial Docker Infrastructure

Planned Containers:

```text
cyberhealth-app
cyberhealth-db
suricata
wazuh
soc-dashboard
ai-engine
```

Future containers may be added as the platform evolves.

---

# 8. Future Evolution

The architecture is intentionally modular to support future enhancements:

* CyberShield Academy
* Additional target applications
* Advanced threat simulations
* Distributed infrastructure
* AI-powered threat hunting
* Automated remediation workflows

---

# 9. Conclusion

CyberShield Range Architecture v1.0 establishes the technical foundation of an intelligent cyber range integrating attack simulation, security monitoring, threat detection, incident response and cybersecurity education.

This architecture will evolve iteratively throughout the project lifecycle while preserving modularity, scalability and research relevance.

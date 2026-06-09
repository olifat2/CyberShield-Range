# CyberShield Range

> Intelligent cyber range combining web security, network monitoring, threat detection and incident response.

---

## Overview

CyberShield Range is an intelligent cybersecurity training and experimentation platform designed to simulate cyberattacks, monitor security events, detect threats, and assist incident response operations within a controlled environment.

The project aims to bridge the gap between offensive security training and defensive security operations by providing a realistic cyber range where learners can:

* Launch attack simulations.
* Observe attack traces in real time.
* Analyze security events.
* Study detection mechanisms.
* Experiment with incident response strategies.
* Explore AI-assisted threat analysis.

---

## Vision

CyberShield Range aims to become a complete cybersecurity ecosystem integrating:

* Cybersecurity education
* Web application security
* Network security monitoring
* Threat detection
* Security Operations Center (SOC) practices
* AI-assisted incident analysis

The platform is designed as both a research project and a practical training environment.

---

## Core Objectives

* Simulate realistic cyberattack scenarios.
* Provide hands-on cybersecurity training.
* Correlate application and network events.
* Detect threats using hybrid approaches.
* Assist administrators in incident response.
* Build a practical SOC-oriented learning environment.

---

## Main Components

### CyberHealth

A realistic healthcare management application used as the primary attack target.

Features include:

* Patient management
* Medical records
* Appointments
* User authentication
* Role management

---

### Attack Simulation Engine

Supports attack scenarios such as:

* SQL Injection
* Brute Force
* Session Hijacking
* Port Scanning
* Data Exfiltration
* Privilege Escalation

---

### Detection Engine

Hybrid detection approach:

* Signature-based detection
* Rule-based correlation
* Behavioral analysis
* AI-assisted anomaly detection

---

### SOC Dashboard

Provides:

* Real-time alerts
* Incident timeline
* Threat scoring
* Detection analytics
* Response recommendations

---

### Response Engine

Possible actions:

* IP blocking
* Session termination
* Administrator notifications
* Assisted remediation

---

## High-Level Architecture

```text
Internet
    |
Firewall / Reverse Proxy
    |
CyberHealth Application
    |
Log Collection Layer
    |
Detection Engine
    |
AI Engine
    |
SOC Dashboard
    |
Response Engine
```

---

## Technologies

### Development

* PHP
* Laravel
* REST API

### Infrastructure

* Docker
* Docker Compose
* Ubuntu Linux

### Network Security

* Suricata
* Wazuh
* Zeek
* Wireshark

### Artificial Intelligence

* Python
* Pandas
* Scikit-Learn
* Jupyter Notebook

### Databases

* MySQL
* Elasticsearch

---

## Roadmap

### Phase 1 — Foundations

* [ ] Project architecture
* [ ] Docker laboratory
* [ ] Network fundamentals
* [ ] OWASP studies

### Phase 2 — CyberHealth

* [ ] Core application
* [ ] Authentication
* [ ] User management
* [ ] Logging system

### Phase 3 — Attack Simulation

* [ ] SQL Injection scenarios
* [ ] Brute Force scenarios
* [ ] Session attacks
* [ ] Port scanning scenarios

### Phase 4 — Detection

* [ ] Suricata integration
* [ ] Wazuh integration
* [ ] Event correlation

### Phase 5 — Artificial Intelligence

* [ ] Data collection
* [ ] Anomaly detection
* [ ] Threat scoring

### Phase 6 — Response

* [ ] Semi-automatic response
* [ ] Alert management
* [ ] Incident handling

---

## Research Direction

Master's research focus:

> Designing an intelligent cyber range capable of correlating web application and network security events to improve cyberattack detection and incident response through hybrid detection techniques and artificial intelligence.

---

## Repository Structure

```text
CyberShield-Range
│
├── docs/
├── cyberhealth/
├── simulations/
├── detection/
├── ai-engine/
├── dashboard/
├── infrastructure/
├── lab/
├── assets/
│
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## Author

**Olivier Fatombi**

System & Network Administrator (Linux & Windows)
Full-Stack Developer
Cybersecurity Research Enthusiast

---

## Project Status

This project is currently in the planning and architecture phase as part of a long-term cybersecurity research and development initiative.

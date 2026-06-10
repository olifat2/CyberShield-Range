# Cyber Lab Infrastructure v1.0

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

This document defines the initial Cyber Lab infrastructure used by CyberShield Range.

The laboratory provides a controlled environment for:

* cybersecurity experimentation;
* attack simulation;
* security monitoring;
* threat detection;
* incident response training.

The infrastructure must remain lightweight enough to run on a personal workstation while remaining realistic.

---

# 2. Infrastructure Objectives

The Cyber Lab must support:

* realistic attack scenarios;
* web application monitoring;
* network traffic analysis;
* centralized logging;
* threat detection;
* AI-assisted analysis.

---

# 3. Logical Architecture

```text
Learner
   |
   v

Attack Simulation Engine
   |
   v

CyberHealth Application
   |
   +-------------------+
   |                   |
   v                   v

Application Logs   Network Traffic
   |                   |
   v                   v

Wazuh             Suricata
   |                   |
   +---------+---------+
             |
             v

     Detection Engine
             |
             v

         AI Engine
             |
             v

      SOC Dashboard
```

---

# 4. Infrastructure Components

## CyberHealth Container

Purpose:

* Main target application.
* Generates realistic business activity.
* Produces application logs.

Technology:

* Laravel
* PHP
* Nginx

---

## Database Container

Purpose:

* Stores application data.

Technology:

* MySQL

---

## Attack Simulation Container

Purpose:

* Executes predefined attack scenarios.

Examples:

* SQL Injection
* Brute Force
* Session Hijacking
* Port Scanning

---

## Suricata Container

Purpose:

* Monitor network traffic.
* Detect malicious patterns.
* Generate IDS alerts.

Outputs:

* Security alerts
* Network events

---

## Wazuh Container

Purpose:

* Collect logs.
* Monitor hosts.
* Centralize security events.

Sources:

* Laravel
* Linux
* MySQL
* Suricata

---

## AI Engine Container

Purpose:

* Analyze events.
* Detect anomalies.
* Produce threat scores.

Technology:

* Python
* Scikit-Learn

---

## SOC Dashboard Container

Purpose:

* Visualize incidents.
* Manage alerts.
* Review recommendations.

Users:

* Learners
* SOC Administrators

---

# 5. Initial Network Design

```text
Cyber Lab Network

192.168.100.0/24

------------------------------------------------

Attack Simulation

192.168.100.10

------------------------------------------------

CyberHealth

192.168.100.20

------------------------------------------------

Database

192.168.100.30

------------------------------------------------

Suricata

192.168.100.40

------------------------------------------------

Wazuh

192.168.100.50

------------------------------------------------

AI Engine

192.168.100.60

------------------------------------------------

SOC Dashboard

192.168.100.70
```

The addressing scheme is illustrative and may evolve during implementation.

---

# 6. Event Collection Flow

Application Events:

```text
CyberHealth
    |
    v
Wazuh
    |
    v
SOC Dashboard
```

Network Events:

```text
Network Traffic
       |
       v
Suricata
       |
       v
Wazuh
       |
       v
SOC Dashboard
```

Threat Analysis:

```text
Wazuh
   |
   v
AI Engine
   |
   v
Risk Score
   |
   v
SOC Dashboard
```

---

# 7. Deployment Strategy

Phase 1:

Single workstation deployment.

Environment:

* Ubuntu Linux
* Docker
* Docker Compose

---

Phase 2:

Cloud deployment.

Environment:

* VPS
* Docker
* Domain name

---

# 8. Resource Considerations

Development Hardware:

* Intel Core i7
* 16 GB RAM
* Ubuntu Linux

Expected Compatibility:

The initial infrastructure is designed to operate efficiently within these hardware constraints.

---

# 9. Future Expansion

Future versions may include:

* multiple target applications;
* distributed environments;
* virtual machine integration;
* advanced network segmentation;
* threat hunting environments.

---

# 10. Conclusion

The Cyber Lab Infrastructure provides the operational foundation of CyberShield Range.

It establishes the environment where attacks are simulated, events are collected, threats are detected and incident response activities are performed.

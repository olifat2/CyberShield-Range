# CyberHealth Functional Specifications v1.0

## Document Information

| Field        | Value             |
| ------------ | ----------------- |
| Project      | CyberShield Range |
| Component    | CyberHealth       |
| Version      | 1.0               |
| Status       | Draft             |
| Author       | Olivier Fatombi   |
| Last Updated | June 2026         |

---

# 1. Introduction

CyberHealth is the primary target application used within CyberShield Range.

It simulates a healthcare information system that manages patients, medical staff, appointments and medical records.

The application serves two purposes:

1. Provide realistic healthcare workflows.
2. Generate security-relevant events for cybersecurity training and experimentation.

---

# 2. Objectives

CyberHealth must:

* support realistic business operations;
* generate application logs;
* provide attack surfaces;
* support security monitoring;
* produce meaningful incident scenarios.

---

# 3. User Roles

## System Administrator

Responsibilities:

* Manage users.
* Manage permissions.
* Review audit logs.
* Configure the platform.

---

## Doctor

Responsibilities:

* Access patient records.
* Create medical reports.
* Manage appointments.

---

## Nurse

Responsibilities:

* View assigned patients.
* Update patient information.
* Manage appointment preparation.

---

## Receptionist

Responsibilities:

* Register patients.
* Schedule appointments.
* Update contact information.

---

## Patient

Responsibilities:

* Access personal information.
* View appointments.
* Download medical documents.

---

# 4. Core Modules

## Authentication Module

Features:

* Login
* Logout
* Password reset
* Session management

Security Events:

* Failed login attempts
* Successful logins
* Password changes
* Session creation

---

## User Management Module

Features:

* User creation
* Role assignment
* Account activation
* Account suspension

Security Events:

* Privilege changes
* User creation
* Account locking

---

## Patient Management Module

Features:

* Patient registration
* Profile updates
* Patient search

Security Events:

* Unauthorized access attempts
* Bulk data access
* Suspicious searches

---

## Medical Records Module

Features:

* Create records
* View records
* Update records
* Download reports

Security Events:

* Sensitive data access
* Record modifications
* Excessive downloads

---

## Appointment Module

Features:

* Create appointments
* Update appointments
* Cancel appointments

Security Events:

* Unauthorized modifications
* Suspicious scheduling activity

---

## Audit Trail Module

Features:

* Activity tracking
* Change history
* Security logging

Security Events:

* Administrative actions
* Sensitive operations
* Data exports

---

# 5. Main Data Entities

## Users

Fields:

* id
* name
* email
* password
* role
* status

---

## Patients

Fields:

* id
* patient_number
* full_name
* date_of_birth
* phone
* address

---

## Medical Records

Fields:

* id
* patient_id
* doctor_id
* diagnosis
* treatment
* notes

---

## Appointments

Fields:

* id
* patient_id
* doctor_id
* appointment_date
* status

---

## Audit Logs

Fields:

* id
* user_id
* action
* target
* timestamp
* ip_address

---

# 6. Security-Critical Assets

The following assets are considered sensitive:

## Patient Data

* Personal information
* Contact information

---

## Medical Records

* Diagnoses
* Treatments
* Medical history

---

## User Accounts

* Credentials
* Permissions

---

## Audit Logs

* Security events
* Administrative activities

---

# 7. Attack Surfaces

CyberHealth intentionally exposes attack surfaces for controlled simulations.

## Authentication

Potential Scenarios:

* Brute Force
* Credential Stuffing

---

## Search Features

Potential Scenarios:

* SQL Injection

---

## Session Management

Potential Scenarios:

* Session Hijacking

---

## File Downloads

Potential Scenarios:

* Unauthorized Data Access
* Data Exfiltration

---

## User Management

Potential Scenarios:

* Privilege Escalation

---

# 8. Security Events Generated

Examples:

* Failed login
* Successful login
* Password reset
* Session creation
* Session termination
* User creation
* User deletion
* Patient record access
* Record modification
* File download
* Permission change

---

# 9. Educational Scenarios

## Scenario 1

SQL Injection

Objective:

Extract patient information.

Expected Detection:

* Suricata alerts
* Wazuh logs
* AI anomaly score

---

## Scenario 2

Brute Force

Objective:

Compromise a user account.

Expected Detection:

* Multiple failed logins
* Risk score increase

---

## Scenario 3

Session Hijacking

Objective:

Reuse a stolen session.

Expected Detection:

* Abnormal session activity
* User behavior anomaly

---

## Scenario 4

Data Exfiltration

Objective:

Download sensitive records.

Expected Detection:

* Large data transfer
* Excessive access behavior

---

# 10. Future Modules

Future versions may include:

* Pharmacy Management
* Billing
* Laboratory Management
* Medical Imaging
* Telemedicine

---

# 11. Conclusion

CyberHealth provides a realistic healthcare management environment that serves as the primary target application for CyberShield Range.

It enables attack simulation, event generation, threat detection and cybersecurity education while maintaining a realistic business context.

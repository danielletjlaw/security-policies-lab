# Incident Response Policy

**Organization:** ShopCore (fictional)  
**Policy ID:** POL-IR-001  
**Version:** 1.0  
**Effective Date:** 2026-11-12  
**Review Cycle:** Annual  
**Owner:** Information Security Team  
**NIST Control Family:** IR — Incident Response (NIST SP 800-53 Rev. 5)

---

## 1. Purpose

This policy establishes ShopCore's requirements for preparing for, detecting, containing, and recovering from security incidents. It ensures that incidents are handled consistently, documented thoroughly, and communicated appropriately to minimize harm to customers, operations, and the organization.

---

## 2. Scope

This policy applies to:

- All ShopCore employees, contractors, and third-party vendors
- All systems, applications, and data owned or operated by ShopCore
- Any event that compromises or threatens the confidentiality, integrity, or availability of ShopCore systems or customer data

---

## 3. Definitions

| Term | Definition |
|---|---|
| **Security Event** | Any observable occurrence in a system or network (not all events are incidents) |
| **Security Incident** | An event that actually or potentially compromises confidentiality, integrity, or availability |
| **Data Breach** | A confirmed incident in which unauthorized parties accessed or exfiltrated protected data |
| **Severity Level** | A classification of incident urgency (see Section 3.1) |

### 3.1 Incident Severity Levels

| Level | Description | Example |
|---|---|---|
| **P1 — Critical** | Active compromise with ongoing data loss or system unavailability | Ransomware encrypting production database |
| **P2 — High** | Confirmed breach or significant system compromise, contained | Unauthorized admin account access confirmed |
| **P3 — Medium** | Suspected compromise or significant policy violation under investigation | Unusual login patterns from foreign IP |
| **P4 — Low** | Minor policy violation or anomaly with no confirmed impact | Single failed login attempt on admin account |

---

## 4. Policy Statements

### 4.1 Incident Response Plan

- ShopCore shall maintain a written Incident Response Plan (IRP) that details procedures for each phase of the incident response lifecycle: Preparation, Detection & Analysis, Containment, Eradication, Recovery, and Post-Incident Activity.
- The IRP shall be reviewed and tested **at least annually** through a tabletop exercise.

### 4.2 Reporting

- **All employees shall report suspected security incidents immediately** to the Information Security Team at the designated incident reporting channel.
- Employees shall not attempt to investigate or remediate a suspected incident on their own. Attempting to cover up or delay reporting of an incident is a policy violation.
- P1 and P2 incidents shall be escalated to the CISO (or equivalent) within **1 hour** of detection.

### 4.3 Response Timelines

| Severity | Initial Response | Containment Target | Customer Notification (if breach) |
|---|---|---|---|
| P1 — Critical | 15 minutes | 2 hours | 72 hours (or as required by law) |
| P2 — High | 1 hour | 8 hours | 72 hours (or as required by law) |
| P3 — Medium | 4 hours | 24 hours | As applicable |
| P4 — Low | 1 business day | 5 business days | Not typically required |

### 4.4 Containment and Eradication

- Affected systems shall be isolated from the network as soon as a P1 or P2 incident is confirmed, unless isolation would destroy forensic evidence needed for investigation.
- No affected system shall be rebuilt or wiped until forensic evidence has been preserved and approved for release by the Information Security Team.
- Root cause shall be identified and documented before any system is returned to production.

### 4.5 Evidence Preservation

- All logs, screenshots, and artifacts related to a security incident shall be preserved in a tamper-evident format for a minimum of **12 months**.
- Chain of custody shall be documented for any evidence that may be used in legal proceedings.

### 4.6 External Notification

- If a data breach involves customer PII or payment card data, ShopCore's Legal team shall be notified immediately to assess regulatory notification obligations.
- Notification to affected customers, regulators, and law enforcement shall follow applicable legal requirements and ShopCore's breach notification procedures.

### 4.7 Post-Incident Review

- A Post-Incident Review (PIR) shall be conducted within **5 business days** of closing any P1 or P2 incident.
- The PIR shall document: timeline of events, root cause, what worked, what failed, and corrective actions with assigned owners and due dates.
- PIR findings shall be used to update the IRP and any relevant risk register entries.

---

## 5. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Information Security Team | Lead incident response; maintain the IRP; conduct PIRs |
| IT Operations | Provide technical support for containment and recovery |
| Legal / Compliance | Advise on notification obligations; manage external communications |
| CISO (or equivalent) | Approve major containment decisions; own executive escalation |
| All Employees | Report suspected incidents immediately; cooperate with investigations |

---

## 6. Compliance

Failure to report a suspected security incident, or any attempt to conceal an incident, is a serious policy violation and may result in immediate termination and legal liability. Cooperation with incident investigations is mandatory for all employees.

---

## 7. Review Cycle

This policy shall be reviewed annually and after any P1 or P2 incident that reveals a gap in policy coverage.

---

## 8. References

- NIST SP 800-53 Rev. 5: IR-1 (Policy), IR-2 (Training), IR-4 (Incident Handling), IR-5 (Monitoring), IR-6 (Reporting), IR-8 (Plan)
- NIST SP 800-61r3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management

# Security Policies — ShopCore E-Commerce Application

**Author:** Danielle Law  
**Framework:** NIST SP 800-53 Rev. 5  
**System:** ShopCore (fictional e-commerce web application)  
**Status:** Complete

---

## About This Project

This project contains four security policies for ShopCore, a fictional cloud-hosted e-commerce platform. Each policy is aligned to a NIST SP 800-53 Rev. 5 control family and written to be enforceable — not just theoretical.

These policies are designed to address risks identified in the companion [Risk Register project](https://github.com/danielletjlaw/risk-register-lab), demonstrating how policies back up risk treatment plans.

---

## Policies in This Repo

| File | Policy | NIST Control Family |
|---|---|---|
| `access-control-policy.md` | Access Control Policy | AC — Access Control |
| `incident-response-policy.md` | Incident Response Policy | IR — Incident Response |
| `data-classification-policy.md` | Data Classification Policy | RA / MP — Risk Assessment / Media Protection |
| `password-authentication-policy.md` | Password & Authentication Policy | IA — Identification & Authentication |

---

## How Policies Are Structured

Each policy follows a consistent structure:

1. **Purpose** — why this policy exists
2. **Scope** — who and what it applies to
3. **Policy Statements** — the actual rules (shall/shall not)
4. **Roles and Responsibilities** — who owns enforcement
5. **Compliance** — consequences of violation
6. **Review Cycle** — how often it is reviewed
7. **References** — NIST controls and other standards cited

---

## Relationship to the Risk Register

| Risk Register Entry | Policy That Addresses It |
|---|---|
| R-001 SQL Injection | Access Control Policy (least privilege, developer access) |
| R-002 Credential Stuffing | Password & Authentication Policy (MFA, lockout) |
| R-004 Ransomware via Phishing | Incident Response Policy (detection, containment) |
| R-005 XSS / Session Hijacking | Access Control Policy (session management) |
| R-008 Insider Threat | Access Control Policy (RBAC, monitoring) |
| R-013 PII in Logs | Data Classification Policy (data handling) |

---

*This is a fictional scenario created for portfolio purposes. No real customer data or systems are involved.*

# Password & Authentication Policy

**Organization:** ShopCore (fictional)  
**Policy ID:** POL-IA-001  
**Version:** 1.0  
**Effective Date:** 2026-11-12  
**Review Cycle:** Annual  
**Owner:** Information Security Team / Identity & Access Team  
**NIST Control Family:** IA — Identification & Authentication (NIST SP 800-53 Rev. 5)

---

## 1. Purpose

This policy establishes minimum requirements for passwords, multi-factor authentication, and account security at ShopCore. Its purpose is to prevent unauthorized access to ShopCore systems and customer accounts through weak, stolen, or compromised credentials.

---

## 2. Scope

This policy applies to:

- All ShopCore employee, contractor, and service account credentials
- All customer accounts on the ShopCore platform
- All systems, applications, and APIs that use password-based or token-based authentication

---

## 3. Policy Statements

### 3.1 Password Requirements — Employee and Admin Accounts

- Passwords shall be a **minimum of 15 characters**.
- Passwords shall not contain the employee's name, username, or ShopCore's name.
- Passwords shall be checked against a list of known-breached passwords at creation and reset. Passwords found in breach databases shall be rejected.
- Passwords shall not be required to expire on a fixed schedule **unless** there is evidence of compromise. (Per NIST SP 800-63B, forced periodic rotation without a breach trigger leads to weaker passwords, not stronger ones.)
- Passwords shall never be written down, shared, stored in plaintext, or transmitted via email or chat.

### 3.2 Password Requirements — Customer Accounts

- Customer passwords shall be a **minimum of 12 characters**.
- Customers shall be encouraged (not required) to use a passphrase.
- Customer passwords shall be checked against known-breached password lists at account creation and each password change.
- ShopCore shall never display a customer's password in plaintext at any time, including in support tools.

### 3.3 Password Storage

- All passwords shall be stored using an adaptive hashing algorithm: **bcrypt, scrypt, or Argon2**. MD5, SHA-1, and unsalted SHA-256 are prohibited for password storage.
- Password hashes shall never be logged, exported, or included in backups that are accessible to non-DBA roles.

### 3.4 Multi-Factor Authentication (MFA)

- MFA is **required** for all employee and admin accounts without exception.
- MFA is **required** for all access to the ShopCore admin portal, cloud infrastructure console, and production systems.
- MFA is **strongly recommended** for customer accounts and shall be offered as an opt-in feature at account creation.
- Acceptable MFA methods:
  - TOTP authenticator app (e.g., Google Authenticator, Authy) — **preferred**
  - Hardware security key (FIDO2/WebAuthn) — **preferred**
  - SMS one-time code — **acceptable** (note: vulnerable to SIM-swapping; not recommended for admin accounts)
  - Email one-time code — **acceptable for customers only**
- Security questions alone do not constitute a second factor and shall not be used as MFA.

### 3.5 Account Lockout

- Employee and admin accounts shall be locked after **5 consecutive failed login attempts**.
- Customer accounts shall be locked after **10 consecutive failed login attempts**.
- Lockout duration: **30 minutes** (automatic unlock) or immediate unlock by IT upon verification of identity.
- All lockout events shall be logged and reviewed by the Information Security Team for patterns indicating a credential stuffing or brute force attack.

### 3.6 Default and Service Account Credentials

- Default credentials on all systems, devices, and applications shall be changed before deployment to production. No system shall go live with a vendor default password.
- Service accounts (used by applications, not humans) shall have long, randomly generated passwords (minimum 32 characters) stored in a secrets management system (e.g., AWS Secrets Manager). Service account credentials shall never be hardcoded in source code.
- Service accounts shall not have interactive login capability unless operationally required, and that requirement must be documented and approved.

### 3.7 Password Managers

- Employees are strongly encouraged to use an approved enterprise password manager for storing and generating credentials. Storing passwords in browser auto-fill for admin systems is prohibited.

### 3.8 Credential Compromise Response

- If an employee suspects their credentials have been compromised, they shall immediately report it to the Information Security Team and change their password.
- If ShopCore detects that customer credentials may have been exposed (e.g., via a breach of a third-party service using the same email/password), potentially affected customers shall be notified and required to reset their password at next login.

---

## 4. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Identity & Access Team | Enforce technical password and MFA controls; manage lockout policies |
| Information Security Team | Own and audit this policy; review lockout logs for attack patterns |
| All Employees | Follow password requirements; never share credentials; report compromise |
| Developers | Implement secure password storage (bcrypt/Argon2); never hardcode credentials |

---

## 5. Compliance

Using, sharing, or storing credentials in a manner inconsistent with this policy is a violation subject to disciplinary action. Hardcoding credentials in source code is a critical violation that may result in immediate termination and mandatory security review of all affected systems.

---

## 6. Review Cycle

This policy shall be reviewed annually and whenever NIST SP 800-63B guidance is updated or a credential-related incident occurs.

---

## 7. References

- NIST SP 800-53 Rev. 5: IA-1 (Policy), IA-2 (User Identification and Authentication), IA-5 (Authenticator Management), IA-6 (Authentication Feedback), IA-11 (Re-Authentication)
- NIST SP 800-63B: Digital Identity Guidelines — Authentication and Lifecycle Management

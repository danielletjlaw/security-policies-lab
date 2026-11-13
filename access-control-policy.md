# Access Control Policy

**Organization:** ShopCore (fictional)  
**Policy ID:** POL-AC-001  
**Version:** 1.0  
**Effective Date:** 2026-11-12  
**Review Cycle:** Annual  
**Owner:** Information Security Team  
**NIST Control Family:** AC — Access Control (NIST SP 800-53 Rev. 5)

---

## 1. Purpose

This policy establishes requirements for controlling access to ShopCore systems, applications, and data. Its purpose is to ensure that access is granted based on business need, limited to the minimum necessary, and revoked promptly when no longer required.

---

## 2. Scope

This policy applies to:

- All ShopCore employees, contractors, and third-party vendors
- All systems, applications, databases, and cloud resources owned or operated by ShopCore
- All access methods, including direct system access, API access, and administrative interfaces

---

## 3. Policy Statements

### 3.1 Least Privilege

- **All users shall be granted only the minimum level of access required to perform their job function.** Access shall not be granted based on role title alone; each request must include a documented business justification.
- Privileged (administrative) access shall be separate from standard user accounts. No employee shall use an admin account for routine daily tasks.
- Production database access shall be restricted to designated database administrators only. Application developers shall not have direct access to production databases.

### 3.2 Access Provisioning and Deprovisioning

- Access to all ShopCore systems shall be formally requested, approved by the employee's manager, and provisioned by the IT team before use.
- When an employee changes roles, access inconsistent with the new role shall be removed within **5 business days**.
- When an employee separates from ShopCore (voluntary or involuntary), all system access shall be revoked within **24 hours** of the separation date. Involuntary separations require revocation at the time of notification.
- A formal access review shall be conducted **quarterly** to verify that all active access remains appropriate.

### 3.3 Role-Based Access Control (RBAC)

- Access to ShopCore systems shall be managed through defined roles. Permissions are assigned to roles, and users are assigned to roles — not granted permissions individually.
- The following roles are defined for the ShopCore application:

| Role | Access Level |
|---|---|
| Customer | Own account data only |
| Support Agent | Read-only access to customer accounts; no payment data |
| Developer | Development and staging environments only; no production data |
| Database Administrator | Production database access; no application code deployment |
| System Administrator | Full infrastructure access; audited at all times |
| Security Team | Read access to all logs and audit trails |

### 3.4 Session Management

- Application sessions shall expire after **30 minutes of inactivity** for customer accounts and **15 minutes** for admin accounts.
- Session tokens shall be invalidated upon logout. Applications shall not reuse session tokens across sessions.
- Session cookies shall have the `HttpOnly` and `Secure` flags set at all times.

### 3.5 Remote Access

- Remote access to internal ShopCore systems shall require VPN authentication in addition to standard credentials.
- The ShopCore admin portal shall not be accessible from the public internet. Access shall be restricted to approved corporate IP ranges or VPN.

### 3.6 Third-Party Access

- Third-party vendors requiring system access shall be granted the minimum access necessary for the specific engagement and for the duration of that engagement only.
- All third-party access shall be documented, approved by the Information Security Team, and reviewed monthly.

---

## 4. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Information Security Team | Own and enforce this policy; conduct quarterly access reviews |
| IT / Identity & Access Team | Provision and deprovision access per approved requests |
| Managers | Approve access requests; notify IT within 24 hours of a separation |
| All Employees | Use only authorized access; report suspected unauthorized access |

---

## 5. Compliance

Violations of this policy may result in disciplinary action up to and including termination of employment or contract. Violations that result in unauthorized data exposure may also carry legal consequences under applicable data protection regulations.

---

## 6. Review Cycle

This policy shall be reviewed annually by the Information Security Team and updated as needed to reflect changes in technology, regulation, or business operations.

---

## 7. References

- NIST SP 800-53 Rev. 5: AC-1 (Policy), AC-2 (Account Management), AC-3 (Access Enforcement), AC-5 (Separation of Duties), AC-6 (Least Privilege), AC-11 (Session Lock), AC-17 (Remote Access)
- NIST SP 800-63B: Digital Identity Guidelines

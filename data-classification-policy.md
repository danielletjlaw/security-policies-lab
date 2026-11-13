# Data Classification Policy

**Organization:** ShopCore (fictional)  
**Policy ID:** POL-DC-001  
**Version:** 1.0  
**Effective Date:** 2026-11-12  
**Review Cycle:** Annual  
**Owner:** Information Security Team  
**NIST Control Families:** RA — Risk Assessment / MP — Media Protection (NIST SP 800-53 Rev. 5)

---

## 1. Purpose

This policy establishes a classification scheme for ShopCore data so that employees understand how to handle, store, transmit, and dispose of information based on its sensitivity. Proper classification reduces the risk of accidental data exposure and ensures that the most sensitive data receives the strongest protections.

---

## 2. Scope

This policy applies to:

- All data created, collected, processed, stored, or transmitted by ShopCore in any format (digital or physical)
- All employees, contractors, and third-party vendors with access to ShopCore data

---

## 3. Data Classification Tiers

ShopCore uses four classification tiers. When in doubt, classify data at the **higher** tier.

### Tier 1 — Restricted

**Definition:** The most sensitive data. Unauthorized disclosure would cause severe harm to customers, the business, or regulatory standing.

**Examples:**
- Payment card data (card numbers, CVVs, expiration dates)
- Customer Social Security Numbers or government-issued IDs
- Authentication credentials (passwords, API keys, session tokens)
- Encryption keys and certificates
- Security audit reports and vulnerability assessments

**Handling Requirements:**
- Encrypted at rest (AES-256 or equivalent) and in transit (TLS 1.2 minimum)
- Access restricted to named individuals with documented business need; no group access
- Shall not be stored in logs, emails, or unencrypted files under any circumstances
- Shall not be copied to development or test environments
- Disposal: cryptographic erasure or certified physical destruction

---

### Tier 2 — Confidential

**Definition:** Sensitive business or personal data. Unauthorized disclosure would cause meaningful harm but not necessarily catastrophic impact.

**Examples:**
- Customer PII (names, addresses, email addresses, phone numbers)
- Order history and purchase records
- Employee personnel records
- Internal financial data and contracts
- System architecture diagrams and network topology

**Handling Requirements:**
- Encrypted at rest and in transit
- Access restricted to employees with a business need; documented in access control lists
- Shall not be shared with third parties without a signed Data Processing Agreement (DPA)
- Shall not be stored in personal cloud storage (Google Drive, Dropbox, etc.)
- Disposal: secure deletion (minimum 7-pass overwrite) or physical shredding

---

### Tier 3 — Internal

**Definition:** Non-sensitive operational information. Unauthorized disclosure would cause limited harm but is still not intended for public release.

**Examples:**
- Internal policies and procedures
- Meeting notes and project plans
- Help desk tickets and change logs
- General IT inventory and asset lists

**Handling Requirements:**
- Not required to be encrypted at rest, but encryption is recommended
- Access restricted to ShopCore employees and authorized contractors
- Shall not be posted to public websites, social media, or external forums
- Disposal: standard deletion or recycling bin emptying

---

### Tier 4 — Public

**Definition:** Information approved for public release. No restrictions on distribution.

**Examples:**
- Marketing materials and press releases
- Product descriptions and pricing
- Public-facing website content
- Job postings

**Handling Requirements:**
- No special handling requirements
- Verify accuracy before publication; once public, it cannot be recalled
- Label clearly as "Approved for Public Release" before distributing externally

---

## 4. Labeling

- **Digital files:** Classification tier shall be noted in the document header or file metadata where technically feasible (e.g., "Classification: Restricted").
- **Emails:** Employees shall include the classification tier in the subject line when emailing Restricted or Confidential data (e.g., "[CONFIDENTIAL]").
- **Physical documents:** Restricted and Confidential physical documents shall be labeled on the cover page.

---

## 5. Data Handling Rules Summary

| Requirement | Restricted | Confidential | Internal | Public |
|---|---|---|---|---|
| Encrypt at rest | Required | Required | Recommended | Not required |
| Encrypt in transit | Required | Required | Recommended | Not required |
| Access control | Named individuals | Need-to-know | All employees | Unrestricted |
| Copy to dev/test | Never | Only if masked | Allowed | Allowed |
| Share with third parties | Prohibited without explicit approval | Requires DPA | With manager approval | Freely |
| Log/email storage | Never | Avoid | Allowed | Allowed |

---

## 6. Special Rules for Logs

- Application logs shall **never** contain Restricted data (payment card numbers, passwords, session tokens).
- Logs containing Confidential data (customer PII) shall be treated as Confidential, access-restricted, and retained for no longer than **90 days** unless required for an active investigation.
- Log access shall be limited to the Information Security Team and designated IT operations staff.

---

## 7. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Information Security Team | Own this policy; audit compliance; classify new data types |
| Data Owners (business unit leads) | Classify data their team creates; ensure team compliance |
| All Employees | Classify and handle data per this policy; report misclassification |
| IT / DevSecOps | Enforce technical controls (encryption, access restrictions) |

---

## 8. Compliance

Mishandling of Restricted or Confidential data, including sending it to unauthorized parties or storing it in unsecured locations, is a policy violation and may result in disciplinary action, termination, and legal liability under applicable privacy regulations.

---

## 9. Review Cycle

This policy shall be reviewed annually and whenever ShopCore begins processing a new category of sensitive data.

---

## 10. References

- NIST SP 800-53 Rev. 5: RA-2 (Security Categorization), MP-1 (Policy), MP-2 (Media Access), MP-3 (Media Marking), MP-6 (Media Sanitization)
- NIST FIPS 199: Standards for Security Categorization of Federal Information and Information Systems

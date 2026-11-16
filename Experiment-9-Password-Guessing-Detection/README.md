# Experiment 9: Password-Guessing Detection and Mitigation

## 1. Objective

Analyze a small set of fictional authentication events, identify signs of password guessing, and recommend controls to reduce the risk and impact of account compromise.

## 2. Scope and safety

This is a defensive, offline exercise. Use only the synthetic events in this document or instructor-provided, sanitized logs. Do not attempt logins, run password-guessing tools, or test real accounts or systems.

## 3. Fictional event data

The following records are invented for this exercise. All times are UTC.

| Time | Account | Source | Result |
|---|---|---|---|
| 09:00:11 | `alex@example.test` | `198.51.100.24` | Failed |
| 09:00:18 | `sam@example.test` | `198.51.100.24` | Failed |
| 09:00:25 | `jordan@example.test` | `198.51.100.24` | Failed |
| 09:00:33 | `taylor@example.test` | `198.51.100.24` | Failed |
| 09:01:02 | `alex@example.test` | `198.51.100.24` | Failed |
| 09:01:14 | `sam@example.test` | `198.51.100.24` | Failed |
| 09:01:29 | `jordan@example.test` | `198.51.100.24` | Failed |

The documentation-only IP address is reserved for examples. The events do not establish that any account was accessed successfully.

## 4. Procedure

### Step 1: Review and summarize

Using only the event table, record:

1. The time window covered and total number of failures.
2. The number of distinct accounts and source addresses.
3. Whether failures are concentrated on one account or distributed across several accounts.
4. What the evidence confirms, and what it does not establish.

### Step 2: Assess the pattern

Explain why repeated failures across multiple accounts from one source may warrant investigation. Compare this pattern with repeated failures against a single account. Do not conclude that an attack succeeded or identify an actor based on these records alone.

### Step 3: Recommend defensive actions

Propose actions suitable for an organization’s identity and incident-response teams:

- Correlate authentication events with the identity provider, application, VPN, and endpoint logs for the same time window.
- Check for successful sign-ins, unusual locations or devices, password resets, and changes to account recovery settings.
- Apply risk-based rate limits and alerts, with safeguards to avoid locking out legitimate users or enabling denial of service.
- Require multifactor authentication, especially for privileged and remotely accessible accounts.
- Use breached-password screening and user education to reduce reuse of weak or exposed passwords.
- If compromise is confirmed, follow the organization’s incident-response process to secure affected accounts, revoke active sessions, preserve evidence, and notify the appropriate responders.

For each recommendation, identify the evidence that would trigger it and the team responsible.

### Step 4: Document the assessment

Complete a summary table:

| Finding | Evidence | Confidence or limitation | Defensive follow-up |
|---|---|---|---|
| Failures were distributed across several accounts | One source has repeated failures for multiple accounts in the same short interval | Suspicious pattern; does not prove a successful login or malicious intent | Correlate identity-provider and application logs |
| No successful sign-in is shown | Every supplied record is marked failed | The sample may not include all relevant events | Review the complete authentication timeline |

## 5. Result

The synthetic authentication records were assessed for suspicious patterns, evidentiary limits were documented, and defensive monitoring and account-protection measures were proposed without testing any real account or system.

## 6. References

- [NIST SP 800-63B: Digital Identity Guidelines — Authentication and Lifecycle Management](https://pages.nist.gov/800-63-4/sp800-63b.html)
- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)

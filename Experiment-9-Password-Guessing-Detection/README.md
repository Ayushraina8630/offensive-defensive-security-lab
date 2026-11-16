# Experiment 9: Password-Guessing Detection and Mitigation

## 1. Objective

Analyze fictional authentication events to identify patterns consistent with password guessing, then recommend and validate defensive controls without attempting logins against real accounts or systems.

## 2. Scope and safety

This is a defensive log-analysis exercise. Use only the fictional records below or sanitized logs provided by an instructor. Do not run password-guessing tools, test credentials, or access systems unless you have explicit authorization and an approved isolated lab.

## 3. Fictional authentication records

All names and addresses below are fictional. `FAIL` means an authentication attempt was rejected; `SUCCESS` means it was accepted.

| Time (UTC) | Account | Source address | Result |
|---|---|---|---|
| 09:00 | alex | 192.0.2.41 | FAIL |
| 09:01 | alex | 192.0.2.41 | FAIL |
| 09:02 | alex | 192.0.2.41 | FAIL |
| 09:03 | alex | 192.0.2.41 | FAIL |
| 09:04 | alex | 192.0.2.41 | FAIL |
| 09:05 | alex | 192.0.2.41 | SUCCESS |
| 09:06 | sam | 198.51.100.27 | FAIL |
| 09:06 | lee | 198.51.100.27 | FAIL |
| 09:07 | pat | 198.51.100.27 | FAIL |
| 09:08 | alex | 203.0.113.8 | FAIL |
| 09:09 | lee | 203.0.113.8 | SUCCESS |

## 4. Procedure

### Step 1: Summarize the events

Group the records by account and source address. Count failed and successful attempts, and note the time window for each group.

### Step 2: Identify suspicious patterns

Look for repeated failures against one account, attempts against multiple accounts from one source, and a successful login shortly after repeated failures. Treat these patterns as signals for investigation, not proof of malicious activity or account compromise.

For this sample, the records show repeated failures for `alex` followed by a success, and several accounts receiving failures from one source. The success for `lee` from a different source should be reviewed in its own context.

### Step 3: Recommend defensive checks

For each signal, identify what additional authorized evidence would help validate it, such as identity-provider logs, MFA outcomes, account lockout events, source reputation from approved services, and the user's confirmation of expected activity. Preserve relevant records according to the organization's incident-response process.

### Step 4: Select and validate mitigations

Recommend controls appropriate to the environment, such as:

- Require multi-factor authentication, especially for privileged and remotely accessible accounts.
- Use rate limits, progressive delays, and risk-based challenges to reduce repeated attempts while accounting for legitimate users.
- Use breached-password screening and strong, unique passwords; do not rely on password rotation alone.
- Alert on unusual failure rates and on successful sign-ins that follow repeated failures.
- Review lockout policy to balance abuse resistance with denial-of-service risk.
- Investigate and respond to suspected account compromise using approved procedures, including session revocation and credential reset when warranted.

Explain the expected benefit and possible operational impact of each selected control. Validate detections with sanitized or synthetic events rather than attempting logins.

## 5. Result

The fictional records were reviewed for repeated failures, multi-account targeting, and successes following failures. Findings were treated as investigation leads, and defensive controls were selected without performing an attack.

## 6. References

- [NIST SP 800-63B: Digital Identity Guidelines](https://pages.nist.gov/800-63-4/sp800-63b.html)
- [CISA: Implementing Phishing-Resistant MFA](https://www.cisa.gov/resources-tools/resources/implementing-phishing-resistant-multi-factor-authentication-mfa)

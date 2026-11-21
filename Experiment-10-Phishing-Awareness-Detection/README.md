# Experiment 10: Phishing Awareness and Detection

## 1. Objective

Review a fictional phishing message, identify social-engineering indicators, and describe safe reporting and defensive response steps using synthetic evidence only.

## 2. Scope and safety

This is a defensive tabletop exercise. Do not send messages, register lookalike domains, visit links or attachments, collect credentials, or target real people. The message and event records below are fictional.

## 3. Fictional message

**From:** IT Service Desk `<helpdesk@example.invalid>`  
**Subject:** Action requested: account notice  
**Message:** “An account change is waiting for review. Contact the service desk using the address in your organization’s directory if you have questions.”

The `.invalid` domain is reserved and is not a real service. No link or attachment is included in this exercise.

## 4. Procedure

### Step 1: Identify indicators

Review the message without interacting with it. Record indicators such as an unexpected request, pressure to act, mismatched sender identity, unusual language, and requests to disclose information or bypass normal procedures. No single indicator proves that a message is malicious.

### Step 2: Decide how to handle it

- Verify unexpected requests using a known, independently obtained contact method.
- Use the organization’s approved reporting mechanism; do not forward suspicious content to unrelated recipients.
- Do not reply, open attachments, follow links, or provide account information.

### Step 3: Review synthetic telemetry

| Event | Fictional observation |
|---|---|
| Mail filter | Message held for review due to sender policy |
| User report | One recipient reported the message |
| Link or attachment activity | None; this scenario contains neither |
| Credential submission | None |

Explain which records an authorized responder should preserve and what additional mail-gateway or identity-provider evidence would be useful. Treat the observations as leads, not proof of compromise.

### Step 4: Recommend defensive actions

- Validate sender authentication and mail-routing policy with the messaging administrator.
- Review similar messages in the organization using approved mail-security tools.
- If a real user interacted with a suspected message, follow incident-response procedures; consider credential reset and session revocation only when warranted.
- Provide clear reporting guidance and measure report quality and response time alongside user click metrics.

## 5. Result

The fictional message was assessed without interacting with any content or contacting a target. Suspicious indicators, safe handling steps, and defensive follow-up were documented.

## 6. References

- [CISA: Recognize and Report Phishing](https://www.cisa.gov/secure-our-world/recognize-and-report-phishing)
- [NIST SP 800-61 Rev. 2: Computer Security Incident Handling Guide](https://csrc.nist.gov/pubs/sp/800/61/r2/final)

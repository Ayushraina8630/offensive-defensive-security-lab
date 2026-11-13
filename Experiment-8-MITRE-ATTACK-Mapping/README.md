# Experiment 8: Defensive Threat Analysis with MITRE ATT&CK

## 1. Objective

Analyze a fictional security incident, map only the behaviors supported by the available evidence to the MITRE ATT&CK framework, and recommend defensive mitigations and monitoring.

## 2. Scope and safety

This is a defensive analysis exercise. Use the fictional incident below or instructor-provided, sanitized logs. Do not scan, access, or test systems without explicit authorization. This exercise does not require executing an exploit or emulating an attack.

## 3. Fictional incident

A monitoring team reviews an alert involving an internet-facing application server. The available, sanitized evidence states:

- The application generated an alert for an unexpected request associated with an attempted exploitation of a known software weakness.
- Shortly afterward, endpoint monitoring recorded an unusual child process running under the application service account.
- Network monitoring recorded an outbound connection from the server that was not on the approved destination list.
- The team has not yet confirmed whether the activity succeeded or whether data was accessed.

Treat these statements as the complete evidence set. Do not infer attacker identity, intent, successful compromise, or data theft without additional evidence.

## 4. Procedure

### Step 1: Establish the evidence timeline

Arrange the four observations in time order using the incident record. Separate confirmed facts from hypotheses, and note what additional logs would help validate each observation (for example, application, endpoint, identity, and network telemetry).

### Step 2: Map supported behavior to ATT&CK

Consult the official MITRE ATT&CK Enterprise knowledge base. For each observation:

1. Identify a candidate tactic or technique only when the evidence supports it.
2. Record the technique ID, name, and a short explanation of the evidence-to-technique match.
3. Mark uncertain or unsupported mappings as **unconfirmed** rather than treating them as established facts.

The unexpected request may warrant reviewing **T1190: Exploit Public-Facing Application** as a candidate. The process and outbound-connection observations require further investigation before assigning additional techniques.

### Step 3: Identify defensive mitigations

Recommend controls appropriate to the evidence, such as:

- Patch or otherwise remediate the affected application and its dependencies.
- Restrict access to the application and isolate affected systems when warranted by incident-response procedures.
- Run the organization’s approved endpoint investigation and preserve relevant logs.
- Review application-service permissions and remove unnecessary privileges.
- Restrict and monitor outbound connections using approved network controls.
- Validate recovery and monitor for recurrence after remediation.

For each recommendation, explain which observation it addresses and identify an owner or team responsible for follow-up.

### Step 4: Prepare the analysis

Complete a table like the following:

| Observation | Candidate ATT&CK mapping | Confidence and rationale | Defensive action |
|---|---|---|---|
| Unexpected request associated with attempted exploitation | T1190, if supported by application and security logs | State what is confirmed and what remains uncertain | Remediate the weakness and review application logs |
| Unusual child process | Unconfirmed pending endpoint investigation | Identify the telemetry needed to determine its purpose | Investigate with approved endpoint-response procedures |
| Unapproved outbound connection | Unconfirmed pending network and process correlation | Identify the destination and process evidence still needed | Restrict and monitor outbound traffic |

## 5. Result

The incident observations were organized into a timeline, evaluated against MITRE ATT&CK without overstating the evidence, and paired with defensive mitigations and monitoring actions.

## 6. References

- [MITRE ATT&CK Enterprise](https://attack.mitre.org/)
- [T1190: Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190/)
- [M1050: Exploit Protection](https://attack.mitre.org/mitigations/M1050/)
- [M1030: Network Segmentation](https://attack.mitre.org/mitigations/M1030/)

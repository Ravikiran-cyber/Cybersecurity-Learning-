SIEM Alert Investigation

1. Project Overview

This project explains how a SOC Analyst investigates a security alert using SIEM concepts.

2. Objective

To understand alert triage, severity assessment, investigation, and incident response.

3. Tools and Technologies

- SIEM concepts
- Microsoft Sentinel (conceptual example)
- Security event analysis
- Incident response procedures

4. What Is SIEM?

Security Information and Event Management (SIEM) collects and analyzes security logs from different sources to help detect suspicious activities.

Examples include Microsoft Sentinel and Splunk.

5. Sample Security Scenario

Alert Name: Multiple Failed Login Attempts

Scenario: A monitoring system generates an alert after several failed login attempts against a user account within a short period.

Note: This is a hypothetical scenario, not a real SIEM alert.

6. Alert Details

- Alert Type: Suspicious login activity
- Severity: Medium (provisional)
- Affected Account: user1
- Data Source: Windows Security Logs
- Relevant Event ID: 4625
- Status: Under investigation

The severity is provisional and should be reassessed using the available evidence and the organization's alerting rules.

7. Investigation Process

1. Review the alert details and timestamps.
2. Examine the related failed login events.
3. Identify the source IP address and affected account.
4. Check whether the activity is expected or unusual.
5. Look for a successful login following the failed attempts.
6. Correlate the alert with other available security events.
7. Record findings and decide whether escalation is necessary.

8. Investigation Findings

Hypothetical findings:

- Multiple failed login attempts were recorded.
- The activity requires further validation.
- No evidence of account compromise has been established.

Initial Assessment: Suspicious activity requiring further investigation. A brute-force attack is one possible explanation, but it is not confirmed.

9. Recommended Actions

- Verify the activity with the account owner.
- Investigate any unusual successful login.
- Follow company procedures to contain confirmed threats.
- Reset credentials if compromise is suspected.
- Escalate high-risk findings to the incident response team.
- Document the final outcome.

10. Conclusion

SIEM alerts help SOC Analysts identify potentially suspicious activity. Analysts must investigate the available evidence, assess risk, and take appropriate action before closing an alert.

11. Learning Outcome

This case study helped me understand SIEM alert triage, basic investigation steps, severity assessment, and escalation procedures.

Disclaimer

This is a simulated educational case study. No real security alerts were investigated, and no live SIEM platform was configured.

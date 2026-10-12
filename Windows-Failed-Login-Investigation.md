Windows Failed Login Investigation

1. Project Overview

This project demonstrates how a SOC Analyst can investigate failed login attempts using Windows Security Event Logs.

2. Objective

To understand failed login attempts, identify potentially suspicious activity, and recommend appropriate security actions.

3. Tools and Technologies

- Windows Security Event Logs
- Windows Event ID 4625
- SIEM concepts
- Incident investigation and documentation

4. What Is Event ID 4625?

Windows Security Event ID 4625 records a failed account logon attempt.

A single failed login does not necessarily indicate an attack. Multiple failures or unusual login patterns may require further investigation.

5. Sample Security Scenario

Scenario: A Windows computer records several failed login attempts for the same user account within a short period.

Note: This is a hypothetical scenario created for learning. No real Windows logs were collected.

Sample Observations

- Event ID: 4625
- Activity: Failed login attempts
- Account: user1
- Source IP: 192.0.2.25 (reserved for documentation examples)
- Pattern: Multiple failures within a short period

6. Investigation Steps

1. Review the failed login events and their timestamps.
2. Identify the affected user account.
3. Check the source IP address and logon type.
4. Determine whether the attempts came from an expected device or location.
5. Check for successful logins before or after the failures.
6. Correlate the events with other security alerts if available.

7. Potential Threats

- Brute-force attempts
- Password spraying
- Mistyped passwords
- An outdated application using an old password

These are possible explanations, not confirmed conclusions.

8. Recommended Response

- Verify the activity with the account owner.
- Check for unusual successful logins.
- Follow company procedures to block suspicious sources when justified.
- Reset credentials if compromise is suspected.
- Escalate confirmed or high-risk activity to the incident response team.

9. Conclusion

Windows Event ID 4625 is useful for investigating failed login attempts. SOC Analysts must examine context and correlate evidence before classifying activity as malicious.

10. Learning Outcome

This case study helped me understand Windows failed login events, basic investigation steps, and how SOC Analysts document potential security incidents.

Disclaimer

This is a simulated educational case study, not a real investigation or a hands-on Windows lab.

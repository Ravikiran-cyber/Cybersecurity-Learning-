SOC Log Analysis: Detecting Brute-Force Login Attempts

1. Project Overview

This project demonstrates how a SOC Analyst can analyze Windows security events to identify repeated failed login attempts that may indicate a brute-force attack.

2. Objective

- Understand Windows authentication logs.
- Identify repeated failed login attempts.
- Apply basic detection logic.
- Recommend appropriate investigation and response actions.

3. Tools Used

- GitHub
- Windows Security Event Logs (sample data)
- Microsoft Sentinel Kusto Query Language (KQL)

Note: The sample data is fictional. Microsoft Sentinel is discussed as an example; this project does not claim that a live Sentinel environment was configured.

4. Understanding the Logs

Windows Security Event ID 4625 indicates a failed logon attempt.

Repeated failures against the same account from the same source may indicate a brute-force attempt. However, legitimate users can also enter incorrect passwords.

5. Sample Log Data

The following events are fictional examples created for this project.

Time| Account| Source IP| Event ID
10:00| user1| 192.0.2.10| 4625
10:01| user1| 192.0.2.10| 4625
10:02| user1| 192.0.2.10| 4625
10:03| user1| 192.0.2.10| 4625
10:04| user1| 192.0.2.10| 4625
10:05| user1| 192.0.2.10| 4624

Event ID 4624 indicates a successful logon. The example IP address is reserved for documentation and is not intended to identify a real attacker.

6. Detection Logic

A simple detection rule can flag five or more failed login attempts for the same account and source IP within five minutes.

The final successful login should also be investigated, but the sample events alone do not establish that an account was compromised.

7. Example Microsoft Sentinel KQL Query

SecurityEvent
| where EventID == 4625
| summarize FailedAttempts = count()
    by Account, IpAddress, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5
| project TimeGenerated, Account,
          IpAddress, FailedAttempts
| order by FailedAttempts desc

This example assumes Windows security events are available in the SecurityEvent table with the listed fields. The query has not been run against a live environment.

8. Investigation Steps

1. Identify the account with repeated failed logins.
2. Check the source IP address and event timestamps.
3. Review the Windows logon type and failure reason.
4. Search for successful logins around the same time.
5. Check whether the activity is expected or unusual.
6. Correlate with other alerts before deciding whether an attack occurred.

9. Recommended Response

- Validate the activity with the account owner or IT team.
- Review the account for signs of compromise.
- Follow approved procedures to contain confirmed malicious activity.
- Reset credentials if compromise is suspected.
- Escalate suspicious findings according to incident response procedures.
- Document the evidence and final conclusion.

10. Conclusion

Analyzing authentication logs helps SOC Analysts identify potentially suspicious login patterns. Detection rules can highlight activity for investigation, but alerts must be validated before being classified as attacks.

11. Learning Outcomes

- Learned the meaning of Windows Event IDs 4624 and 4625.
- Understood a basic failed-login detection rule.
- Practiced writing a Microsoft Sentinel KQL query.
- Learned investigation, escalation, and response steps.

Disclaimer

This is a simulated learning project using fictional log data. No real attack was conducted, and the query was not tested against a live SIEM environment.

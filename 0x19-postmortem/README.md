  Postmortem: DNS Configuration Error Leading to Service Disruptions
Issue Summary
Duration: The DNS outage occurred from February 15, 2024, 10:00 AM (EAT) to February 15, 2024, 2:30 PM (EAT).
  Impact: During the outage, users experienced DNS resolution failures, resulting in service disruptions across our web applications. Approximately 75% of users were affected.
Timeline
10:00 AM: Issue detected through monitoring alerts indicating a sudden spike in failed DNS queries.
 10:15 AM: Incident escalated to the Network Operations Center (NOC) team.
  10:30 AM: Investigation began, focusing on DNS servers and configurations.
  11:00 AM: Assumed root cause: Misconfigured DNS records due to recent infrastructure changes.
  11:30 AM: Debugging path: Checked DNS zone files, verified records, and reviewed recent changes.
  12:00 PM: Escalated incident to the Systems Engineering team for further analysis.
  1:00 PM: Root cause confirmed: Incorrect TTL (Time-to-Live) values in DNS records causing caching issues.
   1:30 PM: Resolution: Updated TTL values to align with best practices.
   2:30 PM: DNS resolution stabilized, services restored.

Root Cause and Resolution
   Cause: The misconfigured TTL values led to excessive caching, resulting in outdated DNS records being served to clients.
    Resolution: We adjusted TTL values to shorter intervals (e.g., 5 minutes) to reduce caching duration. Additionally, we audited all DNS records for consistency.

Corrective and Preventative Measures
   Automated TTL Management: Implement automated scripts to adjust TTL values based on record type and importance.
  Regular Audits: Conduct quarterly DNS record audits to catch misconfigurations promptly.
    Monitoring Enhancements: Set up real-time alerts for abnormal DNS query patterns.
    Documentation Update: Document best practices for DNS configuration and record management.




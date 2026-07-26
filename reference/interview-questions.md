# Rapid Interview Questions

## Identity, Windows and Microsoft 365

**Why use groups for permissions?**  
They scale, improve auditability and allow access to follow job roles instead of individual exceptions.

**Reset versus change?**  
A change requires the current password. A reset is an administrative replacement without the old password and therefore requires identity verification and auditing.

**What causes most domain-join failures?**  
Incorrect DNS, blocked connectivity, time skew, permissions or a computer-account conflict.

**What is Kerberos used for?**  
Ticket-based authentication in Active Directory. It depends heavily on DNS and time synchronisation.

**Why set Microsoft 365 usage location?**  
Service and licence availability is evaluated using the user's location.

**Why might a mailbox not appear immediately?**  
Microsoft 365 service provisioning is asynchronous.

**What is modern authentication?**  
Token-based authentication integrated with Microsoft identity controls such as MFA and Conditional Access.

## ITSM

**Incident versus service request?**  
An incident restores broken or degraded service; a request delivers a standard approved need.

**Impact versus urgency?**  
Impact is the business scope. Urgency is the required restoration speed. Together they determine priority.

**Why keep work notes?**  
They provide continuity, evidence, auditability and faster escalation.

**What is MTTR?**  
Mean time to resolve or restore, depending on the organisation's agreed definition.

## Linux and Monitoring

**`systemctl restart` versus `reload`?**  
Restart recreates the process. Reload applies supported configuration changes without a full stop/start.

**What does `journalctl -b` mean?**  
It displays journal records from the current boot.

**Why filter logs by time first?**  
It reduces noise and aligns evidence with the symptom or recent change.

**What is a Zabbix item?**  
A specific metric or value collected from a host.

**What is a trigger?**  
An expression that evaluates item data and creates an event when a condition is met.

**What is a Prometheus target?**  
An endpoint Prometheus scrapes for metrics.

**What makes a useful dashboard?**  
It answers operational questions quickly, uses correct units, shows relevant trends and thresholds and avoids clutter.

## Change and closure

**Why have a rollback plan?**  
It limits impact when implementation fails and defines a safe recovery path.

**What is good closure evidence?**  
Successful technical testing, monitoring stability, user confirmation and complete documentation.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
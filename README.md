<div align="center">

# IT Infrastructure & Microsoft 365 Hands-On Labs

### Practise → Verify → Troubleshoot → Explain

[![GitHub stars](https://img.shields.io/github/stars/toannguyenitoz/it-infrastructure-m365-hands-on-labs?style=for-the-badge)](https://github.com/toannguyenitoz/it-infrastructure-m365-hands-on-labs/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/toannguyenitoz/it-infrastructure-m365-hands-on-labs?style=for-the-badge)](https://github.com/toannguyenitoz/it-infrastructure-m365-hands-on-labs/network/members)
[![GitHub issues](https://img.shields.io/github/issues/toannguyenitoz/it-infrastructure-m365-hands-on-labs?style=for-the-badge)](https://github.com/toannguyenitoz/it-infrastructure-m365-hands-on-labs/issues)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Microsoft 365](https://img.shields.io/badge/Microsoft%20365-Administrator-0078D4?style=for-the-badge&logo=microsoft)](labs/03-microsoft-365-user-and-license.md)
[![Active Directory](https://img.shields.io/badge/Active%20Directory-Hands--On-0052CC?style=for-the-badge&logo=windows)](labs/01-active-directory-user-management.md)
[![Linux](https://img.shields.io/badge/Linux-systemd%20%7C%20journalctl-FCC624?style=for-the-badge&logo=linux&logoColor=black)](labs/06-linux-service-management.md)
[![Monitoring](https://img.shields.io/badge/Monitoring-Zabbix%20%7C%20Grafana-F46800?style=for-the-badge&logo=grafana)](labs/08-zabbix-agent.md)

A job-ready lab portfolio covering **Active Directory, Windows domain administration, Microsoft 365, Exchange Online, Outlook, ITSM, Linux, Zabbix, Prometheus, Grafana, incident management and change management**.

[GitHub Profile](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/) • [Open an Issue](https://github.com/toannguyenitoz/it-infrastructure-m365-hands-on-labs/issues)

</div>

---

## About This Repository

This repository converts a revision guide into a practical infrastructure lab portfolio. Every module follows the same operational model:

> **Understand why → Perform the task → Verify the result → Troubleshoot failures → Explain it in an interview**

It is designed for IT Support, Service Desk, Desktop Support, Systems Administration and Infrastructure roles. Each lab includes objectives, prerequisites, procedures, verification, troubleshooting, security considerations and interview-ready answers.

## Core Learning Outcomes

| Area | What you will practise |
|---|---|
| Identity | Create and reset Active Directory users, manage OUs and group-based access |
| Windows domain | Configure DNS, join Windows clients and validate secure channel and Group Policy |
| Microsoft 365 | Create cloud users, set usage location, assign licences and verify provisioning |
| Outlook | Configure Exchange Online using modern authentication and troubleshoot profiles |
| ITSM | Install and operate ServiceDesk Plus, classify tickets and manage SLA-driven work |
| Linux | Manage services with `systemctl` and investigate failures with `journalctl` |
| Monitoring | Configure Zabbix Agent, Prometheus, Node Exporter and Grafana dashboards |
| Documentation | Write professional incident and change records with evidence and rollback plans |

## Repository Map

```text
.
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SECURITY.md
├── labs/
│   ├── 01-active-directory-user-management.md
│   ├── 02-windows-domain-join.md
│   ├── 03-microsoft-365-user-and-license.md
│   ├── 04-outlook-exchange-online.md
│   ├── 05-servicedesk-plus-itsm.md
│   ├── 06-linux-service-management.md
│   ├── 07-linux-log-analysis.md
│   ├── 08-zabbix-agent.md
│   ├── 09-grafana-prometheus-dashboard.md
│   └── 10-incident-change-documentation.md
├── scenarios/
│   └── new-employee-onboarding.md
├── reference/
│   ├── master-quick-reference.md
│   ├── interview-questions.md
│   └── seven-day-revision-plan.md
└── templates/
    ├── incident-record-template.md
    └── change-request-template.md
```

## Hands-On Labs

| Lab | Module | Key verification |
|---:|---|---|
| 01 | [Active Directory user management](labs/01-active-directory-user-management.md) | User exists in correct OU, enabled, correct UPN and groups |
| 02 | [Join Windows client to domain](labs/02-windows-domain-join.md) | Domain membership, DNS SRV lookup, `gpresult /r` |
| 03 | [Microsoft 365 user and licence](labs/03-microsoft-365-user-and-license.md) | Usage location, assigned SKU and service plans |
| 04 | [Outlook with Exchange Online](labs/04-outlook-exchange-online.md) | Mail flow, calendar sync and no repeated prompts |
| 05 | [ServiceDesk Plus and ITSM](labs/05-servicedesk-plus-itsm.md) | Complete ticket lifecycle and SLA evidence |
| 06 | [Linux service management](labs/06-linux-service-management.md) | Service active, enabled, listening and reachable |
| 07 | [Linux log analysis](labs/07-linux-log-analysis.md) | Time-scoped log evidence and documented root cause |
| 08 | [Zabbix Agent](labs/08-zabbix-agent.md) | Agent available, host matched and latest data received |
| 09 | [Grafana and Prometheus](labs/09-grafana-prometheus-dashboard.md) | Exporter metrics, target UP and four useful panels |
| 10 | [Incident and change documentation](labs/10-incident-change-documentation.md) | Complete, auditable and evidence-based records |

## Golden Troubleshooting Model

1. Confirm the exact symptom.
2. Determine the scope: one user, one device, one site or everyone.
3. Check prerequisites and recent changes.
4. Capture the exact error and relevant logs.
5. Test the simplest dependency first.
6. Apply one controlled change at a time.
7. Verify the result, document the evidence and prevent recurrence.

## Portfolio Evidence Checklist

For every completed lab, save:

- A screenshot showing the completed task.
- Command output proving success.
- A short problem-and-fix note.
- A one-minute verbal explanation.
- Sanitised evidence with no real passwords, tenant names, tokens or customer data.

## About Me

### Xuan Toan Nguyen — IT Support & Systems Administration Professional

I am based in **Adelaide, South Australia**, with more than **20 years of enterprise IT experience** supporting business-critical services in a regulated banking environment.

My background includes hands-on work across:

- Windows Server, Active Directory, DNS, DHCP, Group Policy, File Services and NTFS permissions.
- Microsoft 365, Exchange Online, Microsoft Entra ID, MFA, licensing and user lifecycle administration.
- Tier 2/3 troubleshooting, incident coordination, root-cause analysis and service continuity.
- Infrastructure support, system maintenance, technical documentation and vendor coordination.
- Governance, cybersecurity, privacy and data-management requirements.
- Remote Desktop Support L2 and ITSM ticket lifecycle experience in Adelaide.

I am currently completing a **Certificate IV in Information Technology — Systems Administration Support at TAFE SA**.

**Achievements and certifications**

- Microsoft Certified: Azure Fundamentals — **AZ-900**
- **Silver Medalist**, Cloud Computing — WorldSkills Australia South Australian Regional Competition 2026
- More than 20 years of enterprise technology experience

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-toannguyenitoz-181717?style=for-the-badge&logo=github)](https://github.com/toannguyenitoz)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Toan%20Nguyen-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/toan-nguyen-it-oz/)
[![Location](https://img.shields.io/badge/Location-Adelaide%2C%20Australia-00843D?style=for-the-badge)](https://www.google.com/maps/place/Adelaide+SA)

</div>

## Security and Lab Safety

- Use isolated VMs, snapshots and non-production tenants.
- Never expose default credentials or evaluation systems directly to the internet.
- Use delegated administration rather than Domain Admin or Global Administrator for routine tasks.
- Restrict monitoring ports to trusted servers and use TLS, PSK or certificates.
- Sanitise screenshots, commands and exported logs before publishing.
- Review [SECURITY.md](SECURITY.md) before contributing scripts or evidence.

## Quick Links

- [Integrated onboarding scenario](scenarios/new-employee-onboarding.md)
- [Master command reference](reference/master-quick-reference.md)
- [Rapid interview questions](reference/interview-questions.md)
- [Seven-day revision plan](reference/seven-day-revision-plan.md)
- [Incident record template](templates/incident-record-template.md)
- [Change request template](templates/change-request-template.md)

## Contributing

Contributions, corrections and lab improvements are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

Released under the [MIT License](LICENSE). Lab examples are provided for education and portfolio development. Product names and trademarks remain the property of their respective owners.

---

<div align="center">

### Practise • Verify • Troubleshoot • Explain

Maintained by **Xuan Toan Nguyen**

[![GitHub](https://img.shields.io/badge/GitHub-toannguyenitoz-181717?style=flat-square&logo=github)](https://github.com/toannguyenitoz)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-toan--nguyen--it--oz-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/toan-nguyen-it-oz/)

[Back to top](#it-infrastructure--microsoft-365-hands-on-labs)

</div>
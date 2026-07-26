# Lab 04 — Configure Outlook with Exchange Online

## Objective
Connect a licensed Microsoft 365 work account to Outlook through Autodiscover and modern authentication, then verify mail and calendar synchronisation.

## Behind the scenes

| Stage | Explanation |
|---|---|
| Autodiscover | Finds mailbox and service settings from the email address |
| Modern authentication | Uses Microsoft identity, MFA and token-based authentication |
| Exchange connection | Connects to Exchange Online over HTTPS |
| Cached mode | Stores an OST cache for performance and offline access |
| Synchronisation | Synchronises mail, calendar, contacts and folders |

## Procedure

1. Confirm the user exists, has an Exchange Online licence and can sign in on the web.
2. In Outlook select **File > Add Account**, or enter the address during first-run setup.
3. Enter the full work email address.
4. Complete passwordless/password sign-in and MFA.
5. Let Outlook detect Microsoft 365 automatically; do not choose POP or IMAP for a normal enterprise mailbox.
6. Wait for initial synchronisation.
7. Send and receive a test message, create a calendar event and verify Sent Items.

## Verification checklist

- Status shows connected to Microsoft Exchange.
- Inbox and folders synchronise.
- Internal and external send/receive works.
- Calendar opens and updates.
- Modern authentication is used.
- No repeated credential prompts occur.

## Troubleshooting

| Symptom | Isolation and fix |
|---|---|
| Cannot sign in anywhere | Identity/password issue; inspect Entra sign-in logs |
| Web works, Outlook fails | Profile, cache or client issue; update or recreate profile |
| Repeated password prompt | Remove stale Credential Manager entries; review modern auth and Conditional Access |
| Disconnected/offline | Check service health, internet, Work Offline, proxy, VPN and firewall |
| Mail does not send | Check Outbox, quota, attachment size, transport rules and service health |
| Autodiscover failure | Check accepted domain, DNS, proxy inspection and client updates |

## Data note
An OST is a cache and is not the primary backup. PST files may contain exported or local data and must follow organisational retention and data-handling policy.

## Interview answer

> Exchange provides full mailbox, calendar, contacts, free/busy, modern authentication and enterprise policy support. IMAP mainly synchronises email and does not provide the complete Microsoft 365 experience.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
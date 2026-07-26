# Lab 07 — Analyse Linux Logs with journalctl

## Objective
Query the systemd journal by service, boot, time, severity, process and field to identify root cause quickly.

## Essential commands

```bash
journalctl -b
journalctl -b -1
journalctl -u ssh --no-pager
journalctl -u nginx -n 100 --no-pager
journalctl -u nginx -f
journalctl --since "1 hour ago"
journalctl -p err -b
journalctl -k -b
journalctl -u ssh -o json-pretty
```

Severity runs from `0 emerg` to `7 debug`. Lower numbers are more severe. `journalctl -p err` includes levels 0–3.

## Real-world searches

```bash
journalctl -u ssh --since today | grep -i 'failed password'
journalctl -b -1 -p err --no-pager
journalctl -u nginx -p err --since '30 min ago'
journalctl _COMM=sudo --since today
journalctl _PID=1234 -o verbose
journalctl --disk-usage
```

## Analysis workflow

1. Define the exact time window, host, service and symptom.
2. Start with service logs for the relevant boot.
3. Filter by severity, message, PID, process, user or unit.
4. Correlate errors with configuration changes and dependencies.
5. Test the suspected cause.
6. Save only the relevant sanitised evidence.
7. Document root cause, fix and verification.

> `journalctl --vacuum-*` deletes old data. Follow retention, compliance and incident-preservation requirements before removing logs.

## Interview answer

> I check `systemctl status`, then `journalctl -u service -b` for the current boot and `journalctl -b -1` when the issue began during a previous shutdown or boot. I validate configuration, dependencies, ports and permissions, then correlate timestamps with recent changes.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
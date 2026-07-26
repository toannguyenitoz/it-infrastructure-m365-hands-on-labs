# Lab 06 — Linux Service Management with systemctl

## Objective
Control service state, configure boot behaviour, inspect status and troubleshoot failures on a systemd-based Linux host.

## Core commands

```bash
systemctl status <service> --no-pager
sudo systemctl start <service>
sudo systemctl stop <service>
sudo systemctl restart <service>
sudo systemctl reload <service>
sudo systemctl enable --now <service>
sudo systemctl disable --now <service>
systemctl is-active <service>
systemctl is-enabled <service>
systemctl --failed
```

## Apache practice on Ubuntu

```bash
sudo apt update
sudo apt install apache2 -y
sudo systemctl enable --now apache2
systemctl status apache2 --no-pager
curl -I http://localhost
sudo ss -lntp | grep :80
journalctl -u apache2 -n 50 --no-pager
```

## Troubleshooting sequence

1. Read `systemctl status <service> --no-pager`.
2. Read `journalctl -u <service> -b --no-pager`.
3. Validate configuration with the service's native test command.
4. Check listening ports and conflicts using `ss -lntp`.
5. Check permissions, paths, dependencies, environment files and disk space.
6. Correct one issue, restart and verify.
7. Enable at boot only after the service runs correctly.

## Common symptoms

| Symptom | Typical cause | Useful command |
|---|---|---|
| Unit not found | Wrong name or package missing | `systemctl list-unit-files` |
| Exit code 1 | Invalid configuration | `journalctl -u name -b` |
| Address in use | Port conflict | `sudo ss -lntp` |
| Permission denied | Ownership, AppArmor/SELinux or privilege | `namei -l path` and logs |
| Works manually, not at boot | Not enabled or dependency ordering | `systemctl is-enabled name` |
| Repeated too quickly | Crash loop | `systemctl reset-failed name` |

## Interview answer

> `start` changes the service state now. `enable` configures boot-time activation. `enable --now` performs both, but I still verify service state, listening ports and logs.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
# Lab 08 — Install and Configure Zabbix Agent

## Objective
Install an endpoint agent, securely connect it to Zabbix Server or Proxy, register the host and verify monitoring data.

## Architecture

`Zabbix Server/Proxy ↔ Zabbix Agent → Items → Triggers → Events → Alerts and dashboards`

## Important settings

| Setting | Purpose |
|---|---|
| `Server` | Addresses allowed to perform passive checks |
| `ServerActive` | Server or proxy used for active checks |
| `Hostname` | Must match the host configured in Zabbix for active checks |
| `ListenPort` | Agent port, commonly TCP 10050 |
| TLS settings | Certificate or PSK encryption and authentication |

## Ubuntu/Debian outline

```bash
sudo apt update
sudo apt install zabbix-agent2 -y
sudo nano /etc/zabbix/zabbix_agent2.conf
sudo systemctl enable --now zabbix-agent2
systemctl status zabbix-agent2 --no-pager
sudo ss -lntp | grep 10050
sudo tail -n 100 /var/log/zabbix/zabbix_agent2.log
```

Example:

```ini
Server=192.168.1.10
ServerActive=192.168.1.10
Hostname=Linux-Server-01
ListenPort=10050
```

## Add the host

1. Select the correct host group.
2. Add the exact host name used by the agent.
3. Configure agent interface IP/DNS and port.
4. Link the correct official template.
5. Check availability and **Latest data**.
6. Perform a controlled alert test in the lab.

## Troubleshooting

| Problem | Checks |
|---|---|
| Connection refused | Agent state, listening address, port and host firewall |
| Timeout | Routing, NAT, proxy and `Server` allow-list |
| Host not found | Exact `Hostname` and `ServerActive` target |
| No data | Template, item support, logs and collection interval |
| Permission denied | File and command permissions; safe UserParameter design |
| Unsupported key | Agent version, platform support and syntax |

## Security
Restrict TCP 10050 to trusted Zabbix servers/proxies. Use encrypted communication, least privilege and protected PSK/certificate material.

## Interview answer

> Passive checks are requested by the server or proxy from the agent. With active checks, the agent retrieves its check list and sends results. Firewall direction and exact hostname matching are therefore different.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
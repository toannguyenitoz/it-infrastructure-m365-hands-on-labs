# Master Quick Reference

## Windows and Active Directory

```powershell
dsa.msc
ipconfig /all
nslookup contoso.com
nslookup -type=SRV _ldap._tcp.dc._msdcs.contoso.com
w32tm /query /status
whoami /all
gpresult /r
nltest /dsgetdc:contoso.com
Test-ComputerSecureChannel -Verbose
(Get-CimInstance Win32_ComputerSystem).Domain
```

## Microsoft 365 and Outlook

```powershell
Connect-MgGraph -Scopes 'User.ReadWrite.All','Directory.ReadWrite.All'
Get-MgUser -UserId user@contoso.com
Get-MgUserLicenseDetail -UserId user@contoso.com
Get-MgSubscribedSku
```

Useful interfaces:

- Outlook: **File > Account Settings > Account Settings**
- Windows: **Control Panel > Credential Manager**
- Microsoft 365 admin centre: **Users > Active users**
- Microsoft Entra admin centre: **Sign-in logs**

## Linux and Monitoring

```bash
systemctl status service --no-pager
journalctl -u service -b -p err --no-pager
ss -lntp
curl -I http://localhost
df -h
free -h
zabbix_agent2 -t agent.ping
curl http://localhost:9100/metrics
curl http://localhost:9090/-/ready
docker ps
```

## Troubleshooting order

1. Symptom
2. Scope
3. Recent change
4. Dependency
5. Logs
6. Controlled fix
7. Verification
8. Documentation

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
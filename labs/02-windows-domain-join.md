# Lab 02 — Join a Windows Client to an Active Directory Domain

## Objective
Configure a Windows client to trust the domain so central authentication, Kerberos, Group Policy and administration can work.

## Memory line
A domain join is primarily a **DNS, connectivity, time, permissions and computer-account** operation. The client must use approved AD DNS, not public DNS.

## Prerequisites

| Requirement | Quick test |
|---|---|
| Correct DNS | `nslookup -type=SRV _ldap._tcp.dc._msdcs.contoso.com` |
| DC connectivity | `Test-NetConnection DC01 -Port 389` |
| Time synchronisation | `w32tm /query /status` |
| Supported edition | `winver` — Windows Home cannot join classic AD DS |
| Approved permissions | Delegated domain-join account |
| Unique hostname | `hostname` |

## Procedure

1. Configure preferred DNS to the domain controller or approved internal DNS.
2. Confirm DNS resolution, connectivity and time.
3. Rename the computer if required.
4. Open **System Properties > Computer Name > Change**.
5. Select **Domain**, enter the DNS domain name and provide approved credentials.
6. Restart and sign in using `user@contoso.com` or `CONTOSO\username`.

```powershell
Rename-Computer -NewName 'CLIENT01' -Restart
Add-Computer -DomainName 'contoso.com' -Credential (Get-Credential) -Restart
```

## Verification

```powershell
(Get-CimInstance Win32_ComputerSystem).Domain
whoami
nltest /dsgetdc:contoso.com
gpresult /r
Test-ComputerSecureChannel -Verbose
```

## Common ports

`53` DNS • `88` Kerberos • `123` NTP • `135` RPC • `389` LDAP • `445` SMB/SYSVOL • `636` LDAPS • `3268/3269` Global Catalog

## Troubleshooting

| Error | First checks |
|---|---|
| Domain cannot be contacted | DNS settings, SRV records, firewall and DC connectivity |
| Access denied | Credential format and delegated permissions |
| Existing computer account | Ownership and hardened account-reuse policy |
| Clock skew | Time source and `w32tm` status |
| Trust relationship failed | `Test-ComputerSecureChannel -Verbose`; repair or controlled rejoin |

## Interview answer

> Active Directory publishes domain controllers and services in DNS SRV records. A client can have internet access but still fail to join when it uses public DNS because it cannot locate LDAP, Kerberos or the domain controller.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
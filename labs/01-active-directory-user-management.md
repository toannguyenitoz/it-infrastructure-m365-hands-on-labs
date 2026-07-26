# Lab 01 — Active Directory User Management

## Objective
Create a domain identity in the correct OU, set a secure temporary password, assign role-based groups, verify the account and explain reset versus change.

## Key concepts

| Term | Meaning |
|---|---|
| AD DS | Central directory for users, computers, groups and policies |
| OU | Container used to organise objects and delegate administration |
| UPN | Sign-in name such as `user@contoso.com` |
| sAMAccountName | Legacy sign-in name used as `DOMAIN\username` |
| Password reset | Administrator replaces the password without knowing the old one |
| Password change | User proves the old password and selects a new one |

## GUI procedure

1. Open **Active Directory Users and Computers** with `dsa.msc`.
2. Navigate to the approved OU.
3. Select **New > User** and follow the naming standard.
4. Set a compliant temporary password.
5. Select **User must change password at next logon**.
6. Add only approved role-based groups.
7. Verify the UPN, enabled state and group membership.

## PowerShell

```powershell
New-ADUser -Name 'John Doe' -GivenName John -Surname Doe `
  -SamAccountName jdoe -UserPrincipalName jdoe@contoso.com `
  -Path 'OU=Users,DC=contoso,DC=com' -Enabled $true `
  -AccountPassword (Read-Host -AsSecureString 'Temporary password')

Set-ADAccountPassword -Identity jdoe -Reset `
  -NewPassword (Read-Host -AsSecureString 'New password')
Set-ADUser -Identity jdoe -ChangePasswordAtLogon $true
Unlock-ADAccount -Identity jdoe
```

> `net user username password` changes a local account by default. Use ADUC, the ActiveDirectory PowerShell module or `/domain` for a domain identity.

## Verification

```powershell
Get-ADUser jdoe -Properties Enabled,UserPrincipalName,MemberOf |
  Select Name,Enabled,UserPrincipalName,MemberOf
```

## Troubleshooting

| Symptom | First check | Likely fix |
|---|---|---|
| User not found | Domain, OU and replication | Search entire directory and verify replication |
| Password rejected | Domain password policy | Use compliant length, history and complexity |
| Account locked | Lockout status and failed logons | Verify identity, unlock and investigate stale credentials |
| Access denied | Delegated permissions | Use an approved least-privilege admin account |
| Sign-in fails | Username format, DNS and DC reachability | Test UPN and `DOMAIN\user`; verify network and DNS |

## Interview answer

> I create the user in the correct OU, follow the naming standard, set a compliant temporary password, force a change at first sign-in, assign access through groups and verify the object, permissions and audit trail.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
# Lab 03 — Microsoft 365 User and Licence Assignment

## Objective
Provision a cloud identity, set usage location, assign the approved product licence and verify service activation.

## Workflow
Create identity → Set UPN and usage location → Assign licence → Wait for provisioning → Apply MFA/security policy → Test access

## Admin centre procedure

1. Sign in with an approved **User Administrator** or **Licence Administrator** account.
2. Go to **Users > Active users > Add a user**.
3. Enter the display name, username, verified domain and password settings.
4. Set the correct usage location.
5. Assign only the required product licence and service plans.
6. Do not assign an admin role unless formally approved.
7. Verify the user and licence assignment state.

## Microsoft Graph PowerShell

```powershell
Connect-MgGraph -Scopes 'User.ReadWrite.All','Directory.ReadWrite.All'

$passwordProfile = @{
  Password = 'Temporary-Password'
  ForceChangePasswordNextSignIn = $true
}

New-MgUser -DisplayName 'John Doe' -GivenName 'John' -Surname 'Doe' `
  -UserPrincipalName 'johndoe@contoso.com' -MailNickname 'johndoe' `
  -AccountEnabled -UsageLocation 'AU' -PasswordProfile $passwordProfile

Get-MgSubscribedSku | Select SkuPartNumber,SkuId,ConsumedUnits
Set-MgUserLicense -UserId 'johndoe@contoso.com' `
  -AddLicenses @{SkuId='<GUID>'} -RemoveLicenses @()
```

## Verification

```powershell
Get-MgUser -UserId johndoe@contoso.com
Get-MgUserLicenseDetail -UserId johndoe@contoso.com
```

## Troubleshooting

| Problem | Cause or fix |
|---|---|
| No licences available | Purchase capacity, remove unused assignments or select another approved SKU |
| Assignment fails | Set usage location; check plan conflicts and permissions |
| Mailbox not ready | Confirm Exchange Online is included and allow asynchronous provisioning |
| User cannot sign in | Check enabled state, password, MFA, Conditional Access and sign-in logs |
| Synced user cannot be edited | Make authoritative changes in on-premises AD |

## Security note
Global Administrator is not required for routine provisioning. Use separate admin accounts and the least privileged supported role.

## Interview answer

> A licence enables service plans such as Exchange Online, Teams, SharePoint and Microsoft 365 Apps depending on the SKU. Provisioning is asynchronous, so I verify assigned plans and allow appropriate time before declaring a failure.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)
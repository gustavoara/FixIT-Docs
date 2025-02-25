# Convert User to SID and SID to User in PowerShell / Converter Usuário para SID e SID para Usuário no PowerShell

## 📌 Description / Descrição
This script retrieves the **Security Identifier (SID) of a user account** and also converts a given SID back into a **user account name** using PowerShell.

Este script recupera o **Security Identifier (SID) de uma conta de usuário** e também converte um SID fornecido de volta para um **nome de conta de usuário** usando PowerShell.

---

## 🛠 Steps performed:
1. Converts a **username** into its corresponding **SID**.
2. Converts a **SID** back into its corresponding **username**.

---

## 🔧 Commands:
### 🔹 Convert Username to SID
```
$objUser = New-Object System.Security.Principal.NTAccount("DOMAIN\username")
$strSID = $objUser.Translate([System.Security.Principal.SecurityIdentifier])
$strSID.Value
```

### 🔹 Convert SID to Username
```
$objSID = New-Object System.Security.Principal.SecurityIdentifier `
    ("S-1-5-21-0000000000-1111111111-2222222222-3333")
$objUser = $objSID.Translate([System.Security.Principal.NTAccount])
$objUser.Value
```

---

## ⚠️ Notes:
- Replace **"DOMAIN\username"** with the actual domain and username.
- Replace **"S-1-5-21-0000000000-1111111111-2222222222-3333"** with the correct SID.
- **Run PowerShell as Administrator** if needed.

---

## 💡 When to use?
- To **find the SID** of a specific user account.
- To **identify a user from a given SID** in system logs.
- For **troubleshooting permissions and Active Directory issues**.

---

## 🔍 Search Tags:
Convert user to SID, convert SID to user, get SID from username, get username from SID, PowerShell SID lookup, Active Directory SID search

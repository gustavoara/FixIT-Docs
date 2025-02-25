# Fix CredSSP Error in Remote Desktop / Corrigir Erro CredSSP no Remote Desktop

## 📌 Description / Descrição
This command fixes the **CredSSP encryption error** that occurs when trying to connect to a remote machine via Remote Desktop (MSTSC).

Este comando corrige o **erro de criptografia do CredSSP**, que ocorre ao tentar conectar-se a uma máquina remota via Remote Desktop (MSTSC).

---

## 🛠 Steps performed:
1. Adds a registry key to allow **Oracle Remediation** for CredSSP encryption.
2. Enables Remote Desktop connections that fail due to **CredSSP encryption errors**.
3. If the issue persists, a **computer restart is required**.

---

## 🔧 Commands:
```
reg add "HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\System\CredSSP\Parameters" /f /v AllowEncryptionOracle /t REG_DWORD /d 2
```

---

## ⚠️ Notes:
- **Run CMD as Administrator** before executing the command.
- If the fix **does not take effect immediately**, restart the computer.
- This setting **lowers security restrictions**, so it should be used carefully in secure environments.

---

## 💡 When to use?
- When **Remote Desktop (MSTSC) fails** with a **CredSSP encryption error**.
- If **older systems cannot connect to updated servers** due to CredSSP policies.
- To quickly **allow remote access without modifying Group Policies**.

---

## 🔍 Search Tags:
Fix CredSSP error, Remote Desktop encryption fix, MSTSC cannot connect, CredSSP registry fix, AllowEncryptionOracle, Remote Desktop authentication issue

---

📂 **`fix-credssp-rdp.md`**

# Reset Group Policy / Resetar Políticas de Grupo no Windows

## 📌 Description / Descrição
This script **removes all applied Group Policy settings** from a Windows computer and forces an update.  

Este script **remove todas as Políticas de Grupo aplicadas** em um computador Windows e força uma atualização.

---

## 🛠 Steps performed:
1. Deletes the Group Policy history.
2. Removes registry keys related to Group Policy settings.
3. Deletes the security policy database.
4. Purges Kerberos ticket cache.
5. Forces a Group Policy update.

---

## 🔧 Commands:
```cmd
DEL /S /F /Q “%ALLUSERSPROFILE%\Microsoft\Group Policy\History\*.*
REG DELETE HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Group Policy /f
REG DELETE HKLM\Software\Policies\Microsoft /f
REG DELETE HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies /f
REG DELETE HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies /f
REG DELETE HKCU\Software\Policies\Microsoft /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Group Policy Objects" /f
DEL /F /Q C:\WINDOWS\security\Database\secedit.sdb
klist purge
gpupdate /force
pause

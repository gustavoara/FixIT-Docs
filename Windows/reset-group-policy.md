# Reset Group Policy / Resetar Políticas de Grupo no Windows

## 📌 Description / Descrição
This command resets all applied Group Policy settings on a Windows computer by deleting cached policies and forcing an update.

Este comando redefine todas as configurações da Política de Grupo aplicadas em um computador Windows, excluindo políticas em cache e forçando uma atualização.

---

## 🛠 Steps performed:
1. Deletes the Group Policy history.
2. Removes registry keys related to Group Policy settings.
3. Deletes the security policy database.
4. Purges Kerberos ticket cache.
5. Forces a Group Policy update.

---

## 🔧 Commands:
```
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
```

---

## ⚠️ Notes:
- **Run CMD as Administrator** before executing the commands.
- Restart the computer if Group Policy settings don’t update properly.
- This action **removes all applied policies**, including security settings.

---

## 💡 When to use?
- When **Group Policy settings are stuck** and not applying correctly.
- If a **GPO is corrupted** and causing system issues.
- To **reset Group Policy to default settings** before applying new policies.

---

## 🔍 Search Tags:
Reset GPO, Group Policy not applying, delete Group Policy cache, force gpupdate, fix GPO issues, remove policies Windows

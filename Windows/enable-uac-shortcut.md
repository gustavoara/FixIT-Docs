# Create a Shortcut to Enable UAC / Criar um Atalho para Habilitar o UAC

## 📌 Description / Descrição
This method allows you to create a shortcut to manually access **User Account Control (UAC) settings** when elevation is not possible.

Este método permite criar um atalho para acessar manualmente as **configurações do Controle de Conta de Usuário (UAC)** quando a elevação não é possível.

---

## 🛠 Steps performed:
1. Create a shortcut pointing to **UserAccountControlSettings.exe**.
2. Use **"Run as administrator"** to access UAC settings.
3. Enable UAC to restore normal privilege escalation.

---

## 🔧 Commands:
### 🔹 Shortcut Target:
```
C:\Windows\System32\UserAccountControlSettings.exe
```

---

## ⚠️ Notes:
- Useful when **UAC is disabled**, preventing administrator elevation.
- Allows restoring UAC when **"Run as administrator"** is unavailable.
- After enabling UAC, restart the system for changes to take effect.

---

## 💡 When to use?
- When **UAC is disabled** and **administrator privileges cannot be elevated**.
- If an application requires **UAC activation** to function properly.
- To **restore standard security settings** in Windows.

---

## 🔍 Search Tags:
Enable UAC manually, restore UAC, run as administrator workaround, UserAccountControlSettings.exe, fix UAC disabled issue, Windows privilege escalation fix

---

📂 **`enable-uac-shortcut.md`**

# Delete Executable and Clean Up Directory / Deletar Executável e Limpar Diretório

## 📌 Description / Descrição
This script navigates through subdirectories, attempts to delete a specific executable file, and if successful, deletes the entire folder.

Este script percorre subdiretórios, tenta deletar um arquivo executável específico e, se for bem-sucedido, remove toda a pasta.

---

## 🛠 Steps performed:
1. Loops through all subdirectories in the specified path.
2. Tries to delete the targeted executable file.
3. If the executable is successfully deleted, the entire folder is removed.
4. If deletion fails, no action is taken (likely because the file is in use).

---

## 🔧 Commands:
```
for /d %%i in (H:\Target_Folder\*) do (
	del /f /s /q "%%i\TargetApp.exe"
	If NOT exist "%%i\TargetApp.exe" (
		del /f /s /q "%%i"
		rmdir "%%i" /s /q
	)
)
```

---

## ⚠️ Notes:
- **Modify the path (`H:\Target_Folder\*`) and executable name (`TargetApp.exe`) as needed.**
- If the executable **cannot be deleted**, the folder is **not removed**, likely because the process is running.
- **Run CMD as Administrator** for better permission handling.

---

## 💡 When to use?
- To **clean up directories** after removing a specific application.
- When needing to **delete multiple instances** of an application in different subdirectories.
- To **automate cleanup tasks** in batch scripting.

---

## 🔍 Search Tags:
Batch script delete executable, for loop delete files, remove directory if file is deleted, batch clean up folders, delete app if not running

---

📂 **`delete-exe-cleanup.md`**

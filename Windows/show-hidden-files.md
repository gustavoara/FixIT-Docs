# Remove File Attributes in Windows / Remover Atributos de Arquivos no Windows

## 📌 Description / Descrição
This command removes system, hidden, archive, and read-only attributes from all files and folders within a selected drive.

Este comando remove os atributos de sistema, oculto, arquivamento e somente leitura de todos os arquivos e pastas dentro de uma unidade selecionada.

---

## 🛠 Steps performed:
1. Select the drive where the files are located.
2. Execute the attribute removal command to reset all file and folder attributes.

---

## 🔧 Commands:
```
D:
attrib -s -h -a -r /S /D *.*
```

---

## ⚠️ Notes:
- **Run CMD as Administrator** before executing the command.
- This will affect **all files and folders** within the selected drive.
- Useful for **recovering files hidden by malware** or fixing **restricted file access**.

---

## 💡 When to use?
- To **remove system and hidden attributes** from files and folders.
- When files **become inaccessible due to attribute restrictions**.
- To **recover files that were hidden by a virus or incorrect permissions**.

---

## 🔍 Search Tags:
Remove attributes Windows, attrib command, show hidden files, unhide files CMD, recover hidden files, attrib -s -h -a -r

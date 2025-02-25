# Convert RTF to Plain Text in PowerShell / Converter RTF para Texto Simples no PowerShell

## 📌 Description / Descrição
This PowerShell script converts **Rich Text Format (RTF) content** into **plain text** using the Windows Forms RichTextBox component.

Este script em PowerShell converte conteúdo no formato **Rich Text Format (RTF)** para **texto simples** usando o componente **RichTextBox** do Windows Forms.

---

## 🛠 Steps performed:
1. Loads the **System.Windows.Forms** assembly.
2. Creates a **RichTextBox** object.
3. Assigns an **RTF-formatted string** to the RichTextBox.
4. Extracts the **plain text content** from the RTF.

---

## 🔧 Commands:
```
Add-Type -AssemblyName System.Windows.Forms

$Rtb = New-Object System.Windows.Forms.RichTextBox

$stringRTF = "{\rtf1\ansi\deff0{\fonttbl{\f0\fswiss Helvetica;}}{\colortbl ;\red255\green0\blue0;} This is some \cf1\ul red underlined\cf0\ulnone  text.}"
$Rtb.Rtf = $stringRTF
$Retorno = $Rtb.Text

Write-Host $Retorno

```

---

## ⚠️ Notes:
- The script **requires a GUI environment** to run properly.
- Useful for **extracting plain text** from **RTF-formatted documents**.
- Can be integrated into **automation scripts** that process formatted text.

---

## 💡 When to use?
- To **convert RTF content into plain text** in PowerShell.
- When handling **formatted text extraction** in automation tasks.
- For **processing and cleaning RTF data** in scripting environments.

---

## 🔍 Search Tags:
Convert RTF to text, PowerShell RTF parsing, extract text from RTF, RichTextBox PowerShell, System.Windows.Forms RTF conversion

---

📂 **`convert-rtf-text.md`**

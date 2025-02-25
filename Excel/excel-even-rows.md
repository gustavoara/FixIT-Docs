# Identify Even Rows in Excel / Identificar Linhas Pares no Excel

## 📌 Description / Descrição
This formula is used to check if a row is **even-numbered** in an Excel spreadsheet.

Esta fórmula é usada para verificar se uma linha possui **numeração par** em uma planilha do Excel.

---

## 🛠 Steps performed:
1. Use the formula to determine if a row is even.
2. Apply it in **conditional formatting** to highlight even rows.
3. Use it for filtering or alternating row-based calculations.

---

## 🛠 How-To: Apply Conditional Formatting for Even Rows

### 1️⃣ Open Conditional Formatting
- Select the range where you want to apply the formatting.
- Go to **Home** > **Conditional Formatting** > **New Rule**.

### 2️⃣ Choose "Use a formula to determine which cells to format"
- In the formula box, enter:
```
=MOD(LIN();2)=0
```

### 3️⃣ Select the Formatting Style
- Click **Format** and choose the desired background color or text style.
- Click **OK** to apply.

### 4️⃣ Apply and Save
- Click **OK** again to finalize the formatting.
- Now, all even-numbered rows will be highlighted.

---

## 🔧 Formula:
```
=MOD(LIN();2)=0
```

---

## ⚠️ Notes:
- This formula **returns TRUE for even rows** and **FALSE for odd rows**.
- Can be used in **conditional formatting** to create alternate row shading.
- Useful for **data analysis and structured reports**.

---

## 💡 When to use?
- To **highlight even-numbered rows** for better readability.
- For **conditional formatting** in large datasets.
- To **filter or analyze row-based data structures**.

---

## 🔍 Search Tags:
Excel even rows, highlight even rows, conditional formatting, alternate row shading, Excel MOD function, filter even rows

---

📂 **`excel-even-rows.md`**

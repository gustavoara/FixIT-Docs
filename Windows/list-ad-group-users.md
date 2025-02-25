# List Users in an Active Directory Group / Listar Usuários de um Grupo no Active Directory

## 📌 Description / Descrição
This command retrieves a list of users belonging to a specific **Active Directory group**.

Este comando recupera uma lista de usuários pertencentes a um **grupo do Active Directory**.

---

## 🛠 Steps performed:
1. Finds the **group's Distinguished Name (DN)** using its **SAM ID**.
2. Retrieves **all members of the group**, including nested groups.
3. Displays **usernames** in **SAMAccountName** format.

---

## 🔧 Commands:
```
dsquery group -samid "GROUP_NAME" | dsget group -members -expand | dsget user -samid
```

---

## ⚠️ Notes:
- Replace **"GROUP_NAME"** with the actual **SAM ID** of the group.
- Requires **Active Directory module** and **domain admin privileges**.
- If the command does not return results, ensure the **group exists** and is correctly spelled.

---

## 💡 When to use?
- To **audit group membership** in Active Directory.
- For **troubleshooting access issues** related to group policies.
- When exporting **user lists from AD** for documentation or security reviews.

---

## 🔍 Search Tags:
List AD group members, dsquery group users, get users from AD group, Active Directory user list, export AD group members

---

📂 **`list-ad-group-users.md`**

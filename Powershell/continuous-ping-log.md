# Continuous Ping with Timestamp / Ping Contínuo com Timestamp

## 📌 Description / Descrição
This PowerShell script performs a **continuous ping test** while logging the results with timestamps.  
Useful for monitoring network stability and identifying when a host becomes unreachable.

Este script em PowerShell executa um **ping contínuo**, registrando os resultados com timestamps.  
Útil para monitorar a estabilidade da rede e identificar quando um host fica inacessível.

---

## 🛠 Steps performed:
1. Ensures the directory **C:\TEMP\PING\** exists.
2. Runs a **continuous ping** to a specified IP.
3. Logs each response with **date and time** in a text file.

---

## 🔧 Commands:
```
$logDir = "C:\TEMP\PING"
$logFile = "$logDir\ping_log.txt"
$targetIP = "192.168.1.1"

# Create the directory if it doesn't exist
if (!(Test-Path -Path $logDir)) {
    New-Item -ItemType Directory -Path $logDir -Force
}

# Run continuous ping with timestamp logging
Ping.exe -t $targetIP | ForEach-Object {"{0} - {1}" -f (Get-Date),$_} >> $logFile
```

---

## ⚠️ Notes:
- Replace **`192.168.1.1`** with the target **IP or hostname**.
- Logs are saved in **C:\TEMP\PING\ping_log.txt**.
- To **stop the script**, press **CTRL + C**.

---

## 💡 When to use?
- To **monitor network connectivity** over time.
- When **diagnosing intermittent network issues**.
- To **track when a host goes offline** with timestamps.

---

## 🔍 Search Tags:
Continuous ping with timestamp, log ping results, network monitoring PowerShell, ping with date and time, PowerShell ping test

---

📂 **`continuous-ping-log.md`**

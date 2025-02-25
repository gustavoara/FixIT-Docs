# Collect Printer Data via SNMP / Coletar Dados de Impressoras via SNMP

## 📌 Description / Descrição
This PowerShell script scans a network range to collect information about printers using **SNMP (Simple Network Management Protocol)**.

Este script em PowerShell escaneia um intervalo de rede para coletar informações sobre impressoras usando **SNMP (Simple Network Management Protocol)**.

---

## 🛠 Steps performed:
1. Defines the **network range** to scan for printers.
2. Creates a temporary directory (`C:\TEMP\SNMP`) to store logs.
3. Downloads **SnmpWalk.exe** if it is not already available.
4. Uses **SNMP queries** to retrieve:
   - Printer **Model**
   - **Serial Number**
   - **Page Counter**
5. Saves the collected data into a `.txt` file.

---

## 🔧 Commands:
```
$directory = "C:\TEMP\SNMP"
$snmpWalkExe = "$directory\SnmpWalk.exe"
$downloadUrl = "https://fixitdocs.gustavoaraujo.com/Files/SnmpWalk.exe"
$outputFile = "$directory\IVENTPRT.txt"

$ipBase = "10.0.0."
$ipStart = 1
$ipEnd = 250

if (!(Test-Path -Path $directory)) {
    New-Item -ItemType Directory -Path $directory -Force
}

if (!(Test-Path -Path $snmpWalkExe)) {
    try {
        Invoke-WebRequest -Uri $downloadUrl -OutFile $snmpWalkExe
        Write-Host "SnmpWalk.exe downloaded successfully!"
    } catch {
        Write-Host "Error downloading SnmpWalk.exe. Check the URL and connection."
        exit
    }
}

for ($x = $ipStart; $x -le $ipEnd; $x++) {
    $ip = "$ipBase$x"
    $pingResult = "{2}" -f (ping -n 1 -w 8 $ip)
    $response = $pingResult.Substring(0,8)

    if ($response -eq "Resposta") {
        $modelString = "{3}" -f (& $snmpWalkExe -r:$ip -op:.1.3.6.1.2.1.1.1.0)
        $model = $modelString -replace '.*Value='

        if ($model.Length -ge 5) {
            $model = $model.Substring(0,5)
        } else {
            $model = "DESCO"
        }

        switch ($model) {
            "RICOH" {
                $serialString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.4.1.367.3.2.1.2.1.3.0 -op:.1.3.6.1.4.1.367.3.2.1.2.1.4.0)
                $serial = $serialString -replace '.*Value='
                $counterString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.2.1.43.10.2.1.4.1.0 -op:.1.3.6.1.2.1.43.10.2.1.4.1.1)
                $counter = $counterString -replace '.*Value='
                $brandModelString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.2.1.1.4.0 -op:.1.3.6.1.2.1.1.5.0)
                $brandModel = $brandModelString -replace '.*Value='
                $ip + ",RICOH," + $brandModel + "," + $serial + "," + $counter >> $outputFile
                break    
            }
            "Broth" {
                $serialString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.2.1.43.5.1.1.16.1 -op:.1.3.6.1.2.1.43.5.1.1.17.2)
                $serial = $serialString -replace '.*='
                $counterString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.2.1.43.10.2.1.4.1.0 -op:.1.3.6.1.2.1.43.10.2.1.4.1.1)
                $counter = $counterString -replace '.*='
                $brandModelString = "{3}" -f (& $snmpWalkExe -r:$ip -os:.1.3.6.1.2.1.25.3.2.1.3.0 -op:.1.3.6.1.2.1.25.3.2.1.3.1)
                $brandModel = $brandModelString -replace '.*=Brother '
                $ip + ",BROTHER," + $brandModel + "," + $serial + "," + $counter >> $outputFile
                break    
            }
            default {
                $ip + ",UNKNOWN,-,-,-" >> $outputFile
            }
        }
    } 
}
```

---

## ⚠️ Notes:
- **Ensure SNMP is enabled** on the printers before running the script.
- The **network range** (`$ipBase`, `$ipStart`, `$ipEnd`) should be adjusted based on your environment.
- The script automatically **downloads SnmpWalk.exe** if not found locally.
- Results are saved in **C:\TEMP\SNMP\IVENTPRT.txt**.

---

## 💡 When to use?
- To **inventory network printers** and collect model, serial number, and page count.
- For **automated printer monitoring** via SNMP.
- When **manual printer discovery is not feasible** in large networks.

---

## 🔍 Search Tags:
SNMP printer discovery, get printer serial via SNMP, SNMPWalk.exe script, PowerShell SNMP printers, scan network printers, inventory printers with SNMP

---

📂 **`snmp-printer-inventory.md`**

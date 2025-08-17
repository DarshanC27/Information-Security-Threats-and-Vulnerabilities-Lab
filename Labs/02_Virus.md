# Lab 02: Computer Virus – Infection Demonstration

## 🎯 Objective
To understand how **computer viruses** replicate and infect systems, and to analyze their behavior and the required security countermeasures.

---

## 🧪 Lab Environment
- **Attacker Machine**: Admin Machine-1 (Windows VM)
- **Victim Machine**: AD Domain Controller VM (Windows Server)
- **Firewall**: pfSense (running throughout the lab)
- **Tool Used**: JPS Virus Maker (proof-of-concept, for learning only)

---

## 📝 Lab Steps

### Step 1: Snapshot for Safety
- On VMware, created a **snapshot** of AD Domain Controller VM before infection.  
  *(This ensures system can be reverted after the lab.)*

### Step 2: Create the Virus
- On Admin Machine-1:
  - Navigated to:  
    `Z:\CCT Module 01 Information Security Threats and Vulnerabilities\Virus Maker\JPS Virus Maker`
  - Launched `JPS.exe` (Virus Maker 4.0).
- Selected multiple malicious options:  
  - Disable Task Manager  
  - Disable Windows Update  
  - Disable Control Panel  
  - Disable Drives  
  - Auto Startup  
  - Turn Off Windows Firewall & Defender  
- Configured extra payloads:  
  - Change Windows Password → `Pa$$w0rd`  
  - Change Computer Name → `Test`  
- Clicked **Create Virus!** → Generated file `Server.exe`.

### Step 3: Deploy the Virus
- Shared the `Server.exe` file with the **victim machine** (AD Domain Controller).
- Logged into victim machine:  


Username: CCT\Administrator
Password: admin@123

- Executed `Server.exe` → Virus activated.

### Step 4: Observe Infection
- Desktop screen became **blank** → system disruption.
- Attempted login again → original password failed.  
- Logged in with new password set by the virus → `Pa$$w0rd`.
- Tried opening **Task Manager** → access denied.  
- Verified that other system features (Control Panel, Updates) were disabled.

### Step 5: Revert Snapshot
- Shut down infected VM.  
- Reverted to the **snapshot** taken earlier (to restore clean state).

---

## 📸 Screenshots
*(Add screenshots in `/Screenshots/` folder and reference them here)*

Example:
![Virus Maker Interface](../Screenshots/virus_maker.png❤️❤️❤️❤️❤️)  
*JPS Virus Maker tool used to generate a custom virus.*

![Virus Execution](../Screenshots/virus_execution.png❤️❤️❤️❤️❤️)  
*Desktop disruption after executing the virus payload.*

---

## 🔎 Observations
- The virus was able to **replicate malicious behavior** by modifying system settings.
- Demonstrated capabilities included:
- Locking user accounts with a **new password**.
- Disabling security features (Firewall, Defender, Updates).
- Restricting system tools (Task Manager, Control Panel).
- This reflects how **real-world malware disrupts system operations** and causes downtime.

---

## 🛡 Defensive Measures
- **Use Antivirus/EDR** with behavioral detection.  
- Apply **principle of least privilege** to minimize admin rights.  
- Maintain **system backups & snapshots** to recover quickly.  
- Enforce **patch management** for OS and software.  
- Educate users against opening **suspicious executables**.

---

## 📌 Conclusion
This lab demonstrates how attackers can create a virus that **modifies system settings, locks accounts, and disables defenses**.  
Security professionals must implement **defense-in-depth** strategies to detect and mitigate such threats.

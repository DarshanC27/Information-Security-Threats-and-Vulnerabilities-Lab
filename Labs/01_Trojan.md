# Lab 01: Trojan – Remote Access Trojan (RAT) Demonstration

## 🎯 Objective
To understand how attackers use **Remote Access Trojans (RATs)** to gain unauthorized access to a victim system, and to analyze the risks and defensive countermeasures.

---

## 🧪 Lab Environment
- **Attacker Machine**: Admin Machine-1 (Windows VM)
- **Victim Machine**: Web Server VM (Windows Server)
- **Firewall**: pfSense (running throughout the lab)
- **Tool Used**: Theef RAT (proof-of-concept, for learning only)

---

## 📝 Lab Steps

### Step 1: Setup
- Started **Admin Machine-1** and **Web Server VM**.
- Logged into Web Server as:


Username: Administrator
Password: admin@123


### Step 2: Deploy Trojan on Victim
- Navigated to:  
`Z:\CCT Module 01 Information Security Threats and Vulnerabilities\Remote Access Trojans (RAT)\Theef`
- Executed `Server210.exe` → installed the Trojan server on victim.

### Step 3: Connect as Attacker
- On Admin Machine-1, launched `Client210.exe`.
- Entered:
- IP Address: `10.10.1.16` (victim’s IP)
- Port: default (9871)
- Clicked **Connect** → successful connection established.

### Step 4: Control Victim Machine
- Viewed **Computer Information** → PC details, OS, Network.
- Opened **Task Manager** → listed running processes.
- Killed a process remotely using the client.
- Enabled **Keylogger** → recorded victim keystrokes.
- Captured **screenshots** and **webcam feed** from victim.

---

## 📸 Screenshots
*(Add screenshots in `/Screenshots/` folder and reference them here)*

Example:
![Trojan Client Interface](../Screenshots/trojan_client.png❤️❤️❤️❤️❤️❤️)  
*Theef RAT client connected to the victim machine.*

![Trojan Keylogger](../Screenshots/trojan_keylogger.png❤️❤️❤️❤️❤️)  
*Keystrokes captured from victim machine.*

---

## 🔎 Observations
- Trojan allowed **full remote access** to the victim system.
- Attackers could:
- Steal sensitive data (via keylogger/screenshots).
- Control victim processes (via Task Manager).
- Use victim machine for further attacks (pivoting).

---

## 🛡 Defensive Measures
- **Patch Management**: Keep OS and apps updated.  
- **Endpoint Security**: Deploy **EDR/Antivirus** to detect RAT behavior.  
- **Firewall Rules**: Block unused ports (Theef used port `9871`).  
- **User Awareness**: Train users to avoid suspicious downloads/phishing.  
- **Network Monitoring**: Use IDS/IPS to detect unusual outbound traffic.  

---

## 📌 Conclusion
This lab demonstrates how a **Remote Access Trojan (RAT)** can compromise a system and give full control to an attacker.  
Understanding its behavior helps defenders strengthen security controls and mitigate such threats effectively.

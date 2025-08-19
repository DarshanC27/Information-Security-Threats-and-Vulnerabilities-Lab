# Lab 03: Computer Worm – Propagation Demonstration

## 🎯 Objective
To understand how **computer worms** propagate across systems and networks, and to analyze their potential impact and defensive strategies.

---

## 🧪 Lab Environment
- **Victim Machine**: Web Server VM (Windows Server)
- **Firewall**: pfSense (running throughout the lab)
- **Tool Used**: Internet Worm Maker Thing (proof-of-concept, for learning only)

---

## 📝 Lab Steps

### Step 1: Setup
- Started **Web Server VM**.  
- Logged in as:
  

Username: Administrator
Password: admin@123   



### Step 2: Launch Worm Maker
- Navigated to:  
`Z:\CCT Module 01 Information Security Threats and Vulnerabilities\Worm Maker\Internet Worm Maker Thing`
- Executed `Generator.exe`.

### Step 3: Configure Worm
- Entered:
- **Worm Name**: JB Worm  
- **Author**: Jason  
- **Version**: 4.0  
- **Message**: “Your System is Hacked”  
- **Output Path**: `C:\`
- Enabled **Compile to EXE Support** → worm created as an executable.

### Step 4: Add Payloads
- Selected multiple disruptive payloads:
- Hide All Drives  
- Disable Task Manager  
- Disable Keyboard & Mouse  
- Show Pop-up Messages  
- Disable Windows Security & Updates  
- Change IE Homepage → `http://www.moviescope.com`  
- Lock Workstation  
- Trigger Blue Screen of Death (BSOD)  
- Enabled **Infection Options** → Infect `.bat` files.  
- Selected **Extras** → Hide Virus Files.  

### Step 5: Generate Worm
- Clicked **Generate Worm** → successfully created `worm.vbs` in `C:\`.  
- Worm executable stored and ready for execution.  

---

## 📸 Screenshots
*(Add screenshots in `/Screenshots/` folder and reference them here)*

Example:
![Worm Maker Interface](./Screenshots/Worm%20Maker%20Interface.png) 
*Internet Worm Maker Thing – configuration panel.*

![Worm Execution](./Screenshots/Worm%20Execution.png)   
*System disruption after worm payload triggered.*

---

## 🔎 Observations
- Worm was created with **custom payloads** that could:  
- Spread by infecting `.bat` files.  
- Disable system security features.  
- Cause denial-of-service (BSOD).  
- Modify system settings (homepage, registry).  
- Demonstrates how worms **self-propagate without user interaction**, unlike Trojans.  
- Worms can also serve as a **payload carrier** for further malware (botnets).  

---

## 🛡 Defensive Measures
- **Network Segmentation** → limit worm spread between systems.  
- **IDS/IPS Deployment** → detect unusual propagation traffic.  
- **Endpoint Security** → block execution of suspicious `.vbs` or `.exe` files.  
- **Patch Management** → fix known exploits worms rely on.  
- **User Awareness** → avoid running unverified attachments.  

---

## 📌 Conclusion
This lab demonstrates how a worm can be crafted to **propagate across systems and cause disruption**.  
Unlike viruses and trojans, worms spread automatically and can quickly turn into a **large-scale outbreak** if not controlled.  
Strong **network security, monitoring, and patching** are essential to defend against worm attacks.

# Lab 04: Spyware – User System Monitoring & Surveillance

## 🎯 Objective
To understand how **spyware** can be used to monitor user activity in stealth mode, and to analyze its risks along with defensive measures.

---

## 🧪 Lab Environment
- **Host Machine**: AD Domain Controller VM (attacker)  
- **Target Machine**: Web Server VM (victim)  
- **Firewall**: pfSense (running throughout the lab)  
- **Tool Used**: Spytech SpyAgent (proof-of-concept, for learning only)  

---

## 📝 Lab Steps

### Step 1: Setup Remote Connection
- Started **AD Domain Controller** and **Web Server VM**.  
- On AD Domain Controller:  
  - Launched **Remote Desktop Connection**.  
  - Connected to Web Server using:  
    ```
    Username: John
    Password: user@123
    ```
- Established successful remote session with victim machine.

### Step 2: Deploy SpyAgent
- Copied **Spytech SpyAgent** folder to victim’s Desktop.  
- Executed `Setup.exe` (password: `spytech`).  
- Installed SpyAgent with **default settings**.  
- Selected installation type: **Administrator/Tester**.  
- Enabled **Complete + Stealth Configuration** and **Load on Windows Startup**.  

### Step 3: Configure SpyAgent
- Created SpyAgent password: `test@123`.  
- Set SpyAgent to run in **stealth mode** (hidden).  
- Started monitoring → SpyAgent began logging activities silently.  

### Step 4: Victim Activity
- On Web Server VM (as victim user "John"):  
  - Browsed websites (e.g., Gmail).  
  - Created a text file with sensitive information.  
  - Performed normal user operations.  

### Step 5: Retrieve Logs
- On AD Domain Controller:  
  - Brought SpyAgent out of stealth mode (`Ctrl+Shift+Alt+M`).  
  - Entered access password (`test@123`).  
- Viewed collected logs:  
  - **Keystrokes Typed**  
  - **Screenshots of activity**  
  - **Website Usage**  
  - **Files & Documents accessed**  
  - **Email Activity**  

---

## 📸 Screenshots
*(Add screenshots in `/Screenshots/` folder and reference them here)*  

Example:  
![SpyAgent Dashboard](./Screenshots/SpyAgent%20Dashboard.png)  
*SpyAgent interface after retrieving captured data.*  

![Keylogger Logs](./Screenshots/Keylogger%20Logs.png)  
*Keylogger showing victim keystrokes.*  

---

## 🔎 Observations
- SpyAgent ran **completely hidden** from the victim.  
- Captured **sensitive data** such as keystrokes, emails, and browsing history.  
- Delivered logs remotely, showing how spyware exfiltrates data.  
- Demonstrates the **privacy and data theft risks** of spyware.  

---

## 🛡 Defensive Measures
- **Anti-Spyware / ED**

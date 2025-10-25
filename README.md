# Firewall Configuration & Testing (Task 4)

## 📋 Task Overview
Configured and tested the firewall using UFW on Kali Linux. Demonstrated allowing, blocking, deleting specific port rules, and verified behavior with local tests and screenshots.

---

## 🎯 Objectives

- Enable and configure the Linux firewall with UFW.
- Add rules to allow/deny traffic for specific ports.
- Test results (and removal) of firewall rules.
- Document the full workflow with screenshots and command logs.

---

## 🛠️ Tools Used

- 🐧 Kali Linux Terminal
- 🔒 UFW (Uncomplicated Firewall)

---

## ⚙️ Methodology

### 1️⃣ **Check & Install UFW**

```
sudo apt install ufw
```

UFW is already the newest version


### 2️⃣ **Enable Firewall**

```
sudo ufw enable
```

Firewall is active and enabled

### 3️⃣ **List Existing Rules**

```
sudo ufw status numbered
```

View rules list/status 

### 4️⃣ **Allow SSH (Port 22)**

```
sudo ufw allow 22
```

Rule added for SSH (port 22)

### 5️⃣ **Block Telnet (Port 23)**

```
sudo ufw deny 23
```

Rule added for Telnet (port 23)

### 6️⃣ **Check Rules Table**

```
sudo ufw status numbered
```

Rules list showing "DENY IN 23" and "ALLOW IN 22"

### 7️⃣ **Delete a Rule (Allow 22 as Example)**

```
sudo ufw delete 2
```

Rule #2 deleted confirmation

### 8️⃣ **Test Blocked Telnet Locally**

```
telnet localhost 23
```

Connection refused (as expected)

---

## 📝 Commands Used (All Together)

```
sudo apt install ufw       # Install/check UFW
sudo ufw enable            # Enable firewall
sudo ufw status numbered   # List rules
sudo ufw allow 22          # Allow SSH
sudo ufw deny 23           # Deny Telnet
sudo ufw status numbered   # Check numbered rules
sudo ufw delete 2          # Delete rule #2 
telnet localhost 23        # Test Telnet block
```

---

## 🚀 Key Takeaways

- Disabling insecure ports/services is essential for system security.
- Always audit and test firewall configuration.
- UFW simplifies firewall rule management with readable commands.
- Security is increased by blocking unused/insecure ports (e.g. Telnet).
- Testing blocked/allowed ports with network tools confirms rule effectiveness.
- Documentation and screenshots are critical for audits/reports.

---

## 🎤 Interview Q&A

**1. What is a firewall?**  
A security device/software that controls incoming/outgoing traffic based on defined rules.

**2. Difference: Stateful vs Stateless?**  
Stateful tracks connection context, stateless looks only at individual packets.

**3. Inbound/Outbound rules?**  
Inbound: traffic entering; Outbound: traffic leaving.

**4. Why use UFW?**  
Easier and safer for beginners.

**5. Why block Telnet?**  
Telnet is insecure as it uses plaintext, blocking reduces attack surface.

**6. Verifying a rule?**  
Try to connect to a blocked port/service (should fail).

---


## 📂 Repository Structure

```
firewall-config-task4/
├── README.md                 # This file
├── screenshots/images        # Firewall config & test images
├── ufw-commands.txt          # All commands used
├── findings.txt              # List/summary of rule logic
```


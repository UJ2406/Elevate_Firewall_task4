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

## 🧠 Concepts Learned 

1.  **Firewall Fundamentals**
   - Firewalls are essential security tools that filter incoming and outgoing network traffic based on user-defined rules to protect systems from unauthorized access.

2.  **Linux UFW Management**
   - Using UFW (Uncomplicated Firewall), I learned to easily install, enable, and check firewall status and manage iptables rules in a more user-friendly way.

3.  **Rule Creation, Testing, and Deletion**
   - Understood and practiced adding rules to allow (e.g., SSH port 22) and block (e.g., Telnet port 23) specific ports.
   - Practiced deleting unwanted rules and verifying active rule lists with the `status numbered` command.

4.  **Blocking Insecure Services**
   - Telnet (port 23) was specifically blocked due to its insecure, plaintext communication.
   - Only allowing trusted services (like SSH) is a core security practice.

5.  **Testing & Verification**
   - Used telnet command-line tool to verify the firewall’s effectiveness (observed “Connection refused” when blocking was in place).

6.  **Numbered Rule Management**
   - Learned to work with UFW's numbered rules for easy removal and audit, supporting clear and organized rule management.

7.  **Network Port & Protocol Awareness**
   - Differentiated between protocols/ports and understood the security risk and role of each.

8.  **Stateful Filtering**
   - Acknowledged that modern firewalls (like UFW/iptables) are stateful and track active connections for more secure and efficient filtering.

9.  **Documentation & Evidence**
   - Collected command logs and screenshots at each step for proper documentation and audit trail—crucial for real-world infosec reporting.

10.  **General Best Practices**
    - Only open what you need, document all changes, test after every rule, and regularly review/update your rules for continued protection.

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
├── screenshots               # Firewall config & test images
    ├── UFW Installed
    ├── Firewall Enabled
    ├── Allow SSH
    ├── Block Telnet
    ├── Telnet Blocked Test
    ├── Rules Table, Delete Rule Success          
├── ufw-commands.txt          # All commands used
├── findings.txt              # List/summary of rule logic
```


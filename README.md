<!-- Banner -->
<p align="center">
  <img src="https://img.shields.io/badge/Linux-KodeKloud-blue?style=for-the-badge&logo=linux" alt="Linux Badge"/>
  <img src="https://img.shields.io/badge/SysAdmin-DevOps-orange?style=for-the-badge&logo=redhat" alt="SysAdmin Badge"/>
  <img src="https://img.shields.io/badge/Automation-Cron-green?style=for-the-badge&logo=gnubash" alt="Automation Badge"/>
</p>

<h1 align="center">🐧 Linux – KodeKloud Practice Repository</h1>

<p align="center">
  Hands-on practice tasks, solutions, and notes from the <b>KodeKloud Linux Learning Path</b>.  
  A structured collection to strengthen Linux administration and DevOps fundamentals.
</p>

---

## 📂 Repository Structure
Each task is organized by topic and includes problem statements and their corresponding solutions.

Linux-Leve-1/

├── Task-01/ # Custom Apache User Setup

├── Task-02/ # Group Creation and User Assignment  

├── Task-03/ # Linux User Setup with Non-Interactive Shell

├── Task-04/ # Service User Creation without Home Directory

├── Task-05/ # Temporary User Setup with Expiry

├── Task-06/ # Linux User Data Transfer

├── Task-07/ # Secure Root SSH Access

├── Task-08/ # Data Backup for Developer

├── Task-09/ # Script Execution Permissions

├── Task-10/ # File Permission Correction

├── Task-11/ # String Replacement

├── Task-12/ # Secure Data Transfer

├── Task-13/ # Restrict Cron Access (✅ Latest)

└── ...


## ✅ Example Task

### Task 13: Restrict Cron Access

**Problem:**  

Allow only `rose` to use crontab on App Server 3 while denying access to `garrett`.

**Solution:**

```bash
# Allow only rose
echo "rose" | sudo tee /etc/cron.allow

# (Optional) Explicitly deny garrett
echo "garrett" | sudo tee /etc/cron.deny

# Secure the files
sudo chown root:root /etc/cron.allow /etc/cron.deny
sudo chmod 644 /etc/cron.allow /etc/cron.deny
```

**Verification:**

- `rose` → can run `crontab -e`

- `garrett` → denied access

---

🛠 Topics Covered

- User & Group Management
- File Permissions & Ownership
- Package Management (yum, apt, rpm, dpkg)
- Services, Processes & Systemd
- Networking & Firewall
- Storage & Disk Management
- SSH & Security Hardening
- Sudo & Privilege Escalation
- Cron & Automation

---

🎯 Goal

- This repository is a step towards:
- Strengthening my Linux Administration skills.
- Building a solid foundation for DevOps.
- Preparing for real-world troubleshooting scenarios.

---

📌 References

- [KodeKloud Linux Courses](https://kodekloud.com/)
- [The Linux Documentation Project](https://tldp.org/)
- [Red Hat & Ubuntu Official Docs](https://access.redhat.com/documentation)

---

<p align="center"> 👨‍💻 Maintained by <b>Merouane Khadraoui</b><br> 📍 Oran, Algeria </p>
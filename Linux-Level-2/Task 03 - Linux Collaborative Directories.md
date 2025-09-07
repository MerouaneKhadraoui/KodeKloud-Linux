# Task 03: Linux Collaborative Directories

## Question

The Nautilus team doesn't want its data to be accessed by any of the other groups/teams due to security reasons and want their data to be strictly accessed by the `sysops` group of the team.

**Task:**

Setup a collaborative directory `/sysops/data` on `app server 1` in `Stratos Datacenter`.

The directory should be group owned by the group `sysops` and the group should own the files inside the directory. The directory should be `read/write/execute` to the user and group owners, and `others` should not have any access.

---

## Solution

1. **Login to app server 1**

```bash
ssh tony@app01
```

---

2. **Check if the sysops group exists**

From the jump host:

```bash
getent group sysops
```

---

3. **Create the required directory**

```bash
sudo mkdir -p /sysops/data
```

---

4. **Set group ownership**

```bash
sudo chown :sysops /sysops/data
#or 
sudo chgrp sysops /sysops/data
```

---

5. **Set correct permissions**

```bash
sudo chmod 770 /sysops/data
#or
sudo chmod 2770 /sysadmin/data  # Set permissions with SGID
```

---

6. **Enable SGID (Set Group ID) on the directory**

This ensures that new files/directories created inside inherit the `sysops` group automatically.

```bash
sudo chmod g+s /sysops/data
#or
sudo chmod 2770 /sysadmin/data  # Set permissions with SGID
```

---

7. **Verify settings**

```bash
ls -ld /sysops/data
```
Expected output:
```bash
drwxrws--- 2 root sysops 4096 Sep  7 13:00 /sysops/data
```
- `rwxrws---` =
    - owner: rwx
    - group: rwx + `s` (SGID)
    - others: no access

---

🔑 **Final Answer (concise commands)**

```bash
sudo groupadd sysops    # only if group doesn't exist
sudo mkdir -p /sysops/data
sudo chown root:sysops /sysops/data
sudo chmod 2770 /sysops/data
```

(Here `2770` = `2` for SGID + `770` permissions)
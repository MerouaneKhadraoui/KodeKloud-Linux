# Task 13: Restrict Cron Access

## Question

In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.

**Task:**  

Configure crontab access on App Server 3 as follows: Allow crontab access to `rose` user while denying access to the `garrett` user.

---

## Solution

1. **Check the file on jump host**

   ```bash
   ls -l /tmp/nautilus.txt.gpg
   ```

2. **SSH into App Server 1 (from jump host)**

   ```bash
   ssh tony@stapp01
   ```
   Check target directory:

   ```bash
   ls -ld /home/opt
   ```

3. **Use scp from jump host to copy file**

   From the jump host:

   ```bash
   scp /tmp/nautilus.txt.gpg tony@stapp01:/home/opt/
   ```
   
   Enter the password when prompted.

---

## Verification

Verify on App Server 1
SSH again:

```bash
ssh tony@stapp01
ls -l /home/opt/nautilus.txt.gpg
```

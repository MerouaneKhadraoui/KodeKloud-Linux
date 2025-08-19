# Task 12: Secure Data Transfer

## Question

A `Nautilus` developer has stored confidential data on the jump host within `Stratos DC`. To ensure security and compliance, this data must be transferred to one of the app servers. Given developers lack direct access to these servers, the system admin team has been enlisted for assistance.

**Task:**  

Copy `/tmp/nautilus.txt.gpg` file from jump server to `App Server 1` placing it in the directory `/home/opt`.

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

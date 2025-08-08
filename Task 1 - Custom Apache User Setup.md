# Task 1: Custom Apache User Setup

## Question

In response to heightened security concerns, the `xFusionCorp Industries` security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:

**Task:**  
a. Create a user named `james` on `App server 2` within the `Stratos Datacenter`.

b. Assign a unique UID `1286` and designate the home directory as `/var/www/james`.

---

## Solution

```bash
ssh steve@stapp02
sudo su -
id james
useradd -d /var/www/james -u 1286 -m james
chmod -R 755 /var/www/james/
```
Type the password for the user when prompted to complete the user creation process.

---

## Verification

To verify that the user has been created, check by running:

```bash
id james
getent passwd james
ls -lah /var/www/james/
```

**Example Output:**

```text
[root@stapp02 ~]$ id james
uid=1002(james) gid=1003(james) groups=1003(james)
[root@stapp02 ~]$ getent passwd james
james:x:1002:1003::/home/james:/bin/bash
```

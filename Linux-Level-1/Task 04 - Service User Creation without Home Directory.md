# Task 4: Service User Creation without Home Directory

## Question

In response to the latest tool implementation at `xFusionCorp Industries`, the system admins require the creation of a service user account. Here are the specifics:

**Task:**  
Create a user named `mariyam` in `App Server 3` without a home directory.

---

## Solution

```bash
ssh banner@stapp03
sudo useradd -M mariyam
```
Type the password for the user when prompted to complete the user creation process.

---

## Verification

To verify that the user has been created with a non-interactive shell, check the user's shell by running:

```bash
id mariyam
getent passwd mariyam
cat /etc/passwd | grep mariyam
```

**Example Output:**

```text
[banner@stapp03 ~]$ id mariyam 
uid=1002(mariyam) gid=1002(mariyam) groups=1002(mariyam)
[banner@stapp03 ~]$ getent passwd mariyam
mariyam:x:1002:1002::/home/mariyam:/bin/bash
[banner@stapp03 ~]$ cat /etc/passwd | grep mariyam
mariyam:x:1002:1002::/home/mariyam:/bin/bash
```

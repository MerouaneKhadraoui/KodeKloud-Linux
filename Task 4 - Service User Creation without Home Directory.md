# Task 4: Service User Creation without Home Directory

## Question

The system admins team of `xFusionCorp Industries` has set up a new tool on all app servers, as they have a requirement to create a service user account that will be used by that tool. They are finished with all apps except for `App Server 3` in `Stratos Datacenter`.



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
[banner@stapp03 ~]# getent passwd mariyam
mariyam:x:1002:1002::/home/mariyam:/bin/sh
```

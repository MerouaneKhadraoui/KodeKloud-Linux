# Task 2: Group Creation and User Assignment

## Question

There are specific access levels for users defined by the `xFusionCorp Industries` system admin team. Rather than providing access levels to every individual user, the team has decided to create groups with required access levels and add users to that groups as needed. See the following requirements:

**Task:**  
a. Create a group named `nautilus_sftp_users` in all App servers in `Stratos Datacenter`.
b. Add the user `kano` to `nautilus_sftp_users` in all App servers.

---

## Solution

```bash
ssh tony@stapp01.stratos.xfusioncorp.com
sudo groupadd nautilus_sftp_users
id kano
sudo useradd -G nautilus_sftp_users -m kano
```
Type the password for the user when prompted to complete the group creation process.

---

## Verification

To verify that the group and user has been created, check by running:

```bash
id kano
getent group nautilus_sftp_users
getent passwd kano
```

**Example Output:**

```text
[tony@stapp01 ~]$ getent group nautilus_sftp_users
nautilus_sftp_users:x:1003:
[tony@stapp01 ~]$ getent passwd kano
kano:x:1003:1004::/home/kano:/bin/sh
[tony@stapp01 ~]$ id kano
uid=1003(kano) gid=1004(kano) groups=1004(kano),1003(nautilus_sftp_users)
```

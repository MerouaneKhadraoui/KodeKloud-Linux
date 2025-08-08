# Task 2: Group Creation and User Assignment

## Question

The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:

**Task:**  
a. Create a group named `nautilus_noc` across all App servers within the `Stratos Datacenter`.

b. Add the user `kano` into the `nautilus_noc` group on all App servers. If the user doesn't exist, create it as well.

---

## Solution

```bash
ssh tony@stapp01
sudo groupadd nautilus_noc
id kano
sudo useradd -G nautilus_noc -m kano
```
Type the password for the user when prompted to complete the group creation process.

---

## Verification

To verify that the group and user has been created, check by running:

```bash
id kano
getent group nautilus_noc
getent passwd kano
groups kano
```

**Example Output:**

```text
[tony@stapp01 ~]$ id kano
uid=1002(kano) gid=1003(kano) groups=1003(kano),1002(nautilus_noc)
[tony@stapp01 ~]$ getent group nautilus_noc
nautilus_noc:x:1002:
[tony@stapp01 ~]$ getent passwd kano
kano:x:1002:1003::/home/kano:/bin/bash
[tony@stapp01 ~]$ groups kano
kano : kano nautilus_noc
```

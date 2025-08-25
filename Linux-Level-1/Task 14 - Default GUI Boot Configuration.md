# Task 14: Default GUI Boot Configuration

## Question

With the installation of new tools on the app servers within the `Stratos Datacenter`, certain functionalities now necessitate graphical user interface (GUI) access.

**Task:**  

Adjust the `default runlevel` on all App servers in `Stratos Datacenter` to enable GUI booting by default. It's imperative not to initiate a server reboot after completing this task.

---

## Solution

You need to allow `rose` and deny `garrett` on App Server 3.

1. **Check Current Default Target**

```bash
systemctl get-default
```
Likely it will show:

```bash
multi-user.target
```


2. **Set Default Target to GUI**

```bash
sudo systemctl set-default graphical.target
```
Output:

```swift
Created symlink /etc/systemd/system/default.target → /usr/lib/systemd/system/graphical.target.
```

3. **(Optional) Verify New Default**

```bash
systemctl get-default
```
It should now show:

```bash
graphical.target
```

⚠️ Do NOT reboot – task explicitly says no reboot.

---

✅ **Final Answer (KodeKloud-style)**

On each app server run:

```bash
sudo systemctl set-default graphical.target
systemctl get-default   # verify → should return "graphical.target"
```
No need to restart the system.
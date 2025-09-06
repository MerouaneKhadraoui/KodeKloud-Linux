# Task 02: Linux Banner

## Question

During the monthly compliance meeting, it was pointed out that several servers in the `Stratos DC` do not have a valid banner. The security team has provided serveral approved templates which should be applied to the servers to maintain compliance. These will be displayed to the user upon a successful login.

**Task:**

Update the `message of the day` on all application and db servers for `Nautilus`. Make use of the approved template located at `/home/thor/nautilus_banner` on jump host

---

## Solution

1. **Check the banner file**

```bash
cat /home/thor/nautilus_banner
```
This is the content that should be copied.

---

2. **Copy banner file to App Servers and DB Server**

From the jump host:

```bash
# App Server 1
scp /home/thor/nautilus_banner tony@stapp01:/etc/motd

# App Server 2
scp /home/thor/nautilus_banner steve@stapp02:/etc/motd

# App Server 3
scp /home/thor/nautilus_banner banner@stapp03:/etc/motd

# DB Server
scp /home/thor/nautilus_banner peter@stdb01:/etc/motd
```

---

3. **Verification**

On any of the servers, run:

```bash
cat /etc/motd
```
✅ It should display the content from nautilus_banner.

---

🔹 Final Notes

- The jump host is only for connecting and copying.
- Always place the banner in `/etc/motd`, since that file is displayed after login.
- Sometimes `sudo` is needed because `/etc/motd` is root-owned.
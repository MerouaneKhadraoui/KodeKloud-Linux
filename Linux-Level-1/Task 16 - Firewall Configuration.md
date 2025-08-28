# Task 16: Firewall Configuration

## Question

The `Nautilus` system admins team has rolled out a web UI application for their backup utility on the `Nautilus backup server` within the `Stratos Datacenter`. This application operates on port `8083`, and `firewalld` is active on the server. To meet operational needs, the following requirements have been identified:

**Task:**  

Allow all incoming connections on port `8083/tcp`. Ensure the zone is set to `public`.

---

## Solution

Here's the exact step-by-step solution you'd run on the Nautilus backup server:

1. **Check if firewalld is running**

```bash
sudo systemctl status firewalld
```
If it's not active, start it:

```bash
sudo systemctl start firewalld
```

2. **Verify the active zone**

```bash
sudo firewall-cmd --get-active-zones
```
👉 Normally it should show public as the default zone.
If not, set the default zone to **public**:

```bash
sudo firewall-cmd --set-default-zone=public
```

3. **Add a permanent rule to allow port 8083/tcp**

```bash
sudo firewall-cmd --zone=public --add-port=8083/tcp --permanent
```

4. **Reload firewalld to apply changes**

```bash
sudo firewall-cmd --reload
```

5. **Confirm the rule is applied**

```bash
sudo firewall-cmd --zone=public --list-ports
```
You should see:

```bash
8083/tcp
```

---

✅ Done — now all incoming connections on `8083/tcp` are allowed in the `public` zone.
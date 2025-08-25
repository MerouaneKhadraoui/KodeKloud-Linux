# Task 13: Restrict Cron Access

## Question

In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.

**Task:**  

Configure crontab access on `App Server 3` as follows: Allow crontab access to `rose` user while denying access to the `garrett` user.

---

## Solution

You need to allow `rose` and deny `garrett` on App Server 3.

1. **Login to App Server 3**

```bash
ssh banner@stapp03
# (or use the provided access in your KodeKloud lab)
```

2. **Create/modify `/etc/cron.allow`**

Since you only want `rose` to have cron access:

```bash
echo "rose" | sudo tee /etc/cron.allow
```

3. **Make sure `garrett` is denied**

If you still want explicit denial, you can also add him to `/etc/cron.deny`:

```bash
echo "garrett" | sudo tee /etc/cron.deny
```

4. **Set proper permissions (for security compliance):**

```bash
sudo chown root:root /etc/cron.allow /etc/cron.deny
sudo chmod 644 /etc/cron.allow /etc/cron.deny
```

---

🔎 **Verification**

- Test as `rose`:

```bash
su - rose
crontab -e
```

→ Should work ✅

- Test as garrett:

```bash
su - garrett
crontab -e
```


→ Should give “You (garrett) are not allowed to use this program (crontab)” ❌

---

⚡ **Final Note**: Since `/etc/cron.allow` exists, only users in it will have access. That automatically denies everyone else (including `garrett`).

👉 So the cleanest solution is **just put** `rose` **in** `/etc/cron.allow`, no need to touch cron.deny.
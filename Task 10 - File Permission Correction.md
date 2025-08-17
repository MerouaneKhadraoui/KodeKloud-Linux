# Task 10: File Permission Correction

## Question

After conducting a security audit within the `Stratos DC`, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named `/etc/resolv.conf` on `Nautilus App 1` server requires adjustments to its Access Control Lists (ACLs) as follows:

**Task:**  

1. The file's user owner and group owner should be set to `root`.

2. `Others` should possess `read only` permissions on the file.

3. User `javed` must not have any permissions on the file.

4. User `jerome` should be granted `read only` permission on the file.

---

## Solution

1. **Login to App Server 1**

   ```bash
   ssh tony@stapp01
   ```

2. **Ensure correct ownership**

   ```bash
   sudo chown root:root /etc/resolv.conf
   ```

   - This sets user owner = root and group owner = root.

3. **Set basic permissions**

   We need:

   - Owner (`root`) → default system should have full (read/write).
   - Group (`root`) → usually read/write.
   - Others → read only.

   ```bash
   sudo chown root:root /etc/resolv.conf
   ```
   
   This makes:

   - `root` (user): read + write
   - `root` (group): read
   - Others: read

4. **Deny all permissions for `javed`**

   We use **ACL** for this:

   ```bash
   sudo setfacl -m u:javed:--- /etc/resolv.conf
   ```

5. **Grant read-only permission to `jerome`**

   ```bash
   sudo setfacl -m u:jerome:r-- /etc/resolv.conf
   ```

---

## Verification

To verify the permissions, run:

```bash
ls -l /etc/resolv.conf
getfacl /etc/resolv.conf
```

- `ls -l` should show:

```bash
-rw-r--r-- 1 root root ...
```

- `getfacl` should show ACL entries for `javed` (no permissions) and `jerome` (read).
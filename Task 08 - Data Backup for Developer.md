# Task 8: Data Backup for Developer

## Question

Within the Stratos DC, the Nautilus storage server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `javed` has requested a copy of their data stored in `/data/javed`. The System Admin team has provided the following steps to fulfill this request:

**Task:**  

a. Create a compressed archive named `javed.tar.gz` of the `/data/javed` directory.

b. Transfer the archive to the `/home` directory on the Storage Server.

---

## Solution

1. **Login to Storage Server**

   ```bash
   ssh natasha@ststor01
   sudo -i
   #Password : Bl@kW
   ```

2. **Create a compressed archive**

   Create a compressed archive of `/data/javed`.
   Use `tar` with the `-czf` options:

   ```bash
   tar -czf javed.tar.gz /data/javed
   ```

   ***Explanation:***
   - `tar` → create an archive.
   - `-c` → create.
   - `-z` → compress using gzip.
   - `-f javed.tar.gz` → name of the resulting archive.
   - `/data/javed` → source directory.

3. **Move the archive**
   Move the archive to `/home`.
   Once the archive is created in your current working directory, move it:

   ```bash
   mv javed.tar.gz /home/
   ```


---

## ✅ Final combined command (optional in one line):

To verify the permissions, run:

```bash
tar -czf /home/javed.tar.gz /data/javed
```
This way, the archive is directly created in `/home` without needing `mv`.

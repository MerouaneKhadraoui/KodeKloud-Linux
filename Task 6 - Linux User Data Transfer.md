# Task 6: Linux User Data Transfer

## Question

Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus `App Server 3` at the `/home/usersdata` location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:

**Task:**  

Locate all files (excluding directories) owned by user `mark` within the `/home/usersdata` directory on `App Server 3`. Copy these files while preserving the directory structure to the `/official` directory.

---

## Solution

```bash
sudo find /home/usersdata -type f -user mark -exec cp --parents {} /official \;
```
Type the password for the user when prompted to complete the task.

---

## Explanation

- `find /home/usersdata` → start search in `/home/usersdata`.

- `-type f` → only files.

- `-user mark` → owned by user `mark`.

- `-exec cp --parents {} /official \;` → copy files to `/official` while keeping original directory structure intact.

Example: `/home/usersdata/project/file.txt` → `/official/home/usersdata/project/file.txt`

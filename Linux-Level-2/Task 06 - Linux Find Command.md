# Task 06: Linux Find Command

## Question

During a routine security audit, the team identified an issue on the Nautilus App Server. Some malicious content was identified within the website code. After digging into the issue they found that there might be more infected files. Before doing a cleanup they would like to find all similar files and copy them to a safe location for further investigation. Accomplish the task as per the following requirements:

**Task:**

a. On `App Server 1` at location `/var/www/html/media` find out all files (not directories) having `.js` extension.

b. Copy all those files along with their `parent directory structure` to location `/media` on same server.

c. Please make sure not to copy the entire `/var/www/html/media` directory content.

---

## Solution

1. **Login to app server 1**

```bash
ssh tony@app01
```

---

2. **DIdentify all .js files**

```bash
find /var/www/html/media -type f -name "*.js"
```
This will list only files (not directories).

---

3. **Copy them to /media while preserving the parent directory structure**

We can use cp --parents or rsync.

```bash
find /var/www/html/media -type f -name "*.js" -exec cp --parents {} /media \;
```
- `--parents` ensures the directory hierarchy under `/var/www/html/media` is preserved when copying.
- Example: If file is `/var/www/html/media/js/app.js`, it will be copied as `/media/var/www/html/media/js/app.js`.

---

🔑 **Final Answer**

```bash
find /var/www/html/media -type f -name "*.js" -exec cp --parents {} /media \;
```

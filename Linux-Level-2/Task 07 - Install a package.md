# Task 07: Install a package

## Question

As per new application requirements shared by the `Nautilus` project development team, serveral new packages need to be installed on all app servers in `Stratos Datacenter`. Most of them are completed except for `git`.

**Task:**

Therefore, install the `git` package on all `app-servers`.

---

## Solution

1. **SSH into each App Server**

```bash
ssh tony@app01
```
(Replace `tony` with the right user given in the KodeKloud lab; sometimes it’s `tony`, `steve`, or `banner` depending on the server).

---

2. **Check if `git` is installed**

```bash
git --version
```
If it’s missing, you’ll see `command not found`.

---

3. **Install `git`**

```bash
sudo yum install -y git
```

---

4. **Check if `git` is installed**

```bash
git --version
```
You should see something like:

```bash
git version 2.47.1
```
---

5. **Repeat for all App Servers**

Do steps 1–4 on each `app-server`.
Once `git` is installed everywhere, the task is complete ✅.
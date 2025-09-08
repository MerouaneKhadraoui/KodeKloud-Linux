# Task 04: Linux String Substitute (sed)

## Question

There is some data on `Nautilus App Server 1` in `Stratos DC`. Data needs to be altered in several of the files. On `Nautilus App Server 1`, alter the `/home/BSD.txt` file as per details given below:

**Task:**

a. Delete all lines containing word `following` and save results in `/home/BSD_DELETE.txt` file. (Please be aware of case sensitivity)


b. Replace all occurrence of word `from` to `them` and save results in `/home/BSD_REPLACE.txt` file.


`Note:` Let's say you are asked to replace word `to` with `from`. In that case, make sure not to alter any words containing the string itself; for example upto, contributor etc.

---

## Solution

1. **Login to app server 1**

```bash
ssh tony@app01
```

---

2. **Delete all lines**

```bash
sed '/following/d' /home/BSD.txt > /home/BSD_DELETE.txt
```
- `/following/d` → deletes any line that contains the exact string `following` (case-sensitive).
- `>` redirects output into `/home/BSD_DELETE.txt`.

---

3. **Replace all occurrences of word**

```bash
sed 's/\<from\>/them/g' /home/BSD.txt > /home/BSD_REPLACE.txt
```
- `s/.../.../g` → substitute all occurrences on each line.
- `\<from\>` → matches the **whole word** `from` only (not inside another word like `upfrom` or `infromation`).
- Output goes into `/home/BSD_REPLACE.txt`.

---

4. **Verification**

- Make sure there are no lines containing `following`:
```bash
grep -n "following" /home/BSD_DELETE.txt
```
If nothing shows up → ✅ good (no matches found).
Or quickly confirm difference with original:
```bash
diff /home/BSD.txt /home/BSD_DELETE.txt | grep following
```

- Make sure all `from` are replaced with `them`:
```bash
grep -n "from" /home/BSD_REPLACE.txt
```
If nothing shows up → ✅ all replaced.

To highlight replacements:
```bash
grep -n --color=always "them" /home/BSD_REPLACE.txt
```
---

🔑 **Final Answer**

```bash
sed '/following/d' /home/BSD.txt > /home/BSD_DELETE.txt
sed 's/\<from\>/them/g' /home/BSD.txt > /home/BSD_REPLACE.txt
```

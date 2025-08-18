# Task 11: String Replacement

## Question

Within the Stratos DC, the backup server holds template XML files crucial for the Nautilus application. Before utilization, these files require valid data insertion. As part of routine maintenance, system admins at `xFusionCorp Industries` employ string and file manipulation commands.

**Task:**  

Your task is to substitute all occurrences of the string `Random` with `Software` within the XML file located at `/root/nautilus.xml` on the backup server.

---

## Solution

You need to replace all occurrences of `Random` with `Software` in the file `/root/nautilus.xml`.

Run this command:

```bash
sed -i 's/Random/Software/g' /root/nautilus.xml
```

---

## Explanation

- `sed` → stream editor for text manipulation.
- `-i` → edits the file in place (saves changes directly to /root/nautilus.xml).
- `'s/Random/Software/g'` →
   - `s` = substitute
   - `Random` = pattern to find
   - `Software` = replacement string
   - `g` = global replacement (all occurrences in each line).

---

## Verification

After running the command, check the file:

```bash
cat /root/nautilus.xml | grep Software
```

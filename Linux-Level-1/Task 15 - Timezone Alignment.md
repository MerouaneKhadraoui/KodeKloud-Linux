# Task 15: Timezone Alignment

## Question

In the daily standup, it was noted that the timezone settings across the `Nautilus Application Servers` in the `Stratos Datacenter` are inconsistent with the local datacenter's timezone, currently set to `America/Bahia_Banderas`.

**Task:**  

Synchronize the timezone settings to match the local datacenter's timezone (`America/Bahia_Banderas`).

---

## Solution

You need to allow `rose` and deny `garrett` on App Server 3.

1. **CSSH into each Nautilus Application Server (usually `stapp01`, `stapp02`, `stapp03`).**

```bash
ssh tony@stapp01
ssh steve@stapp02
ssh banner@stapp03
```
(Passwords are normally provided in the KodeKloud portal instructions.)

2. **Check the current timezone**

```bash
timedatectl
```

3. **List available timezones (to confirm spelling and path)**

```bash
timedatectl list-timezones | grep Bahia
```
You should see:

```bash
America/Bahia_Banderas
```

---

4. **Set the timezone to `America/Bahia_Banderas`**

```bash
sudo timedatectl set-timezone America/Bahia_Banderas
```

---

5. **Verify the change**

```bash
timedatectl
```
Output should now show:

```pgsql
Time zone: America/Bahia_Banderas (CDT, -0500)
```

---

6. **Repeat steps 1–5 on each application server until all are aligned**

---

✅ After completing on all `stappXX` servers, timezone settings across the Nautilus Application Servers will be consistent with the datacenter timezone (`America/Bahia_Banderas`).
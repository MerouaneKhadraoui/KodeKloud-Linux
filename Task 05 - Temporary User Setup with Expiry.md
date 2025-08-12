# Task 5: Temporary User Setup with Expiry

## Question

As part of the temporary assignment to the `Nautilus` project, a developer named `yousuf` requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

**Task:**  

Create a user named `yousuf` on `App Server 3` in Stratos Datacenter. Set the expiry date to `2024-03-28`, ensuring the user is created in lowercase as per standard protocol.

---

## Solution

```bash
ssh banner@stapp03
sudo useradd -e 2024-03-28 yousuf
```
Type the password for the user when prompted to complete the user creation process.

---

## Verification

To verify the expiry date for the user, run:

```bash
sudo chage -l yousuf
```

The output should show the account expiration date as `Mar 28, 2024`.

**Example Output:**

```text
Account expires    : Mar 28, 2024
```

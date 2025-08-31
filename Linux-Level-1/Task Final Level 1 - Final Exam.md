# Final Exam - Linux Level 1

## Question 1 (Weight: 8)

The system admins team want to create a user on an app server in `Stratos Datacenter`. Create the user as per the details given below:

Create a user named `ryan` with a `non-interactive` shell on `App server 1` in `Stratos Datacenter`.

---

## Question 2 (Weight: 8)

After conducting comprehensive security audits on its servers, `xFusionCorp Industries` security team has instituted several new security measures. Among these measures is the discontinuation of direct root login through SSH.

Disable direct SSH `root` login across all application servers located in the `Stratos Datacenter`.

---

## Question 3 (Weight: 10)

As part of the temporary resource allocation, `Jim` has been appointed to the Nautilus project as a backup developer. To facilitate this, a temporary user account is required for `Jim`. It is advisable to create a user account with a specified expiration date to ensure restricted server access beyond the designated period.

A user profile under the name `jim` has already been established on `App Server 1` within the `Stratos Datacenter`. Adjust the account's expiration date to `2024-04-15`. Additionally, locate all files (excluding directories) owned by this user within the `/home/usersdata` directory and copy them to the `/beta` directory while maintaining their original ownership.

---

- user 'jim' owned files are not copied to directory '/beta' on App Server 1

---

## Question 4 (Weight: 12)

The `Nautilus` security team performed an audit on all servers present in `Stratos DC`. During the audit some critical data/files were identified which were having the wrong permissions as per security standards. Once the report was shared with the production support team, they started fixing the issues one by one. It has been identified that one of the files named `/etc/hosts` on `Nautilus App 1` server has wrong permissions, so that needs to be fixed and the correct ACLs needs to be applied.

a. User `virat` must not have any permission on this file.

b. User `vivek` should have `read only` permission on this file. Further, `dbadmin` group should have `read/write` permissions on this file.

---

## Question 5 (Weight: 8)

Some directories and files needed to be created on an app server in `Stratos Datacenter`. Complete this task as per the details mentioned below:

Create a directory named `/opt/itadmin` on `App server 1` in `Stratos Datacenter`.
Further, create a blank file named `/opt/itadmin/itadmin.txt`.

---

## Question 6 (Weight: 14)

The development team requires specific logs stored within the Nautilus storage server situated in the Stratos DC. Access the designated location on the server to retrieve the necessary logs. Further, perform below actions:

Create a `tar` archive named `logs.tar` (under natasha's home) of `/var/log/` directory.
Now, create a compressed tar archive as well named `logs.tar.gz` (under natasha's home) of `/var/log/` directory.

---

## Question 7 (Weight: 14)

There is some data on `Nautilus App Server 1` in `Stratos DC`. Data needs to be altered in some of the files. On `Nautilus App Server 1`, alter the `/home/BSD.txt` file as per details given below.


a. Delete all lines containing the word `following` and save the results in `/home/BSD_DELETE.txt` file. (Please be aware of case sensitivity)

b. Replace all occurrences of the word `from` (look for the exact match) with `for` and save the results in `/home/BSD_REPLACE.txt` file.

`Note:` Let's say you are asked to replace the word `to` with `from`. In that case, make sure not to alter any words containing the string itself, for example; up**to**, contribu**to**r etc.

---

## Question 8 (Weight: 8)

The xFusionCorp Industries security team recently did a security audit of their infrastructure and came up with some ideas to improve the application and server security. They decided to use SElinux for an additional security layer. They are still planning how they will implement it, however, they have decided to start testing with app servers, so based on the recommendations they have the following requirements:

Install the required packages of SElinux on `App server 1` in `Stratos Datacenter` and `disable` it permanently for now, it will be enabled after making some required configuration changes on this host. Don't worry about rebooting the server as there is already a reboot scheduled during tonight's maintenance window. Also ignore the status of the SElinux command line right now; the final status after reboot should be `disabled`.

---

## Question 9 (Weight: 14)

During the security audit last week, the security team found some issues on one of the app servers in `Stratos DC`. They shared a report and asked to apply some resource limits for some users.

Configure a resource limit (hard limit) for the `developers` group so that this group cannot exceed `5 logins` (maxlogins) on `App server 1` in `Stratos Datacenter`    .

---

## Question 10 (Weight: 4)

The `Nautilus` system admins team recently deployed a web UI application for their backup utility running on the `Nautilus backup server` in `Stratos Datacenter`. The application is running on port `3001`. They have a `firewalld` installed on that server. The requirements that have come up include the following:

Open all incoming connections on `3001/tcp` port, zone should be `public`.

---


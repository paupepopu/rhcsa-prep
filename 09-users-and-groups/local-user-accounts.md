# Local User Accounts and Root Password

**Exam Objective:** Manage users and groups\
**Course Reference:**\
**Date:**

## Practice Task

**Task (2026-08-21):** Set the root password and created a local user "student" with a password, during RHEL installation.

**Verification:**

```bash
id student
uid=1000(student) gid=1000(student) groups=1000(student),10(wheel)

grep student /etc/passwd
student:x:1000:1000:student:/home/student:/bin/bash
```

User "student" confirmed created with a home directory and shell, and is a member of the `wheel` group (sudo access).

*Related to install lab — see also [`06-file-systems`](../06-file-systems/partition-layout-and-mount-points.md) and [`08-basic-networking`](../08-basic-networking/network-interface-configuration.md).*

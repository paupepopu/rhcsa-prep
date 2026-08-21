# Network Interface Configuration (DHCP)

**Exam Objective:** Manage basic networking\
**Course Reference:**\
**Date:**

## Practice Task

**Task (2026-08-21):** Configured the network interface to obtain an
address via DHCP, during RHEL installation.

**Verification:**

```bash
ip a
ens160: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet [private IP]/24 scope global dynamic noprefixroute ens160

nmcli device show ens160
GENERAL.STATE:   100 (connected)
IP4.ADDRESS[1]:  [private IP]/24
IP4.GATEWAY:     [redacted]
IP4.DNS[1]:      [redacted]

ping -c 3 8.8.8.8
3 packets transmitted, 3 received, 0% packet loss
```

Interface came up with a `dynamic` address (confirms DHCP, not static),
and external connectivity confirmed via ping.

*Related to install lab — see also [`06-file-systems`](../06-file-systems/partition-layout-and-mount-points.md) and [`09-users-and-groups`](../09-users-and-groups/local-user-accounts.md).*

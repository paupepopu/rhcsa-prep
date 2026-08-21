# Partition Layout and Mount Points

**Exam Objective:** Create and configure file systems — mount file systems, configure swap space\
**Course Reference:** Sander van Vugt RHCSA Course — Module 1, Installing with Custom Partitioning Lesson\
**Date:** 2026-08-21

## Summary

Partitions are typically mounted on different directories. During custom partitioning at install, RHEL displays a list of the most commonly used directories for mount points, each with a specific purpose:

- **`/boot`** — holds the kernel, initramfs, and bootloader files needed to
  start the system. Kept separate so it stays reachable even if the rest
  of the filesystem (e.g., an encrypted or LVM `/`) isn't mountable yet
  at boot time.
- **`/boot/efi`** — the EFI System Partition (ESP) is only present on UEFI systems. Holds bootloader files the UEFI firmware reads directly.
- **`/`** (root) — the main filesystem holding the OS and most data not otherwise split into its own mount point.
- **swap** — disk space used as overflow when RAM is full.

## Pitfalls

- Confusing `/boot` (kernel/bootloader files, always needed) with
  `/boot/efi` (firmware-readable ESP, UEFI-only) — not the same thing,
  both can exist on the same system.

## Practice Task

**Task (2026-08-21):** Installed RHEL with 10GiB root, 1GiB swap, left 8.41GiB unused.

**Verification:**

```bash
df -h /
/dev/nvme0n1p2   10G  5.8G  4.2G  59%  /

swapon -s
/dev/nvme0n1p3   partition   1048572 (≈1GiB)   -2

lsblk
nvme0n1p1   600M   /boot/efi
nvme0n1p2    10G   /
nvme0n1p3     1G   [SWAP]
```

Root and swap partitions confirmed at expected sizes; `/boot/efi` present
(UEFI system).

*Related to install lab — see also [`09-users-and-groups`](../09-users-and-groups/local-user-accounts.md) and [`08-basic-networking`](../08-basic-networking/network-interface-configuration.md).*

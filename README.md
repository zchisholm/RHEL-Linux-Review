# RHEL-Linux-Review

## Hard Links vs Soft Links
- Hard Link
  A hard link creates another reference to an existing file on the disk. Both the hard link and the original file point to the same data block. Changes made to one are reflected in the other.
  
**Example**
```bash
  ln <source_file> <link_name>
```
- Soft Link
  A soft link (also known as a symbolic link) acts like a pointer to another file. It stores the path to the original file. Modifying the original file affects the linked file, but changes to the soft link itself have no impact.

**Exmaple**
```bash
ln -s <source_file> <link_name>
```

## Locating the uid:gid of a file

To find the user ID (UID) and group ID (GID) of a file, use the `ls -l` command.

## What is a Sticky Bit set?

The sticky bit is a special permission that affects how files within a directory are deleted. When set on a directory, only the owner of the file or the root user can delete it, regardless of write permissions for the group or others.

Setting the sticky bit:

```bash
chmod +t <directory_name>
```

Unsetting the sticky bit:

```bash
chmod -t <directory_name>
```

## Raid 0, 1, 5, 6

- **RAID 0** (Striping): Splits data evenly across two or more disks, with no redundancy, offering improved performance but no fault tolerance.
- **RAID 1** (Mirroring): Duplicates data across two or more disks, offering fault tolerance at the cost of halved storage capacity.
- **RAID 5** (Striped with Parity): Distributes parity information across three or more disks, providing a balance of good performance, storage efficiency, and fault tolerance.
- **RAID 6** (Striped with Double Parity): Similar to RAID 5 but with double parity, allowing it to withstand the failure of two disks.

## Creating: Vol group, logical volume, and file system

To create a volume group, use `vgcreate`. For a logical volume, use `lvcreate` within a volume group. Finally, format the logical volume with a file system using `mkfs`.
For example:
```bash
lvcreate
mkfs.ext4
```

## What are LUKS Volumes

A LUKS stands for Linux Unified Key Setup. It's a specification for disk encryption. It secures data on a volume by requiring a passphrase or key to access the encrypted data, enhancing data security at rest.

## Access Control:  Discretionary and Mandatory

- **Discretionary Access Control (DAC)**: Access control is at the discretion of the owner, who can set permissions for other users.
- **Mandatory Access Control (MAC)**: Enforces access control policies at a system-wide level, beyond the discretion of individual users, typically managed by security policies like SELinux.


## Configuring usbguard

`usbguard` is a security framework for regulating USB device access to a Linux system. It can be configured via the `usbguard` command-line interface or through its configuration file to allow, block, or reject USB devices.

For example:
```bash
# TODO://
```

## Adding a user to sudoer file

1. Edit the Sudoers File with `visudo`
   ```bash
   sudo visudo
   ```
2. 
### What is ALL = (ALL)

In the sudoers file, `ALL = (ALL)` allows a user to execute any command as any user on any host, providing broad administrative privileges.

## Setting up a network interface from a command line

Use the `nmcli` or `ip` command to configure network interfaces. `nmcli` is a command-line client for NetworkManager, while `ip` is a lower-level utility for managing network interfaces, routes, and policies.

## Setting up a firewall

## Disallow ssh connection for root 

## Configuring RHEL and Active Directory (AD)

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

## What are Luks Volumes

## Access Control:  Discretionary and Mandatory

## Configuring usbguard

## Adding a user to sudoer file
### What is ALL = (ALL)

## Setting up a network interface from a command line

## Setting up a firewall

## Disallow ssh connection for root 

## Configuring RHEL and Active Directory (AD)

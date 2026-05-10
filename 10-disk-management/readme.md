
# Disk and Storage Management in Linux

Managing disks and storage is one of the most important tasks for Linux administrators and DevOps engineers.
Linux provides powerful commands to check disk usage, create partitions, format disks, mount storage, manage LVM, and configure swap memory.

This section covers the most commonly used Linux disk and storage management commands.

---

# Topics Covered

## Disk Information Commands

* `lsblk` — View available disks and partitions
* `fdisk -l` — Display partition details
* `blkid` — Show device UUID information
* `df -h` — Check filesystem disk usage
* `du -sh` — Check directory size

---

## Partition Management Commands

* `fdisk` — Create and manage partitions
* `parted` — Manage GPT partition tables
* `mkfs.ext4` — Format partition with ext4 filesystem
* `mkfs.xfs` — Format partition with XFS filesystem

---

## Mount and Unmount Commands

* `mount` — Attach filesystem to a directory
* `umount` — Detach mounted filesystem
* `mount -o remount,rw` — Remount filesystem in read-write mode

---

## LVM (Logical Volume Management)

* `pvcreate` — Create physical volume
* `vgcreate` — Create volume group
* `lvcreate` — Create logical volume
* `mkfs.ext4` — Format logical volume
* `mount` — Mount logical volume

---

## Swap Space Management

* `mkswap` — Create swap area
* `swapon` — Enable swap
* `swapoff` — Disable swap

---

# Viewing Disk and Storage Information

## Check Available Disks

Use the following command to view all available disks and partitions:

```bash
lsblk
```

---

## View Partition Details

```bash
fdisk -l
```

This command displays detailed partition information for all disks.

---

## Check Disk Space Usage

```bash
df -h
```

The `-h` option displays output in human-readable format.

---

## Check Directory Size

```bash
du -sh /var/log
```

This command shows the total size of a directory.

---

# Partition Management

## Create a New Partition

```bash
fdisk /dev/sdX
```

Inside `fdisk`:

* Press `n` → Create new partition
* Press `w` → Save changes

---

## Format a Partition

### Format with ext4 Filesystem

```bash
mkfs.ext4 /dev/sdX1
```

### Format with XFS Filesystem

```bash
mkfs.xfs /dev/sdX1
```

---

# Mounting and Unmounting Filesystems

## Mount a Partition

```bash
mount /dev/sdX1 /mnt
```

This makes the partition accessible through the `/mnt` directory.

---

## Unmount a Partition

```bash
umount /mnt
```

---

## Remount Filesystem as Read-Write

```bash
mount -o remount,rw /mnt
```

---

# Logical Volume Management (LVM)

LVM provides flexible disk management in Linux and is widely used in enterprise environments.

---

## Create Physical Volume

```bash
pvcreate /dev/sdX
```

---

## Create Volume Group

```bash
vgcreate vg_name /dev/sdX
```

---

## Create Logical Volume

```bash
lvcreate -L 10G -n lv_name vg_name
```

---

## Format and Mount Logical Volume

```bash
mkfs.ext4 /dev/vg_name/lv_name
mount /dev/vg_name/lv_name /mnt
```

---

# Swap Space Management

Swap space acts as virtual memory when physical RAM becomes full.

---

## Create Swap Space

```bash
mkswap /dev/sdX
```

---

## Enable Swap

```bash
swapon /dev/sdX
```

---

## Disable Swap

```bash
swapoff /dev/sdX
```

---

# Understanding When to Use `fdisk`, `mount`, or Both

## Step 1 — Check Available Disks

Always begin by checking available block devices:

```bash
lsblk
```

### Example Output

| NAME   | SIZE | TYPE | MOUNTPOINT |
| ------ | ---- | ---- | ---------- |
| sda    | 100G | disk |            |
| ├─sda1 | 96G  | part | /          |
| └─sda2 | 4G   | part | [SWAP]     |
| sdb    | 20G  | disk |            |

* `sda` → Existing disk already in use
* `sdb` → New disk without partitions

---

# When to Use `fdisk`

Use `fdisk` when:

* The disk is new
* No partitions exist
* You need to create partitions like `/dev/sdb1`

Example:

```bash
sudo fdisk /dev/sdb
```

After partition creation, verify using:

```bash
lsblk
```

---

# When to Use `mount`

Use `mount` when:

* The partition already exists
* The filesystem is already formatted
* You only need to access the storage

Example:

```bash
sudo mkdir /mnt/mydisk
sudo mount /dev/sdb1 /mnt/mydisk
```

---

# Full Disk Setup Process

Use the complete process when working with a brand-new disk.

## Step 1 — Check Disks

```bash
lsblk
```

## Step 2 — Create Partition

```bash
sudo fdisk /dev/sdb
```

## Step 3 — Format Partition

```bash
sudo mkfs.ext4 /dev/sdb1
```

## Step 4 — Mount the Partition

```bash
sudo mkdir /data
sudo mount /dev/sdb1 /data
```

Now the disk is ready for use.

---

# Quick Command Reference

| Task                      | Command                            |
| ------------------------- | ---------------------------------- |
| View disks and partitions | `lsblk`                            |
| Create partitions         | `fdisk`                            |
| Format filesystem         | `mkfs.ext4`                        |
| Mount filesystem          | `mount`                            |
| Unmount filesystem        | `umount`                           |
| Check disk usage          | `df -h`                            |
| Check folder size         | `du -sh`                           |
| Configure swap            | `mkswap`, `swapon`                 |
| Manage LVM                | `pvcreate`, `vgcreate`, `lvcreate` |

---

🚀 Disk and storage management is a critical Linux skill for DevOps engineers, system administrators, and cloud professionals. Understanding these commands helps in managing servers, troubleshooting storage issues, and maintaining production systems efficiently.

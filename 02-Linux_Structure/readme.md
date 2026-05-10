
# Linux Folder Structure Explained (DevOps View)

## Introduction

Understanding the Linux directory structure is essential for every DevOps engineer.
Unlike Windows, Linux follows a **single-root hierarchy (`/`)**, where every file and directory is organized under the root directory.

Each folder has a specific purpose, and knowing them helps in system navigation, troubleshooting, and deployment work.

---

# 1. Symbolic Link Directories (Modern Linux Structure)

These directories are often **linked to `/usr`** in modern Linux distributions to simplify structure.

| Directory           | Purpose                                              |
| ------------------- | ---------------------------------------------------- |
| `/bin → /usr/bin`   | Essential user commands like `ls`, `cp`, `mv`        |
| `/sbin → /usr/sbin` | System administration commands (used by admins)      |
| `/lib → /usr/lib`   | Shared libraries required by system and applications |

👉 These are mostly symbolic links and part of unified Linux filesystem design.

---

# 2. Core System Directories

These are critical directories required for system operation.

## `/boot`

* Contains boot-related files like kernel and bootloader
* Not typically used inside containers

---

## `/usr`

* Stores user-installed applications, binaries, and libraries
* One of the largest directories in Linux systems

---

## `/var`

* Contains variable data that changes frequently
* Examples:

  * Logs (`/var/log`)
  * Caches
  * Spool files

---

## `/etc`

* Stores system-wide configuration files
* Example files:

  * Network settings
  * User settings
  * Service configurations

---

# 3. User and Application Directories

## `/home`

* Contains personal directories for users
* Example:

  * `/home/raj`
  * `/home/admin`

---

## `/root`

* Home directory of the root (admin) user

---

## `/opt`

* Used for optional or third-party software installations
* Common in enterprise environments

---

## `/srv`

* Stores service-related data
* Example: web server files, FTP data

---

# 4. Temporary and System Runtime Directories

## `/tmp`

* Stores temporary files
* Automatically cleaned on reboot

---

## `/run`

* Stores runtime information of processes
* Contains data created during system boot

---

## `/proc` (Virtual Filesystem)

* Provides real-time system and process information
* Example:

  * CPU info
  * Memory usage
  * Running processes

---

## `/sys` (Virtual Filesystem)

* Provides kernel and hardware information
* Used for system tuning and device management

---

## `/dev`

* Contains device files
* Examples:

  * `/dev/sda` (disk)
  * `/dev/null` (null device)

---

# 5. Mount Points

## `/mnt`

* Temporary mount location for filesystems

```bash id="mount1"
mount /dev/sdb1 /mnt
```

---

## `/media`

* Used for removable devices like USB drives and CDs

---

## `/data`

* Custom mount point (commonly used in DevOps setups)
* Often mapped to external storage or cloud volumes

---

# Quick Linux Directory Cheat Sheet

| Directory | Purpose             |
| --------- | ------------------- |
| `/`       | Root of filesystem  |
| `/etc`    | Config files        |
| `/var`    | Logs & dynamic data |
| `/usr`    | Applications        |
| `/home`   | User data           |
| `/root`   | Admin user home     |
| `/tmp`    | Temporary files     |
| `/proc`   | Process info        |
| `/dev`    | Device files        |
| `/mnt`    | Temporary mounts    |

---

🚀 For DevOps engineers, understanding Linux folder structure is critical for navigating servers, debugging issues, managing logs, deploying applications, and working with cloud environments efficiently.

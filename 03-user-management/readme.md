# User Management in Linux (DevOps Essentials)

## Introduction

Linux is a **multi-user operating system**, which means multiple users can access and work on the same system at the same time.

For DevOps engineers, user management is critical for:

* Security control
* Access management
* System administration
* Production environment safety

---

## Key System Files for User Management

Linux stores user and group information in important system files:

* **`/etc/passwd`** → User account information
* **`/etc/shadow`** → Encrypted passwords and password policies
* **`/etc/group`** → Group information
* **`/etc/gshadow`** → Secure group credentials

---

# 1. Creating Users in Linux

## `useradd` — Standard User Creation

### Create a basic user

```bash id="useradd1"
useradd username
```

* Creates user without home directory

---

### Create user with home directory

```bash id="useradd2"
useradd -m username
```

---

### Create user with specific shell

```bash id="useradd3"
useradd -s /bin/bash username
```

---

## `adduser` — Interactive User Creation (Debian-based)

```bash id="adduser1"
adduser username
```

* Prompts for password and details
* Easier for beginners

---

# 2. Managing User Passwords

## Set or Change Password

```bash id="passwd1"
passwd username
```

---

## Password Policies

### Set password expiry (e.g., 90 days)

```bash id="chage1"
chage -M 90 username
```

---

### Lock user account

```bash id="lockuser"
passwd -l username
```

---

### Unlock user account

```bash id="unlockuser"
passwd -u username
```

---

# 3. Modifying Users

## Change Username

```bash id="usermod1"
usermod -l new_username old_username
```

---

## Change Home Directory

```bash id="usermod2"
usermod -d /new/home/directory -m username
```

---

## Change Default Shell

```bash id="usermod3"
usermod -s /bin/zsh username
```

---

# 4. Deleting Users

## Remove user only

```bash id="userdel1"
userdel username
```

## Remove user with home directory

```bash id="userdel2"
userdel -r username
```

---

# 5. Group Management

## Create Group

```bash id="groupadd1"
groupadd groupname
```

---

## Add User to Group

```bash id="groupadd2"
usermod -aG groupname username
```

---

## Check User Groups

```bash id="groups1"
groups username
```

---

## Change Primary Group

```bash id="usermod4"
usermod -g new_primary_group username
```

---

# 6. Sudo Access (Privilege Management)

## Add User to Sudo Group

### Debian-based systems

```bash id="sudo1"
usermod -aG sudo username
```

### RHEL-based systems

```bash id="sudo2"
usermod -aG wheel username
```

---

## Grant Specific Sudo Permissions

Edit sudo configuration safely:

```bash id="visudo1"
visudo
```

Add rule:

```bash id="sudoers"
username ALL=(ALL) NOPASSWD: /path/to/command
```

---

# Quick User Management Cheat Sheet

| Task         | Command              |
| ------------ | -------------------- |
| Create user  | `useradd`, `adduser` |
| Set password | `passwd`             |
| Modify user  | `usermod`            |
| Delete user  | `userdel`            |
| Create group | `groupadd`           |
| Add to group | `usermod -aG`        |
| Check groups | `groups`             |
| Sudo access  | `visudo`             |

---

🚀 User management is a core Linux administration skill. In DevOps, it is essential for securing servers, controlling access to applications, and managing production environments safely and efficiently.

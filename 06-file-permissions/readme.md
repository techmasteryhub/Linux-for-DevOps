
# File Permissions in Linux (DevOps Essential Guide)

## Introduction to File Permissions

In Linux, file permissions control **who can access files and what actions they can perform**.
Every file and directory is associated with three types of users:

* **Owner (User)** → The creator or owner of the file
* **Group** → Users belonging to the same group
* **Others** → Everyone else on the system

Permissions define what each category can do:

* **Read (r / 4)** → View file content
* **Write (w / 2)** → Modify file content
* **Execute (x / 1)** → Run the file or script

---

## Checking File Permissions

To view permissions of a file:

```bash id="lsperm"
ls -l filename
```

### Example Output:

```bash
-rwxr--r-- 1 user group 1234 Mar 28 10:00 myfile.sh
```

### Breakdown:

* `rwx` → Owner permissions
* `r--` → Group permissions
* `r--` → Others permissions

---

# Changing Permissions with `chmod`

## Symbolic Method

Used to add, remove, or set permissions using symbols.

```bash id="chmodsym1"
chmod u+x filename   # Add execute permission for owner
chmod g-w filename   # Remove write permission from group
chmod o=r filename   # Give only read permission to others
chmod u=rwx,g=rx,o= filename
```

---

## Numeric (Octal) Method

Each permission has a numeric value:

* Read = 4
* Write = 2
* Execute = 1

### Examples:

```bash id="chmodnum1"
chmod 755 filename
```

* Owner: rwx
* Group: r-x
* Others: r-x

```bash id="chmodnum2"
chmod 644 filename
```

* Owner: rw-
* Group: r--
* Others: r--

```bash id="chmodnum3"
chmod 700 filename
```

* Owner: full access
* Group: no access
* Others: no access

---

# Changing Ownership with `chown`

## Change File Owner

```bash id="chown1"
chown newuser filename
```

## Change Owner and Group

```bash id="chown2"
chown newuser:newgroup filename
```

## Change Only Group

```bash id="chown3"
chown :newgroup filename
```

## Recursive Ownership Change

```bash id="chown4"
chown -R newuser:newgroup directory/
```

---

# Changing Group Ownership with `chgrp`

```bash id="chgrp1"
chgrp newgroup filename
```

### Recursive Change:

```bash id="chgrp2"
chgrp -R newgroup directory/
```

---

# Special Permissions in Linux

## 1. SetUID (s on user execute bit)

Allows a file to run with the **owner’s permissions**.

```bash id="setuid"
chmod u+s filename
```

👉 Common example: `/usr/bin/passwd`

---

## 2. SetGID (s on group execute bit)

### On files:

Runs with group permissions

### On directories:

New files inherit the group

```bash id="setgid"
chmod g+s filename
chmod g+s directory/
```

---

## 3. Sticky Bit (t on others execute bit)

Used mainly on shared directories.

Only file owner can delete their files.

```bash id="stickybit"
chmod +t directory/
```

👉 Common example: `/tmp`

---

# Default Permissions using `umask`

## Check current umask

```bash id="umask1"
umask
```

## Set umask value

```bash id="umask2"
umask 022
```

### Effect:

* Files → 644
* Directories → 755

---

# Quick Reference Table

| Task                | Command     |
| ------------------- | ----------- |
| View permissions    | `ls -l`     |
| Change permissions  | `chmod`     |
| Change owner        | `chown`     |
| Change group        | `chgrp`     |
| Set UID             | `chmod u+s` |
| Set GID             | `chmod g+s` |
| Sticky bit          | `chmod +t`  |
| Default permissions | `umask`     |

---

🚀 File permissions are a core Linux security concept. For DevOps engineers, mastering `chmod`, `chown`, and `umask` is essential for securing servers, managing deployments, and preventing unauthorized access in production systems.

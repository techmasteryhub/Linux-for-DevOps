# File Management in Linux (DevOps Essentials)

## Introduction

File management is one of the most frequently used skill sets in Linux.
For DevOps engineers, these commands are used daily for managing files, directories, logs, configurations, and deployment scripts on servers.

This section covers the most important Linux file and directory operations along with file viewing and editing commands.

---

# 1. File and Directory Management

## Navigation Commands

### `ls` — List Files and Directories

```bash id="lscmd"
ls
```

Displays all files and folders in the current directory.

---

### `cd` — Change Directory

```bash id="cdcmd"
cd /path/to/directory
```

Used to move between directories.

---

### `pwd` — Show Current Path

```bash id="pwdcmd"
pwd
```

Displays the full path of the current working directory.

---

## Directory Operations

### Create Directory

```bash id="mkdircmd"
mkdir new_folder
```

---

### Remove Empty Directory

```bash id="rmdircmd"
rmdir empty_folder
```

---

## File Operations

### Remove File

```bash id="rmfile"
rm file.txt
```

---

### Remove Directory (with content)

```bash id="rmrf"
rm -r folder
```

> ⚠️ Be careful: this permanently deletes everything inside the folder.

---

### Copy Files

```bash id="cpfile"
cp file1.txt file2.txt
```

---

### Copy Directories

```bash id="cpdir"
cp -r dir1 dir2
```

---

### Move or Rename Files

```bash id="mvfile"
mv old_name new_name
```

---

# 2. File Viewing and Reading

## Display File Content

### `cat` — View File Content

```bash id="catcmd"
cat file.txt
```

---

### `tac` — Reverse File Content

```bash id="taccmd"
tac file.txt
```

---

### `less` — Scrollable View

```bash id="lesscmd"
less file.txt
```

* Scroll up/down easily
* Press `q` to quit

---

### `more` — Page-by-Page View

```bash id="morecmd"
more file.txt
```

---

## View Specific Lines

### First Lines

```bash id="headcmd"
head -n 10 file.txt
```

---

### Last Lines

```bash id="tailcmd"
tail -n 10 file.txt
```

---

# 3. File Editing

## Simple File Editors

### `nano` — Beginner-Friendly Editor

```bash id="nanocmd"
nano file.txt
```

---

### `vi` — Powerful Terminal Editor

```bash id="vicmd"
vi file.txt
```

Used widely in DevOps and production environments.

---

## Writing to Files

### Overwrite File Content

```bash id="echo1"
echo "Hello" > file.txt
```

---

### Append to File

```bash id="echo2"
echo "Hello" >> file.txt
```

---

# Quick File Management Cheat Sheet

| Task             | Command               |
| ---------------- | --------------------- |
| List files       | `ls`                  |
| Change directory | `cd`                  |
| Current path     | `pwd`                 |
| Create directory | `mkdir`               |
| Remove file      | `rm`                  |
| Remove folder    | `rm -r`               |
| Copy file        | `cp`                  |
| Move/rename      | `mv`                  |
| View file        | `cat`, `less`, `more` |
| First lines      | `head`                |
| Last lines       | `tail`                |
| Edit file        | `vi`, `nano`          |
| Write to file    | `echo`                |

---

🚀 File management is a core Linux skill for DevOps engineers. These commands are essential for working with servers, handling logs, managing deployments, and troubleshooting production systems efficiently.

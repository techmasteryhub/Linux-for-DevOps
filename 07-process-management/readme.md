# Process Management in Linux (DevOps Focus)

## Introduction to Process Management

In Linux, a **process** is simply a running instance of a program.
Every process is assigned a unique **Process ID (PID)** and is typically created by a parent process.

For DevOps engineers, process management is essential for:

* Troubleshooting application issues
* Managing server load
* Controlling services in production
* Ensuring system stability and performance

---

# 1. Viewing Running Processes

## `ps` — Snapshot of Processes

### Show all processes

```bash id="psaux"
ps aux
```

### Show processes for a specific user

```bash id="psuser"
ps -u username
```

### Find a process by name

```bash id="psname"
ps -C processname
```

---

## `pgrep` — Find PID by Process Name

```bash id="pgrepcmd"
pgrep processname
```

* Returns only the PID(s)
* Useful in scripts and automation

---

## `pidof` — Get Process ID

```bash id="pidofcmd"
pidof processname
```

* Quickly finds PID of a running application

---

# 2. Managing Processes

## Terminating Processes

### Kill using PID

```bash id="killcmd"
kill PID
```

### Kill using process name

```bash id="pkillcmd"
pkill processname
```

### Force kill process

```bash id="kill9cmd"
kill -9 PID
```

### Force kill all instances

```bash id="pkill9cmd"
pkill -9 processname
```

> ⚠️ `kill -9` should be used only when a process does not respond.

---

## Stopping and Resuming Processes

### Stop a process

```bash id="stopcmd"
kill -STOP PID
```

### Resume a process

```bash id="contcmd"
kill -CONT PID
```

---

# 3. Background and Foreground Jobs

## Run a process in background

```bash id="bgcmd"
command &
```

## View background jobs

```bash id="jobscmd"
jobs
```

## Bring job to foreground

```bash id="fgcmd"
fg %jobnumber
```

## Suspend and resume process

* `Ctrl + Z` → Pause process
* `bg %jobnumber` → Resume in background

---

# 4. Process Priority Management

Linux allows you to control how much CPU priority a process gets.

## Run with lower priority

```bash id="nicecmd"
nice -n 10 command
```

## Change priority of running process

```bash id="renicecmd1"
renice -n 10 -p PID
```

## Increase priority (requires root)

```bash id="renicecmd2"
renice -n -5 -p PID
```

---

# 5. Monitoring Processes

## `top` — Real-time Process Monitoring

```bash id="topproc"
top
```

Inside `top`:

* `k` → kill process
* `r` → renice process
* `q` → quit

---

## `htop` — Advanced Process Viewer

```bash id="htopproc"
htop
```

* Interactive UI
* Easier navigation than `top`
* Can manage processes visually

---

# 6. Daemon (Service) Management

Daemon processes run in the background and power most services in Linux.

## List all services

```bash id="systemctl1"
systemctl list-units --type=service
```

## Start a service

```bash id="systemctl2"
systemctl start service-name
```

## Stop a service

```bash id="systemctl3"
systemctl stop service-name
```

## Enable service at boot

```bash id="systemctl4"
systemctl enable service-name
```

---

# Quick Process Management Cheat Sheet

| Task             | Command                 |
| ---------------- | ----------------------- |
| View processes   | `ps aux`, `top`, `htop` |
| Find PID         | `pgrep`, `pidof`        |
| Kill process     | `kill`, `pkill`         |
| Force kill       | `kill -9`               |
| Stop/Resume      | `STOP`, `CONT`          |
| Background jobs  | `&`, `jobs`, `fg`, `bg` |
| Priority control | `nice`, `renice`        |
| Service control  | `systemctl`             |

---

🚀 Mastering process management is critical for DevOps engineers because it directly impacts application performance, system stability, and production troubleshooting.


# Linux System Monitoring for DevOps Engineers

## Introduction to System Monitoring

System monitoring is a key responsibility in Linux administration and DevOps.
It helps you track system health, identify performance issues, and troubleshoot failures in real time.

With the right tools, you can monitor:

* CPU usage
* Memory consumption
* Disk utilization
* Network activity
* Running processes and system logs

---

# Categories of Monitoring Commands

## 1. CPU and Memory Monitoring

These commands help you understand how system resources are being used.

### `top` — Real-time System View

```bash id="topcmd"
top
```

* Shows running processes
* CPU and memory usage
* System load in real time
  Press `q` to exit.

---

### `htop` — Interactive Process Viewer

```bash id="htopcmd"
htop
```

* User-friendly version of `top`
* Easy navigation using arrow keys
* Can kill processes using function keys

---

### `vmstat` — System Performance Statistics

```bash id="vmstatcmd"
vmstat 1 5
```

* Updates every 1 second
* Shows CPU, memory, and I/O stats

---

### `free` — Memory Usage

```bash id="freecmd"
free -m
```

* Displays total, used, and free memory in MB

---

## 2. Disk Monitoring

### `df` — Disk Space Usage

```bash id="dfcmd"
df -h
```

* Shows available and used disk space in human-readable format

---

### `du` — Directory Size

```bash id="ducmd"
du -sh /var/log
```

* Shows total size of a specific directory

---

### `iostat` — Disk and CPU Performance

```bash id="iostatcmd"
iostat
```

* Displays CPU usage and disk I/O performance

---

## 3. Network Monitoring

### `ip` — Network Interface Details

```bash id="ipcmd"
ip a
```

* Shows IP addresses and network interfaces

---

### `netstat` — Open Ports and Connections

```bash id="netstatcmd"
netstat -tulnp
```

* Displays listening ports and active connections

> Modern alternative: `ss`

```bash id="sscmd"
ss -tulnp
```

---

### `ping` — Connectivity Test

```bash id="pingcmd"
ping google.com
```

* Checks whether a server or website is reachable

---

### `traceroute` — Network Path Tracking

```bash id="tracecmd"
traceroute google.com
```

* Shows the route packets take to reach a destination

---

### `nslookup` — DNS Lookup

```bash id="nslookupcmd"
nslookup example.com
```

* Resolves domain names to IP addresses

---

## 4. Log Monitoring

Logs are critical for debugging system and application issues.

---

### Live System Logs

```bash id="syslogcmd"
tail -f /var/log/syslog
```

* Continuously displays system log updates

---

### Systemd Logs

```bash id="journalcmd"
journalctl -f
```

* Used in modern Linux systems with systemd

---

### Kernel Logs

```bash id="dmesgcmd"
dmesg | tail
```

* Shows latest kernel-level messages

---

# Quick Summary Table

| Area         | Command                                                 |
| ------------ | ------------------------------------------------------- |
| CPU & Memory | `top`, `htop`, `vmstat`, `free`                         |
| Disk         | `df`, `du`, `iostat`                                    |
| Network      | `ip`, `netstat`, `ss`, `ping`, `traceroute`, `nslookup` |
| Logs         | `tail -f`, `journalctl`, `dmesg`                        |

---

🚀 Mastering these monitoring commands is essential for DevOps engineers to maintain system health, detect issues early, and ensure high availability in production environments.

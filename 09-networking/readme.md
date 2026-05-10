# Important Linux Networking Commands for DevOps Engineers

Networking is one of the most important areas in Linux administration and DevOps.
These commands help in checking connectivity, troubleshooting network issues, verifying IP addresses, and downloading files from remote servers.

---

## 1. `ping` — Test Network Connectivity

The `ping` command is used to check whether a remote server or website is reachable from your system.

```bash id="7nxyfc"
ping google.com
```

### Common Use Cases

* Verify internet connectivity
* Check communication between servers
* Troubleshoot network issues

---

## 2. `ifconfig` — View Network Interface Information

The `ifconfig` command displays network interface details such as IP address and network status.

```bash id="g7x5ji"
ifconfig
```

> Note: `ifconfig` is considered deprecated in modern Linux distributions. The `ip` command is now preferred.

### Common Use Cases

* Check interface configuration
* View assigned IP addresses
* Troubleshoot network interfaces

---

## 3. `ip a` — Display IP Address Information

The `ip` command is the modern replacement for `ifconfig`.

```bash id="k2r9yb"
ip a
```

This command displays:

* IP addresses
* Network interfaces
* Interface status

### Common Use Cases

* Verify server IP address
* Check active network interfaces
* Diagnose network problems

---

## 4. `netstat` — Check Network Connections and Ports

The `netstat` command shows active network connections and listening ports.

```bash id="e7a8tr"
netstat -tulnp
```

### What the Options Mean

* `t` → TCP connections
* `u` → UDP connections
* `l` → Listening ports
* `n` → Show numeric addresses
* `p` → Display process ID and application name

### Common Use Cases

* Check which ports are open
* Verify running services
* Troubleshoot connectivity issues

---

## 5. `curl` — Access Data from URLs

The `curl` command is used to send requests to websites, APIs, and servers.

```bash id="u6a3vk"
curl https://example.com
```

### Common Use Cases

* Test APIs
* Verify website responses
* Troubleshoot web applications

`curl` is widely used in DevOps automation and scripting.

---

## 6. `wget` — Download Files from the Internet

The `wget` command downloads files directly from remote servers.

```bash id="m4k1tc"
wget https://example.com/file.zip
```

### Common Use Cases

* Download software packages
* Fetch scripts and configuration files
* Automate file downloads

---

# Quick Command Summary

| Command          | Purpose                            |
| ---------------- | ---------------------------------- |
| `ping`           | Check network connectivity         |
| `ifconfig`       | Display network interface details  |
| `ip a`           | Show IP address information        |
| `netstat -tulnp` | View open ports and connections    |
| `curl`           | Send requests to websites and APIs |
| `wget`           | Download files from remote servers |

---

🚀 These networking commands are essential for Linux administrators, cloud engineers, and DevOps professionals working with servers, containers, and production environments.

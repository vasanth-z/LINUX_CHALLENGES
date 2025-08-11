# 🎯 Challenge 19: Network Interface Configuration & Information

## Objective
Learn to use modern networking commands (`ip`) to inspect and understand your system's network configuration. This is a fundamental skill for troubleshooting connectivity issues and verifying network settings.

---

## Steps

### 1️⃣ Identify Your Network Interfaces
Use the `ip addr` command to list all network interfaces on your system. Interfaces are typically named:
- `eth0` (Ethernet)
- `wlan0` (Wi-Fi)
- Or a longer name like `enp0s3`

Look for the interface that has an assigned IP address to find your active connection.

**Command:**
```bash
ip addr
```

### 2️⃣ Display Detailed Interface Information
Once you've identified your primary network interface (e.g., enp0s3), use ip again to get detailed information about just that interface.

Command (replace enp0s3 with your actual interface name):

```bash
ip addr show enp0s3
```

### 3️⃣ Display the Routing Table
Use the ip route command to show your system's routing table.
This table tells the kernel where to send network traffic for different destinations.
The default route shows which gateway is used for all traffic.

Command:

```bash
ip route
```





## Commands and Purpose

| Command | Purpose |
|---------|---------|
| `ip addr` | Displays all network interfaces and their IP addresses. |
| `ip link` | Shows detailed link-layer (interface) information. |
| `ifconfig` | Displays and configures network interface parameters (older command, replaced by `ip`). |
| `ip route` | Shows or manipulates the IP routing table. |

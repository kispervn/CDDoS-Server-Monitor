# CDDoS Server Monitor | Real-Time Linux Server Monitoring Dashboard

Monitor server resources, network traffic, and connections in real time. A lightweight CLI server monitor for Linux (Ubuntu 24.04, Debian, RHEL) with no dependencies on external config files.

![CDDoS Server Monitor - Real-time Linux server stats dashboard showing CPU, RAM, network, connections](https://sv2.anhsieuviet.com/2026/03/08/image4494f193c652954a.png)

---

## Server Monitor Overview

CDDoS Server Monitor displays live server statistics: CPU load, RAM usage, disk I/O, network bandwidth, and HTTP(S) connections for ports 80 and 443. It helps sysadmins monitor server health and spot traffic spikes quickly.

---

## Features

- **System Resources** — Load average (1m, 5m, 15m), CPU %, RAM MB and %, Disk I/O (read/write MB/s)
- **Network Monitoring** — Total bandwidth and In/Out (kB/s)
- **Connection Stats** — Port 80/443 queries, unique IPs, ESTABLISHED connections
- **Top IPs** — Clients ranked by connection count (optional DNS lookup)
- **Standalone** — No config files; uses system hostname
- **Colored Output** — Simple terminal styling for readability

---

## Requirements

- Bash
- `ss` or `netstat` (iproute2 / net-tools)
- `sar` (sysstat)
- `free`

Dependencies are auto-installed via apt or yum.

---

## Usage

```bash
./cddos
```

---

## Options

| Variable | Default | Description |
|----------|---------|-------------|
| `SKIP_DNS` | 1 | Set `0` to enable hostname lookup for top IPs |
| `MAX_IPS_FOR_DNS` | 100 | Max IPs to resolve when DNS is enabled |
| `GETENT_TIMEOUT` | 1 | Timeout (seconds) per DNS lookup |

Example:

```bash
SKIP_DNS=0 ./cddos
```

---

## Metrics Explained

| Metric | Description |
|--------|-------------|
| Load Avg | 1, 5, 15 min load average |
| CPU | Usage percentage |
| RAM | Used MB and usage % |
| Disk I/O | Read/write throughput (MB/s) |
| Bandwidth | Total and In/Out (kB/s) |
| Queries | All connections to port 80/443 |
| ESTAB | ESTABLISHED connections |
| Unique IPs | Distinct IPs to port 80 and 443 combined |

---

## License

MIT

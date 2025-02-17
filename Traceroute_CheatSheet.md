
# 🌐 Traceroute Command Cheat Sheet

`traceroute` (on Linux/MacOS) or `tracert` (on Windows) is a network diagnostic tool used to trace the path packets take from the source to the destination. It helps in identifying network bottlenecks and routing issues.

---

## 📘 Basic Commands

| Command | Description | Example |
|---------|-------------|---------|
| `traceroute example.com` | Displays the route packets take to reach a domain. | `traceroute google.com` |
| `traceroute 8.8.8.8` | Traces the route to an IP address. | `traceroute 1.1.1.1` |
| `tracert example.com` | Windows version of traceroute. | `tracert google.com` |
| `tracert 8.8.8.8` | Traces the route to an IP address in Windows. | `tracert 8.8.8.8` |

---

## 🔄 Protocol and Port Options

| Command | Description | Example |
|---------|-------------|---------|
| `traceroute -I example.com` | Uses ICMP echo instead of UDP packets. | `traceroute -I example.com` |
| `traceroute -T example.com` | Uses TCP SYN packets. | `traceroute -T google.com` |
| `traceroute -U -p 53 example.com` | Uses UDP packets to a specific port (e.g., DNS). | `traceroute -U -p 53 example.com` |
| `traceroute -P tcp example.com` | Specifies the protocol to use (ICMP, TCP, or UDP). | `traceroute -P tcp example.com` |

---

## ⏱ Timing and Hops Control

| Command | Description | Example |
|---------|-------------|---------|
| `traceroute -m 15 example.com` | Sets the maximum number of hops (TTL). | `traceroute -m 15 google.com` |
| `traceroute -w 3 example.com` | Sets the wait time for a response. | `traceroute -w 3 example.com` |
| `traceroute -q 4 example.com` | Specifies the number of queries per hop. | `traceroute -q 4 google.com` |

---

## 📜 Display and Output Options

| Command | Description | Example |
|---------|-------------|---------|
| `traceroute -n example.com` | Displays IP addresses without resolving hostnames. | `traceroute -n google.com` |
| `traceroute -v example.com` | Enables verbose output for more details. | `traceroute -v example.com` |
| `traceroute -A example.com` | Displays AS (Autonomous System) numbers. | `traceroute -A google.com` |
| `traceroute -g 192.168.1.1 example.com` | Specifies a loose source route gateway. | `traceroute -g 192.168.1.1 google.com` |

---

## 🔧 Miscellaneous Commands

| Command | Description | Example |
|---------|-------------|---------|
| `traceroute -s 192.168.1.100 example.com` | Sets the source IP address for outgoing packets. | `traceroute -s 192.168.1.100 google.com` |
| `traceroute -z 0.5 example.com` | Sets the pause between probes in seconds. | `traceroute -z 0.5 google.com` |
| `traceroute -F example.com` | Sets the "Don't Fragment" bit. | `traceroute -F example.com` |
| `traceroute -l 1200 example.com` | Sets the packet length in bytes. | `traceroute -l 1200 google.com` |

---

## ⚙️ Platform-Specific Commands

| Platform | Command | Example |
|----------|---------|---------|
| **Windows** | `tracert -d example.com` | Skips DNS name resolution. |
| **Windows** | `tracert -h 20 example.com` | Sets the maximum hops. |
| **Windows** | `tracert -w 3000 example.com` | Sets the wait time (in ms). |
| **Linux/MacOS** | `traceroute -I example.com` | Uses ICMP echo requests. |
| **Linux/MacOS** | `traceroute -T example.com` | Uses TCP SYN packets. |

---

## 📜 Notes

- `traceroute` uses UDP packets by default on Linux/MacOS, while `tracert` on Windows uses ICMP Echo Requests.
- Some firewalls block traceroute probes, resulting in timeout (`*`) entries.
- `sudo` may be required for some options, like using ICMP or TCP packets.

---

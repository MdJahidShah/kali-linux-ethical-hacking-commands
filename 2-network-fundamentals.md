# 2. Network Fundamentals

> Understanding traffic is non-negotiable

| Command          | Description           | How it works                  |
| ---------------- | --------------------- | ----------------------------- |
| `ip a`           | Show interfaces       | Queries kernel network stack  |
| `ip r`           | Routing table         | Displays packet routing paths |
| `ifconfig`       | Legacy interface tool | Manages NIC configuration     |
| `arp -a`         | ARP table             | Maps IP → MAC                 |
| `netstat -tulnp` | Open ports            | Reads kernel socket table     |
| `ss`             | Socket stats          | Faster netstat replacement    |
| `ping`           | Host reachability     | ICMP echo requests            |
| `traceroute`     | Path discovery        | TTL-based hop mapping         |

---

[Return Home](https://mdjahidshah.github.io/kali-linux-ethical-hacking-commands/)

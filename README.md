# 👋 Hey, I'm Gaya

🔐 **407 Proxy Authentication Required.**

---

```python
import socket

def port_scan(target, ports):
    print(f"Scanning {target}...")
    for port in ports:
        try:
            with socket.create_connection((target, port), timeout=0.5) as s:
                print(f"[+] Port {port} is OPEN")
        except (socket.timeout, socket.error, ConnectionRefusedError):
            continue
        except KeyboardInterrupt:
            print("\nScan stopped.")
            break

if __name__ == "__main__":
    target_ip = "192.168.1.1"
    common_ports = [21, 22, 80, 443, 8080]
    port_scan(target_ip, common_ports)
```

---

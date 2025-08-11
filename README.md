# 👋 Hey, I'm Gaya

🔐 **407 Proxy Authentication Required.**

---

```python
import socket

def port_scan(target, ports):
    print(f"Scanning {target}...")
    for port in ports:
        try:
            s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
            s.settimeout(0.5)
            result = s.connect_ex((target, port))
            if result == 0:
                print(f"[+] Port {port} is OPEN")
            s.close()
        except KeyboardInterrupt:
            print("\nScan stopped.")
            break
        except socket.error:
            print("Host unreachable.")
            break

if __name__ == "__main__":
    target_ip = "192.168.1.1"
    common_ports = [21, 22, 80, 443, 8080]
    port_scan(target_ip, common_ports)
```

---

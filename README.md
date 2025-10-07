# 👋 Hey, I'm Gaya

🔐 **407 Proxy Authentication Required.**

---

```lua
local socket = require("socket")

local function port_scan(target, ports)
    print(string.format("Scanning %s...", target))
    
    for _, port in ipairs(ports) do
        local sock = socket.tcp()
        sock:settimeout(0.5)
        
        local success, err = sock:connect(target, port)

        if success then
            print(string.format("[+] Port %d is OPEN", port))
            sock:close()
        else
            sock:close()
        end
    end
end

io.write("Enter IP to scan: ")
local target_ip = io.read()

local common_ports = {21, 22, 80, 443, 8080}
port_scan(target_ip, common_ports)
```

---

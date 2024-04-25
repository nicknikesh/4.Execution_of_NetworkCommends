# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## CODE

CLIENT :
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

SERVER :
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```

TRACER :
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans) 
```

## Output

TRACER :

![Screenshot 2024-04-24 053041](https://github.com/nicknikesh/4.Execution_of_NetworkCommends/assets/145633284/3ff2f390-3430-4ffe-908a-69496887e9c4)

CLIENT :

![Screenshot 2024-04-24 052846](https://github.com/nicknikesh/4.Execution_of_NetworkCommends/assets/145633284/4bc0f1d5-f9a2-4bf8-862d-2bfd7a02a98b)

SERVER :

![Screenshot 2024-04-24 052835](https://github.com/nicknikesh/4.Execution_of_NetworkCommends/assets/145633284/bb14dcd4-201e-493e-915a-fa8cd1045dfd)

## Result
Thus Execution of Network commands Performed 

# 4.Execution_of_NetworkCommands

# Name : Gayathri A
# RegNo : 212221230028
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

# Code :

# Client :
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
# Server :

```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```

# Tracer :
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans) 
```
## Output :

# Tracer :

![image](https://github.com/Gayathriraj18/4.Execution_of_NetworkCommends/assets/94154854/aea68ece-fc1d-4f30-b3ab-fd584b229da6)

# Client :

![image](https://github.com/Gayathriraj18/4.Execution_of_NetworkCommends/assets/94154854/6bd0ef3e-26a0-43e7-9c05-459786973e73)

# Server :

![image](https://github.com/Gayathriraj18/4.Execution_of_NetworkCommends/assets/94154854/fbb7e63f-9ed0-4425-b993-2ccfd562da03)


## Result
Thus Execution of Network commands Performed .

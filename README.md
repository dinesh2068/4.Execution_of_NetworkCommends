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

## PROGRAM:
## PING COMMAND:
## CLIENT.PY:
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
## SERVER.PY:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter the website you want to ping ")
 s.send(ip.encode())
 print(s.recv(1024).decode())
```

## OUPUT:
## PING COMMAND:
## CLIENT.PY:

![image](https://github.com/dinesh2068/4.Execution_of_NetworkCommends/assets/151390189/41eb4864-16eb-4aea-bba2-04e4d6a56c89)

## SERVER.PY:

![image](https://github.com/dinesh2068/4.Execution_of_NetworkCommends/assets/151390189/7a11ad22-7731-4413-a825-20c902cbe523)

## TRACEROUTE COMMMAND:

![Screenshot 2024-04-08 103927](https://github.com/dinesh2068/4.Execution_of_NetworkCommends/assets/151390189/927d7050-6bc8-4304-89aa-c2c7b208e3cb)

## Result
Thus Execution of Network commands Performed 

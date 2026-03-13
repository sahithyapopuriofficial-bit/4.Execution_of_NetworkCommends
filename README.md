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

## PROGRAM
```
Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")
```
## Output
<img width="487" height="164" alt="image" src="https://github.com/user-attachments/assets/ee5b7844-894d-40cc-8c68-656a21e62112" />

<img width="544" height="329" alt="image" src="https://github.com/user-attachments/assets/b8d3164c-e63c-4c30-a274-35f461f6a032" />

<img width="748" height="886" alt="image" src="https://github.com/user-attachments/assets/74918df7-6324-4610-bfbd-35a00d78f697" />

## Result
Thus Execution of Network commands Performed 

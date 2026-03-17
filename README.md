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
### 1)ping

<img width="844" height="353" alt="Screenshot 2026-03-14 134215" src="https://github.com/user-attachments/assets/2cc399a9-8b97-488b-a03f-810ff8cd3863" />

 ### 2)Tracert

 <img width="1046" height="561" alt="Screenshot 2026-03-14 135947" src="https://github.com/user-attachments/assets/bf12371a-cf99-4673-929f-6bd5a2bd06fe" />

### 3)ipconfig

<img width="984" height="719" alt="Screenshot 2026-03-14 140004" src="https://github.com/user-attachments/assets/85b71583-4ab4-4221-9e38-a0e6a1f66ec3" />

### 4)netstat

<img width="886" height="909" alt="Screenshot 2026-03-14 140019" src="https://github.com/user-attachments/assets/402366da-0c89-416c-8b36-6102a1863cfc" />

### 5)nslookup

<img width="799" height="555" alt="Screenshot 2026-03-14 140044" src="https://github.com/user-attachments/assets/95417380-db21-426c-98c6-53fb9c851c67" />

### 6)getmac

<img width="956" height="171" alt="Screenshot 2026-03-14 140056" src="https://github.com/user-attachments/assets/b22592d1-6ff3-46b7-a213-391bf5e02cf2" />

### 7)nbtstat

<img width="1105" height="600" alt="Screenshot 2026-03-14 140109" src="https://github.com/user-attachments/assets/a77173f7-fd86-4512-aa7e-87966d334bfe" />

### 8)arp

<img width="958" height="789" alt="Screenshot 2026-03-14 140126" src="https://github.com/user-attachments/assets/3d20f668-27bb-4216-bcce-ed2e56350c4a" />

### 9)systeminfo

<img width="705" height="964" alt="Screenshot 2026-03-14 140223" src="https://github.com/user-attachments/assets/0b844e7a-e58b-4e0f-9826-c1f08aa16f23" />

## Result
Thus Execution of Network commands Performed 

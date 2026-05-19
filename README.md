# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM:
## Server.py:
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for connection...")
c, addr = s.accept()
print("Connected to", addr)
while True:
    ClientMessage = c.recv(1024).decode()
    if not ClientMessage:
        break
    print("Client >", ClientMessage)
    msg = input("Server > ")
    c.send(msg.encode())
c.close()
s.close()
```

## Client.py:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    if msg == "exit":
        break
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
s.close()
```

## OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2026-05-19 081716" src="https://github.com/user-attachments/assets/1ef52f50-7368-4e44-8363-3c871a96a87a" />








## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.

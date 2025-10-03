# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## server.py
```
import socket

s = socket.socket()
s.bind(('127.0.0.1', 5001))
s.listen(1)
print("Server started... Waiting for connection")

conn, addr = s.accept()
print("Connected with", addr)

while True:
    data = conn.recv(1024)
    if not data:
        break
    conn.sendall(data)   # Echo back
conn.close()
```
## client.py
```
import socket

s = socket.socket()
s.connect(('127.0.0.1', 5001))

while True:
    msg = input("Enter message (or 'exit'): ")
    if msg.lower() == "exit":
        break
    s.sendall(msg.encode())
    data = s.recv(1024)
    print("Echo from server:", data.decode())

s.close()
```
## OUPUT
<img width="725" height="177" alt="image" src="https://github.com/user-attachments/assets/8e87fc5f-369c-4b34-aade-8ddeaabe408b" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

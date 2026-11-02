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
Server.py
~~~
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = '127.0.0.1'  
port = 12345

server_socket.bind((host, port))

server_socket.listen(1)
print("Server is waiting for connection...")

conn, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    data = conn.recv(1024).decode()
    
    if not data:
        break

    print("Received from client:", data)

    conn.send(data.encode())
conn.close()
server_socket.close()
~~~
client.py
~~~
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = '127.0.0.1'  
port = 12345

server_socket.bind((host, port))

server_socket.listen(1)
print("Server is waiting for connection...")

conn, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    data = conn.recv(1024).decode()
    
    if not data:
        break

    print("Received from client:", data)

    conn.send(data.encode())
conn.close()
server_socket.close()
~~~
## OUPUT


<img width="1305" height="417" alt="image" src="https://github.com/user-attachments/assets/ba723c66-5810-4ed3-b482-8e6ed1387a61" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

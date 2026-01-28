# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
# SERVER :

```python
import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client_socket.connect(("127.0.0.1", 8080))

message = input("Enter message: ")
client_socket.sendall(message.encode())

data = client_socket.recv(1024)
print("Echo from server:", data.decode())

client_socket.close()
```

# CLIENT :

```python
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_socket.bind(("127.0.0.1", 8080))
server_socket.listen(1)

print("Server listening on port 8080...")

conn, addr = server_socket.accept()
print("Connected by", addr)

while True:
    data = conn.recv(1024)
    if not data:
        break
    conn.sendall(data)

conn.close()
server_socket.close()
```

## OUTPUT:

<img width="1762" height="350" alt="image" src="https://github.com/user-attachments/assets/00c1e87e-e8f8-48a1-a64c-b1896a7c5cbc" />


## RESULT:
The program is executed successfully

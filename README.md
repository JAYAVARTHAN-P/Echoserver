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
## Echo Server.py
```
import socket

HOST = '127.0.0.1'  # Standard loopback interface address (localhost)
PORT = 65432        # Port to listen on (non-privileged ports are > 1023)

def echo_server():
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.bind((HOST, PORT))
        s.listen()
        print(f"Echo server listening on {HOST}:{PORT}")
        conn, addr = s.accept()
        with conn:
            print(f"Connected to {addr}")
            while True:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)

if __name__ == "__main__":
    echo_server()

```
## Echo Client.py
```
import socket

HOST = '127.0.0.1'  # The server's hostname or IP address
PORT = 65432        # The port used by the server

def echo_client(message):
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.connect((HOST, PORT))
        s.sendall(message.encode())
        data = s.recv(1024)
        print(f"Received from server: {data.decode()}")

if __name__ == "__main__":
    message = input("Enter message to send to server: ")
    echo_client(message)

```
## OUTPUT:
## Server
![Screenshot_2024-03-01_08_33_43](https://github.com/JAYAVARTHAN-P/Echoserver/assets/121369281/e7582f47-021f-4504-b3ca-1860ad7091e1)

## Client 

![Screenshot_2024-03-01_08_33_57](https://github.com/JAYAVARTHAN-P/Echoserver/assets/121369281/c9bdca74-bcf7-404e-9e89-e5922b27b522)



## RESULT:
The program is executed successfully

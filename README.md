# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
SERVER:
```
import socket


s = socket.socket()


s.bind(('localhost', 8000))


s.listen(5)

print("Server waiting for connection...")

c, addr = s.accept()

print("Connected to:", addr)

while True:

    data = input("Enter a data: ")

  
    c.send(data.encode())

    ack = c.recv(1024).decode()

    if ack:
        print(ack)
    else:
        c.close()
        break
```
CLIENT:
```
import socket


s = socket.socket()


s.connect(('localhost', 8000))

while True:
    
    print(s.recv(1024).decode())

    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="1913" height="402" alt="Screenshot 2026-05-13 151112" src="https://github.com/user-attachments/assets/42a9c279-4b6e-4567-b9fa-6f25937dd9bb" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

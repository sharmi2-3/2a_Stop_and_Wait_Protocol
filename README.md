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
client 
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addrs=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
server
```
 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
client 
![Screenshot 2025-05-08 143847](https://github.com/user-attachments/assets/9c28818c-a5b9-4b9d-b3aa-fae18ea9637c)

server
![Screenshot 2025-05-08 143858](https://github.com/user-attachments/assets/0a5f7c6e-7948-451c-9b9a-876a2eecc880)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

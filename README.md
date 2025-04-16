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
![Screenshot 2025-04-16 200729](https://github.com/user-attachments/assets/87fe372f-c1e2-4e27-ad7b-d2d3116862ee)
server
![Screenshot 2025-04-16 200801](https://github.com/user-attachments/assets/61f5ca72-d25e-428f-b8ec-985d80bb8639)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

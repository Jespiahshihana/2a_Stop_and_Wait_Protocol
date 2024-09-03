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
## CLIENT CODE
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
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
## SERVER CODE
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT OUTPUT
![Exp 2 a client](https://github.com/user-attachments/assets/addf8f8e-f6e0-45ee-bc37-f834a0684204)
## SERVER OUTPUT
![Exp 2 a server](https://github.com/user-attachments/assets/c400d77e-188a-44e1-bdd5-63f6d38e09c4)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

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
### Client :
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### Client:
![image](https://github.com/Gokkul-M/2a_Stop_and_Wait_Protocol/assets/144870543/e01ebcd4-38a0-4eff-94c0-b7039fc4e509)
### Server:
![image](https://github.com/Gokkul-M/2a_Stop_and_Wait_Protocol/assets/144870543/ed91706c-9319-4546-a4b5-b7a6a6493571)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

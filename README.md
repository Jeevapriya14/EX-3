# EX-3 STUDY OF SOCKET PROGRAMMING AND CLIENT - SERVER MODEL

DATE : 23-03-2023

AIM :

  To write a python program to perform sliding window protocol


ALGORITHM :

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program

PROGRAM :

CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
   ip=c.recv(1024).decode()
   try:
    c.send(address[ip].encode())
   except KeyError:
    c.send("Not Found".encode())
```
 
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```

CLIENT OUTPUT :

![EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL](https://github.com/Jeevapriya14/EX-3/assets/121003043/745438ee-6d15-4afc-b58f-e0c6db91b171)

SERVER OUTPUT:
![EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL](https://github.com/Jeevapriya14/EX-3/assets/121003043/6931c249-3c4a-4d4d-97d9-4200f03ea470)


RESULT:

  Thus, python program to perform stop and wait protocol was successfully executed.
  
